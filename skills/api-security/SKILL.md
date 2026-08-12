---
name: api-security
description: API, server-action, RPC, network-boundary, CORS, request/response, SSRF, rate-limit, and external-provider response safety. Use when modifying network APIs or server-side HTTP behavior.
---


# API Security

## Contracts

- Preserve the project's canonical API contract.
- Use predictable success/error shapes.
- Use stable machine-readable error codes when practical.
- Include or propagate request/correlation IDs where supported.
- Clients must validate response shape before rendering/storing data.
- HTTP 200 does not guarantee a valid payload.

## Request Safety

- Authenticate protected endpoints.
- Authorize the exact resource/action before privileged side effects.
- Reject unsupported content types where relevant.
- Apply practical body limits before expensive parsing.
- Validate request data at the boundary.
- Do not expose internal stack traces, SQL errors, provider internals, bucket names, secret names, or credential material.

## Upstream Safety

- Set timeouts for external calls.
- Bound large external response reads where practical.
- Validate provider response shape and trusted fields.
- Do not blindly trust raw provider JSON.

## SSRF

When the server fetches URLs:

- prefer fixed provider SDKs/base URLs or exact destination allowlists;
- restrict protocols;
- block localhost, private, link-local, metadata, and internal destinations as appropriate;
- account for redirects and DNS resolution;
- set size/time limits.

## CORS

For production browser APIs:

- use exact trusted origins where cross-origin access is required;
- do not reflect arbitrary origins;
- do not combine permissive origins with credentials.

## Rate Limiting

Apply endpoint-specific abuse controls where relevant.

Do not trust attacker-controlled forwarded headers or unverified identity claims for rate-limit identity.

Keep valid signed webhook retry capacity separate from generic abusive traffic when necessary.
