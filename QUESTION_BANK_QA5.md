# ADF JOA Trainer — Question Bank QA5

**Application:** v1.20  
**Question-bank version:** `2026-09-02-QA5`

This audit was added after a user questioned the Hard Number Series worked example:

`10, 14, 19, 26, 36, 50, ?`

That example is mathematically correct. Its first differences are:

`+4, +5, +7, +10, +14`

and the increases between those differences are:

`+1, +2, +3, +4`

so the next increase is `+5`, making the next first difference `+19`, and:

`50 + 19 = 69`.

The explanation was nevertheless made more explicit in v1.20 because the previous shortened wording was easy to misread.

## Independent correctness checks

This QA does not merely ask whether the application's stored answer agrees with its own marker.

- Total deterministic Category Practice slots structurally checked: **3,840**
- Numerical bank items independently recalculated: **960**
  - 240 Number Series
  - 240 Number Value
  - 240 Word Problems
  - 240 Matrix Completion
- Medium/Hard worked examples checked: **32**
- Full Practice Tests rebuilt and checked: **18**
- Numerical questions appearing in the Full Practice Tests were independently recalculated again.

Additional guards:
- no duplicate text answer choices;
- no duplicate visual answer choices;
- correct answer must be present / valid;
- Accuracy & Precision exact-match counts independently recounted;
- fixed Family Tree relationships independently checked;
- static True/False/Uncertain logic families independently checked;
- every Full Practice Test remains 51 canonically unique questions.

## Defects found during the audit and fixed

The questioned Number Series item itself was **not** defective.

The broader audit did uncover visual-choice defects that the earlier self-consistency QA had not caught:

1. **Picture Matrix — count combination**
   - Some questions could contain two visually identical answer choices when the correct dot count was 1.
   - Fixed by constructing guaranteed-unique count distractors.

2. **Picture Analogy — fill transformation**
   - A distractor could become identical to the correct answer when two randomly selected base shapes happened to match.
   - Fixed by forcing the shape distractor to use a different shape.

3. **Picture Odd One Out — count/fill**
   - The four majority figures were sometimes literally identical.
   - Not mathematically wrong, but poor question design and unnecessarily repetitive.
   - Dot arrangements can now rotate while retaining the same count/fill invariant.

4. **Picture Odd One Out — orientation/fill**
   - A 0° and 360° construction could create duplicate-looking figures.
   - Replaced with unique displayed orientations.

## Final result

`{"ok":true,"stats":{"total":3840,"numericalIndependent":1274,"worked":32,"fullTests":18},"failureCount":0}`

**PASS — zero QA5 failures after the fixes.**
