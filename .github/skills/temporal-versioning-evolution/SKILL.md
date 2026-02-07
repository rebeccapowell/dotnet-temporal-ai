---
name: temporal-versioning-evolution
description: Safely evolve Temporal workflows in .NET using Workflow.GetVersion, immutable history rules, and continue-as-new strategies.
---

# Workflow Evolution: Versioning + Continue-As-New

## When to use
Use when the user wants to:
- change workflow logic in production
- reorder steps / change branching
- add/remove activities or timers
- manage history size for long-running workflows

## Required output
1. A safe change plan using `Workflow.GetVersion` (show old + new branches)
2. A removal policy for old branches (only after all executions that might replay old history are complete)
3. If relevant: continue-as-new trigger strategy (history thresholds, state carryover)

## Guardrails
- Workflow history is immutable.
- Never delete old branches prematurely.
