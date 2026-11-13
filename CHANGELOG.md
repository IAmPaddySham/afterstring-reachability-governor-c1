# Changelog

## 1.0.0 (2026-11-13): cycle 1 released as a finding

- First public release. There is no earlier tag: no prereg tag was cut, because G5 (freeze) was never reached.
- Adds the finding in `README.md`: the test setup failed, the Governor was not run on the sealed cases, no label.
- Adds the record: `PREREGISTRATION.md` (public form of the signed preregistration v2 with Amendments 1 and 2), `RESULTS_SCHEMA.md` (no results were produced in cycle 1), `DEVIATIONS.md`, `KNOWN_ISSUES.md`, `WHAT_THIS_SHOWS.md`, `GOVERNANCE.md`, `SOURCES.md`, `TRACEABILITY_MAP.md`, `REPRODUCE.md`, `RELEASE_MANIFEST.md`.
- Adds `HUMAN_SIDE.md`, `LETTER_FROM_THE_OPERATOR.md` (non-authoritative), `FAQ.md`, `ENGINEERING_DESIGN.md`, `CITATION.cff`, `paper/DEEP_ANALYSIS.md` and `paper/EXECUTIVE_SUMMARY.md`.
- Does not add the Governor code. It was committed privately at `5d0407c`, built and unit-tested by its own suite, never run on the sealed cases, and held back on purpose until a later cycle, once tested and working. `ENGINEERING_DESIGN.md` describes it.
- Adds `CASES_MANIFEST.sha256` (hashes only). The cases are not included.
- Adds `LICENSE`, `NOTICE` and `SHA256SUMS`.
