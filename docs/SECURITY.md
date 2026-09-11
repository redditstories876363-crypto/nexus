# Security & Guardrails

## Authentication & Authorization

- **API Keys**: All requests must include a `X-NEXUS-API-KEY`.
- **RBAC**: Roles (Admin, Developer, Viewer) control access to agent configurations and tool deployments.

## Guardrails

NEXUS implements a multi-layer guardrail system:

1. **Input Sanitization**: Filters out prompt injection attempts.
2. **PII Redaction**: Uses Presidio to mask sensitive data before sending prompts to external LLM providers.
3. **Output Validation**: Ensures agent responses follow specific schemas (e.g., valid JSON or YAML).
4. **Execution Sandboxing**: All code-execution tools run in ephemeral Docker containers with restricted network access.

## Budget Management

Set hard limits in `.env` or via the UI to prevent runaway costs:
- `MAX_MONTHLY_SPEND=100.00`
- `MAX_TOKENS_PER_TASK=50000`