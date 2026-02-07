---
name: temporal-payloads-codecs
description: Payload converters/codecs and encryption/PII boundaries for Temporal .NET. Emphasizes determinism constraints and safe placement.
---

# Payloads, Converters, Codecs, and Encryption Boundaries

## When to use
Use when the user asks about:
- serialization formats and payload converters
- codec servers / encryption-at-rest of payloads
- PII handling and data minimization in histories
- determinism implications of codecs/converters

## Required output
- Recommended approach (converter vs codec) and where it runs
- Determinism note: what must be stable and why
- Placement guidance: Workflow vs Activity vs Worker vs external codec server

## Guardrails
- Encryption and codecs must not introduce nondeterminism.
- Codec servers belong outside workflows.
