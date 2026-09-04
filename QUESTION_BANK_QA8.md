# ADF JOA Trainer — Question Bank QA8

**Application:** v1.23  
**Question-bank version:** `2026-09-04-QA8`

This release prioritises two things above all else:

1. questions must be valid, solvable and correctly marked;
2. successive Full Practice Tests should expose the learner to a broad range of question constructions rather than repeatedly presenting the same or nearly identical material.

## Finite-bank verification

All **3,840 deterministic Category Practice slots** were regenerated and structurally checked.

Checks included:
- stored answer accepted by the application marker;
- requested difficulty preserved;
- visible multiple-choice options distinct;
- orientation/fill relationships visibly inferable from the displayed figures;
- nested-shape rules valid from the actual side counts;
- no invalid answer indexes or missing answers.

Result: **PASS**

## Independent Numerical verification

All **960 Numerical bank questions** were independently recalculated outside the generator's stored-answer logic:

- Number Series: 240
- Number Value: 240
- Word Problems: 240
- Matrix Completion: 240

Result: **960 / 960 independently verified, 0 failures.**

## Required-statements logic distribution

The `Which statements are required to PROVE...` family no longer has a fixed answer.

Across the deterministic bank the four answer structures are evenly represented:

- `A + B`: 20
- `A + C`: 20
- `B + C`: 20
- `A + B + C`: 20

Each construction is generated so that the omitted statement is genuinely unnecessary rather than merely relabelled.

## Accuracy & Precision variety

The previous small list of recurring organisation names has been replaced by a combinatorial identity generator.

Across the 240 deterministic Accuracy & Precision questions:

- distinct left-column entries generated: **1,428**
- maximum reuse of any exact entry: **2**

This removes the recurring dependence on a small list such as `Boreal Hill Dining` or `Kestrel-8 Services`.

## Nested-shape odd-one-out

The earlier easy construction often showed four repetitions of essentially the same nested pair plus one visibly different outsider.

v1.23 replaces that design.

Easy:
- four varied nested pairs;
- normal rule: outer has exactly one more straight side than inner;
- at least four distinct outer/inner pair combinations per question.

Medium:
- outer and inner differ by exactly one straight side;
- direction may reverse between panels.

Hard:
- outer and inner straight-side counts add to nine.

All 30 deterministic Easy nested-shape questions passed the varied-pair guard.

## Visual rendered-pixel audit

The Abstract bank was rendered through Chromium and compared at pixel level:

- Abstract questions rendered: **960**
- answer-option images compared: **4,153**
- questions containing identical rendered answer choices: **0**

This catches cases where different internal specifications nevertheless draw the same picture.

## Full Practice Test coverage

All **18** baseline Practice Tests were rebuilt and validated.

Every test contains:
- 51 unique questions;
- 17 Numerical / 17 Verbal / 17 Abstract;
- all 16 active training subtypes;
- 4 Number Series;
- 3 Number Value;
- 6 Word Problems;
- 4 Matrix Completion.

The six Word Problems in every test deliberately cover:
- Speed / Distance / Time
- Percentages
- Ratios
- Averages
- Work rates
- Combinations / unit cost

All 18 tests passed.

## Cross-test repetition simulation

A three-exam sequence was simulated using the same history-aware avoidance used by the app.

The second test was generated while avoiding the first; the third while avoiding both previous tests.

Results:
- exact repeats Test 1 → Test 2: **0**
- exact repeats Test 1 → Test 3: **0**
- exact repeats Test 2 → Test 3: **0**
- near-duplicate surface matches across those three simulated tests: **0**

The app treats exact previously saved questions as a hard exclusion whenever a fresh valid candidate exists, and heavily penalises near-duplicate prompt/display structures. As more tests are completed, some methodology necessarily recurs because the JOA skill families themselves recur, but the selection engine now strongly favours fresh implementations.

## Overall result

**PASS — QA8 completed with zero outstanding bank-validation failures.**
