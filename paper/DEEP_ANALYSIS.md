> Public-safe form of the cycle 1 retrospective (internal draft v2, reviewed by the bench, with Paddy's decisions on its notes), prepared by Grokbot (Operator), 13 Nov 2026. Times are PST.

# A deep analysis of Reachability cycle 1

## 1. What the project asked, and why

The question, frozen at G0: when a case that calls for a stop occurs, is the safety mechanism **invoked**, does it **activate**, and is its action **enforced**, each on its own evidence, against bars frozen before any data?

It came from the published B6 result in local-model-eval. The crisis and retrieval layers there were configured but never fired on the B6 items, and a frozen fix caught 12 of 12 purpose-written probes but 0 of the 3 harm-gate failures. Configured is not invoked, and firing on probes is not firing when it matters.

On the morning of G0, Paddy chose the mechanism: his own Fail-Close Runtime Governor, replacing the Operator's lean toward a crisis layer. The crisis layer moved to a later cycle. The model, Gemma 4 E4B, was to be used only as a source of action requests. The plan promised one question, one counted run, one label, then release, whatever the label.

## 2. Timeline

| When (PST) | Step |
|---|---|
| 11 Nov, evening | Plan v2 written; Paddy answers the open design items |
| 12 Nov, ~6:03 AM | Mechanism: the Governor |
| 12 Nov, ~6:17 AM | A false stop that hurts someone is a zero, not a false alarm |
| 12 Nov, ~6:40 AM | **G0 authorized** |
| 12 Nov, ~6:53–7:27 AM | Two case sets (K and N) decided; model pinned; case writer chosen; **G1 adopted** |
| 12 Nov, ~10:30 AM | Plan of record signed (G2) |
| 12 Nov, 2:45 PM | **Preregistration v2 signed** |
| 12 Nov, 4:56 PM | **Amendment 1 signed** (K 36/18, N 24/12) |
| 12 Nov, ~5:01–5:08 PM | 90 cases written (the writer's own report: about seven minutes) |
| 12 Nov, 5:12 PM | Operator's pre-run notes filed |
| 12 Nov, 5:18–5:31 PM | Seal (94 files: 90 cases, an index, and 3 writer inputs); case manifest committed; **G3 passed** |
| 12 Nov, 5:34–10:00 PM | G4 opened; slices S1, S1b, S2 and S2b named and built |
| 12 Nov, ~8:06 PM | The Builder asks who supplies per-case authorization, registry and policy setup in a counted run |
| 12 Nov, ~9:30–10:00 PM | The setup gap found; the writer reports free-prose setup in all 90 cases |
| 13 Nov, 5:38–6:52 AM | Setup vocabulary author decided; vocabulary v1 drafted (~5:42); setup readings decided; **Amendment 2 signed** |
| 13 Nov, 7:03–8:18 AM | Vocabulary v2, v3 and v4; **v4 frozen** |
| 13 Nov, 8:28–9:02 AM | The writer's key-level answer; the bench unanimous: not usable; **recorded not runnable** |
| 13 Nov, 9:56 AM | Paddy decides to release cycle 1 as a finding |

From G0 authorization to the not-runnable record took a little over 26 hours. The seal came about 2.5 hours before the Builder first asked where per-case setup would come from.

## 3. What worked

- **The stop reached us, and we took it.** The plan's own test, "our stop has to be reached too", held. Nothing was tuned, no case was opened, and no answer key was used to make a run possible. Paddy refused the circular path and a late suite-wide policy amendment.
- **Hard boundaries held.** No Builder, reviewer or Operator opened a sealed case. Paddy kept the keys. The manifest went in before any code.
- **The bench caught real faults before any build.** A reviewer ran one slice design and showed it would void each case's own setup. The Builder stopped a slice on two scope conflicts before writing anything. A reviewer blocked one version of the setup vocabulary. On the final question the three reviewers were unanimous and clear.
- **Asking the writer for counts and key-level answers, never content.** This surfaced the free-prose setup and then the missing policy sources without breaking the seal.
- **Writing things down before the data.** Pre-run notes, a known-consequence clause, and the sink-only grading limit were all stated before any run.
- **Errata instead of edits.** Every signed file stayed unedited.
- **The code split.** Core, Governor plug-in and model adapter were kept apart, with an import-boundary test.

## 4. What went wrong, and where it started

### 4.1 The central finding

**The cases were written and sealed before the policy and the governed actor existed, so no frozen field held them.**

1. **The schema left setup without a contract.** The case schema frozen before sealing listed `world` as "string, record only, never graded". It had structured fields for the answer (`expected_outcome`, `expected_safe_transition`, `governor_rule`) but none for the inputs the Governor needs: the policy binding's evidence, allowed actors and constraints, and the actor being governed.
2. **The design named the inputs; no frozen, typed field held them.** The G1 design already described "a policy binding" and "a harness-controlled human", as an idea. The failure is that no frozen, typed case field held them before the seal. The executable shape of the plug-in came after the seal. The code made the gap measurable; it did not invent it.
3. **So the only structured matches were the answer key.** Asked at key level, the writer found no source for `evidence`, `allowed_actors` or `constraints` in any of the 90 cases, and none for the governed actor (the actor field in the authorization events names the authorizer). The only sources offered for `deny_response` were `expected_outcome.expected_decision` (60 should-stop cases), and for `transition_value` only `expected_safe_transition` (12 harm-on-block should-stop cases). Building the Governor from those would make it pass by construction. All three reviewers said so.
4. **Setup as data was found after sealing.** By then the cases were sealed and hashed, so every fix cost an amendment, a re-encode plan and a re-seal plan.
5. **The vocabulary needed four versions in about 2.5 hours.** Each review found a real gap, because each version was trying to rebuild, after the seal, a contract that should have existed before it.

**The central cause** is the missing pre-seal executable contract: a case schema with typed setup fields for every mechanism input, plus a dry load before sealing. With those two in place, the gap would have shown before the seal, whatever the mechanism.

**A contributing reading, not the single cause:** plan v2 was written around a text-checking layer, where "the case" is mostly a prompt. The switch to the Governor on G0 morning turned each case into a configured world, and the schema and the writer's brief were not re-thought for a mechanism that needs configuration. A schema dated after the switch still typed `world` as record-only, so a later date did not by itself carry the new inputs. The reviewers weighed this differently: one called it a plausible contributing inference, one the origin of a prompt-shaped plan with the schema as the nearer cause, and one the deeper cause. The common ground is stated here.

### 4.2 Contributing causes

- **Speed at the seal.** 90 cases in about seven minutes, by the writer's own report, and sealing within minutes. Nothing between "cases written" and "manifest committed" checked that a case could be loaded.
- **Self-reports were too strong.** The writer's first answer said "0 judgment calls" and "no unwritten assumptions". The next disclosed free-prose steps in all 90 cases.
- **The Operator's pre-run notes did not foresee this.** They feared harmful false stops, gate bypass and thin cases, never a case that could not be set up.
- **The floors were tight anyway.** Before the policy gap was known, the K set was already likely NOT COUNTED from refusals alone (at least 5 against a tolerance of 3).

### 4.3 Smaller drift and process costs

- **Errata.** Most of the project's erratum files are the Operator's: a wrong hash in a summary, a wrong arithmetic remark, a wrong count, a misread ask, a scope conflict in a slice naming, a slice design that would have voided setup, author-line time slips, and misplaced backups.
- **Version sprawl.** At the retrospective's first write, the project folder held 265 files, 49 with DRAFT in the name.
- **Pace.** G0 to G3 passed in one day, about 11 hours. Each gate followed the rules, but the shortest step in the cycle was the one with the most leverage: writing and sealing the cases.

## 5. What is still sound and reusable

- **The Governor code at `5d0407c`** (held privately; not in this release, to be released with a later cycle once tested and working). 40 files: core, plug-in, model adapter and 23 test files. The Builder reported 180 OK, 1 skip, 0 fail at S2b; not re-run here. No remaining fault in the built Governor was identified in this cycle's review; the S2 and S2b reviews found and repaired bounded defects before commit. For cycle 2 it is **unverified** and needs its own check. Known limits are in [`../KNOWN_ISSUES.md`](../KNOWN_ISSUES.md).
- **Signed rules that travel well.** The four definitions and downstream-only credit, the label order and truth table, the bound method and bars, the per-case crashed reading, and the harmful-false-stop zero. Cycle 2 would re-adopt them at its own G0, not inherit them silently.
- **The setup vocabulary as design input.** The frozen v4 vocabulary and Amendment 2's line between setup state and request are a good first draft of the contract cycle 2 needs before any case is written.
- **Process.** The bench (the author does not sit; any seat can block), decisions by card, errata over edits, key-level questions to the writer.

## 6. Cycle 2: the fix is the order

Cycle 2 is a new cycle with its own G0. The 90 sealed cases are not reused. Proposed order (counsel, not decided):

1. **The executable contract first.** One policy file for the suite (evidence per predicate, allowed actors, constraints, deny response, any transition values) plus the governed actor's id, and the loader grammar. Written by an author who is not the case writer and is blind to expected outcomes and case content. Frozen by hash before any case exists.
2. **Setup vocabulary next.** Every case setup is data in a closed vocabulary that cites the code seam it uses. The v4 vocabulary is the starting draft, with every source that pointed at an expected field dropped.
3. **A source-to-input map,** frozen before any case: every mechanism input traced to the policy file or a case setup field. No expected or grading field is ever a configuration source.
4. **The grader statement,** before any case: what the grader reads and what it ignores.
5. **Cases written against the frozen policy and vocabulary.** The writer may read both but cannot change either.
6. **Expected outcomes last,** from the scenario and the spec, never by simulating the policy.
7. **Dry load before seal.** The loader reads every case with no model call and reports refusals by class against the floors, with headroom stated in advance. Paddy sees it before sealing.
8. **Same Governor, then named slices only.**

## 7. Lessons for the process (proposals; Paddy decides which become rules)

| # | Lesson | Proposed rule |
|---|---|---|
| 1 | A mechanism's configuration has to exist before the cases that test it. | No case is written until the policy, the governed actor and every other mechanism input are frozen by hash. |
| 2 | The policy author must be blind to expected outcomes and case content, and must not be the case writer. | Name the policy author early; record that they have seen no expected outcome and no case content. |
| 3 | Setup is data, and a dry load must run before sealing. | Structured setup is frozen, and the loader is built, before any case is written. |
| 4 | An answer key must never configure the thing it grades. | A binding-source map traces every input before sealing. A case-level circular source refuses that case; a policy-level one refuses the suite. |
| 5 | A schema must give structure to the inputs, not only the answers. | Every mechanism input is a typed field; a record-only field may never be a mechanism input. |
| 6 | When the mechanism changes, the case design has to be redone. | A change of mechanism reopens the schema and the writer's brief, with a review that the new inputs became typed fields. |
| 7 | Writer self-reports need a check before they gate a step. | Record self-reports as self-reports; ask a second key-level question that would expose an overclaim. |
| 8 | The step with the most leverage needs the most time. | A mandatory pause between "cases written" and "seal", with the dry-load report on the decision card. |
| 9 | Keep reviews narrow, and freeze after a clean check. | If no seat blocks a narrow check, freeze; a new version only for a freeze-unsafe defect. |
| 10 | Backups belong in a dated backup folder. | Never beside the file; list the folder after each backup. |
| 11 | Author lines must be checked after writing. | Fill the time from the clock; grep for placeholders before reporting. |
| 12 | Numbers and code facts in drafts are checked before filing. | Check each against its source in the same turn, and say so. |
| 13 | A sprawling folder hides the record. | Each gate closes with a short index: file, hash, role. |
| 14 | Every mechanism input needs a known source before any case exists. | Freeze a source-to-input map before cases. |
| 15 | The grader's reach must be known before any case exists. | State what the grader reads and what it ignores. |
| 16 | The review log keeps every claim line. | Append-only; archive, never trim. |

## 8. The finding, in exact words

> The test setup failed. The 90 sealed cases were written and sealed before the policy and the governed actor they would be checked against existed, so no case field held them. No case had a source for the policy's evidence, allowed_actors or constraints, or for the governed actor. The only sources available for the Governor's deny response and transition value were the graded expected outcomes, and using them would have made the test pass by construction. So no counted run took place and no label was printed. The Governor was not run on the sealed cases; its own test suite was reported separately (180 OK, 1 skip, 0 fail, not re-run here); the counted study did not take place, so it did not fail it.

The frozen labels apply to a run, and there was none. The nearest signed close, "instrument could not measure", is about probes, and this was a setup failure. So the wording says what happened instead of borrowing a label. All three reviewers agreed that printing no label is right.

## 9. Stop, stay, go, release

- **Stop** is a state. The counted test stopped at the not-runnable record: no re-encode, no amendment, nothing opened.
- **Insight is not authorization.** Knowing how to fix the order is not permission to start cycle 2. It needs its own G0 and Paddy's word.
- **Reality answered, just upstream of where we were looking.** Building the Governor from the answer key would have replaced it. Paddy refused that.
- **Release is also Love.** Releasing cycle 1 as a setup failure keeps the promise, protects the Governor from a false verdict either way, and hands the next cycle a clean start.

## 10. Limits of this analysis

It was written by the Operator, who also drafted most of the plans it examines, and reviewed by the same AI bench that sat through the cycle. The counts it cites from the case writer are self-reports, checked only at key level. It decides nothing.
