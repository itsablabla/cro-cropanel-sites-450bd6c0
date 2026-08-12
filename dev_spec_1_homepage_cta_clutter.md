# Homepage CTA clutter — dev spec
Site: voicenotes.com · Priority 1 · High · Effort: Medium (2-5 days)

## Problem
Homepage offers multiple competing CTAs, diluting the primary signup path.

## Evidence (from the live site)
> ctas: Book a demo | Start for free | Get the desktop app | Contact support

## Current state
cta: Book a demo | Start for free | Get the desktop app | Contact support; notes: No direct pricing link in primary CTAs.

## Required change
cta: Start for free as sole emphasized hero CTA; add Pricing as secondary CTA.; notes: Move desktop app and support to nav/footer.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Move desktop app and support to nav/footer.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_homepage_cta_clutter` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
