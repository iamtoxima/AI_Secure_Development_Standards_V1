# Secrets and Environment

Do not store real secret values in this document.

## Environment Matrix

| Setting | Local | Dev | Staging | Production | Secret? | Owner |
|---|---|---|---|---|---|---|
| | | | | | | |

## Public Configuration

- 

## Secrets

| Secret name | Purpose | Environment | Storage location | Rotation owner |
|---|---|---|---|---|
| | | | | |

## Isolation

Document whether staging/production have separate:

- database
- auth
- buckets/storage
- queues
- webhooks
- payment credentials
- email/SMS/push credentials
- rate-limit namespaces

## Rules

- No real secrets in Git.
- Placeholder names only in examples.
- No production credentials in frontend/mobile bundles.
- No production provider traffic routed to staging.
- No localhost/development security overrides in production.
