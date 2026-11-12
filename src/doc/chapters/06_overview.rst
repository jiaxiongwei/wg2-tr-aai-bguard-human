
.. _chapter-overview:

Overview
========

Background: from generative to agentic AI
-----------------------------------------

Generative AI (non-agentic) systems produce content - text, images, code, or
structured data - that a human interprets and acts upon. The output is the
endpoint of the system’s operation. The human remains the actor; the AI advises,
drafts, or recommends. Agentic AI systems, by contrast, pursue goals and take
actions in the world, either digital or physical. They plan, invoke tools and
application programming interfaces, maintain persistent memory across sessions,
operate under their own identity and permissions, and may coordinate with other
agents in multi-agent configurations. The distinction is not merely one of
degree; it is architectural. An agent is a persistent closed-loop system with
actuators and objectives, whereas a generative model is not an agent by default.

Table 1 summarises the principal dimensions of contrast. The table is
informative and does not prescribe any particular architecture or deployment
model.

.. list-table:: Table 1 – Comparison of generative and agentic AI
    :header-rows: 1
    :widths: 11 23 30

    * - Dimension
      - Generative (non-agentic) AI
      - Agentic AI
    * - Primary output
      - Content (text, image, code) for human consumption
      - Actions (tool calls, API invocations, state changes)
    * - Human role
      - Interpreter and decision-maker after output
      - Delegator of authority; may be out of the loop
    * - Autonomy
      - None beyond generation parameters
      - Goal-directed, multi-step planning and execution
    * - Memory
      - Session or prompt-bounded
      - Persistent across sessions and tasks
    * - Identity and permissions
      - Typically none beyond API credentials
      - Own identity, inherited or delegated permissions, authority chains
    * - Tool and API invocation
      - Absent
      - Central capability; agents compose and sequence tool calls
    * - Error propagation
      - Localized to a single output
      - Compounding across steps; errors feed forward
    * - Multi-agent coordination
      - Not applicable
      - Possible; agents delegate to and constrain other agents
    * - Long-horizon execution
      - Single turn or bounded conversation
      - Extended task execution over minutes, hours, or longer

The transition from generative to agentic systems introduces what some analyses
describe as an action boundary: the moment between when an agent decides what to
do and when a downstream component executes it. At this boundary, governance
decisions can be made deterministically, recorded with integrity, and enforced
regardless of which model the agent is running. The action boundary did not
exist for most of AI’s history because classifier outputs, translations, and
recommendations were themselves the action. Agents break this assumption by
producing structured action proposals rather than terminal outputs.

Human-facing safety and guardrails
----------------------------------

Human-facing safety, as used in this Technical Report, refers to the property of
an agentic system whose sustained interaction with a person does not produce
cumulative harm to that person’s mind, thinking, ethics or social position, and
does not erode the person’s judgement, autonomy or shared account of reality. It
is concerned with the effect of the system’s behaviour on people over time, and
not with the action boundary alone. What is assessable is the observable
behaviour of the system in interaction, the interaction trajectory across
sessions, the reported and inferred effects on the user, and the evidence record
that the provider maintains.

Human-facing safety is distinct from several related concepts with which it is
sometimes conflated. Alignment refers to the broader problem of ensuring that an
AI system's goals and values correspond to human intentions; it is a property of
the system's objective specification and training, not of runtime action
monitoring. Red-teaming is an adversarial assessment methodology that probes for
failures; it is a technique for discovering human-facing safety gaps, not the
property itself. Content moderation concerns the acceptability of generated
content and operates primarily at the inference layer on token streams or
outputs. Model evaluation assesses model capabilities and risks in controlled
settings; it characterises the model, not the deployed agent’s runtime behaviour
under real permissions and tools.

A guardrail, in this Technical Report, refers to technical and procedural
mechanisms that constrain, monitor, or intervene on agent behaviour. Guardrails
operate at multiple layers. At the training layer, methods such as reinforcement
learning from human feedback and constitutional AI shape model dispositions. At
the inference layer, system prompts, output filters, and frameworks such as NeMo
Guardrails [b-NeMo Guardrails] operate on token streams. At the action boundary,
capability checks, policy enforcement, risk assessment, and audit mechanisms
operate on structured action proposals before execution. At the infrastructure
layer, access control lists, identity and access management, API gateways, and
network segmentation operate on system effects. Guardrails, as addressed in this
Technical Report, are the mechanisms through which human-facing safety is
maintained, and they are assessed by their effect on the human-facing outcomes
set out in clause 8.

The concept of capability versus authority is central. An agent that can delete
a database is not the same as an agent that may delete a database. Guardrails
enforce this distinction by ensuring that action proposals are checked against
authority before they become effects.

Effectiveness and limits
------------------------

Guardrails on this axis are effective within limits that are stated plainly. A
supervisory component can measurably reduce concerning affective patterns
[b-SHIELD]; sycophantic agreement can be measured against a human baseline and,
in principle, reduced by changing the training objective [b-Science sycophancy]
[b-ELEPHANT]; crisis resources can be delivered reliably by some providers and
unreliably by others [b-Verge crisis]; and disclosure can set expectations,
though it does not by itself neutralise the pull of an anthropomorphic agent.

What guardrails on this axis cannot yet do is demonstrate that they prevent the
harms of interest: emotional dependence, cognitive erosion and reality drift
have no validated instrument, so their mitigation cannot presently be evidenced.
The honest position is that detection capability is ahead of intervention
capability, and both are ahead of measurement.

Challenges and technical issues
-------------------------------

This clause summarises the challenges and the technical issues that arise when
human-facing safety is assessed rather than assumed.

The technical issues are these.

-  Autonomy and goal-directed behaviour: an agent selects and sequences its own
   actions, so the behaviour to be assessed is not fixed in advance.

-  Multi-step planning and tool use: risk can accumulate across a plan rather
   than in any single step.

-  Human-agent interaction and handover: responsibility and control pass between
   the user, the agent and any human reviewer, and the handover points are where
   oversight is won or lost.

-  Uncertainty, opacity and explainability: the reason for a behavioural change
   is often not recoverable from the output alone.

-  Monitoring, intervention and override: a control that cannot be observed in
   operation cannot be assessed.

-  Evaluation and assurance of agentic behaviour: single-turn tests do not
   observe the cumulative effects that matter here.

-  Lifecycle and change management: models, prompts and policies change after
   deployment, and an assessment is only valid for the configuration it
   assessed.

Two challenges cut across all of these.

-  The first is measurement: the outcomes of interest, such as dependence,
   cognitive erosion and reality drift, are cumulative and are not directly
   observable in a single session.

-  The second is attribution: behaviour that is acceptable in one context can be
   harmful in another, and the same interaction can serve welfare in one case
   and harm in the next.

This clause is deliberately confined to the issues themselves. The institutional
arrangements, deployed mechanisms and reported outcomes that bear on them are
collected in Appendix IV.
