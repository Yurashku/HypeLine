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
4. Update `docs/tasks/TASK_REGISTRY.md` if task boundaries changed.
5. Update `docs/schemas/ARTIFACT_SCHEMAS.md` if an artifact format changed.
6. Update `docs/examples/EXAMPLES_BANK.md` if a useful example was produced.

## When to start a new ChatGPT session

Start a new session when:

- the chat contains too many obsolete alternatives;
- the architecture has changed;
- the model starts returning old terms;
- a working draft has become noisy;
- the task switches from exploration to final packaging.

The new session should begin from `CONTEXT_PACK.md`.

## How to prompt new sessions

Use this pattern:

```text
Below is the current context pack for HypeLine / HypEnt.
Treat it as the source of truth for this session.
Do not restore old terms or structures that contradict it.

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
