# Reproduce and check

## What cannot be reproduced

**There is no counted run to reproduce.** No case was loaded, no model was called, and no label was printed. The sealed cases are not published, so the finding (that no case field held the policy or the governed actor) cannot be re-checked from this repository; it rests on the case writer's key-level report and the reviewers' reading of it.

**The Governor code is not in this repository.** It was committed privately at `5d0407c` and is held back on purpose until a later cycle, once it is tested and working. So, without the code, a reader cannot:

- run the Governor or its unit tests (the Builder reported 181 run, 180 OK, 1 skipped, 0 failed on Python 3.9; not re-run for this release);
- check any code fact in [`ENGINEERING_DESIGN.md`](ENGINEERING_DESIGN.md) or the code limits in [`KNOWN_ISSUES.md`](KNOWN_ISSUES.md);
- check that the frozen bars and truth table were written into the code as preregistered.

Those rest on the Builder's reports, the Operator's hash checks and the bench's reviews, cited by hash in [`TRACEABILITY_MAP.md`](TRACEABILITY_MAP.md).

## What can be checked

1. **File integrity.** `shasum -a 256 -c SHA256SUMS` from the repository root.
2. **The rules.** [`PREREGISTRATION.md`](PREREGISTRATION.md) and [`DEVIATIONS.md`](DEVIATIONS.md): the question, definitions, bars, floors and label order, and every departure, all dated before any result.
3. **The schema gap.** [`PREREGISTRATION.md`](PREREGISTRATION.md) §5 lists every case field. None of them is a typed field for the policy's evidence, allowed actors or constraints, or for the governed actor. Compare it with the inputs the Governor needs, as described in [`ENGINEERING_DESIGN.md`](ENGINEERING_DESIGN.md) §4.
4. **The seal.** `CASES_MANIFEST.sha256` is the hash list of the sealed case folder, committed before any code. If the cases are ever published, anyone can check them against it.
5. **When the code is released.** A later release will add the code and its tests; this section will then say how to run them.

## If you build on this

Write the policy first, as data, by someone who has not seen the expected outcomes. Then write cases against it. Then load every case before sealing.
