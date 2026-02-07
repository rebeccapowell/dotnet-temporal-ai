# Workspace Copilot Instructions — Temporal (.NET)

These are always-on workspace rules for Temporal work in this repo.

- **Treat workflows as replayed state machines**. If something can differ on replay, it does not belong in workflow code.
- **All side effects go into activities** (IO, DB, network, filesystem, randomness outside Temporal APIs).
- **Always classify advice** as Workflow vs Activity vs Worker vs Client.
- Prefer **compile-ready** snippets and show the minimal viable structure.
- For version-sensitive questions, consult the **Temporal docs MCP** (if available) rather than guessing.
