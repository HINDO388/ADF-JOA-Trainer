# ADF JOA Trainer — Question Bank QA7

**Application:** v1.22  
**Question-bank version:** `2026-09-02-QA7`

## Screenshot defect

The reported Practice Test 7 nested-shape question was a genuine rendering defect. The inner shape was generated as a smaller SVG viewport but the actual polygon geometry used fixed pixel offsets, so an inner triangle could be almost the same physical size as the outer triangle and overlap it. That could make an intended two-shape panel look like a single triangle.

v1.22 renders the inner figure at the same base geometry and then physically scales the complete inner SVG to **52%**. The generator also forbids the same inner and outer shape in this family.

## Structural bank audit

- Deterministic bank questions checked: **3,840**
- Visual questions checked for semantic visible-option uniqueness: **960**
- Nested-edge questions checked for a valid visible relationship: **83**
- Nested answer-option renderings checked in Chromium for two SVG layers and a genuinely smaller inner layer: **415**
- Independent Numerical calculations checked: **1,266** (all 960 deterministic Numerical bank questions plus every Numerical question appearing across all 18 Full Practice Tests)
- Abstract questions rendered and pixel-compared: **960**
- Abstract answer-option images pixel-compared: **4,153**
- Remaining identical rendered answer choices within a question: **0**
- Result: **PASS**

The nested-edge validity rule now requires every normal option to have more straight sides on the outer shape than the inner shape, while the single correct answer must visibly break that relationship.


## Independent arithmetic verification

The Numerical audit recalculates answers independently from the stored answer field for Number Series, Number Value, Word Problems and Number Matrices. It includes the new Simple Average and two-stage Work Rate families. The final run completed **1,266 independent Numerical calculations with zero failures**.

## Rendered visual verification

All 960 active Abstract-bank questions were rasterised through Chromium. The 4,153 answer-option images were compared by actual rendered pixels, not just by internal object data. No question contained two identical rendered answer choices after the v1.22 fixes.
