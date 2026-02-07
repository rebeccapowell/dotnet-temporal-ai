---
name: temporal-worker-client-hosting-aspire
description: Worker/client lifecycle, task queues, DI hosting patterns, and Aspire (InfinityFlow-style) integration guidance for Temporal .NET.
---

# Worker + Client Hosting (and Aspire)

## When to use
Use when the user asks about:
- creating the Temporal client (singleton per process)
- worker registration and task queues
- scaling workers horizontally
- Aspire/InfinityFlow integration and local dev server patterns
- double-bootstrapping (worker starts itself + Aspire also starts it)

## Required output
- Recommended bootstrap structure (Generic Host / DI lifetimes)
- Task queue naming guidance (stable + explicit)
- Aspire rule: when Aspire is present, workers should be first-class Aspire projects/resources
