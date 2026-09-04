# ADF JOA Trainer — v1.23 Feature QA

## Review / percentage toggle

The Full Practice Test result page now defaults to **Total %**:

`correct ÷ 51`

so unanswered questions count as incorrect.

The toggle switches to:

`correct ÷ attempted`

for attempted-only accuracy.

The same mode is applied simultaneously to:
- the large third result card;
- the percentage column in the Numerical / Verbal / Abstract breakdown.

Browser interaction checks passed on:
- desktop 1440×900
- iPhone 390×844
- iPad 1024×1366

## Review page rename

The user-facing `Progress` navigation label is now **Review**.

The Review page retains the existing completed-test design and adds a prominent **Marked Questions** feature card.

## Marked Questions

Persistent local marked-question storage was tested.

Questions can be marked from:
- an active Category Practice drill;
- Category Practice answer review;
- an active Full Practice Test;
- Full Practice Test answer review.

The Review page's Marked Questions browser:
- groups questions into Numerical / Verbal / Abstract;
- displays question prompt, subtype and difficulty in the list;
- opens the full saved question;
- displays the correct answer and existing solution feedback;
- allows the item to be removed.

The feature uses the existing local-storage record and does not delete completed-test history.

## UTC history dates

Completed Practice Test timestamps now use `timeZone: UTC` and visibly suffix **UTC**.

## Mental Math repeat prevention

A 500-question generated stress sequence was checked using multiplication/division with tables 3, 4, 5 and 6 under `Selected factors only`.

Checks:
- both factors stayed inside the selected set;
- no immediately consecutive underlying arithmetic fact repeated;
- commutative equivalents such as `7×6` followed by `6×7` are treated as the same fact;
- multiplication and its corresponding division fact are also treated as the same immediate fact for repeat prevention.

Result: **PASS**

## Selected factors only

The new toggle is labelled **Selected factors only**.

Standard mode:
- one factor comes from the chosen table set;
- the other may be any value from 1–12.

Selected factors only:
- both factors must come from the chosen set.

For division, the divisor and quotient are the two selected factors from the corresponding multiplication fact.

## Responsive UI

Browser interaction checks on desktop, iPhone and iPad confirmed:
- Review navigation present;
- Marked Questions modal opens and displays detail;
- Total/Attempted percentage toggle changes values correctly;
- UTC suffix visible;
- Mental Math toggle visible;
- Save Question controls visible in Category Practice and Full Practice Tests;
- no page-level horizontal overflow in the checked active-test state.

**Overall feature QA: PASS**
