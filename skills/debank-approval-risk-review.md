---
name: DeBank token and NFT approval risk review
description: Enumerate a wallet's outstanding ERC-20 and NFT approvals and rank the spenders by exposure, using the DeBank Cloud Pro API authorization endpoints.
api: openapi/debank-pro-openapi.yml
operations:
  - get_user_chain_list
  - get_user_token_authorized_list
  - get_user_nft_authorized_list
  - get_get_contract_view
---

# DeBank token and NFT approval risk review

Find what a wallet has approved, to whom, and how much is at risk.

## Before you start

- `AccessKey` header on every call; base `https://pro-openapi.debank.com`.
- Both authorization endpoints are **per chain** — they take `id` (wallet address) and
  `chain_id` (DeBank chain slug) and have no all-chain variant.

## Steps

1. `get_user_chain_list` with `id=<address>` to get the chains this wallet has used.
2. For each chain, `get_user_token_authorized_list` with `id` and `chain_id`. Each entry carries
   the token and a `spenders` list (`Spenders` definition) with the approved amount and the
   spender's protocol attribution.
3. For each chain, `get_user_nft_authorized_list` with `id` and `chain_id` for collection-level
   and token-level NFT approvals (`UserNFTAuthorized`, `nft_contracts`, `nft_tokens`).
4. Rank by exposure: unlimited approvals first, then approved USD value descending. An approval to
   a spender with no protocol attribution deserves the most scrutiny.
5. Optional: `get_get_contract_view` (`GET /cloud/contract`) to resolve an unattributed spender
   address to contract metadata before you report it.

## Rules

- Report, do not act. This API has no revoke operation — revocation is an on-chain transaction the
  user signs in their own wallet. Never claim to have revoked anything.
- Absence of an approval in the response is not proof of safety; it is proof DeBank indexed none
  on the chains you queried. Say which chains you covered.
- Same rate-limit and unit-exhaustion rules as every other endpoint: `429` is rate, `403` is units.
