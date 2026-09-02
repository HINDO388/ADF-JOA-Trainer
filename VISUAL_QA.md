# ADF JOA Trainer — Visual / Responsive QA

**Release:** v1.18

This pass specifically targets the iPad navigation inconsistency reported after v1.17, while also rechecking the principal phone/tablet/desktop responsive states.

## Viewports checked

- iPhone portrait: 390×844
- iPhone landscape: 844×390
- iPad Pro-style portrait: 1024×1366
- iPad Pro-style landscape: 1366×1024
- Smaller iPad portrait: 820×1180
- Smaller iPad landscape: 1180×820
- Desktop: 1440×900
- Large desktop: 1920×1080

## v1.18 regression targets

- iPad landscape uses full-size navigation typography: **19px brand / 16px menu**, with one row.
- iPad portrait uses the hamburger rather than shrinking seven menu labels to 13–14px.
- Portrait → landscape → portrait/landscape orientation changes restore the same deterministic layout.
- Phone layouts continue to use the hamburger.
- Home version text is present and the hidden refresh click handler is active in every tested orientation.
- Main sections were checked for page-level horizontal overflow at every viewport.

## Automated result

**PASS — no failures were found in the tested matrix.**

The dedicated iPad rotation test confirmed:
- initial landscape: full-size tablet-landscape navigation;
- portrait: hamburger;
- return to landscape: the same full-size tablet-landscape navigation with 16px menu text.

## Note

Headless Chromium cannot perfectly reproduce Safari/iPadOS font rasterisation, so the blur report is addressed structurally as well: the 13px/14px tablet compression path is removed and font-size/padding transitions are disabled. The tablet portrait layout now uses the hamburger instead of rendering the full menu at a reduced scale.
