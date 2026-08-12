# Enterprise link lands on email gate — dev spec
Site: voicenotes.com · Priority 10 · Medium · Effort: Low (0.5-2 days)

## Problem
The 'Enterprise' nav label promises an overview but lands on an email capture form, mismatching expectations.

## Evidence (from the live site)
> title: Voicenotes for Enterprise | What is your business email?
> h1: Bring Voicenotes to your team

## Current state
h1: Bring Voicenotes to your team; notes: Page framed around email capture.

## Required change
h1: Bring Voicenotes to your team; cta: Book a demo; notes: Show overview above email form or relabel nav link.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Show overview above email form or relabel nav link.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_enterprise_link_lands_on_email_gate` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
