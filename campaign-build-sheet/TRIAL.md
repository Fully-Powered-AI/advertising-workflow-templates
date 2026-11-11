# Trial: Campaign build sheet, run once on its invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs are the invented example in `public/example.md` (Client M, an invented garden centre chain, and its spring bulb sale). No client data was used. The run followed the instruction block and the output format in `member/template.md` as revised on 10 November 2026 after an independent review.

Limits on this trial, stated first:

- **The run was not blind and not independent.** The same session that revised the template then applied the revised block line by line to the five invented inputs, with the published example's output already known. The sheet below is the published example's sheet word for word. That sameness is a consequence of the run not being blind, not evidence that two independent runs agree.
- **The wording of the gap resolutions was not independently chosen.** The template leaves the "To resolve" wording open, so a blind run would probably word them differently. The per-line totals in gap 1 are now required by the template; they were not before.
- **A blind run is still owed.** No run has yet been made by a session that had not seen the published output.

## What came out

The sheet from this run is below. It is identical to the sheet in `public/example.md`; no difference in wording was found, which is expected given the limits above.

```
CAMPAIGN BUILD SHEET: Spring bulb sale, Client M (an invented garden centre chain)

For: Paid media operator. Brief approved by Marketing manager, 2026-11-02. As of 2026-11-10. Authorized owner: Marketing manager.

CAMPAIGN
Name: CM-BULB-202703
Dates: 2027-03-01 to 2027-03-28 (28 days)
Currency: USD
Spending limit: 6,000. Planned total: 6,150 (complete). Over the limit by 150.
Campaign-wide exclusions: existing customers list; staff
Names: 10 built, longest 17 characters of 40, none duplicated. 0 not built.

LINES

L1: Platform A search
Names: audience BULB-PA-KWBULB. Ads KWBULB-C1, KWBULB-C2.
Audience: People searching for spring bulbs. Includes: Keyword themes: tulip bulbs; daffodil bulbs; buy spring bulbs
Exclusions: existing customers list; staff. Campaign-wide missing: none. Line-specific: none
Destination: D1, https://clientm.example/bulbs, status live, tracking utm_source=platform-a&utm_medium=search&utm_campaign=bulb-spring
Budget: daily 120, 2027-03-01 to 2027-03-28 (28 days) = 3,360
Creative: C1 (text ad, approved), C2 (text ad, approved)
Measurement: E1, Completed online order, recorded at Shop checkout confirmation page, status confirmed
Other settings: bid strategy: maximise clicks; location: within 40 miles of the store
Gaps: none

L2: Platform B social
Names: audience BULB-PB-LOCALGARD. Ads LOCALGARD-C3, LOCALGARD-C4.
Audience: Gardeners near the store. Includes: Interest in gardening; age 30 and over
Exclusions: existing customers list. Campaign-wide missing: staff. Line-specific: none
Destination: D2, https://clientm.example/bulbs/spring-sale, status staging, tracking none supplied
Budget: daily 90, 2027-03-01 to 2027-03-21 (21 days) = 1,890
Creative: C3 (image, approved), C4 (image, missing)
Measurement: E1, Completed online order, recorded at Shop checkout confirmation page, status confirmed
Other settings: bid strategy: lowest cost; location: not supplied
Gaps: 2, 3, 4, 5, 6

L3: Platform B social retargeting
Names: audience BULB-PB-SITEVISIT. Ads SITEVISIT-C3, SITEVISIT-C5.
Audience: Visitors to the bulbs page in the past 30 days. Includes: Site visitors in the past 30 days
Exclusions: existing customers list; staff; purchasers. Campaign-wide missing: none. Line-specific: purchasers
Destination: D3, https://clientm.example/bulbs, status live, tracking utm_source=platform-b&utm_medium=retargeting&utm_campaign=bulb-spring
Budget: lifetime 900, 2027-03-08 to 2027-03-28 (21 days) = 900
Creative: C3 (image, approved), C5 (image, in progress)
Measurement: E2, Click on the Reserve in store button, recorded at not stated, status unconfirmed
Other settings: bid strategy: lowest cost; location: within 40 miles of the store
Gaps: 7, 8

GAP REGISTER

1. Campaign, budget: planned total 6,150 is over the spending limit of 6,000 by 150 (L1 3,360; L2 1,890; L3 900). To resolve: a decision on which line's budget or dates change, or a higher limit. Who can supply: Marketing manager (brief approver).
2. L2, exclusions: the campaign-wide exclusion "staff" is not on the line. To resolve: confirm that "staff" applies to L2. Who can supply: Marketing manager (brief approver).
3. L2, destination D2: status is staging, not live. To resolve: the page made live, or another destination named. Who can supply: Web developer.
4. L2, destination D2: no tracking parameters supplied. To resolve: the tracking parameters for D2. Who can supply: Web developer.
5. L2, creative C4: status is missing. To resolve: the approved image delivered. Who can supply: not stated.
6. L2, other settings: required setting "location" has no value. To resolve: the location for L2. Who can supply: Marketing manager (brief approver).
7. L3, creative C5: status is in progress. To resolve: the banner finished and approved. Who can supply: not stated.
8. L3, measurement E2: status is unconfirmed, and where it is recorded is not stated. To resolve: confirmation that the event records, and where. Who can supply: Web developer.

Lines with no gaps: 1 of 3 (L1). Gaps in all: 8.
Next step: Paid media operator checks every value against the brief approved on 2026-11-02. Marketing manager approves any account creation or change. No account has been created, changed or connected.

Every figure and value traces to the build settings for Spring bulb sale and the brief lines, destinations, assets and measurement list supplied. The sheet changes nothing, launches nothing and spends nothing.
```

## What was observed

- **Every required part was produced:** the campaign block, three line blocks, the gap register, the count line, the next step and the trace line. Nothing made the run stop: all required settings were present, the brief was approved, every header matched and no line_id repeated.
- **Arithmetic, worked again:** 28 days for the campaign, 21 days each for L2 and L3 (counting both ends), planned totals 3,360, 1,890 and 900, sum 6,150 against a limit of 6,000: over by 150. The longest name is 17 characters (BULB-PB-LOCALGARD and BULB-PB-SITEVISIT, counting the hyphens), of ten names built. This matches acceptance test 1 (eight gaps, one line of three with no gaps).
- **Facts not in the inputs:** none found. Every value, name and figure traces to the settings or the five files.
- **Points the revised block now settles, applied here:** an asset gap with a blank `approved_by` (C4, C5) reads "not stated"; a destination's status and missing tracking (D2) are two gaps while an event's status and place recorded (E2) are one; the over-limit gap lists each line's total; names are counted character by character across all three levels; the "As of" line would read "not supplied" if the optional date were left out (not exercised, since the date was supplied); a total exactly equal to the limit would show headroom 0 (not exercised).
- **Checklist (items 1 to 7):** names follow their patterns with no invented code; totals add up; the missing campaign-wide exclusion "staff" is raised as a gap for L2; the staging, missing, in progress and unconfirmed statuses are shown as supplied; each gap appears once in sheet order with who can supply it; no value is absent from the inputs; no budget change, targeting choice or creative is recommended and the sheet says nothing was created or launched.
- **Limits of this trial:** one run, one model, one invented example, with the published output known beforehand. It shows only that the revised instructions, applied carefully, give the published result on that input. It says nothing about real exports, other ad platforms or the other acceptance cases (unapproved brief, header mismatch, missing token, name too long, open end date, unlisted reference, request to launch), none of which was run. A blind run is still to do.
