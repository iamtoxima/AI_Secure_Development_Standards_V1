# External Policy Registry

Baseline snapshot date: 2026-08-12

This registry lists external policy modules available to AI agents. These
modules are normally dormant until the project profile makes them relevant.

| Category | Module | Trigger |
|---|---|---|
| Payment provider | `providers/payments/paystack/POLICY.md` | Paystack integration |
| Payment provider | `providers/payments/flutterwave/POLICY.md` | Flutterwave integration |
| Payment provider | `providers/payments/monnify/POLICY.md` | Monnify integration |
| App store | `compliance/app-stores/google-play/POLICY.md` | Google Play distribution |
| App store | `compliance/app-stores/apple-app-store/POLICY.md` | Apple App Store distribution |
| Nigeria | `compliance/jurisdictions/nigeria/PRIVACY.md` | Nigeria personal-data nexus |
| Nigeria | `compliance/jurisdictions/nigeria/CONSUMER_PROTECTION.md` | Nigerian consumer-facing product |
| Nigeria | `compliance/jurisdictions/nigeria/PAYMENTS_FINTECH.md` | Payment/fintech activity in Nigeria |
| Nigeria | `compliance/jurisdictions/nigeria/DIGITAL_LENDING.md` | Digital/non-traditional consumer lending |
| Security baseline | `security-baselines/OWASP_ASVS.md` | Application security requirements |
| Security baseline | `security-baselines/OWASP_API_SECURITY.md` | Network/API surface |
| Security baseline | `security-baselines/OWASP_MASVS.md` | Mobile app |
| Secure SDLC | `security-baselines/NIST_SSDF.md` | Secure development lifecycle |
| Payment data | `security-baselines/PCI_DSS.md` | Cardholder-data environment may be in scope |

## Rule

Do not copy every module into active project instructions.

Use these modules to:

1. resolve applicability;
2. activate the relevant project Skill/policy;
3. verify current authoritative requirements;
4. create project-specific implementation/release gates.
