---
name: allocations-bank-account-setup
description: Create a new bank account application and synchronize its status.
api: openapi/allocations-openapi.json
operations:
- createApplication
- requestBankAccountSync
- getBankAccountById
generated: '2026-10-05'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/allocations-openapi.json ; every operationId checked against the contract
---

# allocations-bank-account-setup

Create a new bank account application and synchronize its status.

## Steps

1. 1. Call `createApplication` with the required request body fields as defined in the contract.
2. 2. Call `requestBankAccountSync` with the `{id}` path parameter returned from the creation step.
3. 3. Call `getBankAccountById` with the same `{id}` to retrieve the updated account details.

## Rules

- Auth: Include a JWT token in the `Authorization` header as `Bearer <token>`.
- Idempotency: The `createApplication` endpoint supports an `Idempotency-Key` header to avoid duplicate applications.
