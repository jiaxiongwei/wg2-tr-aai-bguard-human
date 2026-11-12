# TR.aai-bguard-human

**Analysis and assessment framework of human-facing safety and guardrails of
agentic AI systems**

Proposed new Technical Report of the Focus Group on Trust and Identity for
humans and agentic AI (FG-TIDA), Working Group 2 (WG2). Status: **draft**.

📄 **Web page:** ./target/html/
📥 **PDF:** ./target/latex

## What this document is

Agentic AI systems pursue goals, invoke tools, keep memory and act across
sessions, so the effect of an interaction is no longer confined to a single
output. This Technical Report analyses the *human-facing* safety of such
systems — the cumulative psychological and cognitive effect of sustained
interaction, including emotional dependence, erosion of user autonomy and drift
from a shared account of reality — and proposes a vendor-neutral framework for
assessing whether human-facing guardrails are present and effective.

It covers terminology and a human-impact risk taxonomy, the current state and
near-term trends, guardrail mechanisms and their limits, an assessment framework
with factors, enforcement layers, a long-horizon evaluation and intervention
loop, required artefacts and accountability roles, standardization points, and
adaptation across cultures, ethics, religions and regulation. It does not set
hard operational limits; its first goal is common measurement and a verifiable
evidence base.

## Contents

| | |
|---|---|
| 1–5 | Scope, References, Definitions, Abbreviations, Conventions |
| 6–8 | Overview, Current state and future trends, Human-impact risk taxonomy |
| 9 | A general assessment framework for human-facing safety |
| 10–11 | Standardization points, Conclusion |
| Appendix I–IV | Key terms, dimensions of human impact, guardrail mapping, industrial practice |
| Bibliography, Annex A | References and the A.1 justification form |

## Working on the document

The document is authored in reStructuredText and built with Sphinx into a web
page and a print PDF.

```shell
pip install -r requirements.txt
sphinx-build -b html src/doc target/html                            # web
sphinx-build -b latex src/doc target/latex && make -C target/latex  # PDF
```

- `src/doc/index.rst` — title, abstract, background, authors, keywords, foreword.
- `src/doc/chapters/` — one file per clause; `09_…/` and `15_…/` are split into
  `_fragment.rst` pieces with `.. include::`.
- `src/doc/images/` — figures.
- `src/doc/conf.py` — project metadata and the `cover_*` values used on the PDF cover.

See **[CONTRIBUTING.md](CONTRIBUTING.md)** for how to propose a change, and
**[WG-ONBOARDING.md](WG-ONBOARDING.md)** for the TIDA authoring workflow.

## Editor

Xiongwei Jia, China Unicom — jiaxw9@chinaunicom.cn

## Licence

MIT, per [LICENSE](LICENSE). See [CHANGELOG.md](CHANGELOG.md) for document history.
