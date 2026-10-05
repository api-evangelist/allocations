---
name: allocations-manage-entity
description: Create a new entity, retrieve it, update its details, and fetch its tax information.
api: openapi/allocations-openapi.json
operations:
- createEntity
- getEntityById
- updateEntity
- getEntityTaxesByEntityId
generated: '2026-10-05'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/allocations-openapi.json ; every operationId checked against the contract
---

# allocations-manage-entity

Create a new entity, retrieve it, update its details, and fetch its tax information.

## Steps

1. 1. `createEntity` – send a POST request to `/v2/entities` with the required JSON body fields for the new entity.
2. 2. `getEntityById` – send a GET request to `/v2/entities/{id}` using the `id` returned from `createEntity`.
3. 3. `updateEntity` – send a PATCH request to `/v2/entities/{id}` with the fields you wish to modify in the JSON body.
4. 4. `getEntityTaxesByEntityId` – send a GET request to `/v2/entities/{id}/taxes` to retrieve tax details for the entity.

## Rules

- Include an `Authorization: Bearer <jwt>` header for all requests (jwt auth scheme).
- POST `createEntity` is not idempotent; avoid retrying without a unique request identifier.
- All endpoints return standard HTTP error codes; handle 4xx for client errors and 5xx for server errors.
