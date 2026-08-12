# Misleading 'Download' menu label — dev spec
Site: voicenotes.com · Priority 2 · Medium · Effort: Low (0.5-2 days)

## Problem
Footer groups Enterprise and Pricing under 'Download', mislabeling their destinations.

## Evidence (from the live site)
> Download [Chrome extension](https://chromewebstore.google.com/detail/voicenotes-ai-transcribe/ijhnkhjjjpoloniinkaobelgghfckiep?hl=en) [iOS](https://apps.apple.com/us/app/voicenotes-ai-notes-meetings/id6483293628) [Android](https://play.google.com/store/apps/details?id=com.app.voicenotes&pli=1) [Enterprise](https://voicenotes.com/enterprise) [P
> Resources [IntegrationsConnect your favourite tools.](https://help.voicenotes.com/en/collections/12277349-integrations)

## Current state
notes: Enterprise and Pricing links under 'Download'.

## Required change
notes: Split Enterprise and Pricing into separate labeled sections.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Split Enterprise and Pricing into separate labeled sections.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_misleading_download_menu_label` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
