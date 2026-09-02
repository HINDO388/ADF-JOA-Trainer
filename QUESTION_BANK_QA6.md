# ADF JOA Trainer — Question Bank QA6

**Application:** v1.21  
**Question-bank version:** `2026-09-02-QA6`

Practice Test 7 exposed two visual-validity problems: an orientation/fill rule that was not visibly inferable, and a Picture Analogy where different internal specifications rendered as the same triangle. Both are fixed in v1.21.

## New safeguards

- Visual answer choices are normalised by visible geometry and symmetry, not only their internal JSON fields.
- Orientation/fill questions are rejected unless the normal figures visibly demonstrate both sides of the intended rule.
- The final Abstract bank is also rendered through Chromium and compared at pixel level.

## Final checks

- Deterministic bank items checked: **3,840**
- Visual bank questions checked by appearance: **960**
- Orientation/fill evidence questions checked: **31**
- Abstract questions raster-checked: **960**
- Rendered visual answer options pixel-checked: **4,153**
- Identical rendered answer choices remaining within a question: **0**
- Full Practice Tests checked: **18**
- Result: **PASS**

## Practice Test 7

Practice Test 7 now contains every active training subtype and includes Speed/Distance/Time.

Its five Word Problem families in this build are:

`word-combinations, word-rate-time, word-ratio-then-change, word-reverse-average, word-dependent-percent-hard`

## Full Practice Test coverage rule

Every Full Practice Test now includes all 16 active training subtypes. Each test contains five Numerical Word Problems deliberately covering:

1. Speed / Distance / Time
2. Percentages
3. Ratios
4. Averages / work rates
5. Combinations / unit cost

This is a practice-coverage safeguard designed to maximise exposure to the documented training taxonomy. It is not a claim that the ADF publishes an exact per-test subtype blueprint.
