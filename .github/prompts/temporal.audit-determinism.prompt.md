---
description: Audit selected code for Temporal workflow determinism/replay safety and produce compile-ready fixes.
agent: Temporal .NET SDK Specialist
---

Task:
- Audit the selected code (or active file if no selection) for Temporal workflow determinism and replay safety.
- List each issue with severity (breaks replay / risky / ok), explain why, and provide a compile-ready fix.
- For every issue, state where it belongs: Workflow / Activity / Worker / Client.
- If side effects exist, propose an activity boundary and show the activity stub + workflow call.

Output format:
1) Findings
2) Patched code
3) Replay notes
