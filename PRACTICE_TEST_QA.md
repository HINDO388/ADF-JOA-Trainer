# ADF JOA Trainer — Full Practice Test QA

**Release:** v1.21

## Test composition

Every 51-question Practice Test now contains:

- 17 Numerical
- 17 Verbal
- 17 Abstract
- all 16 active training subtypes
- 51 canonically unique questions

Numerical allocation is deliberately broad:

- Number Series: 4
- Number Value: 4
- Word Problems: 5
- Matrix Completion: 4

The five Word Problems cover Speed/Distance/Time, percentages, ratios, averages/work-rates and combinations/unit-cost.

## Answer-review interface

The existing completion summary remains unchanged above the review, including Correct, Attempted, Accuracy, Elapsed and the category breakdown.

Selecting **Review answers** now opens an active-test-style interface below it:

- green question number = correct
- red = incorrect
- yellow = unanswered
- selected question is outlined
- clicking any question number opens that exact question in the main pane
- original answer and correct-answer highlighting are retained
- full explanation and difficulty rationale remain visible
- flagged status is retained
- v1.21+ attempts show **Time spent** on the selected question

Older saved attempts that do not contain per-question timing show **Not recorded** rather than inventing a value.

## Responsive regression

The new review was interaction-tested at:

- 1440×900 desktop
- 390×844 iPhone
- 1024×1366 iPad

The completion summary remained present, the review opened below it, all three status colours rendered, selecting a grid item changed the central question, timing was visible and no page-level horizontal overflow was detected.
