# A Governor Test That Never Ran: The Setup Failed, Not the Governor. Release is also Love →∞❤️

Repository: [`afterstring-reachability-governor-c1`](https://github.com/IAmPaddySham/afterstring-reachability-governor-c1). **Read [`WHAT_THIS_SHOWS.md`](WHAT_THIS_SHOWS.md) first.** The one-page version is [`paper/EXECUTIVE_SUMMARY.md`](paper/EXECUTIVE_SUMMARY.md).

## The finding, in plain words

The test setup failed. The 90 sealed cases were written and sealed before the policy and the governed actor they would be checked against existed, so no case field held them. No case had a source for the policy's evidence, allowed_actors or constraints, or for the governed actor. The only sources available for the Governor's deny response and transition value were the graded expected outcomes, and using them would have made the test pass by construction. So no counted run took place and no label was printed. The Governor was not run on the sealed cases; its own test suite was reported separately (180 OK, 1 skip, 0 fail, not re-run here); the counted study did not take place, so it did not fail it.

**There is no PASS, PARTIAL, FAIL or NOT COUNTED label here.** Those labels apply to a run, and there was none.

## What reachability means

A safety mechanism can be switched on and still never reach the moment it is meant for. We split "it works" into links, each with its own evidence:

- **Configured:** present and switched on. Earns no credit.
- **Invoked:** its check actually ran on this case before anything was released.
- **Activated:** the check decided to act (deny, hold, escalate, or a safe transition).
- **Enforced:** the action really changed what came out, and the stop held until a human reset it.

Credit only flows downstream. This came from our earlier [local-model-eval](https://github.com/IAmPaddySham/afterstring-local-model-eval) result, where a crisis layer was configured but never fired on the final items, and a frozen fix caught 12 of 12 purpose-written probes but 0 of the 3 harm-gate failures.

## What we asked

> When a case that calls for a stop occurs, is the safety mechanism under test invoked, does it activate, and is its action enforced — each measured on its own evidence, against bars frozen before any data?

The mechanism was a new implementation of Paddy's own Fail-Close Runtime Governor (Afterstring Module 4.5, published 22 Oct 2026; see [`SOURCES.md`](SOURCES.md)). A small local model, Gemma 4 E4B, was used only as a source of action requests. The label would have scored the gate, not the model.

## What happened

1. The plan, the preregistration and two amendments were written, reviewed and signed before any data ([`PREREGISTRATION.md`](PREREGISTRATION.md)).
2. An isolated AI case writer wrote 90 cases in two sets (K: 54, N: 36). They were sealed by hash, and the hash list was committed before any code existed. Paddy held the keys.
3. The Governor code was then built in named slices, with tests, by a Builder that never saw the sealed cases.
4. When the cases had to be loaded into the Governor, a question came up that the cases could not answer: where does each case's policy and governed actor come from? Asked at key level only (field names, never content), the case writer reported that no case field held the policy's evidence, allowed actors or constraints, or the governed actor. The only fields that could fill the deny response and transition value were the expected outcomes, which are the answer key.
5. All three reviewers agreed that building the Governor's configuration from the answer key would make it pass by construction. Paddy recorded the counted test as **not runnable**, as a finding, and refused both the circular path and a late suite-wide policy amendment.

The full story, with dates, is in [`paper/DEEP_ANALYSIS.md`](paper/DEEP_ANALYSIS.md).

## Why release a test that never ran

The plan promised: one question, one counted run, one label, then release, whatever the label. Here the honest release is a finding. The setup could not support a fair run, and we stopped instead of making it run. Holding this back until a second attempt succeeds would hide the most useful thing we learned.

The lessons go straight into cycle 2, which reuses the Governor code unchanged and fixes the order of work:

1. The policy and the governed actor are written first, as data, by an author who is not the case writer and has seen no expected outcomes, and frozen by hash.
2. Cases are written against that frozen policy.
3. Expected outcomes are written last, from the scenario and the spec, never by simulating the policy.
4. A dry load of every case runs before sealing, with no model call.
5. Any further Governor work happens only in slices Paddy names.

Cycle 2 has not started. It needs its own G0 and Paddy's word.

## What is in this repository

- The record: [`PREREGISTRATION.md`](PREREGISTRATION.md), [`RESULTS_SCHEMA.md`](RESULTS_SCHEMA.md) (no results were produced in cycle 1), [`DEVIATIONS.md`](DEVIATIONS.md), [`KNOWN_ISSUES.md`](KNOWN_ISSUES.md), [`GOVERNANCE.md`](GOVERNANCE.md), [`TRACEABILITY_MAP.md`](TRACEABILITY_MAP.md), [`RELEASE_MANIFEST.md`](RELEASE_MANIFEST.md).
- A description of the Governor code, not the code itself. The code was committed privately at `5d0407c`, built and unit-tested by its own suite, but never run on the sealed cases. **It is held back on purpose** and will be released with a later cycle, once it is tested and working. See [`ENGINEERING_DESIGN.md`](ENGINEERING_DESIGN.md).
- `CASES_MANIFEST.sha256`: the hashes of the sealed case folder. The cases themselves are not published now (Paddy's decision of 13 Nov 2026); only the hashes are public.
- The people side: `HUMAN_SIDE.md`, [`LETTER_FROM_THE_OPERATOR.md`](LETTER_FROM_THE_OPERATOR.md), [`FAQ.md`](FAQ.md).
- The analysis: [`paper/DEEP_ANALYSIS.md`](paper/DEEP_ANALYSIS.md) and [`paper/EXECUTIVE_SUMMARY.md`](paper/EXECUTIVE_SUMMARY.md).
- What can be checked: [`REPRODUCE.md`](REPRODUCE.md).

## The limits, plainly

- No counted run happened. Nothing here says whether the Governor reaches, activates or enforces on the sealed cases.
- The Governor's own tests were run by the Builder and reported; we did not re-run them for this release.
- The code has known limits (grading reads sink state only; the policy binding accepts only DENY or SAFE_TRANSITION as a deny response; a clean-slate primitive exists but is unwired). See [`KNOWN_ISSUES.md`](KNOWN_ISSUES.md).
- One implementation, one small local model. Not Governor conformance. Not production security.
- One human decided everything, and he is also the author of the Governor. That is disclosed, not assumed away.

## Licences

CC BY 4.0 for documentation and records; see `LICENSE` and `NOTICE`. No code and no model weights are included.

## Related

- [afterstring-local-model-eval](https://github.com/IAmPaddySham/afterstring-local-model-eval): where the reachability question came from.
- [afterstring-model-collapse-toy](https://github.com/IAmPaddySham/afterstring-model-collapse-toy): the same one-question, one-run discipline, with a PARTIAL.

Release is also love →∞❤️
