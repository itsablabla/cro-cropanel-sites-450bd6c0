# Per-user prices lack billing period — dev spec
Site: voicenotes.com · Priority 7 · Medium · Effort: Medium (2-5 days)

## Problem
Paid tiers show per-user prices without specifying monthly or annual billing, causing confusion.

## Evidence (from the live site)
> prices: $0 $9 /user $24 /user

## Current state
notes: Prices shown as $9 /user and $24 /user without time unit.

## Required change
notes: Append 'per month' or 'per year' to each price.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Append 'per month' or 'per year' to each price.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_per_user_prices_lack_billing_period` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
