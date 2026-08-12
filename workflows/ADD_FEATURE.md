# Add Feature Workflow

Use when a user requests a capability that is new, previously deferred, or currently inactive.

## 1. Capability Detection

Check `PROJECT_CAPABILITIES.md`.

Classify the requested capability:

- New
- Previously deferred
- Previously removed
- Existing but incomplete
- Existing and being expanded

## 2. Ask Feature-Specific Questions

Ask only questions required for the feature.

Examples for chat:

- who can chat;
- when chat becomes available;
- group or 1:1;
- attachments;
- retention;
- reporting/blocking;
- moderation;
- admin access;
- notification behavior;
- whether contact sharing is allowed.

Examples for payments:

- payer/payee;
- provider;
- currency;
- payment states;
- refund behavior;
- subscriptions/escrow;
- reconciliation;
- webhooks.

## 3. Activate Standards

Use the local dormant library.

Do not fetch the remote repo unless the required standard is missing locally.

Update:

- STANDARDS_MANIFEST
- PROJECT_CAPABILITIES

## 4. Impact Analysis

Use `CHANGE_IMPACT_MAP.md`.

Update affected:

- PRD
- app flow
- architecture
- data model
- API contract
- security requirements
- secrets/environment
- failure modes
- logging/audit
- privacy/retention
- notifications
- test plan
- implementation plan

Only update relevant documents.

## 5. Safe Implementation

- create a Git checkpoint when the change is substantial;
- prefer feature flags/safe disabled states for high-risk incomplete capabilities;
- implement in small milestones;
- test success and important negative/failure paths;
- keep documentation synchronized.
