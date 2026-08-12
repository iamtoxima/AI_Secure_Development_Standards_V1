---
name: environment-deployment
description: Environment separation, secrets/configuration, local/staging/production isolation, CI/CD, hosting, deployment artifacts, rollback, and production configuration safety.
---


# Environment and Deployment Security

## Separation

Keep local, development, staging, and production meaningfully distinct.

For security-sensitive products, avoid sharing:

- production customer data
- production payment credentials
- privileged secrets
- private buckets
- queues
- webhook destinations
- rate-limit namespaces
- production auth configuration

Do not route production payment/email/SMS/push/webhook events into staging.

## Configuration

- Document environment variables and whether each is public config, binding, or secret.
- Keep real secrets out of Git and documentation.
- Keep `.env.example` values non-secret.
- Do not enable localhost/development CORS or debug behavior in production.
- Treat production preview URLs and old deploy versions as potentially reachable unless protected/disabled.

## Build Artifacts

Deploy only intended output.

Do not publicly ship:

- `.env`
- `.git`
- backups
- database dumps
- debug bundles
- temporary files
- private configs
- private source maps when not intentionally protected
- secrets embedded in built assets

## Rollback

Define how to return to the last known-good:

- application version
- worker/service version
- database state/migration strategy
- mobile release where applicable.

Rehearse rollback for high-risk releases when practical.
