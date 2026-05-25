# HypeLine / HypEnt

HypeLine / HypEnt is a working repository for designing an intelligent multi-agent system that supports the product improvement loop: from a raw product idea to a testable intervention, pilot metrics, hypothesis scoring, experiment learning, and reusable project memory.

The repository is organized around project artifacts, not around chat history. ChatGPT sessions are used as working sessions; durable project state must be stored in versioned Markdown files.

## Current operating loop

```text
raw idea
  -> Intervention Claim
  -> Metric Pack
  -> Evidence Note
  -> Expected ATE Prior
  -> pilot / experiment
  -> Pilot Result Pack
  -> Learning Update
  -> ExperimentMemory Record
```

The project intentionally avoids a separate `Capability Block` layer in the main task structure. For current planning, the useful unit is a concrete module/task that produces a reusable artifact.

## Repository map

```text
docs/
  README.md                         Navigation for documentation
  core/
    SOURCE_OF_TRUTH.md              Current project truth
    DECISION_LOG.md                 Important decisions and reversals
    OPERATING_RULES.md              How to work with ChatGPT and project artifacts
  context/
    CONTEXT_PACK.md                 Short context to paste into new ChatGPT sessions
  tasks/
    TASK_REGISTRY.md                Task list and externalizable work packages
  schemas/
    ARTIFACT_SCHEMAS.md             Schemas for claims, metrics, priors, results, learning records
  examples/
    EXAMPLES_BANK.md                Small bank of worked examples and test cases
```

## How to use this repository

1. Start with `docs/context/CONTEXT_PACK.md` before opening a new long ChatGPT session.
2. Update `docs/core/DECISION_LOG.md` after each significant architecture decision.
3. Update `docs/core/SOURCE_OF_TRUTH.md` only when the current system view changes.
4. Add real or synthetic examples to `docs/examples/EXAMPLES_BANK.md` after each useful case review.
5. Treat ChatGPT output as a draft until the durable artifact is committed here.

## Status

This repository currently contains the operating documentation layer for the project. Implementation code and agent prototypes can be added later without mixing them with the project memory artifacts.
