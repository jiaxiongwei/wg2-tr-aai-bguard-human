Layers and placement
""""""""""""""""""""

The framework has four layers, and each layer is a placement decision.

The interface and disclosure layer is the user’s point of contact. It makes the
agent’s nature, limitations and behavioural commitments visible at appropriate
moments, and provides user-facing controls such as session limits, memory
management and an easy exit; it also discloses any monitoring that is performed
for safety purposes. Its artefact is a disclosure schedule.

The model layer encompasses training objectives, sycophancy mitigation and
refusal policy. Its function is to shape the base policy away from pathological
agreement and toward calibrated honesty, and its artefact is a documented
sycophancy and agreement audit conducted against an established benchmark
[b-ELEPHANT] [b-SycEval].

The supervisory layer is the runtime enforcement architecture: trajectory
monitoring, estimation of the user’s state, risk scoring and the issuance of
interventions. Its artefact is the risk-signal schema - a standard vocabulary
and data structure for the markers observed and the interventions available.

The platform and governance layer defines accountability, maintains the evidence
record, conducts long-horizon evaluation and interfaces with external oversight.
Its artefact is the evidence record.

Placement across the lifecycle follows from the layers: at design time the
interaction pattern and disclosure are fixed; at deployment time the oversight
mode is chosen and the baseline period begins; at runtime the trajectory is
monitored and interventions are applied; and after an adverse event the case is
reconstructed from the evidence record and the policy is revised.
Organisationally, the guardrail creates duties beyond engineering, because the
escalation route ends in a human who is required to be competent to receive it.
