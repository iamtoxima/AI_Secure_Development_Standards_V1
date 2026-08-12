---
name: policy-compliance
description: External provider, app-store, regulatory, legal-policy, and security-standard applicability/verification. Use when a task depends on payment-provider requirements, Google Play/App Store rules, jurisdiction-specific law/regulation, PCI/OWASP/NIST claims, or another time-sensitive external policy.
---

# External Policy and Compliance

## Applicability

Do not load or enforce every external policy.

Determine applicability from:

- platform/distribution;
- countries/regions;
- business model;
- data processed;
- provider;
- payment model;
- regulated activity;
- app capabilities.

## Live Verification

Stored policy modules are baselines.

For time-sensitive requirements:

- verify the current official source before implementation when the detail
  affects security/integration correctness;
- verify again before release when the requirement can affect acceptance,
  compliance, payment integrity, or user rights;
- record verification date/version/source where material.

Prefer first-party official sources.

## Conflicts

A provider's technical documentation does not override:

- law/regulation;
- app-store distribution policy;
- privacy requirements;
- mandatory security controls.

Satisfy all applicable requirements.

## Legal Claims

Do not provide definitive licensing/legal conclusions where material legal
interpretation is required.

Identify the question and flag it for qualified human review.

## Evidence

Do not mark a project compliant with an external standard/platform/law merely
because the corresponding Skill/module was read.

Require the project's real implementation, configuration, disclosures, tests,
organizational steps, and release evidence.
