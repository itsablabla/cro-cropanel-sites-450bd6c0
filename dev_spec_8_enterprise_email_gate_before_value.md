# Enterprise email gate before value — dev spec
Site: voicenotes.com · Priority 8 · High · Effort: Medium (2-5 days)

## Problem
Enterprise page leads with a business email capture, blocking access to pricing and product details.

## Evidence (from the live site)
> title: Voicenotes for Enterprise | What is your business email?
> h1: Bring Voicenotes to your team
> ctas: Book a demo | Start for free | Contact support

## Current state
h1: Bring Voicenotes to your team; cta: Book a demo | Start for free | Contact support; notes: Email capture is the first interaction; no pricing shown.

## Required change
h1: Bring Voicenotes to your team; cta: Book a demo as primary; email capture later.; notes: Show indicative pricing or overview above email form.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Show indicative pricing or overview above email form.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_enterprise_email_gate_before_value` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
