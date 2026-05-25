# AI Agent Instructions

This repository stores the durable project memory for HypeLine / HypEnt. Treat repository artifacts as the controlled project state; do not rely on raw chat history when it conflicts with the files here.

## Read order

Before doing substantive work, read:

1. `docs/core/PROJECT_CANON.md` - short control version of the project meaning.
2. `docs/context/CONTEXT_PACK.md` - compact working context for new LLM sessions.
3. `docs/core/SOURCE_OF_TRUTH.md` - deeper current project truth, when needed.

For specific work, also read:

- `docs/core/DECISION_LOG.md` before changing architecture or terminology.
- `docs/tasks/TASK_REGISTRY.md` before changing task boundaries or backlog structure.
- `docs/schemas/ARTIFACT_SCHEMAS.md` before changing artifact fields or allowed values.
- `docs/examples/EXAMPLES_BANK.md` before changing examples or acceptance cases.
- `docs/core/OPERATING_RULES.md` before changing repository memory rules.

## Hard constraints

Do not reintroduce `Capability Block` unless a new explicit decision is added to `DECISION_LOG.md`.

Do not turn `Expected ATE Prior` into an exact forecast of a future pilot result.

Do not make targeting, uplift, HTE, or OPE the default pre-pilot scoring path.

Do not present exploratory post-hoc findings as confirmed experimental learning.

Do not claim automatic rollout decisions or fully autonomous product decision making.

Do not add broad quality metrics unless they can be checked through cases, expert acceptance, or downstream usefulness.

## Update rules

Update `docs/core/PROJECT_CANON.md` when the core project meaning changes or when other documents introduce a meaning-level conflict.

Update `docs/core/SOURCE_OF_TRUTH.md` when the detailed current system view changes.

Update `docs/context/CONTEXT_PACK.md` when a future LLM session would need new context.

Update `docs/core/DECISION_LOG.md` after significant architecture decisions, terminology changes, or reversals.

Update `docs/tasks/TASK_REGISTRY.md` when task boundaries, priorities, or work packages change.

Update `docs/schemas/ARTIFACT_SCHEMAS.md` when artifact fields, allowed values, or validation rules change.

Update `docs/examples/EXAMPLES_BANK.md` when useful examples, test cases, or scenario coverage changes.

## Working style

Prefer concise durable artifacts over raw chat transcripts.

Keep documents explicit about uncertainty, provenance, caveats, and boundaries of use.

When documents conflict, resolve the conflict directly instead of adding another competing summary.
