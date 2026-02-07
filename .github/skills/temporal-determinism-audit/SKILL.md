---
name: temporal-determinism-audit
description: Audit Temporal .NET workflow code for determinism/replay safety and produce compile-ready fixes.
---

# Temporal Determinism Audit (C#)

## When to use
Use this skill when the user:
- pastes workflow code or a workflow diff
- asks “is this safe in a workflow?”
- gets replay / nondeterminism errors
- reports flaky behavior that could be replay-related

## Required output
Always produce:
1. **Findings** (bullets; severity: `breaks replay` / `risky` / `ok`)
2. **Fix** (compile-ready patch or rewritten snippet)
3. **Placement** (Workflow / Activity / Worker / Client)
4. **Replay note** (why this matters on replay)

## Non-negotiable forbidden list (workflows)
- `Task.Run`, `Thread.Sleep`, `Task.Delay`
- `DateTime.UtcNow` (use `Workflow.Now`)
- `Guid.NewGuid()` (use `Workflow.NewGuid()`)
- Random number generators (unless via Temporal deterministic APIs)
- Locks/monitors/semaphores
- Any file/network/database IO
- Static mutable state

## Approved substitutes (workflows)
- `Workflow.DelayAsync`
- `Workflow.Now`
- `Workflow.NewGuid()`
- Deterministic control flow + calling Activities for side effects

## Common rewrite patterns
- Move side effects into `[Activity]` methods
- Use activity retry options (don’t “hide” failures)
- Replace timers/delays with Temporal workflow timers

## If context is missing
Assume code is workflow code unless the user states otherwise, and explicitly state that assumption.
