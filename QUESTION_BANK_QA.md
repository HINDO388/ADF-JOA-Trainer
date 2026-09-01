# ADF JOA Trainer — Question Bank QA Report

**Question-bank version:** `2026-09-01-QA2`

This report records the verification performed on the question bank included in this PWA release.

## Scope checked

- **1,320 Category Practice slots**
  - 11 question subtypes
  - 40 Easy + 40 Medium + 40 Hard slots per subtype
- **918 Full Practice Test slots**
  - 18 fixed practice tests × 51 questions
- **5 familiarisation questions**
- **Total displayed question instances exhaustively checked: 2,243**

The Category Practice bank is now finite and deterministic specifically so the complete released bank can be checked rather than relying on an unbounded date-seeded generator.

## Automated checks — all passed

Every released question instance was checked for:

1. **Structural validity**
   - non-empty prompt
   - valid difficulty band and rationale
   - stored answer exists
   - correct single/multiple-selection count
   - answer is present among selectable options where applicable

2. **Number series**
   - the stored answer follows the displayed series under the intended arithmetic/pattern family
   - simple A-B-A-B alternation is explicitly classified Easy

3. **Number matrices**
   - the stored answer follows the repeated row/grid rule
   - candidate matrices are rejected if a library of common simple matrix rules fits the completed rows but predicts different values for the missing cell
   - duplicate completed rows are rejected

4. **Numerical word problems**
   - every answer is independently recalculated from the numbers and wording shown to the user
   - rate, percentage, ratio, average, work-rate and dependent-percentage templates were checked separately

5. **Abstract / visual questions**
   - stored answers satisfy the stated rotation, reflection, sequence or attribute rule
   - a correct option is never visually identical to an incorrect option
   - non-intentional duplicate visual choices are rejected
   - rendered figures do not clip against their SVG bounds
   - any prompt referring to a reference/starting figure actually displays that figure

6. **Full practice tests**
   - every test contains exactly 51 questions
   - every test contains 17 Numerical, 17 Verbal and 17 Abstract questions
   - the intended Easy/Medium/Hard mix is maintained separately in each reasoning family
   - question numbering is exactly 1–51

7. **Application rendering / marking**
   - every released question can be rendered by the app without a JavaScript exception
   - the app's own answer-check function accepts the stored correct answer for every question

**Automated failures remaining after fixes: 0.**

## Manual semantic review — all passed

The non-mathematical source templates were manually reviewed as well:

- 15 odd-word category sets
- 15 analogy relationships
- 20 synonym/antonym/neither word pairs
- all four deductive-logic template structures
- all 33 subtype × difficulty construction families for difficulty calibration

Difficulty remains a training calibration rather than an official ADF item rating, but Hard is now reserved for genuinely layered/multi-rule, close-distractor, reflection, interleaved, or dependent multi-step constructions.

## Issues found and corrected during this audit

### 1. Missing reference figure in reflection question
The reported question asked which figures could not be produced by rotating "the same original figure" without actually showing an original/reference figure.

**Fix:** Medium and Hard reflection questions now display a labelled **Reference figure** above the options and explicitly ask which option(s) are mirror images rather than rotations.

### 2. Duplicate-looking options in the old hard reflection construction
The earlier hard construction reused the same four 90° orientations, which could produce repeated-looking choices.

**QA2 state:** Hard reflection-based odd-one-out items use six options: four true rotations and two reflections. There is no separate reference figure; the four rotationally equivalent items define the majority class.

### 3. Ambiguous number matrices
The audit found some generated matrices where two plausible simple rules both fitted the completed rows but predicted different missing values.

**Fix:** A matrix-clarity gate now tests generated matrices against a broad library of common simple rules and rejects/regenerates any item with competing predicted answers.

### 4. Visually repetitive multi-attribute items
Some older multi-attribute constructions used rotationally symmetric shapes in ways that made different encoded orientations look identical.

**Fix:** Those constructions now use shapes/attribute combinations whose relevant changes are visibly distinguishable.

### 5. Saved answer-review stability
Previously, historical tests stored the answers but regenerated the question set when reopened. A later bank revision could therefore make an old answer review differ from the test actually taken.

**Fix:** Every newly completed full test now saves an exact snapshot of all 51 questions alongside the answers. Pre-QA legacy results retain their score/timing but are not silently reconstructed against the revised bank.



## QA2 post-calibration re-audit

After removing the unnecessary master/reference figure from the Medium and Hard
Figure Odd-One-Out variants, the complete finite release bank was instantiated
again and structurally/regression checked.

Audit result: `{"ok":true,"checked":2243,"bankVersion":"2026-09-01-QA2"}`

No QA2 regression failures remained.
