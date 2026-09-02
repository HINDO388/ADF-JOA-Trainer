# ADF JOA Trainer — Visual / Responsive QA

**Release:** v1.17

The final saved HTML was exercised in headless Chromium across representative phone, tablet and desktop viewport sizes. This supplements real-device iOS safe-area testing.

## Viewports checked
- iphone_portrait: 390×844
- iphone_landscape: 844×390
- ipad_portrait: 820×1180
- ipad_landscape: 1180×820
- desktop_1440: 1440×900
- desktop_1920: 1920×1080

## Sections checked at every viewport
- Home
- Category Practice
- Full Practice Tests
- Mental Math
- Progress
- Strategy Guide
- Sources & Fidelity

## Additional states checked
- Hamburger open: header clearance, full-screen backdrop, close-button opacity, background scroll lock, internal drawer scrolling and last-item reachability
- Category Practice with Help and Worked Examples expanded
- All Full Practice Test difficulty groups expanded
- Mental Math times-table picker
- Category Practice drill modal
- Active 51-question Full Practice Test shell

## Result
**PASS — no tested page-level overflow, navigation wrapping, menu clipping, backdrop coverage, modal-boundary or drawer-scroll failures detected.**

## v1.17 fixes targeted by this pass
- Drawer top is derived from the actual header bottom instead of a fixed estimate.
- The previous fixed-body iOS scroll lock was removed.
- The menu backdrop explicitly covers the whole viewport.
- The drawer stays content-sized and becomes internally scrollable only when needed.
- Narrow-screen tables, modal actions and visual-option cards have additional overflow protection.

The two supplied iPhone screenshots were used as the regression target for the hamburger issues.