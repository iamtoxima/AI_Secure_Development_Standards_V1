---
name: privacy-data-governance
description: Privacy, personal/sensitive data handling, retention/deletion/export, consent, data minimization, legal hold, and provider/data-flow governance. Use when the product processes personal, sensitive, regulated, or high-trust data.
---


# Privacy and Data Governance

- Identify categories of personal/sensitive data the product stores or transmits.
- Collect only data needed for defined product purposes.
- Document where sensitive data flows and which providers receive it.
- Define retention and deletion behavior for sensitive records.
- Define account deletion and data export behavior when required by the product/jurisdiction.
- Keep policy/consent versions when consent is a meaningful legal/product control.
- Do not place sensitive personal data in URLs, object keys, logs, analytics, notification payloads, or public caches.
- Limit admin/support access to sensitive records.
- Audit especially sensitive access where appropriate.
- Define legal hold/exception behavior when relevant.
- Ensure privacy/terms statements match actual product behavior and providers.
- Flag jurisdiction-specific legal/compliance questions for qualified human review; do not invent legal conclusions.

## Jurisdiction-Specific Privacy

General privacy engineering is not a substitute for applicable law.

When users/business/data processing have a jurisdictional nexus:

- determine the relevant local policy module;
- verify current regulator requirements;
- update retention/deletion/data-subject workflows;
- do not claim legal compliance without required organizational/legal evidence.
