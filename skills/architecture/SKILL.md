---
name: architecture
description: Architecture and subsystem consistency. Use when adding or changing a framework, provider, service boundary, database/auth/storage approach, major subsystem, or cross-cutting architectural pattern; do not use for ordinary localized changes inside established architecture.
---


# Architecture

- Inspect existing architecture and relevant architecture decisions before changing boundaries.
- Do not invent a second client/service/provider abstraction when one already exists.
- Prefer the simplest architecture that satisfies current requirements.
- Avoid speculative infrastructure for hypothetical scale.
- Document material architecture changes and their tradeoffs.
- Identify trust boundaries between clients, servers, databases, storage, queues, providers, and AI systems.
- Keep privileged operations on trusted execution surfaces.
- Define ownership for scheduled jobs, background work, storage, authentication, and external integrations.
- When replacing architecture, plan migration and rollback rather than running two indefinite sources of truth.
