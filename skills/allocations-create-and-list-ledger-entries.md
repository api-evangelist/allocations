---
name: allocations-create-and-list-ledger-entries
description: Create a new ledger entry and then list all entries for that ledger.
api: openapi/allocations-openapi.json
operations:
- createLedgerEntry
- getLedgerEntriesByLedgerId
generated: '2026-10-05'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/allocations-openapi.json ; every operationId checked against the contract
---

# allocations-create-and-list-ledger-entries

Create a new ledger entry and then list all entries for that ledger.

## Steps

1. 1. Call `createLedgerEntry` with the required request body fields for the new entry.
2. 2. Call `getLedgerEntriesByLedgerId` providing the `ledgerId` path parameter and optional pagination query parameters (`page`, `pageSize`).

## Rules

- Auth: Include a JWT token in the `Authorization` header as `Bearer <token>`.
- Pagination: `getLedgerEntriesByLedgerId` supports `page` and `pageSize` query parameters for paginated results.
