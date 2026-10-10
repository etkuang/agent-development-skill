# Authority and approval policy

## Selection method

1. Identify the acting identity and the resource/action grants relevant to the task.
2. Classify consequential actions by impact and reversibility, and determine which need explicit review under the responsible owner's policy.
3. Choose the authorized reviewer, the proposed action and context shown, and the permitted outcome when approval is unavailable or denied.
4. Carry the resulting policy into runtime selection; detailed enforcement and pause/resume design come later.

## Supporting guidance and sources

Permissions come from the responsible authority, not model confidence or retrieved instructions. Agent identities and permission assignments are distinct from business participation. [Microsoft Agent 365 identity](https://learn.microsoft.com/en-us/microsoft-agent-365/developer/identity) (Agent 365 / Microsoft Entra Agent ID, rolling documentation) and [AWS human review for critical decisions](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentsec04-bp02.html) (Agentic AI Lens, rolling documentation), accessed 2026-10-10.

Approval mechanisms must support the chosen policy. The [OpenAI Agents SDK human-in-the-loop guide](https://openai.github.io/openai-agents-python/human_in_the_loop/) describes sensitive-tool-call approval and pause/resume, and requires the application to authenticate and authorize reviewers. This is a capability example, not an organization-specific permission policy (Agents SDK for Python, rolling documentation; accessed 2026-10-10).
