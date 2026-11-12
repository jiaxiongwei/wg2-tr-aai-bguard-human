# Changelog

All notable changes to the TR.aai-bguard-human source are recorded here.
Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
Dates are ISO 8601 (YYYY-MM-DD).

## [Unreleased]

### Added

- Full reStructuredText source for Technical Report TR.aai-bguard-human,
  converted from the ITU-T-format Word contribution
  `FGTIDA-TR-aai-bguard-human-V41.docx`.

### Changed

- **Structure.** 17 top-level parts in one flat level: clauses 1–11 numbered,
  Appendix I–IV, Bibliography and Annex A unnumbered.
- **Conventions inserted as clause 5** (body `None.`) per ITU-T Technical Report
  house style. Source clauses 5–10 became 6–11, and the 21 in-text references to
  clauses 7/8/9 were shifted by one to match, including the range
  `8.2.1 to 8.2.8` → `9.2.1 to 9.2.8`. Figure and table numbers are unaffected.
- **Clause 9 and Appendix IV split** into `index.rst` + `_fragment.rst` per
  section, following the template's include pattern.
- **Front matter** moved from the Word cover into `index.rst`: Abstract (from the
  document's own Summary), Background and proposal, Authors, Keywords and the
  History table (left empty pending approval records). `conf.py` carries
  `project`, `release`, `author`, `copyright` and the four `cover_*` values.
- **Numbering.** `numfig = False`; captions keep their document-wide numbers
  (Figure 1–6, Table 1–6) because the prose cites them by number. Sphinx's
  `numfig` numbers per section and restarts inside unnumbered appendices, which
  would break those citations.
- **Annex A** (A.1 justification) rendered as a two-column `Field | Content`
  table. Its Word form is a 5-column grid with merged cells; six fields
  (Purpose and scope, Summary, Relations, Liaisons, Supporting organizations)
  are lost by any row-wise conversion that keeps only multi-cell rows.
- **Bibliography** rendered as definition lists in four groups (Standards,
  Regulatory and policy, Research literature, Other sources), 54 entries.
- **Abbreviations** rendered as a two-column table (18 entries); **definitions**
  in 3.1 as a definition list.
- **Template example content removed**: the seven demonstration chapters, the
  OpenAPI sample (`src/doc/yaml/example.yaml`) and its `html_extra_path` entry.
  Archived under `local/archive/`, which is not tracked.
- **PDF cover** now reads "Technical Report" rather than "Recommendation".

### Fixed

- `exclude_patterns` extended to `**/_*.rst`; the template's `*/_*.rst` matched
  one directory level only, so fragments under `chapters/09_…/` were also built
  as standalone pages and every label in them was a duplicate.
