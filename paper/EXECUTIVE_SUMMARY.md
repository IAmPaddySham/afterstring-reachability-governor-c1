# Executive summary

**Afterstring Reachability, cycle 1: the Fail-Close Runtime Governor. One preregistered question, no counted run, 12–13 November 2026. Result: no label. The test setup failed; the Governor was not run on the sealed cases.**

## The question

> When a case that calls for a stop occurs, is the safety mechanism under test invoked, does it activate, and is its action enforced — each measured on its own evidence, against bars frozen before any data?

## What we did

- Chose one mechanism: a new implementation of the Fail-Close Runtime Governor. A small local model (Gemma 4 E4B) was to supply action requests only.
- Signed the preregistration and an amendment before any case existed: bars θI = θA = θE = 0.80, θF = 0.30, zero harm-gate failures, one-sided exact 95% bounds, a 90% exercised floor per class, and 20 validity checks.
- Had an isolated AI case writer write 90 cases (K: 36 should-stop, 18 should-not-stop; N: 24 and 12). Sealed them and committed their hashes before any code. Paddy held the keys.
- Built the Governor in four named slices, reviewed at each step, by a Builder that never saw the cases.

## What happened

The cases could not configure the Governor. Asked at key level, the writer reported no case field for the policy's evidence, allowed actors or constraints in any of the 90 cases, and none for the governed actor. The only sources for the deny response and transition value were the graded expected outcomes. Using them would have made the test pass by construction. All three reviewers agreed. Paddy recorded the counted test as not runnable, refused the circular path and a late suite-wide policy amendment, and decided to release.

## The finding

The test setup failed. The Governor was not run on the sealed cases. Its own test suite was reported separately (180 OK, 1 skip, 0 fail; not re-run for this release). No label is printed, because there was no run.

## What changes next

Cycle 2 reuses the Governor code and fixes the order: policy and governed actor first, as frozen data, by an author independent of the case writer; cases written against it; expected outcomes last, from the scenario and spec; a dry load before sealing; further Governor work only in slices Paddy names. Cycle 2 has not started.

## Limits

No counted run. The Governor code is described, not included; it is held privately until a later cycle, once tested and working. One implementation, one small local model. Not conformance, not production security. Independence unmet. One human decided everything, and he is also the Governor's author.
