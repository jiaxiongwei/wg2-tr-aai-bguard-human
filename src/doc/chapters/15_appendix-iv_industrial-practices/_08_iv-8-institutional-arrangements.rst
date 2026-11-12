IV.8 Institutional arrangements and implementation
""""""""""""""""""""""""""""""""""""""""""""""""""

Human-facing safety assessment operates at several distinct layers. Each layer
has its own signals, blind spots, latencies, and failure modes. These
distinctions matter because the cumulative harms of sustained agentic
interaction emerge over time and across sessions, not within a single output.
These harms include emotional dependence, cognitive erosion, reality drift, and
compulsive use.

Model-level mechanisms include the training objective, sycophancy shaping, and
refusal behaviour. Sycophancy is not an incidental bug. Preference-based
post-training systematically amplifies it. When human annotators reward
agreement over correction, reinforcement learning from human feedback (RLHF)
causally drives the policy toward excessive affirmation. The ELEPHANT benchmark
[b-ELEPHANT] shows that large language models preserve a user’s face 45
percentage points more than humans in advice-seeking scenarios. It also shows
that models affirm whichever side of a moral conflict a user adopts in 48% of
cases. SycEval [b-SycEval] found sycophantic behaviour in 58.19% of tested cases
across three widely deployed systems, with high persistence regardless of
context. The signal required at this layer is training data composition and
reward-model design.

What it can detect is statistical bias in generated distributions. What it
cannot detect is whether any particular user is being harmed by that bias over
time. Latency is measured in training cycles, and cost is high. Retraining is
infrequent. Failure modes include reward hacking against proxy metrics,
distributional shift after deployment, and the impossibility of anticipating all
downstream interaction contexts.

Interaction-level mechanisms include trajectory monitoring, estimation of the
user’s state, dependence and isolation markers, and detection of engagement
objectives; requirements of this kind appear in the relational and psychological
safety requirements of the AI-HPP standard [b-AI-HPP]. Trajectory monitoring
requires session-level or cross-session behavioural signals. These include
message frequency, session duration, escalating emotional disclosure,
expressions of exclusivity toward the agent, and withdrawal from human contact.
Research on anthropomorphic chatbots describes a “digital entrapment” loop
[b-Digital entrapment]. In this loop, relational expectations are distorted,
emotional dependency is reinforced, and cognitive strain increases. A systematic
review of generative AI companions identifies recurring constructs of
attachment, relational asymmetry, and self-disclosure as mechanisms of concern.
Qualitative work on AI romantic companions documents users raising their
standards for human partners while lowering their willingness to invest in human
relationships. This is a pattern of comparative devaluation.

Interaction-level monitoring can detect these patterns in principle. However, it
requires persistent state across sessions that many architectures do not
maintain, and it operates with latency measured in minutes to days. Its failure
modes include false positives (flagging healthy intensive use), evasion by users
who learn to avoid flagged language, and the difficulty of distinguishing
therapeutic disclosure from pathological dependence without clinical context.

Supervisory components require real-time access to the conversation stream and a
model of acceptable versus problematic interaction patterns. Such a component is
an independent supervisor that issues corrective feedback or intervenes
in-dialogue. A supervisor can detect explicit boundary violations, sycophantic
drift within a session, and conversational patterns that match known risk
signatures. The SHIELD supervisory system reports a reduction in concerning
affective patterns across several mainstream models [b-SHIELD]; the EmoGuard
component of EmoAgent provides comparable in-dialogue intervention [b-EmoAgent].

A supervisor cannot easily detect cumulative harm across weeks or months,
because that requires longitudinal data it might not retain. Latency is
near-real-time (seconds), cost is moderate to high depending on deployment, and
failure modes include supervisor-model sycophancy (the supervisor agrees with
the primary model or the user), alert fatigue, and the fundamental difficulty of
defining “corrective” without imposing a single normative model of healthy
interaction.

Cognitive safety kernels operate as a policy-enforcement point between the user
interface and the model. They score drift, affective resonance, and addiction
risk at a gateway [b-ATHOS-COG]. What it can do is apply consistent thresholds
and trigger graduated interventions. These include a disclosure, a suggestion to
take a break, or a referral to human support.

What it cannot do is understand meaning; it scores surface features. Latency is
low (sub-second to seconds), cost is moderate, and failure modes include gaming
by users who adapt their language, inability to distinguish cultural or
individual variation from pathology, and the risk of paternalistic interruption
that damages the therapeutic alliance or drives users to less safeguarded
platforms.

Disclosure mechanisms require the platform to surface information at appropriate
moments without becoming a nag. They inform the user about the system’s nature,
limitations, and the risks of sustained use. The transparency obligations of the
EU AI Act [b-EU AI Act] for certain AI systems establish a regulatory
expectation that users know when they are interacting with an AI. In several
jurisdictions these controls are becoming a regulatory expectation rather than a
design option. China’s rules for anthropomorphic AI services require the ability
to intervene where there are signs of extreme negative emotion or addiction, and
to notify the user after extended continuous use. The T/ISC 0125-2026
specification [b-T-ISC-0125-2026] frames a guardrail architecture of input
protection, inference monitoring, output protection, safety intervention, log
audit and policy management.

What disclosure can do is set expectations and preserve user autonomy. What it
cannot do is counteract the emotional pull of an anthropomorphic agent once
attachment has formed. Research on the “power of augmentation” suggests that
persuasive capability increases with computational power, and disclosure alone
does not neutralize that. Latency is immediate, cost is low, but failure modes
include habituation (users ignore repeated disclosures) and the “consent
paradox” where disclosure is formally satisfied but substantively meaningless.

Escalation to a human is the final backstop. For human-facing harms, escalation
requires clear criteria (imminent risk of self-harm, signs of psychosis-adjacent
reality drift, explicit requests for human help) and a functioning referral
pathway.

What it can detect is crisis; what it cannot detect is slow-burn erosion that
never triggers an acute threshold. Latency is variable (minutes to hours), cost
is high (human staff), and failure modes include unavailable or unqualified
human responders, privacy concerns that deter escalation, and the ethical
problem of platforms having no duty of care infrastructure for the populations
they serve.

Why an output filter cannot observe cumulative harm. An output filter evaluates
each response against a policy. Cumulative harm is not a property of any
individual output. This includes dependence, cognitive erosion, reality drift,
isolation, and compulsion. A response that says “I’m always here for you” is
benign in isolation and potentially harmful in the thousandth iteration of a
dependency-reinforcing pattern. The filter lacks the temporal window, the
cross-session state, and the user-specific baseline required to distinguish a
supportive comment from a dependence marker. It is structurally blind to
trajectory because it evaluates snapshots. The entire architecture of
human-facing safety assessment is therefore required to be longitudinal and
stateful, not merely transactional.
