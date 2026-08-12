# Unsubstantiated security claim — dev spec
Site: voicenotes.com · Priority 4 · High · Effort: Medium (2-5 days)

## Problem
The security promise lacks visible certifications or details, reducing trust.

## Evidence (from the live site)
> h2: Enterprise-grade security. No compromise.

## Current state
notes: Claim without supporting details.

## Required change
notes: Add compliance badges and security details.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add compliance badges and security details.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_unsubstantiated_security_claim` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
