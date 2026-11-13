# Release manifest

## Release

- Project: Afterstring Reachability, cycle 1: the Fail-Close Runtime Governor.
- Release decision: Paddy Sham, 13 Nov 2026, 9:56 AM PST, by card: release cycle 1 under the retrospective's failure wording, with no label. The repository is public.
- Repository: `afterstring-reachability-governor-c1` (https://github.com/IAmPaddySham/afterstring-reachability-governor-c1). Release tag: `c1-v1.0`. Release commit: the commit tagged `c1-v1.0`.
- Code: **none in this release.** The Governor tree committed privately at `5d0407c` ("Reachability G4: governor tree through S2b") is held back by Paddy's decision of 13 Nov 2026, 10:26 AM PST, until a later cycle, once tested and working. It is described in `ENGINEERING_DESIGN.md`.
- Licences: CC BY 4.0 for documentation and records; `LICENSE`, `NOTICE`. No code, no model weights.

## Public files

| File | Role | sha256 |
|---|---|---|
| `README.md` | the finding, first | `c86a9e444abe0dcf7835457870ac4c0d27a128cfcca365b942e0b1bba4879eba` |
| `WHAT_THIS_SHOWS.md` | read first | `d0c0da1203c8701dad90c177bf10f90ed36a76efad68903107ec97b687d2e433` |
| `HUMAN_SIDE.md` | the steward's side | `df736f0debd078c51e043cdd372b9b55bdf99fafe31bf8ddd80315d24e4a2a33` |
| `LETTER_FROM_THE_OPERATOR.md` | non-authoritative disclosure | `657efc0a494ffe9d7f585d0ca441da497d29c4a4c4636257727a9d986f0c4061` |
| `FAQ.md` | | `e9e9a9e5e48946e07a68ec3b378dd0ac1651f73aa52aacda8b596365974ead29` |
| `ENGINEERING_DESIGN.md` | | `98904613bf92b2389f70275c9fc7ebb1294011576866fae30c3c2165d8127771` |
| `PREREGISTRATION.md` | public form of signed prereg v2 + Amendments 1 and 2 | `614ea87bba7a64ddf3a4055e8b1ac94a294a02f92960f0e68e17e4d20dadefcd` |
| `RESULTS_SCHEMA.md` | no results were produced in cycle 1 | `ba6546d5b8b93afe0e99432ab628f898f066b2a8490315698ea7d3d4b0da1366` |
| `DEVIATIONS.md` | | `bcc39091d6604bccf0c5391ab9e7d270c02b28395ab14cc4660d61347d572488` |
| `KNOWN_ISSUES.md` | includes the code's limits and the not-runnable decision | `e296bc167159e30edcf0a9c9b8263a77ee13ce6440deb200d8f6e82498cc87eb` |
| `GOVERNANCE.md` | | `dba5a6e7537d9cfcecc2caddc65a068ae956251cfa3f277545345c9e68793223` |
| `SOURCES.md` | | `670a2b6caa29851e06481ab7de34674005d2c2b0fec773405febd1164d4e4c5f` |
| `TRACEABILITY_MAP.md` | | `9934700ecbf59a5cfc18de5480c004a6719eebd2a562eec3d8c66f709b1d6d78` |
| `REPRODUCE.md` | what can honestly be checked | `cfaae914d2b11c86ebf8098f08e6d9d061bc0d121786e8796ed392beb8bbdc8c` |
| `RELEASE_MANIFEST.md` | this file (listed, not self-hashed) | — |
| `CHANGELOG.md` | | `227bb3d54408524856fced1a80ad26b0d1b76b2713cbeaf9087e9206a62bd4d6` |
| `CITATION.cff` | `date-released` set at publication | `00cbdd1da445e54d7af29164ad6a1d1d8d779545853de0250e89e0be80d55061` |
| `paper/DEEP_ANALYSIS.md` | public-safe retrospective with lessons | `8cf440bea1b4cb65f195e46956b177264b295eac62b17bbc449083be44218485` |
| `paper/EXECUTIVE_SUMMARY.md` | one page | `8cf4516aa73c3b006459141f511a3c4dfe2ec1990a0182b3293d2593ff13f78d` |
| `CASES_MANIFEST.sha256` | hash list of the sealed case folder, as committed before any code | `38f9842c60b0cbb8181bbaf9f1263aef529913674e5b629d4bb33bc02d62a6bd` |
| `LICENSE`, `NOTICE` | CC BY 4.0 legal code; notice | `9ba9550ad48438d0836ddab3da480b3b69ffa0aac7b7878b5a0039e7ab429411`; `e1fbc968b8348f8d95ad4fd05d4cf26fffed62e52432f4c37bf6610f155de22a` |
| `SHA256SUMS` | covers every file above | — (generated last; not listed in this file) |

## Evidence named for the finding

The frozen setup vocabulary v4 and the case writer's key-level §14a answer are the evidence for the finding. In this release they are **described** in `paper/DEEP_ANALYSIS.md` §4.1 and cited by hash in `TRACEABILITY_MAP.md`, **not included as files**, by Paddy's decision of 13 Nov 2026. (The §14a answer lists case ids against field names and flags; publishing it says something about the sealed cases, so it touches the separate question of publishing the cases.)

## Explicitly excluded

- **The Governor code and its tests** (40 `.py` files at private commit `5d0407c`): built and unit-tested, never run on the sealed cases, held back until a later cycle, once tested and working.
- The 90 sealed cases, the case index and the three writer inputs kept in the seal. By Paddy's decision of 13 Nov 2026, the cases are not published now; only the hashes are public.
- Keys and key copies; any per-file hash list other than `CASES_MANIFEST.sha256`.
- Blind sheets, grading files, per-grader sheets and held-out data (none were produced; listed for completeness).
- `results/` (no results exist).
- Reviewer seat files, bench asks, gate-pass files and the bench log.
- Internal decision, summary, journal, erratum and note files, and diaries. They are cited by hash in `TRACEABILITY_MAP.md` only.
- The Builder's slice reports and the Operator's receipt checks (cited by hash only).
- Material outside the public specification. Public text quotes nothing from it.
- Pre-existing Governor-named code. It was never under test.
- Model weights.
- Anything private, any local path, machine name or account name.
