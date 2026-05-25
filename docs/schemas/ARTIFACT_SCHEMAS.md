# Artifact Schemas

This file defines the current working schemas for the main HypeLine / HypEnt artifacts. Schemas should stay practical and easy to fill manually before automation is built.

## Intervention Claim

Purpose: convert a raw product idea into a testable statement.

Fields:

- `claim_id`
- `raw_idea`
- `segment`
- `treatment`
- `expected_outcome`
- `direction`
- `horizon`
- `constraints`
- `unknowns`
- `owner_or_source`
- `status`

Validation:

- segment, treatment, outcome, horizon, and direction should be explicit;
- unknown fields must be marked as unknown rather than hidden;
- vague intention is not enough for scoring.

## Metric Pack

Purpose: define how the claim should be measured in a pilot.

Fields:

- `claim_id`
- `decision_metric`
- `proxy_outcomes`
- `secondary_metrics`
- `guardrails`
- `measurement_horizon`
- `expected_lag`
- `variance_or_sensitivity_notes`
- `data_availability`
- `pre_launch_warnings`

Validation:

- decision metric and guardrails must be separated;
- long lag, high variance, weak sensitivity, and metric conflicts should be explicit;
- metric pack must be usable in post-pilot interpretation.

## Evidence Note

Purpose: collect arguments for and against a hypothesis before scoring.

Fields:

- `claim_id`
- `supporting_evidence`
- `counterevidence`
- `analogues`
- `analogue_similarity_notes`
- `assumptions`
- `unknowns`
- `evidence_confidence`
- `provenance`

Validation:

- counterevidence should be present or explicitly marked absent;
- analogue similarity should be explained by product, segment, treatment, metric, horizon, and result;
- evidence must not be represented as experimental proof unless it is experimental proof.

## Expected ATE Prior

Purpose: provide a cautious prior for hypothesis ranking.

Fields:

- `claim_id`
- `outcome`
- `horizon`
- `direction`
- `rough_band`
- `confidence`
- `basis`
- `caveats`
- `business_importance`
- `feasibility`
- `risk`
- `priority_label`

Allowed `priority_label` values:

- `reject`
- `hold`
- `candidate`
- `strong_candidate`

Validation:

- do not produce precise estimates without a real basis;
- the estimate should be challengeable by an expert;
- low evidence should lower confidence even when the idea sounds plausible.

## Pilot Result Pack

Purpose: store factual pilot result separately from interpretation.

Fields:

- `pilot_id`
- `claim_id`
- `design_summary`
- `population`
- `treatment_group`
- `control_group`
- `metrics`
- `effect_estimates`
- `confidence_intervals`
- `decision_statistics`
- `guardrail_results`
- `deviations`
- `data_quality_notes`
- `result_status`

Allowed `result_status` values:

- `scale`
- `rerun`
- `stop`
- `inconclusive`
- `exploratory_only`

Validation:

- deviations and data quality issues must be visible;
- guardrails must not be hidden behind the main metric;
- result and interpretation should be separable.

## Learning Update

Purpose: define what the system should remember after a pilot.

Fields:

- `pilot_id`
- `learning_statement`
- `reusable_conditions`
- `limitations`
- `confidence`
- `provenance`
- `recommended_next_action`
- `experiment_memory_update`

Validation:

- confirmed learning and exploratory observations must be separated;
- limitations should travel with the learning;
- the update must be ready to store in ExperimentMemory.

## ExperimentMemory Record

Purpose: durable memory unit for past pilots and reusable learning.

Fields:

- `record_id`
- `pilot_id`
- `business_context`
- `product_area`
- `segment`
- `treatment`
- `metrics`
- `design`
- `result_summary`
- `decision`
- `learning`
- `confidence`
- `provenance`
- `limitations`
- `similarity_keys`

Validation:

- record should support retrieval by segment, treatment, metric, product, and result;
- unsuccessful, insignificant, negative, and weak results must be stored, not only successes;
- expert should understand the record without the original slide deck.

## Rerun Recommendation

Purpose: decide what to do after weak or ambiguous pilot evidence.

Fields:

- `pilot_id`
- `observed_result`
- `ambiguity_reason`
- `exploratory_findings`
- `confirmatory_question`
- `recommended_action`
- `new_design_requirements`
- `anti_p_hacking_notes`
- `confidence`

Validation:

- old result and proposed new confirmatory pilot must be separated;
- post-hoc findings should not be labeled as confirmed;
- conditions for rerun should be explicit.

## Targeting Policy Pack

Purpose: describe a possible post-pilot targeting policy.

Fields:

- `policy_id`
- `source_pilot_id`
- `target_population`
- `features_used`
- `policy_rule_or_model`
- `expected_benefit_logic`
- `leakage_checks`
- `business_constraints`
- `validation_plan`

Validation:

- policy must be grounded in post-pilot analysis;
- leakage checks must be explicit;
- result should usually motivate a confirmatory pilot, not direct rollout.

## OPE Evaluation Pack

Purpose: evaluate a candidate policy using off-policy evidence when applicable.

Fields:

- `policy_id`
- `logging_policy_description`
- `candidate_policy_description`
- `propensity_source`
- `overlap_diagnostics`
- `ess`
- `weight_distribution`
- `clipping_notes`
- `effect_estimate`
- `uncertainty`
- `reliability_label`
- `stop_factors`

Validation:

- diagnostics are mandatory;
- weak overlap or ESS should lower reliability;
- OPE must not be presented as a replacement for confirmatory A/B testing.

## Causal Evidence Note

Purpose: safely include causal signals from external tools.

Fields:

- `claim_id`
- `causal_artifact_type`
- `source`
- `graph_fragment_or_adjustment_set`
- `assumptions`
- `robustness_notes`
- `confidence`
- `effect_on_expected_ATE_prior`
- `overclaiming_risks`

Validation:

- assumptions and source must be visible;
- causal signal may affect confidence but should not become a proof of effect without experiment;
- uncertainty must remain attached to the signal.
