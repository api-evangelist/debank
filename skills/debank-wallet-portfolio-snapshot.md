---
name: DeBank wallet portfolio snapshot
description: Take a complete cross-chain portfolio reading for one wallet address — total net worth, per-chain balances, token holdings and DeFi protocol positions — using the DeBank Cloud Pro API.
api: openapi/debank-pro-openapi.yml
operations:
  - get_user_total_balance
  - get_user_chain_list
  - get_user_token_all_list
  - get_user_all_simple_protocol_list
  - get_user_all_complex_protocol_list
  - get_user_chain_balance
---

# DeBank wallet portfolio snapshot

Read a wallet's whole on-chain position across every chain DeBank supports.

## Before you start

- Base URL is `https://pro-openapi.debank.com`. The published contract is Swagger 2.0
  (`openapi/debank-pro-openapi.yml`) and carries no `host`/`schemes` block, so set the host yourself.
- Every call needs the header `AccessKey: <your key>`, issued from the DeBank Cloud dashboard.
  There is no OAuth on this API — see `authentication/debank-authentication.yml`.
- Every call spends prepaid **units**. The docs do not publish a per-endpoint unit cost, so measure
  before you loop: read `get_unit_api_list` (`GET /v1/account/units`) at the start and end of a run.
- `id` is the wallet address on every user operation. `chain_id` is a DeBank chain slug
  (`eth`, `bsc`, `matic`, `arb`), not an EVM numeric chain id. Resolve the current set with
  `get_chain_list` — the supported chain range changed on 2025-01-13.

## Steps

1. **Total net worth.** `get_user_total_balance` with `id=<address>`. Returns `total_usd_value`
   plus a per-chain breakdown, including tokens and all protocol positions. If this is all you
   need, stop here — it is one call instead of many.
2. **Narrow to the chains actually used.** `get_user_chain_list` (`GET /v1/user/used_chain_list`)
   returns only the chains where the wallet has ever transacted. Iterate this list, never the full
   chain list, or you will burn units on empty chains.
3. **Token holdings.** `get_user_token_all_list` for all chains at once, or `get_user_token_list`
   per chain. Pass `is_all=false` to exclude protocol-derived tokens and avoid double counting
   against step 4 — the default is `true`.
4. **DeFi positions.** `get_user_all_simple_protocol_list` for a cheap roll-up of protocol asset
   values. Only call `get_user_all_complex_protocol_list` when you need the position detail
   (`PortfolioItem`: supply/borrow/reward legs, `position_index`); it is a much larger payload.
5. **Per-chain drill-down.** `get_user_chain_balance` with `id` and `chain_id` for the net assets
   on a single chain.

## Rules

- **Do not retry writes blindly.** There is no idempotency key on this API
  (`conventions/debank-conventions.yml`); reads are safe to retry, and this skill is read-only.
- **Back off without a signal.** No `RateLimit-*` or `Retry-After` headers are returned. The Pro
  plan ceiling is 100 requests/second. On `429` back off exponentially; on `403` you are out of
  units, not out of rate — stop and top up rather than retrying.
- **Errors are status codes only.** `400` invalid params, `401` missing/invalid AccessKey,
  `403` capacity limit, `429` rate limit, `500` server. There is no JSON error body on these
  endpoints. See `errors/debank-problem-types.yml`.
- Values are USD-denominated and reflect DeBank's own pricing; treat them as indicative.
