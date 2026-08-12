# Lack of risk reversal on pricing — dev spec
Site: voicenotes.com · Priority 6 · Medium · Effort: Medium (2-5 days)

## Problem
Pricing page offers no guarantee or refund statement near decision points, increasing perceived risk.

## Evidence (from the live site)
> prices: $0 $9 /user $24 /user
> ctas: Book a demo | Start for free | Get Started | Contact Sales | Get the desktop app | Contact support

## Current state
cta: Book a demo | Start for free | Get Started | Contact Sales | Get the desktop app | Contact support; notes: No guarantee or refund language.

## Required change
cta: Get Started with no-risk guarantee; notes: Add refund or trial statement near pricing tiers.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add refund or trial statement near pricing tiers.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_lack_of_risk_reversal_on_pricing` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
