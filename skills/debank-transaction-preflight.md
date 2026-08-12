---
name: DeBank transaction preflight
description: Simulate and explain an unsigned EVM transaction before a user signs it, and price the gas, using the DeBank Cloud Pro API wallet endpoints.
api: openapi/debank-pro-openapi.yml
operations:
  - get_gas_market
  - post_pre_exec_tx
  - post_explain_tx
---

# DeBank transaction preflight

Show a user what a transaction will actually do before they sign it.

## Before you start

- `AccessKey` header; base `https://pro-openapi.debank.com`. These are the only two `POST`
  operations in the contract besides Official Account messaging, and they take a JSON body
  (`application/json`).
- These endpoints **simulate**. They do not broadcast, and they do not sign. Nothing here moves funds.

## Steps

1. `get_gas_market` (`GET /v1/wallet/gas_market`) with `chain_id` to get the current gas price
   levels (`gasprice` definition) so you can attach a realistic price to the unsigned tx.
2. `post_pre_exec_tx` (`POST /v1/wallet/pre_exec_tx`) with the unsigned transaction. Returns the
   predicted balance changes — `sends`, `receives`, `token_approve` — so you can tell the user what
   leaves the wallet and what arrives.
3. `post_explain_tx` (`POST /v1/wallet/explain_tx`) for the human-readable action description of
   the same transaction (`ActionObject`), which is what you show the user.
4. Present the two together: the explanation as the headline, the simulated balance deltas as the
   evidence. Flag any `token_approve` in the result explicitly — an approval is the step users
   most often miss.

## Rules

- **These two endpoints have their own error envelope.** Unlike the rest of the API they return
  `{"code": <int>, "message": <string>}`. Handle `1000` unknown node error, `1002` contract
  execution error, `2000` unknown api error, `2001` balance is insufficient, `2002` node service
  unavailable. See `errors/debank-problem-types.yml`.
- A `1002` contract execution error means the transaction would revert. Tell the user it will fail;
  do not retry it unchanged.
- `2002` is DeBank's upstream node being unavailable, not a problem with the transaction. Retry
  with backoff.
- Never present a simulation as a guarantee. State it is a preflight against current chain state.
