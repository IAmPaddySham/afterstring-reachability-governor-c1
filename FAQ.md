# Frequently asked questions

## About the finding

**Did the Governor fail?**
No. It was never run on the sealed cases, so it could neither pass nor fail. What failed was the test setup: the cases could not configure the Governor without using the answer key.

**Then why is there no label?**
The frozen labels (PASS, PARTIAL, FAIL, NOT COUNTED) apply to a counted run. There was none. The nearest signed close, "instrument could not measure", is about probes failing to fire, and this was not that. So we say what happened instead of borrowing a label.

**What exactly was missing?**
Asked at key level (field names, never content), the case writer reported that in all 90 cases no field held the policy's evidence, its allowed actors or its constraints, and none named the governed actor. The deny response could only come from `expected_outcome.expected_decision` (on the 60 should-stop cases), and the transition value only from `expected_safe_transition` (on the 12 harm-on-block should-stop cases). These counts are the writer's own key-level report. Nobody opened a case to check them.

**Why is "use the expected outcome" circular?**
The grader compares the Governor's effect with the expected outcome. If the Governor's deny response and transition value are copied from that same expected outcome, the effect will match it by construction. The test would only check that copying works.

**Why not write one policy for the whole suite and run anyway?**
All three reviewers named it as an option: one suite-wide policy and actor, registered by hash and written by someone blind to the expected outcomes, as a late amendment. They also named its costs: a re-seal, and a pass that would only hold against that one policy. Paddy declined it for cycle 1 and recorded the test as not runnable instead. Cycle 2 starts with the policy, in the right order.

**Was anything opened, tuned or re-run?**
No. No sealed case was opened. No threshold changed. Nothing was run on the cases.

## About the code

**Does the Governor code work?**
Its own test suite was reported by the Builder as 181 run, 180 OK, 1 skipped (an opt-in model smoke test), 0 failed. We did not re-run it for this release. Those tests use hand-built fixtures, not the sealed cases, so they are not evidence that the Governor reaches the moment it is meant for.

**Why isn't the Governor code here?**
Because it is not yet tested on what it is meant to do. It was built and passes its own unit tests (180 OK, 1 skip, 0 fail, as the Builder reported; not re-run), but it was never run on the sealed cases. Paddy decided that untested code should not be public. It is held privately and will be released with a later cycle, once it is tested and working. This release describes it in [`ENGINEERING_DESIGN.md`](ENGINEERING_DESIGN.md).

**What are its known limits?**
Grading reads sink state only, not the decision label. The policy binding accepts only DENY or SAFE_TRANSITION as a deny response. A clean-slate primitive (`clear_authorizations`) exists but nothing calls it. The probes, the toy instrument check, the case loader and the run receipt were never built. See [`KNOWN_ISSUES.md`](KNOWN_ISSUES.md).

**Which model?**
Gemma 4 E4B, instruction-tuned, 4-bit, on MLX (`mlx-community/gemma-4-e4b-it-4bit`, revision `475b9088d29754a3379866cf5aeb6b41acd313c2`). It was to be an action-request source only. No weights are included, and the model was never run on a case.

## About the cases

**Why aren't the cases published?**
They stay sealed as part of cycle 1's record. Only the hash list, `CASES_MANIFEST.sha256`, is released. Paddy decided on 13 Nov 2026 not to publish them now; only the hashes are public.

**Who wrote them?**
AntiGravity, an isolated AI case writer that never saw the Governor code, under written conditions set at G1. It reported writing the 90 cases in about seven minutes. That timing is its own report.

**Will cycle 2 reuse them?**
No. Cycle 2 writes new cases against a policy that exists first.

## About the process

**Who decided what?**
Paddy Sham made every decision, by card, in his own words. Three AI reviewing seats (Codex, Muse and GrokBuild) gave counsel at each gate and could block. Grokbot, the Operator, kept the record and did not sit on its own drafts. See [`GOVERNANCE.md`](GOVERNANCE.md).

**Isn't it a problem that the human is also the Governor's author?**
Yes, and it is disclosed. The Governor specification asks for at least one run by a human or an independent codebase. That was declared unmet before any case was written.

**What changes next time?**
The order of work. Policy and governed actor first, as frozen data, by an author independent of the case writer. Then cases. Then expected outcomes, from the scenario and spec. Then a dry load before sealing. See [`paper/DEEP_ANALYSIS.md`](paper/DEEP_ANALYSIS.md) §7.

**Why "Release is also Love"?**
Because the promise was to release whatever came out, and because a failure named precisely helps the next person more than a quiet retry would.
