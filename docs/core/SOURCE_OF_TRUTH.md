# HypeLine / HypEnt — Source of Truth

This document is the current source of truth for the project. It should be concise, explicit, and stricter than ordinary working notes. Old chat history is not authoritative if it contradicts this file.

## Project purpose

HypeLine / HypEnt is an intelligent multi-agent system for supporting the product improvement cycle.

The system should help transform a raw product idea into a structured intervention, select a practical metric set, collect evidence and analogues, estimate a cautious expected average treatment effect prior, support pilot design, interpret pilot results, and preserve reusable learning in project memory.

## Current core loop

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

## Current architectural principles

1. The repository stores durable project artifacts, not the full chat history.
2. The main decomposition unit is a concrete module/task with a clear output artifact.
3. The project should avoid unnecessary hierarchy. The `Capability Block` layer is intentionally not used in the current structure.
4. Early versions should prefer templates, protocols, examples, and expert review over premature full automation.
5. Scoring should estimate a cautious expected average treatment effect prior, not pretend to predict the exact future pilot result.
6. Every preliminary estimate must include confidence, provenance, caveats, and boundaries of use.
7. Exploratory findings must not be mixed with confirmed experimental learning.

## Core artifacts

- `Intervention Claim` — a raw idea converted into a testable intervention statement.
- `Metric Pack` — decision metric, proxy outcomes, secondary metrics, guardrails, horizon, and measurement warnings.
- `Evidence Note` — evidence, counterevidence, analogues, assumptions, and unknowns.
- `Expected ATE Prior` — cautious direction/band/confidence estimate for expected average treatment effect.
- `Pilot Result Pack` — factual pilot result separated from interpretation and deviations.
- `Learning Update` — what the system should remember after a pilot.
- `ExperimentMemory Record` — durable memory unit for past pilots and reusable learning.

## Main modules / task areas

1. ExperimentMemory — unified memory of pilots and reusable learning.
2. Post-Pilot Learning — standard interpretation and learning extraction after a pilot.
3. Intervention Claim — transformation of raw ideas into testable claims.
4. Metric Pack — practical metric selection for pilots.
5. Expected ATE Scoring — cautious prior for ranking hypotheses.
6. Evidence and Analogues — structured arguments for and against a hypothesis.
7. Rerun Logic — disciplined handling of weak, inconclusive, or ambiguous pilots.
8. Targeting / Uplift / OPE — separate post-pilot research branch with strict applicability limits.
9. Causal Evidence Gateway — safe integration of causal signals without overclaiming.

## First priority scope

The first useful project nucleus is:

```text
ExperimentMemory
+ Intervention Claim
+ Metric Pack
+ Expected ATE Scoring
+ Post-Pilot Learning
```

Together these close the main loop: idea, claim, metrics, scoring, pilot result, learning, memory.

## Explicit non-goals for the early version

- No fully autonomous product decision making.
- No exact forecast of future pilot outcomes.
- No automatic proof of causal effect before an experiment.
- No replacement of analysts in ambiguous interpretation.
- No production-grade knowledge platform in the first iteration.
- No automatic rollout decision without human review.

## Naming notes

`HypeLine` and `HypEnt` are currently treated as closely related project names. If naming becomes important, the decision should be recorded in `DECISION_LOG.md` and reflected here.
