# Trusted authorization enforcement

Use this reference when a task accesses protected resources or executes scoped actions.

## Decision method

Identify both verified user subject and acting service/agent. Choose delegated user access or a narrowly scoped accountable service identity according to the task; shared credentials must preserve the caller's boundary.

Apply least privilege and default deny at trusted source ACLs, row/field rules, gateways or server-enforced scopes before protected data reaches a model or an action executes. Missing or unknown grants do not permit access. Test denied principals and alternate routes.

Read-only execution, model confidence and tool annotations do not establish permission to read a particular record. Masking can minimize permitted exposure while authorization remains necessary.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Microsoft agent identity](https://learn.microsoft.com/en-us/microsoft-agent-365/developer/identity) — Microsoft Agent 365 identity documentation; accessed 2026-10-10.
- [AWS human review](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentsec04-bp02.html) — AWS Well-Architected Agentic AI Lens; accessed 2026-10-10.
- [AWS IAM evaluation](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic_policy-eval-denyallow.html) — AWS IAM policy evaluation documentation; accessed 2026-10-10.
- [SQL masking](https://learn.microsoft.com/en-us/sql/relational-databases/security/dynamic-data-masking?view=sql-server-ver17) — SQL Server 17.x documentation; accessed 2026-10-10.

