---
name: mobile-security
description: Native/mobile application security for iOS, Android, Flutter, React Native, Swift, and Kotlin, including token storage, deep links, release builds, backups, cleartext, and device-facing controls.
---


# Mobile Security

- Assume shipped application binaries can be inspected.
- Do not embed server secrets or privileged credentials.
- Store sensitive tokens in platform secure storage/keychain/keystore mechanisms.
- Do not store sensitive auth material in ordinary preferences/plain local storage.
- Disable sensitive/debug logging in production releases.
- Disable cleartext network traffic in production unless a documented exceptional need exists.
- Use secure TLS defaults.
- Validate deep-link/universal-link/app-link actions and authorization on trusted backend logic.
- Review backup behavior for sensitive app data.
- Use release signing and keep signing secrets private/outside source control.
- Enable appropriate release shrinking/obfuscation/hardening for the stack where useful.
- Consider screenshot/screen-capture restrictions on highly sensitive screens where supported and justified.
- Test on real devices for critical auth, push, deep link, secure storage, and release-build behavior.
- Security should not rely on client-side route guards.

## Store Policy

Mobile security does not replace distribution-store policy.

If distributed through Google Play or Apple App Store:

- activate `policy-compliance`;
- use the relevant app-store policy module;
- classify digital vs physical purchases before selecting payment flow;
- verify current account-deletion/privacy/permission/billing rules before release.
