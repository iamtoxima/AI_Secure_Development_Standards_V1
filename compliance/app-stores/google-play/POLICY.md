# Google Play Policy Baseline

Status: Platform-policy baseline  
Verified against official Google Play documentation: 2026-08-12

Google Play policies change frequently. This file is not a substitute for the
current Developer Program Policies.

## Account Deletion

For apps that allow account creation, the current Google Play baseline requires:

- a readily discoverable in-app account-deletion path;
- an external web resource where deletion can be requested;
- deletion of associated account data, subject to legitimate retention needs;
- disclosure of retained data/reasons where applicable;
- account freezing/deactivation alone does not satisfy deletion.

## Privacy and Data Safety

- maintain an accurate privacy policy;
- complete and keep the Play Data safety declaration accurate;
- include data practices of third-party SDKs/libraries;
- do not assume Google's review proves the declaration is complete;
- update disclosures when product data behavior changes.

## Personal/Sensitive Data and Permissions

- request sensitive permissions only for current core/user-facing functionality;
- request access in context and use minimum-scope alternatives where available;
- respect refusal and provide reasonable alternatives where practical;
- do not collect data for unimplemented/future features;
- verify current restricted-permission declaration/approval requirements before
  release.

Google has announced/implemented evolving minimum-scope rules for areas such as
contacts and location; always verify current effective dates and target-SDK
requirements.

## Payments

For Play-distributed apps:

- determine whether a purchase is a physical good/service or a digital
  good/service;
- current Play policy generally requires Google Play Billing for in-app digital
  goods, app functionality, digital content, and subscriptions unless a current
  exception/eligible program applies;
- physical goods/services and some other categories are treated differently;
- do not assume Paystack/Flutterwave/Monnify is permitted for a digital in-app
  purchase merely because the gateway technically works.

## Third-Party SDKs / AI

The developer remains responsible for policy compliance of third-party code and
data practices, including third-party AI integrations.

## Release Gate

Immediately before Play submission/update, verify current:

- Developer Program Policies;
- Payments policy;
- User Data policy;
- Data safety requirements;
- account deletion;
- sensitive/restricted permissions;
- target API requirements;
- SDK policy;
- content/user-generated-content/AI/children policies relevant to the product.

## Official Sources

- https://support.google.com/googleplay/android-developer/answer/17190352
- https://support.google.com/googleplay/android-developer/answer/10144311
- https://support.google.com/googleplay/android-developer/answer/10787469
- https://support.google.com/googleplay/android-developer/answer/9858738
- https://support.google.com/googleplay/android-developer/answer/10281818
- https://support.google.com/googleplay/android-developer/answer/16558241
