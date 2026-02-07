---
name: temporal-core-concepts
description: Core Temporal concepts, vocabulary, and best practices. Use for explanations, onboarding, and when choosing patterns or SDK features.
---

# Temporal Core Concepts (Doc-first)

## What this skill is for
Use this when the user asks:
- “How does Temporal work?” / “workflow vs activity?”
- Which feature to use (signals vs updates vs queries)
- General best practices and pitfalls
- “Where can I find an official sample for X?”

## Mental model (non-negotiable)
- Workflows are **durable, replayed state machines**.
- Workflow code must be **deterministic** under replay.
- **Activities** are where side effects happen.

## Vocabulary (quick)
- **Workflow Execution**: durable orchestration with replayed history.
- **Activity**: side-effecting step; retried by server policy.
- **Task Queue**: routing for workflow/activity tasks to workers.
- **Signals**: async, fire-and-forget messages into a workflow.
- **Queries**: read-only state inspection.
- **Updates**: state mutation with acknowledgement semantics.
- **Child workflows**: compositional orchestration units.

## Docs-first stance
When in doubt:
1. Prefer official Temporal docs for the feature being discussed.
2. Prefer official samples for runnable patterns.
3. Only add local explanation for the delta between docs/samples and the user’s context.

### Official docs (start here)
- Temporal docs home
- .NET developer guide
- .NET “getting started” tutorial

### Sample discovery (how to map a use-case → sample)
When asked “show me an example for X”:
- Identify the core primitive (activity retry / signal / update / child workflow / schedule / continue-as-new)
- Search official samples repo(s) for that primitive + the target language
- Return the **top 1–3** samples and explain why each is relevant

## Output expectations
- Keep explanations short and practical.
- Always call out determinism implications.
- Always give a “belongs in: Workflow/Activity/Worker/Client” decision when it’s not obvious.
