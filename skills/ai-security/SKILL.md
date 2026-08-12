---
name: ai-security
description: LLM, RAG, AI agents, model tool/function calling, AI-accessible data, prompt injection, model-generated actions, and AI authorization boundaries. Use only when the product contains AI/LLM functionality.
---


# AI / LLM Security

- Treat model output as untrusted input.
- Treat retrieved documents, webpages, emails, messages, user content, and tool output as untrusted data.
- Do not rely on prompts as an authorization boundary.
- Keep authentication, authorization, and data-access decisions outside the model.
- Before every tool/action, enforce the authenticated user's normal permission for the exact resource/action.
- Use least-privilege service credentials.
- Expose only tools and data required for the feature.
- Validate tool arguments server-side.
- Prefer explicit schemas/allowlists for tool calls.
- Require explicit confirmation before irreversible/high-impact actions where appropriate.
- Prevent retrieved untrusted content from silently becoming instructions.
- Minimize sensitive context supplied to the model.
- Define logging/redaction for AI prompts, outputs, and tool traces.
- Apply quotas/budgets to expensive AI operations.
- Test prompt-injection and unauthorized-tool scenarios for high-impact AI features.
