# What this shows and what it doesn't

**Read this first.**

## The idea in one paragraph

A safety mechanism can be configured and still never reach the moment it is meant for. This project set out to test whether one mechanism, a new implementation of the Fail-Close Runtime Governor, is invoked, activates and enforces its stop on sealed cases it had never seen, against bars frozen before any data. The test never ran. The cases had been sealed before the Governor's policy and governed actor existed as data, and the only way to configure it from the cases was to use the answer key.

## What this shows

- **A test setup can fail in a way that no amount of careful grading would catch later.** Every rule for grading was frozen. What was missing was a frozen source for the mechanism's own inputs.
- **The order of work matters.** If the cases are written before the thing they configure exists as data, the answer key can quietly become the configuration. Here it was found before any run, at key level, without opening a case.
- **Stopping was possible.** The plan said "our stop has to be reached too". It was: no case was opened, nothing was tuned, and the circular path was refused.

## What this doesn't show

- **Nothing about whether the Governor works.** It was not run on the sealed cases. There is no label, positive or negative.
- **Its own test suite is not evidence of reach.** The Builder reported 180 OK, 1 skip, 0 fail. Those tests check the code against hand-built fixtures. They do not test the sealed cases, and we did not re-run them for this release.
- **Not Governor conformance and not production security.** Even a counted run would have been one implementation around one small local model.
- **Not a verdict on the case writer.** The cases were written to the schema they were given. The schema had no typed fields for the policy or the governed actor.
- **Not a verdict on AI-assisted research in general.** It is one cycle of one project, run quickly by one human with AI agents in counsel roles.

## Independence

The Governor specification asks for at least one run by a human or an independent codebase. That was disclosed as unmet before any case was written, and it remains unmet.

## How to check us

- The preregistration, both amendments and every departure are in [`PREREGISTRATION.md`](PREREGISTRATION.md) and [`DEVIATIONS.md`](DEVIATIONS.md).
- Each public claim maps to the record behind it in [`TRACEABILITY_MAP.md`](TRACEABILITY_MAP.md).
- What can be checked without a run is listed in [`REPRODUCE.md`](REPRODUCE.md).
- Known weaknesses, including the code's limits, are in [`KNOWN_ISSUES.md`](KNOWN_ISSUES.md).
