# Apple App Store Policy Baseline

Status: Platform-policy baseline  
Verified against official Apple documentation: 2026-08-12

Apple's App Review Guidelines are a living document. Verify them immediately
before submission.

## App Completeness and Review

- submit a functioning, tested product rather than placeholder/incomplete
  behavior;
- provide review access/demo information required for account-based features;
- accurately describe new features and non-obvious functionality in review
  notes.

## Payments

Current Apple baseline distinguishes digital and physical purchases.

- unlocking digital functionality/content/subscriptions in the app generally
  falls under Apple's In-App Purchase requirements unless a current guideline
  exception applies;
- physical goods/services consumed outside the app are treated differently and
  use payment methods other than IAP;
- do not assume an external payment gateway is allowed for a digital in-app
  purchase solely because it is technically possible.

Always verify current storefront/region-specific rules and entitlements.

## Privacy

- provide a privacy policy;
- keep App Store Connect privacy details accurate;
- include data practices of third-party SDKs/partners;
- update privacy disclosures when product behavior changes;
- obtain required consent/permission for data collection/use;
- if tracking applies, evaluate current AppTrackingTransparency requirements.

## Account Deletion

For apps supporting account creation:

- provide a way to initiate account deletion in the app;
- deletion should address associated personal data not legally required to be
  retained;
- make the deletion experience discoverable and transparent;
- if completion occurs on the web where permitted, link directly to the
  appropriate page;
- explain retention and subscription/billing implications where relevant.

## Sign-In and Device Capabilities

Before release verify current requirements for:

- Sign in with Apple where another third-party/social login is used;
- privacy manifests / required-reason APIs / SDK signatures where applicable;
- background modes, notifications, location, camera, contacts, health, and other
  sensitive capabilities.

## Release Gate

Verify the live App Review Guidelines and App Store Connect requirements for the
exact app, region, capability, and business model before submission.

## Official Sources

- https://developer.apple.com/app-store/review/guidelines/
- https://developer.apple.com/support/offering-account-deletion-in-your-app/
- https://developer.apple.com/app-store/app-privacy-details/
- https://developer.apple.com/app-store/user-privacy-and-data-use/
