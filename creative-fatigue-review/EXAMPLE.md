# Creative fatigue review: an invented example

*Illustrative example with invented data.* Client A is an invented online seller of garden furniture. Its paid media lead has noticed that the spring patio campaign is reaching the same shoppers more often and drawing fewer clicks, and asks for a review of the creative. Nothing here describes a real account or a real result.

## What the person supplies

**Campaign:** Spring patio range. Amounts in US dollars. Export dated 20 October 2026. Settings: the defaults (2 weeks, 20,000 impressions and 20 conversions in each window; frequency rise 25 per cent, response drop 15 per cent, cost rise 20 per cent).

**Windows:** baseline 14 September 2026 to 27 September 2026 (chosen by the paid media lead, starting a week after launch); review 5 October 2026 to 18 October 2026.

**Weekly export** (headers as in the template, one row per creative, audience and week; the export holds only the four weeks used):

```
week_start | creative_id | audience                   | spend  | impressions | reach | clicks | conversions
2026-09-14 | V1          | Broad 25-54                | 900.00 | 60000       | 40000 | 720    | 36
2026-09-21 | V1          | Broad 25-54                | 900.00 | 58000       | 38000 | 696    | 35
2026-10-05 | V1          | Broad 25-54                | 900.00 | 60000       | 27000 | 480    | 24
2026-10-12 | V1          | Broad 25-54                | 900.00 | 57000       | 23000 | 399    | 19
2026-09-14 | V1          | Retargeting 30 day         | 400.00 | 20000       | 8000  | 400    | 24
2026-09-21 | V1          | Retargeting 30 day         | 400.00 | 19000       | 7600  | 380    | 23
2026-10-05 | V1          | Retargeting 30 day         | 400.00 | 20000       | 6500  | 320    | 14
2026-10-12 | V1          | Retargeting 30 day         | 400.00 | 20000       | 6250  | 300    | 13
2026-09-14 | S2          | Broad 25-54                | 600.00 | 50000       | 34000 | 400    | 18
2026-09-21 | S2          | Broad 25-54                | 600.00 | 52000       | 35000 | 416    | 19
2026-10-05 | S2          | Broad 25-54                | 600.00 | 51000       | 33000 | 408    | 18
2026-10-12 | S2          | Broad 25-54                | 600.00 | 50000       | 32000 | 400    | 18
2026-09-14 | S2          | Lookalike and interest mix | 500.00 | 40000       | 28000 | 320    | 14
2026-09-21 | S2          | Lookalike and interest mix | 500.00 | 41000       | 28000 | 328    | 14
2026-10-05 | S2          | Lookalike and interest mix | 500.00 | 40000       | 20000 | 240    | 9
2026-10-12 | S2          | Lookalike and interest mix | 500.00 | 40000       | 18000 | 224    | 8
2026-10-05 | C3          | Broad 25-54                | 700.00 | 45000       | 30000 | 585    | 20
2026-10-12 | C3          | Broad 25-54                | 700.00 | 45000       | 30000 | 585    | 20
```

**Audience definitions:**

```
audience                   | description                                            | mix    | size_note
Broad 25-54                | Adults aged 25 to 54 in the sales region               | single | Large
Retargeting 30 day         | People who visited the store site in the last 30 days  | single | Small
Lookalike and interest mix | Lookalikes of past buyers combined with an interest list | mixed  | Medium
```

**Change log:**

```
date       | change_type | scope                      | description
2026-10-07 | bid         | S2                         | Bid strategy for S2 changed from lowest cost to a cost cap
2026-10-08 | tracking    | Retargeting 30 day         | Conversion tag on the retargeting landing page replaced
2026-10-12 | audience    | Lookalike and interest mix | Interest list widened with new interests
```

**Current assets:**

```
creative_id | format    | launch_date | status | last_edited
V1          | Video 15s | 2026-09-07  | live   | none
S2          | Static    | 2026-09-07  | live   | none
C3          | Carousel  | 2026-10-05  | live   | none
```

## What comes out

```
CREATIVE FATIGUE REVIEW: Spring patio range

For: Paid media lead. Baseline window 14 September 2026 to 27 September 2026 (2 weeks); review window 5 October 2026 to 18 October 2026 (2 weeks); export as of 20 October 2026. 5 pairs of creative and audience, 4 compared. Rows outside both windows ignored: 0. Extra columns ignored: none.

Settings used: minimum weeks 2; minimum impressions 20,000; minimum conversions for cost 20; frequency rise 25%; response drop 15%; cost rise 20%. Frequency is average weekly frequency (impressions divided by weekly reach, summed over the window).

Campaign view (compared pairs only): 4 pairs. Baseline: frequency 1.56, click-through 1.08%. Review: frequency 2.04, click-through 0.82%. Change: frequency +30.8%, click-through -24.1%. 3 of 4 compared pairs show the pattern "Frequency up and response down" (the "(click-through only)" variant counts). Compared pairs hold $4,800.00 of $6,200.00 review-window spend (77.4%). Audiences can overlap, so one person may be counted in more than one pair.

Changes in the period:
- 7 October 2026, bid, S2: bid strategy for S2 changed from lowest cost to a cost cap. Treatment: flagged: S2 on Broad 25-54, S2 on Lookalike and interest mix.
- 8 October 2026, tracking, Retargeting 30 day: conversion tag on the retargeting landing page replaced. Treatment: cost not compared and flagged: V1 on Retargeting 30 day.
- 12 October 2026, audience, Lookalike and interest mix: interest list widened with new interests. Treatment: flagged: S2 on Lookalike and interest mix.

Audiences:
- Broad 25-54: adults aged 25 to 54 in the sales region. Mix: single.
- Retargeting 30 day: people who visited the store site in the last 30 days. Mix: single.
- Lookalike and interest mix: lookalikes of past buyers combined with an interest list. Mix: mixed.

Comparison by creative and audience (changes use the rounded figures shown):
Creative | Audience | Weeks (baseline / review) | Frequency baseline | Frequency review | Change | Click-through baseline | Click-through review | Change | Cost per conversion baseline | Cost per conversion review | Change | Pattern | Reading
S2 | Broad 25-54 | 2 / 2 | 1.48 | 1.55 | +4.7% | 0.80% | 0.80% | 0.0% | $32.43 | $33.33 | +2.8% | No pattern | Compared with flags
S2 | Lookalike and interest mix | 2 / 2 | 1.45 | 2.11 | +45.5% | 0.80% | 0.58% | -27.5% | n/c | n/c | n/c | Frequency up and response down (click-through only) | Compared with flags
V1 | Broad 25-54 | 2 / 2 | 1.51 | 2.34 | +55.0% | 1.20% | 0.75% | -37.5% | $25.35 | $41.86 | +65.1% | Frequency up and response down | Compared
V1 | Retargeting 30 day | 2 / 2 | 2.50 | 3.14 | +25.6% | 2.00% | 1.55% | -22.5% | n/c | n/c | n/c | Frequency up and response down (click-through only) | Compared with flags

Not compared:
- C3 on Broad 25-54: short run, no weeks in the baseline window (launched 5 October 2026). Figures for the window it has: 90,000 impressions, frequency 1.50, click-through 1.30%, cost per conversion $35.00 on 40 conversions.

Alternative explanations, by pair:
- S2 on Broad 25-54: bid change on 7 October 2026. Weekly detail: baseline weeks of 14 and 21 September, frequency 1.47 and 1.49, click-through 0.80% and 0.80%; review weeks of 5 and 12 October, frequency 1.55 and 1.56, click-through 0.80% and 0.80%. The weekly figures show click-through flat and frequency changing little before or after the 7 October change.
- S2 on Lookalike and interest mix: mixed audience; bid change on 7 October 2026; audience change on 12 October 2026. Weekly detail: baseline weeks, frequency 1.43 and 1.46, click-through 0.80% and 0.80%; review weeks, frequency 2.00 and 2.22, click-through 0.60% and 0.56%. The movement is already present in the week of 5 October, before the 12 October change and in the same week as the 7 October bid change. Cost not compared because: 17 conversions in the review window, under the minimum of 20.
- V1 on Broad 25-54: none apply.
- V1 on Retargeting 30 day: tracking change on 8 October 2026. Weekly detail: baseline weeks, frequency 2.50 and 2.50, click-through 2.00% and 2.00%; review weeks, frequency 3.08 and 3.20, click-through 1.60% and 1.50%. The week of 5 October contains the 8 October change, so the weekly figures cannot show whether the movement began before it. Cost not compared because: a tracking change applies.

What the comparison shows:
- V1 on Broad 25-54 is the one pair with the pattern and no flag: frequency rose from 1.51 to 2.34, click-through fell from 1.20% to 0.75% and cost per conversion rose from $25.35 to $41.86. No entry in the change log touches it.
- V1 on Retargeting 30 day and S2 on Lookalike and interest mix also show frequency up and click-through down, each with flags, and their cost per conversion was not compared.
- S2 on Broad 25-54 shows no pattern: frequency +4.7%, click-through unchanged. S2 appears in two audiences with different results.
- Across the four compared pairs, frequency rose 30.8% and click-through fell 24.1%. The pattern is on three of four pairs, on two creatives.
- Nothing here shows why click-through fell or frequency rose, and C3 on Broad 25-54 (no baseline) is not compared, nor is cost per conversion for V1 on Retargeting 30 day or S2 on Lookalike and interest mix.

Options to test (options only, none chosen):
1. Does a new video, run beside V1 in Broad 25-54, reach people at a lower weekly frequency and a higher click-through rate than V1 over the next two weeks? Vary: creative (a new video against V1). Hold the same: audience, budget, bid, dates and landing page. First: a person makes and approves the new video and sets it up.
2. Do the frequency and click-through changes in Lookalike and interest mix follow its mix of sources or the 12 October widening? Vary: none; this is a review. Hold the same: not applicable. First: someone exports the lookalike part and the interest part separately for the same weeks, and a person reviews the audience's size before and after the widening.
3. Does the V1 pattern on Broad 25-54 continue? Vary: none; this is a hold. Hold the same: V1, the audience, the settings and the baseline window of 14 to 27 September. First: nothing changes in V1; export the weeks starting 19 and 26 October once both are complete, and run this review again.
4. Can the retargeting conversions be trusted since 8 October? Vary: none; this is a check. Hold the same: not applicable. First: someone compares the conversions counted since the tag was replaced with a second record the team trusts.

Questions for you:
1. Did the 12 October widening change the size of Lookalike and interest mix?
2. Is Broad 25-54 also used by another campaign in the account during October?
3. Did anything outside the ads change between September and October, such as stock, a promotion or a price?
4. Was the 7 October cost cap on S2 expected to change how many people it reaches?

Every figure was calculated from the export, windows, audience definitions, change log and assets supplied, using simple division and addition on the rows given. No cause is claimed, nothing has been changed in any ad account, and whether to test new creative, review the audience or hold is yours to decide.
```
