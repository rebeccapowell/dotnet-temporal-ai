---
name: temporal-observability
description: Observability patterns for Temporal .NET: structured logging, search attributes, and replay-safe logging guidance.
---

# Observability: Logs, Search Attributes, and Replay Noise

## When to use
Use when the user asks:
- “how do I trace/debug this workflow?”
- “how do I make executions searchable in the UI?”
- “why are logs duplicated/noisy during replay?”

## Required output
- What to log in **activities** vs what to avoid in workflow
- Search attribute strategy (what to index; cardinality cautions)
- Practical debugging steps: what to look for in history vs logs

## Guardrails
- Do not suppress real errors; distinguish replay-only noise carefully.
