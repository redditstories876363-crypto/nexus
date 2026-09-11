# Agent Specifications

## Agent Definition

In NEXUS, an Agent is defined by its System Prompt, Toolset, and Model Constraints.

### Default Agent Roles

| Role | Description | Core Capabilities |
| :--- | :--- | :--- |
| **Manager** | Oversees swarm operations and delegates tasks. | Routing, Conflict Resolution |
| **Researcher** | Fetches and synthesizes information. | Web Search, PDF Parsing, RAG |
| **Coder** | Writes and debugs code in a sandbox. | Python, JS, SQL execution |
| **Reviewer** | Quality assurance and security auditing. | Code Review, Fact-checking |

## Configuration (YAML)

Agents are configured via YAML files in the `/agents` directory:

```yaml
name: "SecurityAuditBot"
role: "Reviewer"
llm_config:
  model: "gpt-4-turbo"
  temperature: 0.1
tools:
  - snyk_scan
  - code_analyzer
system_prompt: |
  You are an expert security auditor. 
  Analyze provided code for vulnerabilities like SQLi, XSS, and hardcoded secrets.
```

## Tool Integration

Tools are Python functions decorated with `@nexus_tool`. They must include docstrings for LLM discovery.