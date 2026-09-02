# ADF JOA Trainer — Question Bank QA Report

**Question-bank version:** `2026-09-02-QA4`  
**Application release:** `v1.11`

This release incorporates the complete user-supplied 30-screenshot capture of the
ADF Mentors JOA Online Test training module as a detailed **secondary** source.
The revised 2025 official ADF JOA guide remains the controlling source whenever
official and secondary material differ.

## Scope checked

- **3,840 deterministic Category Practice slots**
  - 16 active subtypes
  - 80 Easy + 80 Medium + 80 Hard slots per subtype
- **918 Full Practice Test items**
  - 18 fixed Practice Tests × 51 questions
- **5 familiarisation items**
- **Total released instances covered by release QA:** 4,763

## ADF Mentors source integration

The captured material was used to broaden the independent practice taxonomy and
training methods:

- Numerical: Number Series, Number Value, Word Problems, Matrix Completion.
- Verbal: General Vocabulary, Sentence Completion, Odd One Out,
  Accuracy & Precision, Word Analogies, Logical Reasoning,
  Seating / Ordering Arrangements, Family Trees.
- Abstract: Picture Series, Picture Matrices, Picture Analogies,
  Picture Odd One Out.

Worked examples and help text now incorporate the source's demonstrated methods:
writing first differences, comparing fractions/decimals, reverse percentages,
distance-speed-time, combinations, matrix row/column rules, analogy bridge
sentences, exact-text comparison, set/Venn sketches, seating slots, family-tree
sketches and feature-by-feature abstract elimination.

ADF Mentors' own simulation-score/difficulty statements remain labelled as
secondary-source training claims. They are **not** used as official ADF pass
marks, occupational cut-scores or difficulty ratings.

## Diversity and duplicate controls

- Canonical fingerprints compare the underlying prompt, display and answer
  structure, so merely shuffling choices does not create a fake "new" question.
- Exact repetition is forbidden inside a single Category Practice run.
- Exact repetition is forbidden inside a single 51-question Practice Test.
- Short 10- and 15-question drills favour different construction families.
- Mixed-category drills distribute active subtypes as evenly as mathematically
  possible; checked subtype counts differ by no more than one.

## Final automated regression result

- Category slots checked: **3,840**
- Active subtypes: **16**
- Single-subtype practice runs checked: **256**
- Mixed-category runs checked: **12**
- Full Practice Tests checked: **18**
- Full-test items checked: **918**
- Subtype render smoke tests: **16**
- Result: **PASS (`ok: true`)**

Every generated stored correct answer in the 3,840-slot bank was accepted by the
application's own marking logic.

## Canonical variation inside each 80-slot difficulty bank

### Number Series (`numSeries`)
- Easy: **80** unique canonical variants; **4** construction families
- Medium: **80** unique canonical variants; **6** construction families
- Hard: **80** unique canonical variants; **7** construction families

### Number Value (`numValue`)
- Easy: **80** unique canonical variants; **4** construction families
- Medium: **80** unique canonical variants; **6** construction families
- Hard: **80** unique canonical variants; **4** construction families

### Word Problems (`wordProblems`)
- Easy: **64** unique canonical variants; **7** construction families
- Medium: **70** unique canonical variants; **8** construction families
- Hard: **69** unique canonical variants; **10** construction families

### Matrix Completion (`numMatrix`)
- Easy: **80** unique canonical variants; **4** construction families
- Medium: **80** unique canonical variants; **5** construction families
- Hard: **80** unique canonical variants; **5** construction families

### General Vocabulary (`wordRelation`)
- Easy: **43** unique canonical variants; **8** construction families
- Medium: **52** unique canonical variants; **8** construction families
- Hard: **51** unique canonical variants; **8** construction families

### Sentence Completion (`sentenceCompletion`)
- Easy: **41** unique canonical variants; **8** construction families
- Medium: **50** unique canonical variants; **8** construction families
- Hard: **49** unique canonical variants; **8** construction families

### Word Categorisation — Odd One Out (`oddWords`)
- Easy: **79** unique canonical variants; **16** construction families
- Medium: **80** unique canonical variants; **16** construction families
- Hard: **78** unique canonical variants; **8** construction families

### Accuracy & Precision (`accuracyPrecision`)
- Easy: **80** unique canonical variants; **3** construction families
- Medium: **80** unique canonical variants; **5** construction families
- Hard: **80** unique canonical variants; **6** construction families

### Word Analogies (`analogy`)
- Easy: **80** unique canonical variants; **5** construction families
- Medium: **80** unique canonical variants; **6** construction families
- Hard: **80** unique canonical variants; **6** construction families

### Logical Reasoning (`deduction`)
- Easy: **54** unique canonical variants; **6** construction families
- Medium: **53** unique canonical variants; **8** construction families
- Hard: **48** unique canonical variants; **8** construction families

### Seating / Ordering Arrangements (`seatingArrangements`)
- Easy: **80** unique canonical variants; **4** construction families
- Medium: **80** unique canonical variants; **6** construction families
- Hard: **80** unique canonical variants; **6** construction families

### Family Trees (`familyTrees`)
- Easy: **79** unique canonical variants; **6** construction families
- Medium: **80** unique canonical variants; **6** construction families
- Hard: **80** unique canonical variants; **6** construction families

### Picture Series (`abstractSequence`)
- Easy: **44** unique canonical variants; **2** construction families
- Medium: **44** unique canonical variants; **3** construction families
- Hard: **62** unique canonical variants; **3** construction families

### Picture Matrices (`abstractMatrix`)
- Easy: **43** unique canonical variants; **4** construction families
- Medium: **43** unique canonical variants; **4** construction families
- Hard: **43** unique canonical variants; **4** construction families

### Picture Analogies (`abstractAnalogy`)
- Easy: **79** unique canonical variants; **5** construction families
- Medium: **76** unique canonical variants; **5** construction families
- Hard: **76** unique canonical variants; **5** construction families

### Picture Odd One Out (`abstractOdd`)
- Easy: **80** unique canonical variants; **4** construction families
- Medium: **71** unique canonical variants; **4** construction families
- Hard: **78** unique canonical variants; **4** construction families

## Full Practice Test structure

All 18 tests passed the following release guards:

- exactly **51** questions;
- exactly **17 Numerical + 17 Verbal + 17 Abstract**;
- **51 unique canonical question fingerprints** within each test;
- every stored correct answer accepted by the application's marker.

The 17/17/17 section split remains explicitly labelled in the application as a
simulation assumption from secondary Australian preparation descriptions; the
official ADF guide confirms 51 total questions and the three reasoning families,
but does not publish that exact section split.

## Difficulty calibration

Medium and Hard retain the upward calibration introduced in the earlier QA3
revision. The new ADF-Mentors-derived modules also use difficulty-specific
construction or distractor changes where possible:

- Easy: direct comparison, single relationship or immediately visible rule.
- Medium: closer distractors, multi-step comparison, reverse operation,
  relational inference, or two simultaneous attributes.
- Hard: layered/reverse calculations, close lexical/logical traps,
  multi-clue inference, chained logic or multiple changing visual rules.

Simple A-B-A-B number alternation remains explicitly classified Easy.

## Interpretation

Longer 25- and 40-question drills can legitimately revisit a broad reasoning
theme because repetition of the underlying skill is useful. The release guard
prevents the **same question** from repeating and applies the strongest family
diversity pressure to short 10- and 15-question drills.

The bank is independent training material. It does not reproduce restricted,
recalled or proprietary live JOA questions.
