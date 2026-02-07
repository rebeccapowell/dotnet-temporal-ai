# AGENTS.md

This repository contains a portable “agent library” intended to work across multiple AI coding assistants.
The primary integration target is **GitHub Copilot**, but the same files are organized so that other tools
(e.g., Claude Code, Codex-style agents) can discover the agent policy, skills, and prompt templates.

## Where to find everything

### 1) Always-on workspace rules
- **Copilot workspace instructions:** `.github/copilot-instructions.md`

These are the baseline constraints that should be treated as “always in effect” when working in this repo,
regardless of which agent or skill is used.

### 2) Custom agents (persona + routing)
- **Agents directory:** `.github/agents/`
- Primary agent:
  - `.github/agents/temporal-dotnet-specialist.agent.md`

These files define the “who/how” behavior (router + policy). They are intentionally lightweight and should
delegate detailed guidance to skills.

### 3) Skills (task-shaped capability packs)
- **Skills directory:** `.github/skills/`
- Each skill lives in its own folder and is defined by:
  - `.github/skills/<skill-name>/SKILL.md`

Skill files include YAML frontmatter (`name`, `description`) and are designed for on-demand loading:
a host assistant should select the most relevant skill(s) for the user request and apply the guidance.

### 4) Prompt templates (push-button workflows)
- **Prompts directory:** `.github/prompts/`
- Prompt files:
  - `.github/prompts/*.prompt.md`

These are reusable “entrypoint prompts” for common workflows (determinism audit, placement decision,
versioning change plan, testing, worker/Aspire bootstrap, etc.). In tools that support prompt files, these
should appear as runnable templates. In tools that do not, they can be used as copy/paste starting points.

## How to use this library (assistant-agnostic)

1. **Read** `.github/copilot-instructions.md` and treat those rules as global constraints.
2. **Select an agent** from `.github/agents/` (default: Temporal .NET SDK Specialist).
3. **Route to skills** in `.github/skills/` based on the request:
   - If reviewing workflow code → use `temporal-determinism-audit`
   - If deciding boundaries → use `temporal-placement`
   - If designing APIs → use `temporal-workflow-apis`
   - If versioning/evolution → use `temporal-versioning-evolution`
   - If testing → use `temporal-testing-dotnet`
   - If hosting/Aspire → use `temporal-worker-client-hosting-aspire`
   - If retries/failures → use `temporal-failures-retries-cancellation`
   - If observability → use `temporal-observability`
   - If payloads/codecs → use `temporal-payloads-codecs`
   - If unsure → start with `temporal-core-concepts`
4. Optionally, **start from a prompt template** in `.github/prompts/` for consistent output formats.

## Conventions

- Keep agents small: routing + non-negotiable policy only.
- Put detailed checklists, examples, and “how-to” guidance into skills.
- Keep skills task-shaped and testable (clear inputs/outputs and guardrails).
- Prefer official documentation for version-sensitive APIs; do not guess.

## Add a new skill

1. Create folder: `.github/skills/<new-skill>/`
2. Add: `.github/skills/<new-skill>/SKILL.md` with YAML frontmatter:
   ```yaml
   ---
   name: <new-skill>
   description: <one-line when-to-use>
   ---
   ```
3. Include: when-to-use, required output, guardrails, and a minimal example.
4. Mention the skill in the router agent’s “Skills catalog” section.
