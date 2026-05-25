# Task Registry

This registry lists the main HypeLine / HypEnt task areas. It is not a full backlog. It describes work packages that can be reasoned about, assigned, researched, or prototyped.

## 1. ExperimentMemory

Role: foundation of the system.

Why needed: past pilots should become reusable system memory instead of remaining scattered across presentations, notes, and informal conclusions.

Expected artifact: `ExperimentMemory Record` and reusable learning card.

Minimum useful result:

- human-readable record schema;
- 10-20 filled examples;
- required fields;
- confidence and provenance rules;
- simple similarity logic for finding relevant past cases.

Acceptance:

- a historical pilot can be encoded without losing key meaning;
- a new hypothesis can retrieve similar cases or explicitly state that no analogue exists;
- an expert can understand the record without extra explanation;
- the record can support scoring and metric selection.

Out of scope:

- automatic ingestion of all historical documents;
- full knowledge-management platform;
- workflow orchestration.

## 2. Post-Pilot Learning

Role: practical early task that gives value even before complex hypothesis generation.

Why needed: a pilot should end with structured learning, not only a report.

Expected artifacts: `Pilot Result Pack` and `Learning Update`.

Minimum useful result:

- result pack template;
- learning update template;
- examples for successful, insignificant, weak, and violated pilots;
- rules for storing results in ExperimentMemory.

Acceptance:

- fact, interpretation, limitations, and reusable learning are separated;
- exploratory findings are not presented as confirmed results;
- the learning update can be stored without extra restructuring.

Out of scope:

- full automated post-pilot discovery;
- replacing analysts in ambiguous interpretation;
- complex uplift/OPE scenarios.

## 3. Intervention Claim

Role: central pre-pilot task.

Why needed: raw ideas are often too vague for metric selection and scoring.

Expected artifact: `Intervention Claim`.

Minimum useful result:

- claim schema;
- good and bad examples;
- validation rules;
- clarifying questions for turning raw ideas into claims.

Acceptance:

- a raw idea can become a claim usable by MetricDesigner and scoring;
- missing fields are explicit;
- an expert can quickly see what is underspecified.

Out of scope:

- generating all new hypotheses from scratch;
- automatically choosing the best hypothesis;
- full product ontology.

## 4. Metric Pack

Role: practical metric selection task.

Why needed: each hypothesis needs a small coherent set of decision metric, proxies, secondary metrics, guardrails, and horizon.

Expected artifact: `Metric Pack`.

Minimum useful result:

- metric pack template;
- typology of decision metrics, proxy outcomes, secondary metrics, and guardrails;
- examples for several pilot types;
- pre-launch warnings for measurement risks.

Acceptance:

- decision metric and guardrails are clearly separated;
- experts can accept the pack or identify missing questions;
- the pack can be used in pilot design and post-pilot interpretation.

Out of scope:

- universal power calculator;
- automatic extraction from data marts;
- optimization for a specific A/B platform.

## 5. Expected ATE Scoring

Role: main hypothesis ranking task.

Why needed: the system needs a cautious prior for expected average effect, not exact future prediction.

Expected artifact: `Expected ATE Prior`.

Minimum useful result:

- format with direction, rough band, confidence, basis, caveats;
- source rules for past pilots, expert judgment, causal evidence, and analogues;
- ordinal scoring rules;
- examples for strong, weak, and unknown hypotheses.

Acceptance:

- no exact numbers are produced without basis;
- every estimate has provenance and caveats;
- an expert can understand and challenge the rank;
- the output helps build a shortlist rather than claiming proof.

Out of scope:

- individual uplift / CATE;
- exact pilot forecast;
- automatic launch decision.

## 6. Evidence and Analogues

Role: support for Intervention Claim and Expected ATE Scoring.

Why needed: the system must record both supporting evidence and counterevidence.

Expected artifact: `Evidence Note`.

Minimum useful result:

- evidence note template;
- evidence/counterevidence/assumptions/unknowns distinction;
- analogue similarity rules;
- examples for several claims.

Acceptance:

- evidence does not silently become proof;
- analogue similarity is explained;
- weak evidence lowers confidence explicitly.

Out of scope:

- scientific literature review for every hypothesis;
- automatic causal discovery;
- proof of causal effect before a pilot.

## 7. Rerun Logic

Role: disciplined post-pilot decision support.

Why needed: weak or insignificant pilots should not automatically be treated as failure, but post-hoc analysis should not be overclaimed.

Expected artifact: `Rerun Recommendation`.

Minimum useful result:

- decision rules for scale, rerun, stop, and exploratory only;
- scenarios for weak design, segment signal, guardrail conflict, and inconclusive result;
- rules separating old result from new confirmatory design.

Acceptance:

- exploratory findings are clearly marked;
- rerun conditions are explicit;
- the recommendation can become a learning record with correct confidence.

Out of scope:

- full A/B design automation;
- full financial rollout calculation;
- production targeting pipeline.

## 8. Targeting / Uplift / OPE

Role: separate post-pilot research branch.

Why needed: after a pilot, the team may ask whether an effect exists only for part of the audience or whether a targeting policy can be evaluated offline.

Expected artifacts: `Targeting Policy Pack` and `OPE Evaluation Pack`.

Minimum useful result:

- applicability protocol;
- data requirements;
- basic policy variants;
- OPE diagnostics: overlap, ESS, weights, clipping, uncertainty;
- examples for applicable, doubtful, and invalid cases.

Acceptance:

- data suitability is checked before conclusions;
- OPE output includes diagnostics, not only effect estimates;
- weak overlap/ESS cases are marked unreliable;
- result supports confirmatory pilot design, not automatic rollout.

Out of scope:

- replacing A/B tests;
- production targeting system;
- automatic rollout.

## 9. Causal Evidence Gateway

Role: integration layer for external causal tools.

Why needed: causal signals can support evidence and scoring but should not be treated as proven experimental effects.

Expected artifact: `Causal Evidence Note`.

Minimum useful result:

- note schema;
- reliability marking rules;
- examples of correct and incorrect usage;
- rules for how signals affect confidence.

Acceptance:

- every causal signal has source, assumptions, and confidence;
- it can raise or lower hypothesis confidence;
- it does not become a claim that the effect is proven without an experiment.

Out of scope:

- causal discovery system development;
- graph model training;
- automatic proof of causality.
