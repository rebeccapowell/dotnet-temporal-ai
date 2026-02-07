---
name: temporal-workflow-apis
description: Design correct Temporal .NET workflow APIs: run method, signals, queries, updates, and child workflow patterns. Includes idempotency notes.
---

# Workflow APIs: Run / Signal / Query / Update / Child Workflows

## When to use
Use this when the user is defining or refactoring:
- workflow entrypoint shape
- signal/query/update APIs
- child workflow orchestration
- idempotency & state model

## Required guidance
- Queries must be **read-only**.
- Signals are **fire-and-forget**; make handlers idempotent.
- Updates **mutate with acknowledgement**; describe acceptance/completion semantics.
- Keep workflow state explicit; do not use static mutable state.

## Output required
Provide:
1. Recommended public surface (method signatures + attributes)
2. State model outline (fields + invariants)
3. Idempotency approach for signals/updates
4. Minimal compile-ready example

## Notes
- Prefer stable, explicit task queues.
- If the SDK supports update stages, mention how to wait for admitted/accepted/completed when relevant.
