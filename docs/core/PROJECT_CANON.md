# HypeLine / HypEnt - Project Canon

This document is the short control version of the project meaning. Read it when you need to check whether the repository still reflects the main ideas correctly.

It is not a replacement for `SOURCE_OF_TRUTH.md`. It is a compact sanity-check artifact inherited from the current source documents.

## Project in one sentence

HypeLine / HypEnt is an intelligent multi-agent decision-support system that helps a product team turn raw product ideas into testable hypotheses, pilot metrics, cautious effect priors, experiment learning, and reusable project memory.

## Problem we solve

Product improvement work often loses structure across long chats, scattered notes, reports, and changing assumptions. Old terms return, new decisions mix with obsolete ones, and experimental learning becomes hard to reuse.

The project solves this by making the repository the durable memory layer. ChatGPT sessions are working sessions; repository artifacts are the controlled project state.

## What the system is

The system is a disciplined artifact workflow around product hypotheses and experiments.

It should help the team:

- convert a raw idea into a testable `Intervention Claim`;
- choose a practical `Metric Pack`;
- collect structured evidence, counterevidence, analogues, assumptions, and unknowns;
- estimate a cautious `Expected ATE Prior` for hypothesis ranking;
- separate pilot facts from interpretation;
- turn pilot results into reusable learning;
- store that learning in `ExperimentMemory` for future decisions.

## What the system is not

The system is not a magic product decision maker.

It must not:

- make fully autonomous product decisions;
- forecast the exact future pilot result;
- claim causal proof before an experiment;
- replace expert review in ambiguous interpretation;
- decide automatic rollout without human review;
- turn exploratory post-hoc findings into confirmed learning.

## Core loop

```text
raw product idea
  -> Intervention Claim
  -> Metric Pack
  -> Evidence Note
  -> Expected ATE Prior
  -> pilot / experiment
  -> Pilot Result Pack
  -> Learning Update
  -> ExperimentMemory Record
```

## Core artifacts

- `Intervention Claim` - a raw idea converted into a testable intervention statement.
- `Metric Pack` - decision metric, proxy outcomes, secondary metrics, guardrails, horizon, and measurement warnings.
- `Evidence Note` - evidence, counterevidence, analogues, assumptions, and unknowns.
- `Expected ATE Prior` - cautious direction, rough band, confidence, basis, and caveats for expected average treatment effect.
- `Pilot Result Pack` - factual pilot result separated from interpretation and deviations.
- `Learning Update` - what the system should remember after a pilot.
- `ExperimentMemory Record` - durable memory unit for past pilots and reusable learning.

Extended and post-pilot artifacts exist, but they are not required for the first core loop unless the relevant branch is active: `Rerun Recommendation`, `Targeting Policy Pack`, `OPE Evaluation Pack`, and `Causal Evidence Note`.

## First POC boundary

The first useful POC is not a production multi-agent platform. It is the minimum artifact workflow that closes the first loop:

```text
ExperimentMemory
+ Intervention Claim
+ Metric Pack
+ Expected ATE Scoring
+ Post-Pilot Learning
```

The POC should prove that a team can move from idea to structured claim, metrics, cautious scoring, pilot interpretation, learning, and memory without losing provenance or mixing exploratory findings with confirmed learning.

## Accepted architecture decisions

- D001: Durable project state lives in repository artifacts, not raw chat history.
- D002: The `Capability Block` layer is not used in current planning.
- D003: Broad effect forecasting is replaced with cautious `Expected ATE Prior`.
- D004: Targeting, uplift, HTE, and OPE stay in a separate post-pilot branch.
- D005: Early quality checks use worked cases, expert acceptance, and downstream usefulness before heavy benchmarks.

## Non-negotiable constraints

- Do not reintroduce `Capability Block` without a new explicit decision.
- Do not turn `Expected ATE Prior` into an exact forecast.
- Do not treat OPE, uplift, or targeting as the default pre-pilot scoring path.
- Do not mix exploratory findings with confirmed experimental learning.
- Do not add vague quality metrics that cannot be checked.
- Do not store important project decisions only in chat.

## Current open questions

- Final naming: whether `HypeLine`, `HypEnt`, or another name becomes the public project name.
- POC form: whether the first implementation is a manual template workflow, a lightweight local tool, or an agent-assisted workflow.
- Data format: whether working artifacts remain Markdown-first or gain structured JSON/YAML forms for automation.
- ExperimentMemory retrieval: what simple similarity logic is sufficient for the first usable version.

## Inherited source documents

This canon inherits from:

- `docs/core/SOURCE_OF_TRUTH.md`
- `docs/core/DECISION_LOG.md`
- `docs/core/OPERATING_RULES.md`
- `docs/context/CONTEXT_PACK.md`
- `docs/tasks/TASK_REGISTRY.md`
- `docs/schemas/ARTIFACT_SCHEMAS.md`
- `docs/examples/EXAMPLES_BANK.md`

If this canon conflicts with a source document, resolve the conflict explicitly. Do not let contradictory project meanings coexist.
