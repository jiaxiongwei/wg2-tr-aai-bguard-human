
.. raw:: latex

    \pagestyle{plain}
    \thispagestyle{plain}
    %% Suppress all TOC entries for the overview chapter (sections, subsections,
    %% Copyright addcontentsline) — restored just before \sphinxtableofcontents
    %% so chapters from Introduction onward appear in the TOC normally.
    \let\osiaorigaddcontentsline\addcontentsline
    \renewcommand{\addcontentsline}[3]{}

.. _front-matter:

Analysis and assessment framework of human-facing safety and guardrails of agentic AI systems
=============================================================================================

.. only:: html

    **Draft Technical Report TR.aai-bguard-human — Analysis and assessment framework of human-facing safety and guardrails of agentic AI systems**

.. raw:: latex

    \begin{center}\textbf{Draft Technical Report TR.aai-bguard-human — Analysis and assessment framework of human-facing safety and guardrails of agentic AI systems}\end{center}

Abstract
--------

Agentic AI systems increasingly pursue goals, invoke tools, maintain memory and
act across sessions. Unlike system-facing safety, which addresses discrete
functional risks at the action boundary, human-facing safety concerns the
cumulative psychological and cognitive effects of sustained interaction:
emotional dependence and attachment, erosion of user autonomy and judgement, and
drift from a shared account of reality. These risks develop across sessions and
are not reliably detectable in a single message or output. Current practice
relies mainly on disclosure, crisis referral, content filtering and session
reminders, but guardrails act relationally and their effectiveness is uneven;
verification, intervention and measurement capabilities lag. Providers,
regulators and third parties therefore lack a common, vendor-neutral way to
describe, assess and evidence whether human-facing safeguards are present and
effective. A technical analysis is needed to clarify mechanisms and limits,
establish shared assessment factors, and identify standardizable elements before
prescriptive limits are set.

The Technical Report defines human-facing terms, presents a human-impact risk
taxonomy, surveys current practice and near-term trends, analyses guardrail
mechanisms and limits, and proposes a vendor-neutral assessment framework
covering assessment factors, four enforcement layers, a long-horizon evaluation
and intervention loop, required artefacts and accountability roles, together
with standardization points and cultural/regulatory adaptation.

Background and proposal
-----------------------

Agentic AI is moving beyond content generation toward goal-driven action:
invoking tools, keeping persistent memory, and operating across sessions.
Human–AI interaction is no longer a one-off output but a long-term relationship
trajectory. Human-facing safety concerns the cumulative effect of sustained
interaction on a person’s psychology, cognition, ethics, and social position.
These effects include emotional dependence and attachment, erosion of user
autonomy and judgement, and drift away from a shared understanding of reality.
This is different from system-facing safety, which focuses on the action
boundary and discrete functional risks. Human-facing safety therefore needs its
own analysis and assessment framework.

Industry deployment is accelerating, but the features that drive adoption
overlap heavily with the features that create risk. Companionship, affective
responsiveness, memory, and continuous availability increase engagement, and can
also lead to dependence, social isolation, and overuse. Current practice focuses
mainly on identity disclosure, crisis referral, content filtering, and session
reminders. These controls act on individual messages or single sessions, and
they struggle to observe cumulative risk across sessions. At the same time,
stated safeguards are hard for external parties to verify, industry
documentation is uneven, and there is no common measurement method or evidence
format. A technical report is needed to analyse the current state, the
mechanisms and limits of guardrails, and to provide a basis for later
standardization.

Existing standards work is fragmented. ITU-T SG17 and FG-TIDA have addressed
agent identity, trust, security frameworks, and agent behaviour management.
ISO/IEC JTC 1/SC 42, NIST, ETSI, IEEE, and UNESCO cover governance, risk
management, AI security, and ethics from different angles. However, several
areas still lack systematic analysis: terminology for human-facing safety, a
human-impact risk taxonomy, guardrail capability requirements, intervention
escalation, cross-session drift measurement, a machine-readable representation
of psychological risk signals, and the timing of identity disclosure. This
Technical Report can serve as an FG-TIDA output that links security and trust
work with human-impact assessment.

The main research directions are: defining human-facing terms and a risk
taxonomy; analysing guardrail mechanisms, layers, and limits, including the gaps
among detection, intervention, and measurement, and the relational nature of
guardrail effects; reviewing industry needs, practice, reported results, and
trends over the next three to five years; proposing a vendor-neutral assessment
framework covering assessment factors, four layers (interface, model,
supervisory, and governance), a long-horizon evaluation and intervention loop,
evidence records, roles and accountability, and adaptation across cultures,
ethics, religions, and regulation; and identifying standardizable elements such
as shared vocabulary, a risk-signal schema, intervention policy and escalation,
identity disclosure, longitudinal evaluation benchmarks, and a shared
control-plane hook.

This Technical Report does not aim to set hard operational limits. Its first
goal is to establish common measurement methods and a verifiable evidence base,
so that standards developers, service providers, regulators, and deployers can
implement consistently and assess independently. The need is to close the gap
between “principles without evidence” and “filters without trajectory
assessment,” avoid safety theatre, protect user autonomy and welfare while
preserving legitimate affective response and room for innovation, and provide
input for future ITU-T Recommendations and cross-organizational coordination.

History
-------

.. list-table::
    :widths: 10 26 18 14 32

    * - Version
      - Document
      - Approval
      - Focus Group
      - Working Group

To access this Document as a PDF, open the published documentation site in your web
browser and click the PDF download link, or navigate directly to the PDF target of
this repository.

Authors
-------

.. list-table::
    :header-rows: 1
    :widths: 30 40 30

    * - Name
      - Affiliation
      - Contact
    * - Xiongwei Jia
      - China Unicom
      - jiaxw9@chinaunicom.cn

Keywords
--------

Agentic artificial intelligence (AI), human-facing safety, human-facing safety assessment, human impact, guardrails

Foreword
--------

Agentic AI systems now act as autonomous entities capable of reasoning, planning, and
executing tasks across services, infrastructures, and organizational boundaries. This
fundamentally changes the nature of identity in digital systems: identity is no longer
limited to human users and static machine instances but must also encompass autonomous,
dynamic, and goal-oriented agents. And identity alone is insufficient — the core question
extends beyond "what an entity is" to "whether, and under what conditions, that entity
should be trusted to act".

The Focus Group on Trust and Identity for humans and agentic AI (FG-TIDA) addresses trust
management and interoperable digital identity infrastructure for humans and for agentic AI,
supporting the development of secure, trustworthy digital ecosystems in which humans and
agentic AI can safely interact and collaborate.

FG-TIDA was established under Recommendation ITU-T A.7 (Focus groups: Establishment and
working procedures), with ITU-T Study Group 17 as its parent group. Further details are
available in the group's terms of reference.

For more news and updates about the TIDA Community, including its supporter organizations,
please refer to the community's published resources.

Note
----

*[Editor: add any note on the status of this Technical Report.]*

.. Intellectual Property Rights — section commented out. To restore it, remove the
   leading ".." and the indentation below, Do not put a ".. raw:: latex" block with
   "\osiacenternextsection" before the heading: the front matter ends with chapters,
   so the patch stays pending and is consumed by the first section, leaving clause 1
   centred and unnumbered.

   Intellectual Property Rights
   ----------------------------

   ITU draws attention to the possibility that the practice or implementation of this
   Recommendation may involve the use of a claimed Intellectual Property Right. ITU takes no
   position concerning the evidence, validity or applicability of claimed Intellectual Property
   Rights, whether asserted by ITU members or others outside of the Recommendation development
   process.

   As of the date of approval of this Recommendation, ITU had not received notice of intellectual
   property, protected by patents/software copyrights, which may be required to implement this
   Recommendation. However, implementers are cautioned that this may not represent the latest
   information and are therefore strongly urged to consult the appropriate ITU-T databases
   available via the ITU-T website at http://www.itu.int/ITU-T/ipr/.
   Implementers should also be aware that the organization that originated the technically
   equivalent document listed in the Bibliography may have received notices of intellectual
   property required for the implementation of this Recommendation.

.. raw:: latex

    %% Copyright notice commented out. To restore, uncomment the lines below.
    %% \vspace{4em}
    %% \begin{center}\textcopyright{} ITU 2026\end{center}
    %%
    %% \medskip
    %% All rights reserved. No part of this publication may be reproduced, by any means whatsoever, without the
    %% prior written permission of ITU.

    %% Restore \addcontentsline so the TOC below (and Chapter 1 onward) populate.
    \let\addcontentsline\osiaorigaddcontentsline
    \sphinxtableofcontents
    \osiamainmatter
    %% Clauses are \section under an unnumbered chapter, so LaTeX would print
    %% them 0.1, 0.2, ...  Number them from 1, and restart the counter here:
    %% the unnumbered front-matter subsections step it before this point.
    \makeatletter
    \renewcommand{\thesection}{\arabic{section}}
    \renewcommand{\thesubsection}{\thesection.\arabic{subsection}}
    \renewcommand{\thesubsubsection}{\thesubsection.\arabic{subsubsection}}
    \makeatother
    \setcounter{section}{0}

.. toctree::
    :maxdepth: 3
    :numbered:
    :hidden:

    chapters/01_scope
    chapters/02_references
    chapters/03_definitions
    chapters/04_abbreviations
    chapters/05_conventions
    chapters/06_overview
    chapters/07_current-state-and-future-trends
    chapters/08_human-impact-risk-taxonomy
    chapters/09_assessment-framework/index
    chapters/10_standardization-points
    chapters/11_conclusion

.. toctree::
    :maxdepth: 3
    :hidden:

    chapters/12_appendix-i_key-terms
    chapters/13_appendix-ii_dimensions
    chapters/14_appendix-iii_guardrail-mapping
    chapters/15_appendix-iv_industrial-practices/index
    chapters/16_bibliography
    chapters/17_annex-a_justification
