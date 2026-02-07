# Temporal Copilot Toolkit (.NET)

This folder provides a **custom Copilot agent**, a set of **Agent Skills**, and a set of **Prompt files** for working with Temporal in .NET.

## What’s included

- `.github/agents/temporal-dotnet-specialist.agent.md`  
  Small **router + policy** agent (kept intentionally light).

- `.github/skills/*/SKILL.md`  
  Task-shaped skills using YAML frontmatter (`name`, `description`). Copilot loads skill content on-demand.

- `.github/prompts/*.prompt.md`  
  Reusable prompt templates you can run from Copilot Chat.

## How to use

1. Select the **Temporal .NET SDK Specialist** agent in Copilot Chat.
2. Use prompts (type `/` in chat) or just ask naturally.
3. When you paste workflow code, the agent should route to determinism audit automatically.

## Notes

- Keep skill files **doc-first** and **sample-driven**.
- When SDK behavior is version-sensitive, consult official Temporal docs.
