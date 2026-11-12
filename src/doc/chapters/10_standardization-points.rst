
.. _chapter-standardization-points:

Standardization points
======================

Work on this axis already exists across standards development organisations, and
this clause draws on it. Within ITU-T, SG17 has the security and assurance work
most relevant here; the Focus Group on Trust and Identity for Humans and Agentic
AI has addressed identity transparency and the human-facing axis directly; and
SG13 and SG16 work on AI architecture and human interaction is relevant to the
framing. Outside ITU-T, ISO/IEC JTC 1/SC 42 addresses AI governance and risk,
NIST has published an AI risk management framework, ETSI has work on securing
artificial intelligence, IEEE has standards on autonomous and ethical systems,
and UNESCO has issued guidance on the ethics of AI. For each point below, where
a standard or a draft already covers the subject, it is cited at that point;
where no citation appears, no standard addressing the point directly was
identified in the preparation of this report. Table 3 in 9.13 lists, for each
point, the deliverable type and the possible venue.

This clause collects the elements of the human-facing axis that appear genuinely
standardizable. It is deliberately plural: the area is being addressed
concurrently by standards bodies, industry consortia, national regulators,
clinicians and research groups, and no single organisation frames it. Each point
is therefore stated with more than one plausible venue.

Within ITU-T, the Focus Group on Trust and Identity for Humans and Agentic AI is
working directly on trust and identity for humans and agentic AI, and is a
natural home for several of the points below [b-ITU-T FG-TIDA].

Terminology for the human-facing axis
-------------------------------------

The vocabulary is unsettled - “companion”, “dependence”, “harm” and “safety” are
used in different senses across the instruments. A shared terminology,
distinguishing cumulative relational harm from discrete content harm, is a
precondition for everything else.

A human-impact risk taxonomy
----------------------------

A stable taxonomy of human-facing risks (clause 8) that can be mapped onto
national specifications and onto clinical constructs. This Technical Report
offers a candidate in RSK-P-01 to RSK-P-08.

Guardrail capability requirements
---------------------------------

Assessable requirements for relationship and psychological safety checks,
independent supervisory components, and tiered intervention, expressed so that
they can be tested rather than asserted.

Intervention policy and escalation
----------------------------------

A specification of the graduated response - what is detected, at what
confidence, which action follows, who is accountable and how the action is
recorded - including the escalation route to human support.

Drift measurement extended to user impact
-----------------------------------------

The drift-measurement concept of the system-facing axis, applied to the
interaction trajectory: baseline, deviation, threshold and confidence.

Identity disclosure requirements
--------------------------------

When, how often and in what form a system is required to disclose its non-human
status, with particular attention to moments of high affective engagement.

Evaluation methodology and benchmarks
-------------------------------------

Longitudinal evaluation methods, cohort baselines, and benchmarks that measure
user outcome rather than model output, together with acceptable-use criteria for
the evaluation itself.

Machine-readable representation of psychological risk signals
-------------------------------------------------------------

Detective systems such as SHIELD [b-SHIELD] and EmoGuard demonstrate that
dependence and manipulation patterns can be measured, but the resulting
assessments have no standard representation, so guardrails from different
suppliers cannot interoperate. A standardized risk-signal schema - observed
signal, trajectory window, confidence, recommended intervention - is a concrete
and bounded deliverable.

Cross-session trajectory evaluation and baselines
-------------------------------------------------

The harm of the human-facing axis is cumulative, whereas most evaluation remains
single-session. Standardized methods for establishing a baseline over an
observation window and detecting adverse cross-session drift are therefore
required (clause 9.4).

Human-impact assessment in guardrail conformity
-----------------------------------------------

Guardrail specifications are today framed largely around content safety and
system security. Incorporating the validated psychological dimensions -
dependence, boundary, manipulation, isolation - as assessable capability
requirements, and mapping them to emerging national specifications such as T/ISC
0125-2026 [b-T-ISC-0125-2026], is a feasible and largely unoccupied direction.

Identity transparency in affective interaction
----------------------------------------------

Requirements for agent identity in interaction already exist at national level
[b-T-ISC-0123-2026], but an obligation to disclose non-human status at moments
of strong affective engagement is not yet reflected in the international
framework.

A shared hook into the system-facing control plane
--------------------------------------------------

A shared runtime substrate is needed for policy attachment points, logging and
an intervention channel. Standards emerging for agent control hooks and
control-path layering [b-OWASP-ACS] [b-IETF-AOCL] provide a natural carrier for
this.

Consolidated standardization points
-----------------------------------

The standardization points and the gaps they address are listed in Table 3.

.. list-table:: Table 3 – Standardization points and the gaps they address
    :header-rows: 1
    :widths: 13 23 8 20

    * - Standardization point
      - What is missing today
      - Deliverable type
      - Possible venue
    * - Terminology for the human-facing axis
      - A shared vocabulary distinguishing cumulative relational harm
      - Technical Report clause
      - ITU-T SG17, ISO/IEC JTC 1/SC 42
    * - Human-impact risk taxonomy
      - A stable taxonomy mappable to national and clinical constructs
      - Technical Report
      - ITU-T SG17, WHO-adjacent bodies
    * - Guardrail capability requirements
      - Assessable requirements for supervisory and relational checks
      - Recommendation
      - ITU-T SG17
    * - Intervention policy and escalation
      - A specified graduated response with accountability
      - Recommendation
      - ITU-T SG17, national regulators
    * - Drift measurement for user impact
      - Baseline/deviation/threshold defined over interaction trajectories
      - Technical Report
      - ITU-T SG17, research consortia
    * - Identity disclosure requirements
      - When and how non-human status is disclosed
      - Recommendation
      - ITU-T SG17, national bodies
    * - Evaluation methodology and benchmarks
      - Longitudinal, outcome-based benchmarks
      - Technical Report
      - ITU-T SG17, MLCommons, academia
    * - Psychological risk-signal schema
      - A standard representation of trajectory risk signals
      - Technical Report
      - ITU-T SG17, health bodies
    * - Shared control-plane hook
      - One substrate for human- and system-facing guardrails
      - Specification
      - OWASP [b-OWASP-ACS] (ACS), IETF (AOCL [b-IETF-AOCL]), ITU-T
