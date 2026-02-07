---
name: temporal-failures-retries-cancellation
description: Model failures correctly in Temporal .NET: retries, timeouts, cancellation, and heartbeats for long-running activities.
---

# Failures, Retries, Cancellation & Heartbeats

## When to use
Use for:
- retry policy design
- distinguishing retryable vs non-retryable failures
- cancellation propagation (workflow → activity)
- diagnosing “it keeps retrying forever”
- long-running activities (heartbeats)

## Required output
- Recommended retry/timeout settings (what + why)
- How to represent business failures vs transient failures
- Cancellation-aware activity pattern (including heartbeat guidance if relevant)
- Placement: what logic belongs in workflow vs activity

## Guardrails
- Do not hide failures; show explicit retry semantics.
- Treat cancellation distinctly from failures/timeouts.
