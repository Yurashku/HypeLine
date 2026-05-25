# Documentation map

This directory is the durable memory layer of the HypeLine / HypEnt project.

## Core documents

- `core/SOURCE_OF_TRUTH.md` — the current agreed view of the system.
- `core/DECISION_LOG.md` — compact history of important architecture decisions.
- `core/OPERATING_RULES.md` — rules for working with ChatGPT and keeping artifacts clean.

## Working context

- `context/CONTEXT_PACK.md` — the short context block to paste into a fresh ChatGPT session.

## Project decomposition

- `tasks/TASK_REGISTRY.md` — the task registry for internal and external work.
- `schemas/ARTIFACT_SCHEMAS.md` — current artifact schemas used by the system.
- `examples/EXAMPLES_BANK.md` — worked examples and test cases.

## Update rhythm

- After every long ChatGPT session: update the context pack if the next session would need the new state.
- After every meaningful architecture change: update the decision log.
- After every major scope change: update the source of truth and task registry.
- After every useful pilot or hypothesis review: add an example or update an existing one.
