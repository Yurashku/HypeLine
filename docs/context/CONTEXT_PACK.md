# HypeLine / HypEnt — Context Pack

Use this file as the opening context for a new ChatGPT session.

## Project in one paragraph

HypeLine / HypEnt is an intelligent multi-agent system for supporting the product improvement loop. The system helps transform a raw product idea into a structured intervention claim, choose a practical metric pack, gather evidence and analogues, estimate a cautious expected average treatment effect prior for hypothesis ranking, support pilot interpretation, and store reusable learning in ExperimentMemory.

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

## Current principles

- Do not use the `Capability Block` layer in the current structure.
- Prefer concrete tasks that produce reusable artifacts.
- Do not ask the system to forecast the exact future pilot result.
- Use `Expected ATE Prior` for cautious ranking of hypotheses.
- Every uncertain estimate needs confidence, provenance, and caveats.
- Keep uplift, targeting, and OPE as a separate post-pilot branch.
- Do not mix exploratory findings with confirmed experimental learning.

## Core loop artifacts

- `Intervention Claim`
- `Metric Pack`
- `Evidence Note`
- `Expected ATE Prior`
- `Pilot Result Pack`
- `Learning Update`
- `ExperimentMemory Record`

## Extended and post-pilot artifacts

- `Rerun Recommendation`
- `Targeting Policy Pack`
- `OPE Evaluation Pack`
- `Causal Evidence Note`

## First priority tasks

1. ExperimentMemory
2. Intervention Claim
3. Metric Pack
4. Expected ATE Scoring
5. Post-Pilot Learning

These tasks form the first useful loop: idea -> claim -> metrics -> scoring -> pilot result -> learning -> memory.

## Things not to reintroduce without an explicit decision

- Capability Block as a main planning layer.
- Too many abstract quality metrics.
- Full automation before templates and examples exist.
- Exact effect forecasting.
- Automatic rollout decisions.
- Uplift/OPE as the default pre-pilot scoring path.

## Default task format

For any task, describe:

- role in the project;
- why it is needed;
- input;
- output artifact;
- minimal useful result;
- acceptance criteria;
- out of scope;
- examples needed.

## Current repository artifacts

- `docs/core/SOURCE_OF_TRUTH.md`
- `docs/core/DECISION_LOG.md`
- `docs/core/OPERATING_RULES.md`
- `docs/tasks/TASK_REGISTRY.md`
- `docs/schemas/ARTIFACT_SCHEMAS.md`
- `docs/examples/EXAMPLES_BANK.md`
