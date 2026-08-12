# External Policy Verification

Version: 1.0  
Baseline verified: 2026-08-12

Provider requirements, app-store policies, cybersecurity standards, laws,
regulations, and platform requirements can change after this repository is
published.

Stored policy modules are **baselines and routing aids**, not a substitute for
current authoritative requirements.

## MUST: Live Verification

When a task is governed by an external authority or provider:

1. Identify the applicable:
   - provider;
   - distribution platform;
   - operating-system platform;
   - jurisdiction;
   - regulated activity;
   - external security/compliance standard.

2. Read the relevant local baseline in this repository or the project's local
   `.ai/standards-library/`.

3. Before implementing a time-sensitive integration or marking a release gate
   complete, verify the current requirement against an authoritative source.

4. Prefer first-party sources:
   - payment/provider documentation;
   - Apple/Google platform documentation;
   - regulator/government websites;
   - official standards organizations such as OWASP, NIST, PCI SSC.

5. Record, when materially relevant:
   - authoritative source;
   - date verified;
   - policy/version identifier when available;
   - implementation requirement;
   - evidence that the project satisfies it.

6. If the current official requirement differs from the stored snapshot:
   - follow the current authoritative requirement;
   - update the project-local policy record;
   - do not silently preserve the stale requirement.

7. Reverify high-risk or fast-changing requirements again before production
   release.

## If Live Verification Is Unavailable

If the AI cannot reach the authoritative source:

- do not invent the current requirement;
- use the stored baseline only as provisional guidance;
- mark the requirement `Current verification required`;
- do not mark the compliance/release gate as Verified.

## Legal and Regulatory Interpretation

AI may identify likely applicability and engineering controls, but must not
pretend to provide definitive legal advice.

When applicability or interpretation materially affects a regulated business,
privacy obligation, licensing requirement, tax/consumer obligation, or another
legal conclusion:

- identify the issue;
- preserve a safe technical default;
- request qualified legal/compliance review before claiming compliance.

## Conflict Rule

When requirements overlap, satisfy all applicable constraints unless they are
genuinely incompatible.

Examples:

- a payment gateway allows a payment method, but an app-store billing policy may
  prohibit that method for a specific digital purchase;
- a provider permits data retention, but applicable privacy law may impose a
  stricter purpose or retention requirement.

Do not treat a provider's documentation as overriding law, platform policy, or
another applicable security obligation.
