---
name: chat-security
description: User-to-user messaging, chat, private comments, chat attachments, moderation, abuse controls, conversation privacy, retention, and dispute/admin access. Use only when messaging functionality exists or is being added.
---


# Chat and Messaging Security

Before implementation establish:

- who may message whom;
- when messaging becomes available;
- whether group chat exists;
- attachment support;
- retention/deletion;
- moderation/reporting/blocking;
- admin/support access;
- notification behavior;
- whether contact sharing is permitted.

## Access

- Authenticate message reads/writes.
- Authorize conversation participation server-side.
- Do not expose conversations through guessable IDs without participant checks.
- Recheck authorization for attachments/private media.

## Privacy

- Return only fields needed by participants.
- Do not expose private address, coordinates, phone, email, payment, or identity data unless the product explicitly requires it.
- Define retention and deletion behavior.

## Abuse

Where applicable implement:

- rate limits;
- report/block controls;
- spam/flood controls;
- content/contact-sharing rules;
- escalation paths.

Do not store prohibited raw content solely for moderation analytics without a justified retention policy.

## Administrative Access

If admins/support can access chat:

- enforce privileged authorization;
- log/audit sensitive access;
- minimize exposed data;
- define when transcript snapshots are allowed.

## State

If chat depends on order/payment/membership state, derive eligibility from trusted server state rather than the client.
