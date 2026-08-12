# Competing CTAs on pricing — dev spec
Site: voicenotes.com · Priority 3 · Urgent · Effort: Medium (2-5 days)

## Problem
Multiple equally prominent CTAs on the pricing page dilute the primary action, confusing self-serve buyers.

## Evidence (from the live site)
> ctas: Book a demo | Start for free | Get Started | Contact Sales | Get the desktop app | Contact support

## Current state
cta: Book a demo | Start for free | Get Started | Contact Sales | Get the desktop app | Contact support; notes: Multiple CTAs of equal prominence.

## Required change
cta: One primary CTA per tier, secondary actions demoted.; notes: Visually demote demo, sales, and desktop-app links.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Visually demote demo, sales, and desktop-app links.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_competing_ctas_on_pricing` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 124,891 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
