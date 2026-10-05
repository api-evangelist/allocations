---
name: allocations-notifications-read
description: Fetch the list of notifications, optionally get the count, and mark specific notifications as read.
api: openapi/allocations-openapi.json
operations:
- getNotifications
- getNotificationsCount
- markNotificationAsRead
generated: '2026-10-05'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/allocations-openapi.json ; every operationId checked against the contract
---

# allocations-notifications-read

Fetch the list of notifications, optionally get the count, and mark specific notifications as read.

## Steps

1. 1. Call `getNotifications` with query parameters `page`, `pageSize` (if pagination is supported) to retrieve the notifications list.
2. 2. Call `getNotificationsCount` to obtain the total number of unread notifications.
3. 3. For each notification you wish to clear, call `markNotificationAsRead` with path parameter `id` of the notification.

## Rules

- Auth: Include a JWT token in the `Authorization` header as `Bearer <token>`.
- Pagination: `getNotifications` supports `page` and `pageSize` query parameters for paginated results.
- Idempotency: `markNotificationAsRead` is idempotent; repeating the call has no additional effect.
