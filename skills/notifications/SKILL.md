---
name: notifications
description: Email, SMS, push notifications, bulk messaging, notification preferences, delivery queues, retries, device tokens, and privacy of notification content.
---


# Notifications

- Keep provider credentials on trusted server infrastructure.
- Do not send privileged/bulk notifications directly from untrusted clients.
- Queue bulk or non-critical notification work when appropriate.
- Record delivery attempts using safe metadata.
- Make retry behavior explicit.
- Use idempotency/deduplication when duplicate sends materially harm the user.
- Remove/revoke invalid device tokens when supported.
- Do not put sensitive private data, payment details, KYC data, secrets, or unnecessary addresses in push/SMS/email payloads.
- Respect transactional vs marketing purpose and user preferences where applicable.
- Require authorization and confirmation for high-impact admin/bulk sends.
- Audit sensitive campaigns/actions when appropriate.
- Failure of a non-critical notification should not invalidate the underlying successful business transaction.
- Define provider outage and retry behavior.
