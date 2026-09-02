# ADF JOA Trainer — Full Practice Test Coverage QA

**Release:** v1.22

## Runtime coverage contract

Every Full Practice Test now hard-fails its internal build if any of these conditions are missing:

- exactly 51 unique questions
- exactly 17 Numerical / 17 Verbal / 17 Abstract
- all 16 active training subtypes represented
- Numerical allocation: 4 Number Series / 3 Number Value / 6 Word Problems / 4 Matrix Completion
- one Speed-Distance-Time Word Problem
- one Percentage Word Problem
- one Ratio Word Problem
- one Average Word Problem
- one Work-Rate Word Problem
- one Combinations / Unit-Cost Word Problem

There is **no silent fallback** that is allowed to drop one of those six numerical domains.

## Difficulty by test tier

- Easier-than-JOA tests: Easy versions of the six Word Problem domains
- JOA-level tests: Medium versions of the six domains
- Harder-than-JOA tests: Hard versions of the six domains

This keeps breadth constant while allowing the reasoning depth to change by tier.

## Practice Test 7 — verified current composition

- Question 8: **word-combinations** (medium) — A kit can be configured with 3 case types, 4 battery choices, 2 label styles and either one of 4 optional accessories or no accessory. How many different configurations are possible?
- Question 12: **word-time-unit-conversion** (medium) — A vehicle maintains 60 km/h for 45 minutes. How far does it travel?
- Question 14: **word-reverse-average** (medium) — The average of 7 test scores is 23. 6 scores are 26, 9, 12, 26, 24, 30. What is the remaining score?
- Question 31: **word-two-stage-output** (medium) — 4 staff process 10 forms each per hour for 1 hour. Then 2 more staff join for 2 further hours. How many forms are processed altogether?
- Question 32: **word-percent-increase** (medium) — A stock level of 80 units is increased by 15%. What is the new stock level?
- Question 36: **word-ratio-share** (medium) — Two equipment types are stocked in the ratio 4:2. There are 42 items altogether. How many belong to the first type?

Practice Test 7 therefore explicitly contains Speed-Distance-Time, Average and Work-Rate questions in the generated build.

All 18 tests passed the same coverage contract in QA7.

## Browser verification of Practice Test 7

The final saved v1.22 file was loaded in Chromium and `buildMock(7)` was executed. Its six Word Problems were:

- Q8 — **word-combinations** (medium): A kit can be configured with 3 case types, 4 battery choices, 2 label styles and either one of 4 optional accessories or no accessory. How many different configurations are possible?
- Q12 — **word-time-unit-conversion** (medium): A vehicle maintains 60 km/h for 45 minutes. How far does it travel?
- Q14 — **word-reverse-average** (medium): The average of 7 test scores is 23. 6 scores are 26, 9, 12, 26, 24, 30. What is the remaining score?
- Q31 — **word-two-stage-output** (medium): 4 staff process 10 forms each per hour for 1 hour. Then 2 more staff join for 2 further hours. How many forms are processed altogether?
- Q32 — **word-percent-increase** (medium): A stock level of 80 units is increased by 15%. What is the new stock level?
- Q36 — **word-ratio-share** (medium): Two equipment types are stocked in the ratio 4:2. There are 42 items altogether. How many belong to the first type?

This directly verifies the built/deployed source file rather than relying only on the intended selection rules.
