# Operating Rules

These rules define how to work with ChatGPT and repository artifacts without letting the project drift.

## Basic rule

ChatGPT is a drafting and reasoning tool. The repository is the source of durable project state.

A statement is considered current only if it is reflected in the appropriate project artifact.

## Recommended rhythm

After a long ChatGPT session:

1. Update `docs/context/CONTEXT_PACK.md` if the next session needs the new context.
2. Update `docs/core/DECISION_LOG.md` if a real decision was made.
3. Update `docs/core/SOURCE_OF_TRUTH.md` only if the current system view changed.
4. Update `docs/core/PROJECT_CANON.md` if the core project meaning changed or another document created a meaning-level conflict.
5. Update `docs/tasks/TASK_REGISTRY.md` if task boundaries changed.
6. Update `docs/schemas/ARTIFACT_SCHEMAS.md` if an artifact format changed.
7. Update `docs/examples/EXAMPLES_BANK.md` if a useful example was produced.

## Project canon check

Use `docs/core/PROJECT_CANON.md` as the short human sanity-check artifact for the project meaning.

After major architecture, scope, terminology, or artifact changes:

1. Re-read `docs/core/PROJECT_CANON.md`.
2. Check whether it still reflects the project correctly.
3. If it conflicts with another document, resolve the conflict explicitly.
4. Do not let a context pack, transfer pack, task registry, or schema file contradict the canon.

The canon is not a replacement for `SOURCE_OF_TRUTH.md`. It is the compact control version of the project meaning.

## Document ownership

- `docs/core/PROJECT_CANON.md` owns the compressed control version of the project meaning.
- `docs/core/SOURCE_OF_TRUTH.md` owns the detailed current project truth.
- `docs/context/CONTEXT_PACK.md` owns the short startup context for new LLM sessions.
- `AGENTS.md` owns instructions for AI agents working in this repository.
- `docs/core/DECISION_LOG.md` owns durable architecture decisions and reversals.
- `docs/tasks/TASK_REGISTRY.md` owns task areas and work packages.
- `docs/schemas/ARTIFACT_SCHEMAS.md` owns artifact fields, allowed values, and validation rules.
- `docs/examples/EXAMPLES_BANK.md` owns worked examples and test cases.

## When to start a new ChatGPT session

Start a new session when:

- the chat contains too many obsolete alternatives;
- the architecture has changed;
- the model starts returning old terms;
- a working draft has become noisy;
- the task switches from exploration to final packaging.

The new session should begin from `CONTEXT_PACK.md`. For a stronger reset, include `PROJECT_CANON.md` first and then the context pack.

## How to prompt new sessions

Use this pattern:

```text
Below is the current project canon and context pack for HypeLine / HypEnt.
Treat them as the source of truth for this session.
Do not restore old terms or structures that contradict them.

[PASTE PROJECT_CANON.md]
[PASTE CONTEXT_PACK.md]

Current task:
...
```

## Artifact hygiene

Avoid storing raw ChatGPT output without review.

Remove:

- duplicate explanations;
- obsolete hierarchy levels;
- vague quality metrics that cannot be checked;
- claims of automation before a working protocol exists;
- text that hides uncertainty;
- post-hoc exploratory findings presented as confirmed learning.

## Update ownership

A project artifact can be rough, but it must be explicit. Prefer a short honest document over a long polished document with mixed versions.
