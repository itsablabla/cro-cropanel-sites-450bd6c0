# Unsubstantiated social proof claim — dev spec
Site: voicenotes.com · Priority 9 · High · Effort: Low (0.5-2 days)

## Problem
The homepage claims real customer results without providing logos or quotes to back it up.

## Evidence (from the live site)
> h2: Real teams. Real meetings. Real results.

## Current state
notes: Claim without supporting evidence.

## Required change
notes: Add customer logos and quotes under the heading.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add customer logos and quotes under the heading.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_unsubstantiated_social_proof_claim` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
