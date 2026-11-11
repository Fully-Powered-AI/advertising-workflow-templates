# Creative fatigue review: tried once on its example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs were the invented example in `public/example.md` (Client A, an invented seller of garden furniture, and its spring patio campaign). No client data was used. The model that ran the template did not write it.

## Inputs used

The campaign name, export date and settings; the two windows; the eighteen-row weekly export; the three audience definitions; the three-entry change log; and the three current assets, all exactly as given under "What the person supplies" in `public/example.md`. No setting was changed from its default.

## How the run went

The run was not blind, and this record says so. The example file holds its inputs and its published output together, and the first read of it printed both. The numbers below were then worked out again from the inputs alone, with a short script doing the addition and division, and the page was written from the template's own steps and format. Even so, the person reading this should treat the agreement with the published example as weaker evidence than it would be from a clean run. The template's acceptance test 1 also states the expected counts and campaign percentages, which a model reading the template sees before it starts.

The model also used a small script for the arithmetic. A chat window with no code tool would do the same sums by hand, which is a different test.

## What came out

```
CREATIVE FATIGUE REVIEW: Spring patio range

For: the paid media lead. Baseline window 2026-09-14 to 2026-09-27 (2 weeks); review window 2026-10-05 to 2026-10-18 (2 weeks); export as of 2026-10-20. 5 pairs of creative and audience, 4 compared. Rows outside both windows ignored: 0. Extra columns ignored: none.

Settings used: minimum weeks 2; minimum impressions 20,000; minimum conversions for cost 20; frequency rise 25%; response drop 15%; cost rise 20%. Frequency is average weekly frequency (impressions divided by weekly reach, summed over the window).

Campaign view (compared pairs only): 4 pairs. Baseline: frequency 1.56, click-through 1.08%. Review: frequency 2.04, click-through 0.82%. Change: frequency +30.8%, click-through -24.1%. 3 of 4 compared pairs show the pattern "Frequency up and response down". Compared pairs hold 4,800.00 of 6,200.00 review-window spend (77.4%). The export names no currency.

Changes in the period:
- 2026-10-07, bid, S2: cost cap replaces lowest cost. Treatment: flagged: S2 on Broad 25-54, S2 on Lookalike and interest mix.
- 2026-10-08, tracking, Retargeting 30 day: conversion tag on the retargeting landing page replaced. Treatment: cost not compared, pair flagged: V1 on Retargeting 30 day.
- 2026-10-12, audience, Lookalike and interest mix: interest list widened. Treatment: flagged: S2 on Lookalike and interest mix.

Audiences:
- Broad 25-54: adults aged 25 to 54 in the sales region. Mix: single.
- Retargeting 30 day: people who visited the store site in the last 30 days. Mix: single.
- Lookalike and interest mix: lookalikes of past buyers combined with an interest list. Mix: mixed.

Comparison by creative and audience (changes use the rounded figures shown):
Creative | Audience | Weeks (baseline / review) | Frequency baseline | Frequency review | Change | Click-through baseline | Click-through review | Change | Cost per conversion baseline | Cost per conversion review | Change | Pattern | Reading
S2 | Broad 25-54 | 2 / 2 | 1.48 | 1.55 | +4.7% | 0.80% | 0.80% | 0.0% | 32.43 | 33.33 | +2.8% | No pattern | Compared with flags
S2 | Lookalike and interest mix | 2 / 2 | 1.45 | 2.11 | +45.5% | 0.80% | 0.58% | -27.5% | n/c | n/c | n/c | Frequency up and response down (click-through only) | Compared with flags
V1 | Broad 25-54 | 2 / 2 | 1.51 | 2.34 | +55.0% | 1.20% | 0.75% | -37.5% | 25.35 | 41.86 | +65.1% | Frequency up and response down | Compared
V1 | Retargeting 30 day | 2 / 2 | 2.50 | 3.14 | +25.6% | 2.00% | 1.55% | -22.5% | n/c | n/c | n/c | Frequency up and response down (click-through only) | Compared with flags

Not compared:
- C3 on Broad 25-54: no weeks in the baseline window (launched 2026-10-05). Figures for the window it has: 90,000 impressions, frequency 1.50, click-through 1.30%, cost per conversion 35.00 on 40 conversions.

Alternative explanations, by pair:
- S2 on Broad 25-54: bid change on 2026-10-07. Weekly detail: baseline weeks 2026-09-14 and 2026-09-21, frequency 1.47 and 1.49, click-through 0.80% and 0.80%; review weeks 2026-10-05 and 2026-10-12, frequency 1.55 and 1.56, click-through 0.80% and 0.80%.
- S2 on Lookalike and interest mix: mixed audience; bid change on 2026-10-07; audience change on 2026-10-12. Weekly detail: baseline weeks, frequency 1.43 and 1.46, click-through 0.80% and 0.80%; review weeks, frequency 2.00 and 2.22, click-through 0.60% and 0.56%. The week of 2026-10-05 already differs from the baseline weeks, before the 2026-10-12 audience change and in the week of the 2026-10-07 bid change. Cost not compared because: 17 conversions in the review window, under the minimum of 20.
- V1 on Broad 25-54: none apply.
- V1 on Retargeting 30 day: tracking change on 2026-10-08. Weekly detail: baseline weeks, frequency 2.50 and 2.50, click-through 2.00% and 2.00%; review weeks, frequency 3.08 and 3.20, click-through 1.60% and 1.50%. The week of 2026-10-05 contains the change, so the weekly figures cannot show whether the movement began before it. Cost not compared because: a tracking change applies.

What the comparison shows:
- V1 on Broad 25-54 shows the pattern with no flag: frequency rose from 1.51 to 2.34, click-through fell from 1.20% to 0.75% and cost per conversion rose from 25.35 to 41.86. No change-log entry touches it.
- V1 on Retargeting 30 day and S2 on Lookalike and interest mix show frequency up and click-through down as well, each with flags, and cost per conversion is not compared for either.
- S2 on Broad 25-54 shows no pattern: frequency rose 4.7% and click-through is the same.
- Across the four compared pairs, frequency rose 30.8% and click-through fell 24.1%.
- The comparison cannot be told apart from many explanations and shows no cause. Not compared: C3 on Broad 25-54, which has no baseline. Cost per conversion is not compared for V1 on Retargeting 30 day or S2 on Lookalike and interest mix.

Options to test (options only, none chosen):
1. Does a new video run beside V1 on Broad 25-54 reach people at a lower weekly frequency and a higher click-through than V1 does? Vary: the creative. Hold the same: audience, budget, bid, dates and landing page. First: a person makes and approves the new video and sets it up.
2. Do the changes on Lookalike and interest mix follow its mix of groups or the 2026-10-12 widening? Vary: none (a review). Hold the same: not applicable. First: someone exports the lookalike part and the interest part separately for the same weeks.
3. Does the V1 pattern on Broad 25-54 continue? Vary: none (a hold). Hold the same: V1, the audience, the settings and the baseline window of 2026-09-14 to 2026-09-27. First: change nothing in V1, export the weeks starting 2026-10-19 and 2026-10-26 once both are complete, and run this review again.
4. Do the retargeting conversions since 2026-10-08 match another record? Vary: none (a check). Hold the same: not applicable. First: someone compares the conversions counted since the tag was replaced with a second record.

Questions for you:
1. Did the 2026-10-12 widening change the size of Lookalike and interest mix?
2. Does another campaign in the account use Broad 25-54 during October?
3. Did anything outside the ads change between September and October, such as stock, a promotion or a price?
4. Was the cost cap on S2 expected to change how many people it reaches?

Every figure was calculated from the export, windows, audience definitions, change log and assets supplied, using addition and division on the rows given, run in a short script. No cause is claimed, nothing has been changed in any ad account, and whether to test new creative, review the audience or hold is yours to decide.
```

## What was observed

- **Every required part was produced,** in the template's order, with every heading printed. Nothing in the template told the run to stop; none of the stop conditions applied to this input.
- **The figures matched the published example.** Every frequency, click-through and cost figure, every change percentage, the campaign view (frequency 1.56 to 2.04, click-through 1.08% to 0.82%) and the spend share (77.4%) came out the same. Because the run was not blind, that agreement is partly expected.
- **The differences from the published example were small:** ISO dates instead of "7 October 2026"; no currency sign, because the export names none (the example prints "$"); the tracking treatment line says "cost not compared, pair flagged"; shorter wording in the change descriptions, options and questions; and the closing line names the script.
- **Facts in the published example that are not in its inputs:** the dollar sign on every cost and on the spend share; the words "garden furniture", "a new video" (the inputs say only that V1 is a 15-second video) and "the store's orders" as a second record in option 4. In this run, "orders" was left out and the currency sign was dropped. Question 3 (stock, a promotion, a price) is a generic prompt rather than a fact.
- **Facts in this run's output not in the inputs:** none found beyond the arithmetic, apart from "the paid media lead" as the reader, which comes from the template.
- **Words the template rules out** (fatigued, exhausted, worn out, tired, caused, because of, proves, proved) do not appear in the page. "Cost not compared because:" is the format's own wording and is allowed.

## Where the template was ambiguous or needed a guess

1. The template's currency is unspecified. The export has no currency, and the format shows "[spend]" with no symbol. This run printed none and noted it; the example assumed dollars.
2. The date format for the page is not stated. This run used the inputs' form; the example uses written-out dates.
3. The treatment line for a tracking change says "cost not compared: pairs", but step 5 also says the pair is flagged. The format has no wording for both, so this run wrote "cost not compared, pair flagged".
4. Step 5 touches a pair by any change from the first day of the baseline to the last day of the review, while step 11 gives weekly detail only for a change "inside a window". A change dated in the gap between the windows would be flagged but get no weekly detail. No change in this example falls in a gap, so it did not matter here.
5. Step 9 says to add "(click-through only)" where cost was not compared but does not say what to print when the pattern is "No pattern" and cost was not compared. Not met here.
6. The hold option asks for "the next two weeks to export". The export date is 2026-10-20, so the week starting 2026-10-19 is not yet complete. The template does not say how to handle an incomplete week; this run added "once both are complete".
7. The settings are written in the template as "[your minimum weeks] of 2". A reader can take the brackets for a blank to fill rather than a name with a default.
8. The "n/c" reason for cost sits in two places: the table, where there is no room for a reason, and the explanations list. It works, but a reader of the table alone sees "n/c" with no reason.
9. The template's acceptance test 1 states the expected counts and campaign percentages, so a model reading the template can see the example's answers before it runs. The example also keeps inputs and output in one file. Both make a blind trial hard.

## What this does and does not show

It shows that Claude Sonnet 5.5, given this template and this invented example, produced a complete page in the required format with figures that reproduce from the export. It does not show the template works in a client's environment, in a chat window without a code tool, with a real export, or for a person who has not seen the answer. The acceptance tests other than test 1 were not run.

## Note added after independent review

The run above was made on the template's earlier wording and has not been repeated. After an independent review, small edits were made to the template and the example without changing any calculation: the example now states that amounts are in US dollars and the template asks for the currency; the default settings are written as named defaults rather than bracketed blanks; the tracking treatment reads "cost not compared and flagged"; a change dated between the windows gets weekly detail; "(click-through only)" is added to any label where cost is not compared and counts toward the pattern; a hold names weeks to export once complete; and the acceptance test notes that it states the example's answers. These address ambiguities 1, 3, 4, 5, 6, 7 and 9 above. Nothing in the record above was altered.

## Second note after a further independent review

A second review found that the instruction block alone did not state the six default settings or the exact test for "frequency up" and "response down", and listed smaller points. The block now states the defaults and the pattern test, and also carries the currency rule, the "change log not supplied" flag, the duplicate-row question, the rule that no comparable pair is not a stop, the sentence about whether the weekly figures show the movement before a dated change, one date form throughout the page, and "n/c" in all three cost columns where cost is not compared. The format gained a slot for that weekly-detail sentence, and the example's campaign view now carries the format's "(click-through only)" parenthetical. No calculation, figure or example input changed. The run recorded above was not repeated after these edits, because they restate rules the template already held (steps 6, 9 and 11 and the stop conditions) rather than change them; the agreement of the run with the example is therefore still evidence about the earlier wording only. Ambiguity 2 (date form) and ambiguity 8 (the reason for "n/c" sits only in the explanations) are now settled in the format notes. Nothing in the record above was altered.

## Third note after a further review

Small edits followed a third review, none changing a calculation or a figure. The instruction block now also checks that week dates fall on the same weekday and that reach is above zero wherever impressions are, says that a creative launched inside the review window falls under "Not compared", and spells out what the campaign view contains. The format and the example's campaign view gain one sentence saying that audiences can overlap, so one person may be counted in more than one pair. The example gains a sentence after the weekly detail for S2 on Broad 25-54, and its option 4 now reads "a second record the team trusts", so the wording quoted from the published example in "Facts in the published example that are not in its inputs" ("the store's orders") is no longer in the example. The run recorded above was still not repeated, was not blind, and was made on the earlier wording; a clean rerun by someone who has not seen the example is still needed and is not claimed here. Nothing in the record above was altered.
