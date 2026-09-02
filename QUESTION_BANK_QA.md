# ADF JOA Trainer — Question Bank QA Report

**Question-bank version:** `2026-09-02-QA3`

This report records the verification performed for the v1.9 question-bank, diversity and difficulty revision.

## Fidelity basis

The trainer continues to use the revised public ADF JOA guide as its controlling source for the published format: **51 scored questions in 20 minutes** across **Numerical, Verbal and Abstract reasoning**, preceded by the documented familiarisation period. High-fidelity constructions remain anchored to the public examples (number series/matrix, numerical word problem, two-statement proof and group odd-one-out). Additional practice families are independent training extensions informed by Australian JOA-focused descriptions, not copied live-test content.

## Scope checked

- **2,640 deterministic Category Practice slots**
  - 11 subtypes
  - 80 Easy + 80 Medium + 80 Hard slots per subtype
- **918 fixed Full Practice Test items**
  - 18 Practice Tests × 51
- **5 familiarisation items**
- **Total released instances covered:** 3,563

## QA3 diversity controls

- Canonical fingerprints ignore option-order shuffling, so the same underlying question cannot masquerade as a new item.
- A hard guard prevents an exact fingerprint appearing twice inside any one Category Practice run.
- A hard guard prevents an exact fingerprint appearing twice inside any one 51-question Practice Test.
- Short Category Practice runs preferentially rotate construction families.
- Mixed Numerical / Verbal / Abstract drills balance all included subtypes to within one question of each other.
- 10-, 15-, 25- and 40-question regression runs were checked.

## Broader question range added

- Number Series: more interleaved, multi-operation, square-offset, changing-difference and dependency constructions.
- Number Matrices: broader weighted/two-operation row rules.
- Numerical Word Problems: broader rate, ratio, average, conversion, changed-base percentage, reverse-percentage, combined-rate and multi-stage scenarios.
- Odd Words: larger category vocabularies and varied subsets rather than repeatedly shuffling a few fixed six-word sets.
- Analogies: multiple relationship families with larger pair pools.
- Synonym / Antonym / Neither: substantially larger semantic pools.
- Deductive Proof: direct conditional, category membership, equality/value transfer, transitive order, exclusion, threshold, contraposition and chained implication methods.
- Abstract: more rotation angles, relational odd-one-out rules, alternating/multi-attribute sequences and close visual distractors.

## Difficulty recalibration

- **Easy:** one principal rule or directly classifiable invariant.
- **Medium:** more consistently requires two linked steps/rules, a reverse operation, conversion, interleaving, semantic precision or two simultaneous visual attributes.
- **Hard:** more consistently requires layered dependencies, multi-stage numerical work, chained/contrapositive logic, close reflection/rotation traps, three simultaneous visual attributes or changing/interleaved rules.
- Simple A-B-A-B number alternation remains explicitly classified Easy.

## Automated result

`{"ok":true,"bankVersion":"2026-09-02-QA3","categorySlotsChecked":2640,"fullPracticeTestsChecked":18,"totalFullTestItems":918}`

Every checked stored correct answer was accepted by the application's own marking function.

## Canonical uniqueness inside each 80-slot bank

### numSeries
- Easy: **80** unique canonical questions; **4** construction families
- Medium: **80** unique canonical questions; **6** construction families
- Hard: **80** unique canonical questions; **7** construction families

### numMatrix
- Easy: **78** unique canonical questions; **4** construction families
- Medium: **80** unique canonical questions; **5** construction families
- Hard: **80** unique canonical questions; **5** construction families

### wordProblems
- Easy: **80** unique canonical questions; **5** construction families
- Medium: **79** unique canonical questions; **7** construction families
- Hard: **69** unique canonical questions; **8** construction families

### oddWords
- Easy: **80** unique canonical questions; **8** construction families
- Medium: **80** unique canonical questions; **8** construction families
- Hard: **80** unique canonical questions; **8** construction families

### analogy
- Easy: **80** unique canonical questions; **5** construction families
- Medium: **80** unique canonical questions; **6** construction families
- Hard: **80** unique canonical questions; **6** construction families

### wordRelation
- Easy: **52** unique canonical questions; **18** construction families
- Medium: **44** unique canonical questions; **18** construction families
- Hard: **48** unique canonical questions; **18** construction families

### deduction
- Easy: **80** unique canonical questions; **3** construction families
- Medium: **80** unique canonical questions; **5** construction families
- Hard: **61** unique canonical questions; **5** construction families

### abstractOdd
- Easy: **72** unique canonical questions; **2** construction families
- Medium: **43** unique canonical questions; **2** construction families
- Hard: **75** unique canonical questions; **2** construction families

### abstractSequence
- Easy: **40** unique canonical questions; **2** construction families
- Medium: **44** unique canonical questions; **3** construction families
- Hard: **64** unique canonical questions; **3** construction families

### rotation
- Easy: **78** unique canonical questions; **1** construction families
- Medium: **75** unique canonical questions; **1** construction families
- Hard: **80** unique canonical questions; **1** construction families

### multiAttribute
- Easy: **80** unique canonical questions; **1** construction families
- Medium: **65** unique canonical questions; **2** construction families
- Hard: **64** unique canonical questions; **2** construction families

## Practice/Test regression checks

- Every subtype: Medium and Hard runs of 10, 15, 25 and 40 questions.
- No exact duplicate within any tested run.
- Short runs use as many distinct construction families as the subtype's available methodology allows.
- Mixed-category 10/15/25/40 runs include every subtype and keep subtype counts within one question.
- All 18 Full Practice Tests contain exactly 51 unique questions and exactly 17 Numerical, 17 Verbal and 17 Abstract items.

## Interpretation

For a long 25- or 40-question drill, broad reasoning themes may legitimately recur because the purpose is repeated exposure to the underlying skill. The system now prevents exact repetition and places the strongest diversity pressure on short 10- and 15-question sets, where variety is most valuable.

The bank remains independently generated practice material and does not reproduce proprietary or recalled live JOA questions.
