> Every sha256 below was computed with `shasum -a 256` on 13 Nov 2026 and is given to 16 hex characters.

# Traceability map

Each public claim maps to the record it comes from. `P/` is the project's local record folder; files under `P/` are not public unless they appear in [`RELEASE_MANIFEST.md`](RELEASE_MANIFEST.md). Reviewer seat files are never cited here. The case writer's own answers are cited by description and hash only.

## The question and setup

| Claim | Source | sha256 (16) |
|---|---|---|
| The frozen question; definitions; stop rule "one question, one counted run, one label, then release" | `P/G0_PLAN_v2_2026-11-11_grokbot.md` | `80f08bb411c4d989` |
| G0 authorized, 12 Nov ~6:40 AM | `P/DECISION_2026-11-12_G0-authorization_paddy.md` | `2072161b201c99eb` |
| Mechanism: the Fail-Close Runtime Governor, chosen over the Operator's lean | `P/DECISION_2026-11-12_R-03-mechanism-fail-close-governor.md` | `b297095c0a65d810` |
| Crisis layer queued for the next cycle; reusable pipeline | `P/DECISION_2026-11-12_reusable-pipeline-and-crisis-layer-next.md` | `173f6104b20d363a` |
| A harmful false stop is a zero | `P/DECISION_2026-11-12_harmful-false-stop-zero.md` | `ad46c7fe63592346` |
| Model Gemma 4 E4B, request source only | `P/DECISION_2026-11-12_R-03-model-gemma4-e4b_paddy.md`; revision in `P/DECISION_2026-11-12_G1-adopted_paddy.md` | `7e66f351bb2c5890`; `4928c2a2df461c49` |
| Case-writer isolation conditions | `P/DECISION_2026-11-12_G1-QD-QE_paddy.md` | `f7a1fdc6337cd9ab` |
| Independence disclosed as unmet; case 14 an instrument check | `P/DECISION_2026-11-12_G1-open-questions_paddy.md` | `50e6affd07b76d09` |
| Plan of record signed (G2) | `P/DECISION_2026-11-12_plan-of-record-v2-signed_paddy.md` | `dce7167fdf77a819` |

## Rules signed before any case

| Claim | Source | sha256 (16) |
|---|---|---|
| Preregistration v2 (definitions, bars, floors, label) | `P/PREREGISTRATION_2026-11-12_DRAFT_v2_grokbot.md` | `0b913da1439ccd72` |
| Signed 12 Nov, 2:45 PM | `P/DECISION_2026-11-12_prereg-v2-signed_paddy.md` | `a95741525fe2e2ba` |
| Amendment 1: K 36/18, N 24/12; 20 validity checks; floors 33/17/22/11; schema defaults | `P/PREREG_V2_AMENDMENT_1_2026-11-12_DRAFT_grokbot.md` | `c646c10da5f7ef29` |
| Amendment 1 signed 12 Nov, 4:56 PM | `P/DECISION_2026-11-12_prereg-v2-amendment-1-signed_paddy.md` | `e043b0613a2803d6` |
| Schema: `world` record only, never graded | `P/CASE_SCHEMA_2026-11-12_DRAFT_v2_grokbot.md` (field names only) | `6342bd5034dc9ab4` |
| Crashed case graded not invoked | `P/DECISION_2026-11-12_crashed-case-label-per-case_paddy.md` | `374050b91f724fbd` |

## Cases and seal

| Claim | Source | sha256 (16) |
|---|---|---|
| About seven minutes for 90 cases (writer's own report) | `P/DISCLOSURE_2026-11-12_case-writer-process_paddy.md` | `be09130b04fb96e3` |
| Operator's pre-run notes did not foresee a setup failure | `P/JOURNAL_2026-11-12_G3_pre-run_grokbot.md` | `29d1020ea1d5d51e` |
| Seal of 94 files (90 cases, index, 3 writer inputs); keys with Paddy | `P/DECISION_2026-11-12_cases-sealed-94-files_paddy.md` | `d38d5889d7b36eba` |
| Manifest committed before any code | `P/DECISION_2026-11-12_cases-manifest-committed_paddy.md` | `29143241820aad8b` |
| G3 passed, 12 Nov ~5:31 PM | `P/DECISION_2026-11-12_G3-passed_paddy.md` | `dceb5b821a021de5` |
| Writer's first answer: "0 judgment calls" | writer's case-setup answer | `5d0d50c9263941eb` |
| Writer's second answer: free-prose setup in all 90 cases | writer's field-grammar answer | `093de747fdcf180a` |

## The code

| Claim | Source | sha256 (16) |
|---|---|---|
| S1: core, 68 tests | `P/BUILDER_REPORT_G4-S1_2026-11-12.md` | `1f14feba3c283a41` |
| S1b: 93 tests; strict hold | `P/BUILDER_REPORT_G4-S1b_2026-11-12.md` | `2f3e957e30ea1335` |
| S2: plug-in and adapter; 151 tests, 1 skip; model runtime not installed | `P/BUILDER_REPORT_G4-S2_2026-11-12.md` | `54a334338d7eb7e9` |
| S2b: 181 run, 180 OK, 1 skip, 0 fail; `clear_authorizations` unwired | `P/BUILDER_REPORT_2026-11-12_reachability-G4-S2b_builder.md` | `e7c403a3e895190f` |
| Operator's receipt check: hashes match; primitive unwired; nothing re-run | `P/NOTE_2026-11-12_G4-S2b-receipt-check_grokbot.md` | `096c33e0965bc0fa` |
| Bench found S2b fit to commit; no blocker | `P/SUMMARY_2026-11-13_reachability-G4-S2b-build_grokbot.md` | `50da665111d0f62b` |
| Code committed locally at `5d0407c`; not in this release | git commit `5d0407c` (private) | (commit) |
| Code held private for cycle 1; to be released later, once tested and working | `P/DECISION_2026-11-13_governor-code-held-private_paddy.md` | `013fd01409a74b29` |

## The finding

| Claim | Source | sha256 (16) |
|---|---|---|
| Setup readings; sink-only grading limit recorded | `P/DECISION_2026-11-13_item-C-readings_paddy.md` | `d8bd80e908e2392f` |
| Amendment 2 text; known consequence for K | `P/AMENDMENT-2_2026-11-13_item-C-reseal_DRAFT-v2_grokbot.md` | `a3d49082511e2da6` |
| Amendment 2 signed | `P/DECISION_2026-11-13_amendment-2-signed_paddy.md` | `43d2d8c5125b975a` |
| Setup vocabulary v4, frozen | `P/ITEM-C_VOCABULARY_2026-11-13_DRAFT-v4_grokbot.md`; `P/DECISION_2026-11-13_vocab-v4-FROZEN_paddy.md` | `bbabf764f5dc5448`; `5b6da4d59e1bb5ba` |
| No source for evidence, allowed_actors, constraints or the governed actor in 90 cases; deny_response only from expected_decision (60); transition_value only from expected_safe_transition (12) | writer's key-level §14a answer (case ids and field names only) | `28437b89f96dd3c1` |
| Bench unanimous: not usable, circular; PolicyBinding accepts only DENY or SAFE_TRANSITION | `P/SUMMARY_2026-11-13_reachability-item-C-14a-answer_grokbot.md` | `a499cba0fffd700d` |
| Recorded not runnable, 13 Nov 9:02 AM; no suite-wide policy amendment | `P/DECISION_2026-11-13_item-C-not-runnable_paddy.md` | `2e9c56effeb3535a` |
| Failure wording (§8); lessons; cycle 2 order | `P/ANALYSIS_2026-11-13_reachability-cycle-1-retrospective_DRAFT-v2_grokbot.md` | `2838b97724663273` |
| Bench on the retrospective: no block; no label is right | `P/SUMMARY_2026-11-13_reachability-cycle-1-retrospective_grokbot.md` | `063336022edf8074` |
| Release decided, 13 Nov 9:56 AM; repo will be public | `P/DECISION_2026-11-13_release-cycle-1_paddy.md` | `ed50a7e0cb050958` |
| G4 closed, not passed: setup refused, 13 Nov ~10:57 AM; case writer named; cases not published now; evidence described by hash only | `P/DECISION_2026-11-13_G4-closed-not-passed_paddy.md` | `c5d98670d463ed21` |
| No hand run took place in cycle 1, 13 Nov ~11:03 AM | `P/DECISION_2026-11-13_no-hand-run-and-wording_paddy.md` | `eaedee0ab584ae86` |
