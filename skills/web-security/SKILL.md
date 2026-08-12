---
name: web-security
description: Browser-facing website/web-app/admin-portal security including XSS, CSRF, cookies, CSP, clickjacking, CORS interaction, redirects, and browser security headers.
---


# Web Security

## Rendering

- Prefer framework-safe text rendering.
- Avoid unsafe HTML insertion APIs.
- Sanitize intentionally supported rich HTML with a maintained allowlist-based sanitizer.
- Encode for the actual output context.

## Session/Cookies

For cookie-based sessions:

- use Secure where HTTPS is required;
- use HttpOnly for session secrets where compatible;
- choose appropriate SameSite behavior;
- minimize Domain/Path scope.

Never put session tokens in URLs.

## CSRF

For cookie-authenticated state changes:

- use appropriate SameSite policy;
- use CSRF tokens/origin validation when required by the architecture;
- never use GET/HEAD for state-changing actions.

## Browser Hardening

Consider centralized:

- Content-Security-Policy
- frame-ancestors / legacy frame protection
- X-Content-Type-Options
- Referrer-Policy
- Permissions-Policy
- HSTS in correct HTTPS production deployments

Do not copy a generic CSP that breaks required functionality.

## Redirects

- Prefer internal relative redirects.
- Validate external redirect destinations against exact trusted destinations where needed.
- Reject deceptive schemes/hosts/protocol-relative bypasses.

## Client Data

Do not treat local storage, JavaScript state, hidden controls, or client role metadata as trusted authorization.
