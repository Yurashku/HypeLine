# Examples Bank

This file stores worked examples and test cases for the project artifacts. It should grow gradually. A small set of high-quality examples is more useful than many generic examples.

## How to use this file

Each example should show how a raw idea becomes one or more structured artifacts.

Recommended example structure:

```text
Example ID:
Source:
Raw idea:
Intervention Claim:
Metric Pack:
Evidence Note:
Expected ATE Prior:
Pilot Result Pack, if available:
Learning Update, if available:
Notes:
```

## Example 001 — Communication timing change

Status: synthetic placeholder

Raw idea:

Improve communication timing for an existing client segment.

Intervention Claim:

For active clients in a defined segment, change the timing of a product communication from the current schedule to a new schedule. Expected outcome is higher conversion to the target action within a short evaluation horizon. Exact segment, treatment content, and horizon must be specified before scoring.

Metric Pack:

Decision metric: conversion to target action within the chosen horizon.

Proxy outcomes: open rate, click rate, intermediate application start.

Guardrails: unsubscribe rate, complaint rate, contact policy violations, negative effect on adjacent product metrics.

Warnings: short-term engagement proxies may not fully represent long-term business value.

Evidence Note:

Supporting evidence: similar communication changes may influence attention and timing sensitivity.

Counterevidence: effect may be mostly channel noise if offer and audience are unchanged.

Unknowns: segment definition, baseline conversion, historical fatigue, channel constraints.

Expected ATE Prior:

Direction: positive but uncertain.

Rough band: low to medium.

Confidence: low until analogues and baseline metrics are available.

Priority label: hold or candidate depending on business importance and implementation cost.

## Example 002 — Offer change for a preselected segment

Status: synthetic placeholder

Raw idea:

Change the offer for a segment that already has high product propensity.

Intervention Claim:

For a high-propensity segment, expose clients to a modified offer instead of the current offer. Expected outcome is an increase in product acceptance or activation within the selected horizon.

Metric Pack:

Decision metric: incremental product acceptance or activation.

Proxy outcomes: offer view, application start, application completion.

Guardrails: margin, cannibalization, complaints, operational load.

Evidence Note:

Supporting evidence: segment already has high propensity, so offer relevance may be strong.

Counterevidence: uplift can be low if the segment would convert anyway.

Unknowns: whether treatment changes incremental behavior or only shifts timing.

Expected ATE Prior:

Direction: positive but possibly small.

Rough band: unknown to medium.

Confidence: medium only if historical analogues exist.

Priority label: candidate if economics and guardrails are acceptable.

## Backlog of examples to add

- Successful pilot with clear scale decision.
- Insignificant pilot with useful reusable learning.
- Negative pilot with strong guardrail issue.
- Weak pilot where rerun is justified.
- Post-pilot targeting case where uplift analysis is appropriate.
- OPE case with good overlap and acceptable ESS.
- OPE case with poor overlap and unreliable estimate.
- Causal evidence note that lowers confidence rather than raising it.
