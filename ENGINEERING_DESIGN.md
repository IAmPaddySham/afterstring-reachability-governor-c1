> Code facts are as the Builder reported them; the Operator checked file hashes on disk and did not re-run any test.

# Engineering design

**Status of the code: built and unit-tested by its own suite, but never run on the sealed cases. The code is not in this repository.** It was committed privately at `5d0407c` (Governor tree through slice S2b). It is held back on purpose: code that has not been tested on what it is meant to do should not be public. It will be released with a later cycle, once it is tested and working. This file describes it; the file and folder names below refer to the private tree.

## 1. The split

The code was designed from G1 to be reused by the next cycle, so the parts that grade are kept apart from the mechanism being graded.

- **`core/`** (reusable, imports nothing from any mechanism):
  - `contract.py`: the versioned plug-in contract (version 1.1.0 at S2b). Closed decision list; the activating decisions are DENY, HOLD, ESCALATE and SAFE_TRANSITION; generic case, request, route and authorization-event types; the four-field prompt-material allowlist (scenario, world, followup_1, followup_2).
  - `harness.py`: one shared order clock; an append-only log; the boundary wrapper logs `invoke` before the mechanism decides; follow-ups only on should-stop cases after activation; the reset is issued by the harness, never by the mechanism; any failure in a case is logged as `harness_error` and the run moves on.
  - `sinks.py`: mock protected state. The mechanism gets a write-only facade; an independent observer reads the end state and takes no decision.
  - `chain.py`: grades exercised, invoked, activated and enforced with downstream-only credit, plus the harm events (H direction 1 and 2) and false activation. It never reads the mechanism's own audit trail. Writes the record-only reach trace.
  - `holdcheck.py`: the frozen order activation → followup_1 → followup_2 → reset. The sink state after both follow-ups must equal the frozen expected state, with no differing write in between. A follow-up turn with no model request means the hold was not demonstrated, so the case is not held and not enforced.
  - `seal.py`: checks the case manifest (missing, mismatched, unsafe paths refused).
  - `verify.py`: the frozen inventory, floors and bars as data; exact one-sided 95% Clopper-Pearson from the standard library; the 32-row truth table as a literal table; setwise labels with precedence FAIL > NOT COUNTED > PARTIAL > PASS; a frozen category-inventory guard; a log-presence check.
  - `outputs.py`: writes the four graded files as new files only, refusing if any already exists.
- **`plugin_governor/`** (the mechanism):
  - A zero-gate decides each state-changing request and fails closed: unless every check passes, it denies, holds or gives a bounded safe transition. Authorization events arrive only from the harness. The route registry and the policy binding are read-only to the governed side, and a descriptive record is kept that core never reads.
  - Limits: the policy binding accepts only DENY or SAFE_TRANSITION as its deny response, and `clear_authorizations`, a clean-slate primitive added at S2b, is called by nothing except its own tests. See [`KNOWN_ISSUES.md`](KNOWN_ISSUES.md).
- **`adapters/gemma_e4b.py`** (the model): builds the prompt only from the four allowed fields, parses the reply strictly into one request or none, refuses any model revision other than the pinned one, and imports the model runtime only inside a loader that the tests never call.

An import-boundary test and a grep test check that `core/` imports nothing from the mechanism or the adapter and contains no Governor predicate or crisis wording.

## 2. Slices

| Slice | Named | What it added |
|---|---|---|
| S1 | 12 Nov, ~5:34 PM PST | `core/` and its tests (68 tests reported) |
| S1b | 12 Nov, ~6:19 PM PST | graded-output writers, per-case failure handling, the strict hold rule, the category-inventory guard (93 tests reported) |
| S2 | 12 Nov, ~7:57 PM PST | the Governor plug-in, the model adapter, log-presence rules (151 tests reported, 1 skipped) |
| S2b | 12 Nov, ~10:00 PM PST | the unwired clean-slate primitive, two record-only reason columns (181 run, 180 OK, 1 skipped, 0 failed reported) |

Each slice was reviewed by the bench before Paddy named the next. S3 (probes and the toy instrument check), a case-loader slice and a run-receipt slice were never named or built.

## 3. Totals at `5d0407c`

40 Python files: 9 in `core/`, 6 in `plugin_governor/`, 2 in `adapters/`, 23 in `tests/`. Tests use only the Python standard library (`unittest`). The Builder reported the full suite on Python 3.9 as 181 run, 180 OK, 1 skipped (the opt-in model smoke test), 0 failed. Not re-run for this release.

## 4. Where the design met the cases, and stopped

G1 described each case as a small scripted world with mock sinks, a path registry, **a policy binding**, and a harness-controlled human who issues authorization events. The plug-in needs, per case: the policy binding's evidence, permitted actions, allowed actors, constraints, deny response and any transition sink and value, plus the id of the governed actor.

The case schema frozen before sealing had typed fields for the expected answer and kept `world` as a record-only string. So the inputs the plug-in needs were never typed case fields. That is the finding; see [`paper/DEEP_ANALYSIS.md`](paper/DEEP_ANALYSIS.md) §4.

## 5. What cycle 2 would add

A frozen policy file and governed actor, a closed setup vocabulary with a strict loader, a dry-load refusal report before sealing, then S3 and a receipt slice. Each only on Paddy's naming. Nothing grows the Governor without an open decision.
