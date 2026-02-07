---
description: Create a safe workflow evolution plan using Workflow.GetVersion and (if needed) continue-as-new.
agent: Temporal .NET SDK Specialist
---

Task:
- Given the “before” and “after” behavior (or diff), produce a safe change plan.
- Use Workflow.GetVersion and show old+new branches.
- Explain when it’s safe to remove old branches.
- Recommend continue-as-new triggers if relevant.

Output format:
1) Change plan
2) Versioning snippet(s)
3) Removal policy
4) Continue-as-new guidance
