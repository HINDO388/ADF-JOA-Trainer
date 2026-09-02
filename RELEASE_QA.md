# ADF JOA Trainer — v1.19 Release QA

## Worked examples

- Active subtypes checked: **16**
- Every subtype now renders exactly:
  - **1 Medium** generated worked example
  - **1 Hard** generated worked example
- Both examples are sourced from the same verified finite question-bank generator used by Category Practice.
- Picture Series, Picture Matrices, Picture Analogies and Picture Odd One Out were checked to contain rendered SVG question/answer graphics.
- Functional result: **PASS**

## iPhone hamburger close control

- The hamburger/X now handles iOS touch on `touchstart`, before the synthetic click stage that can be suppressed by scroll-lock behaviour.
- The following synthetic click is deliberately ignored to prevent double-toggle/reopen.
- The visible button is unchanged, but its invisible hit area is enlarged.
- Headless interaction stress test: **12 open/close cycles per hamburger viewport tested without a failure.**

## Update / blank-screen hardening

The reported one-off white screen with only the version number was reviewed as a plausible cache/navigation race.

v1.19 changes:
- the force updater no longer deletes the currently working PWA caches before navigation;
- downloaded `index.html` is validated before leaving the working build;
- the service worker treats navigation as network-first with `cache: no-store`;
- successful navigation updates one canonical cached `index.html` fallback rather than creating cache-busting-query entries;
- a separate startup watchdog detects an empty `#app`, retries once automatically and then shows a recovery message rather than leaving a pure white screen.

No localStorage deletion exists in the update or recovery path. Saved Full Practice Test history/progress is retained.

## Responsive smoke matrix

Checked:
- iPhone portrait 390×844
- iPhone landscape 844×390
- iPad portrait 1024×1366
- iPad landscape 1366×1024
- desktop 1440×900

Checks included:
- Home app shell present
- version stamp present
- page-level horizontal overflow
- Medium/Hard worked examples
- repeated hamburger open/close where hamburger is active

**Overall result: PASS**
