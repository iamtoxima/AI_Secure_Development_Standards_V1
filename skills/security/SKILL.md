---
name: security
description: General application security and trust-boundary rules. Use for authentication, authorization, untrusted input, sensitive data, privileged actions, security-sensitive state, or any network-facing product surface.
---


# Security

## Trust Boundaries

Treat data crossing a trust boundary as untrusted, including:

- user/form input
- URL/path/query parameters
- headers/cookies
- uploaded files
- webhook payloads
- third-party API responses
- imported documents/content
- AI/model output
- client-stored metadata

Validate type, shape, size, format, allowed values, and relevant business invariants.

Do not rely on generic character stripping as the primary security mechanism.

## Authentication and Authorization

- Authentication answers who the caller is; authorization answers what they may do.
- Enforce protected permissions server-side or in another trusted policy layer.
- Never rely on hidden UI, disabled buttons, route guards, or client claims as the sole authorization control.
- Derive identity from a trusted authenticated context.
- Do not trust client-supplied role, ownership, tenant, permission, entitlement, price, payment status, or privilege fields.
- Check object-level ownership/participant/tenant access for protected resources.
- Default to deny/fail closed when a required authorization fact is missing.

## Trusted State

Security- and money-sensitive state should come from trusted server-side records or verified provider state.

Validate state transitions, not only enum values.

## Secrets

- Keep private secrets out of browser/mobile-delivered code.
- Never hard-code production credentials.
- Never put secrets in URLs or normal logs.
- Treat shipped frontend/mobile binaries as inspectable.
- If a secret may have been exposed, rotation is required; moving it to another file is insufficient.

## Sink-Specific Safety

- SQL: parameterization/safe query APIs.
- NoSQL: construct filters from allowed fields; reject attacker-controlled operators.
- HTML: context-safe escaping; sanitize intentional rich HTML with a maintained allowlist-based sanitizer.
- Shell: avoid shell execution; otherwise structured arguments and strict allowlists.
- Filesystem: server-controlled paths/IDs, canonicalization, containment.
- URL fetch: allowlist/restrict destinations and protocols; address SSRF risk.
- Templates: never compile/evaluate untrusted content as template source.

## Negative Tests

For security-sensitive changes, add targeted tests where practical for:

- missing authentication
- wrong role
- cross-user access
- invalid/tampered input
- invalid state transition
- low-scope credential attempting high-scope action
