# Creative fatigue review

Workflow template, version 0.1.0.

## Purpose

Take a campaign's weekly results by creative and audience, the baseline window the campaign should be judged against and a recent review window, and return one page for the paid media lead: frequency, click-through rate and cost per conversion in each window with the change between them, a marker on every pair saying whether the comparison can be trusted and why not, the alternative explanations that apply, and two to four options to test. The assistant prepares the comparison. It never states a cause for a change, never changes anything in an ad account, and never chooses between testing new creative, reviewing the audience and holding.

## When to use it and when not to

Use it when a campaign's reach or response pattern prompts a look at its creative: frequency rising, click-through easing, cost per conversion climbing, or a creative that has run a long time.

Do not use it for the following.

- Deciding which of several creatives did better, or which attribute to test. That is the creative test evidence review.
- Reporting the campaign's results to a client. That is the client campaign performance report.
- Auditing what is live against a plan. That is the inherited campaign audit.
- Working out return on spend or revenue. This version reads cost per conversion only.
- Pausing, replacing, scaling or editing anything in an ad account. The assistant has no access to one and a person makes every change.

## Roles

- **Starts it and supplies the inputs:** the paid media lead or a media analyst.
- **Checks the figures:** an analyst or the media lead, who recomputes the table from the export.
- **Decides** whether to test new creative, review the audience or hold: the paid media lead, with the creative owner. The assistant never does.

## Inputs

1. **The weekly export,** one row per creative, audience and week. Default headers: `week_start`, `creative_id`, `audience`, `spend`, `impressions`, `reach`, `clicks`, `conversions`. `reach` is the number of different people reached in that week. Extra columns are ignored and named in the output. If a header does not match, stop and ask which column is which; never guess. If the same week, creative and audience appears twice, stop and ask whether the rows should be added together.
2. **The windows.** `baseline_start`, `baseline_end`, `review_start` and `review_end`, each a date; every window is made of whole weeks and the review window comes after the baseline window. The baseline is the campaign's own, chosen by the paid media lead. If a window is missing, stop and ask; never choose one.
3. **The audience definitions,** one row per audience. Default headers: `audience`, `description`, `mix`, `size_note`. `mix` is single or mixed; mixed means the audience combines groups that could behave differently. Every audience in the export must have a row; if one does not, stop and ask.
4. **The change log,** one row per change. Default headers: `date`, `change_type`, `scope`, `description`. `change_type` is one of tracking, audience, bid, budget, offer, price, landing_page, creative, placement or other. `scope` is "all", a list of creative IDs or a list of audience names, all taken from the export. A scope that names anything else is not accepted and the assistant stops and asks which creatives and audiences it covers. If the change log is not supplied, say "Change log not supplied." at the top, and mark every compared pair as "Compared with flags" with the flag "change log not supplied".
5. **The current assets,** one row per creative. Default headers: `creative_id`, `format`, `launch_date`, `status`, `last_edited`. `status` is live or paused. Every creative in the export must have a row.
6. **The campaign name, the currency of the spend column and the export date.** If the currency is missing, print no currency sign and write "currency not supplied"; if the date is missing, write "export date not supplied".
7. **Optional settings,** each with its default: minimum weeks, 2 in each window; minimum impressions, 20,000 in each window; minimum conversions, 20 in each window for cost to be compared; frequency rise, 25 per cent; response drop, 15 per cent for click-through; cost rise, 20 per cent.

## The procedure

1. **Check the inputs.** Headers match; no row repeats; dates read as dates and fall on the same weekday; spend, impressions, reach, clicks and conversions are numbers of zero or more; clicks do not exceed impressions; reach does not exceed impressions; reach is above zero wherever impressions are; each window is whole weeks and the windows do not overlap; no creative has a row dated before its `launch_date`. On any failure, stop and name the rows.
2. **Assign rows to windows.** A row belongs to the baseline window when its week falls inside it, and to the review window likewise. Rows in neither are ignored; report how many.
3. **Work out each pair.** A pair is one creative in one audience. For each window and pair, add spend, impressions, reach, clicks and conversions over its weeks. Frequency is summed impressions divided by summed weekly reach, to two decimals; call it average weekly frequency, because weekly reach counts the same person again in a later week. Click-through rate is clicks divided by impressions as a percentage, to two decimals. Cost per conversion is spend divided by conversions, to the cent.
4. **Find the pairs that cannot be compared.** A pair is not compared when it has fewer than the minimum weeks in either window, or fewer than the minimum impressions in either window. Report its figures for the window it has, as reported, and the reason. A creative launched inside the review window has no baseline and falls here.
5. **Apply the change log.** A change touches a pair when its date falls from the first day of the baseline window to the last day of the review window and its scope is "all", names the pair's creative or names the pair's audience.
   - Tracking: cost per conversion is not compared for that pair, because conversions before and after the change may not be counted the same way. Frequency and click-through are still compared and flagged.
   - Audience: flag the pair, because the people being reached changed.
   - Creative, offer, price or landing_page: flag the pair, because the thing the audience saw or landed on changed.
   - Bid, budget, placement and other: flag the pair and note the change; delivery may differ.
   - A change with scope "all" is a shared change; note it once and flag every pair.
6. **Check conversions.** Cost per conversion is compared only when the pair has at least the minimum conversions in both windows and no tracking change touches it. Otherwise write "n/c" and give the reason.
7. **Flag the audience mix.** A pair in an audience marked mixed is flagged "mixed audience".
8. **Compare.** For each compared pair, the change in frequency, click-through and cost is the review figure over the baseline figure, minus one, as a percentage to one decimal, calculated from the rounded figures shown. State the changes with a plus or minus sign.
9. **Name the pattern,** with no cause attached. "Frequency up and response down" when frequency rose by at least the frequency rise and either click-through fell by at least the response drop or, where cost is compared, cost rose by at least the cost rise. "Frequency up, response steady" when only frequency rose by that much. "Response down, frequency steady" when only response worsened by that much. Otherwise "No pattern". Add "(click-through only)" to any of these labels, including "No pattern", where cost was not compared. These labels describe numbers; none of them says why.
10. **Mark the reading of each pair.** "Compared" when no flag applies, "Compared with flags" when any does, "Not compared" for step 4.
11. **Give the weekly detail** for every compared pair that a dated change touches, inside either window or in the gap between them: its frequency and click-through for each baseline week and each review week, so the reader can see whether the movement began before or after the change.
12. **Build the campaign view** from the compared pairs only: summed impressions, reach and clicks in each window, with frequency and click-through worked out as in step 3, the change in each, the number of compared pairs showing the pattern (the "(click-through only)" variant counts) and the share of review-window spend that sits in compared pairs. Add that audiences can overlap, so one person may be counted in more than one pair, because the view adds weekly reach across pairs.
13. **Write what the comparison shows,** a few sentences using only the table. Words never used: fatigued, exhausted, worn out, tired, caused, because of, proves, proved. Allowed: "rose", "fell", "is the same", "shows the pattern", "cannot be told from". Then say in one sentence, however many pairs it names, what cannot be said, naming the pairs not compared and the cost figures not compared.
14. **Write two to four options to test,** unranked and unrecommended. Each has the question it answers, what to vary (or "none" for a review, a check or a hold), what to hold the same (write "not applicable" for a review or a check) and what must happen first. Cover the three choices the lead has (test new creative, review the audience, hold) where the data supports each, and add a check of tracking when a tracking change applies. For a hold, name the next two weeks to export, to be exported once both are complete (a week still running on the export date is not complete), and say the baseline stays the same.
15. **List the questions for the lead,** at most five, each one whose answer could change the reading.
16. **Return it to the person who asked,** with the trace line.

## Exceptions and stop conditions

- **A header does not match, a row repeats, an audience or creative has no definition, or a window is missing:** stop and ask.
- **A change-log scope names something the export cannot resolve to creative IDs or audience names:** stop and ask which creatives and audiences it covers.
- **Dates, numbers, clicks, impressions or reach do not make sense:** stop and name the rows.
- **No pair can be compared:** not a stop. Print the settings, the change log and the audiences, list every pair under "Not compared", write "None." under the table, the campaign view and "What the comparison shows", and give options that would make a comparison possible.
- **Asked what caused a change, whether the creative is fatigued, or whether the audience is saturated:** decline; the page shows the numbers and the other explanations, and says why a rate alone cannot show the cause.
- **Asked to pause, replace, refresh or scale a creative, change a budget or bid, or make any change in an ad account:** decline; the paid media lead decides and a person makes any change.
- **Asked to choose a baseline window, lower a minimum so a pair can be compared, or compare cost where a tracking change applies:** decline. A person may change a setting before the run; the page then states the setting used.
- **Asked which creative did better:** decline and point to the creative test evidence review.
- **Asked for return on spend or revenue:** say this version does not read revenue.
- **The export contains personal data about people who saw the ads:** stop and ask for an export without it.

## Output format

```
CREATIVE FATIGUE REVIEW: [campaign name]

For: [paid media lead]. Baseline window [start] to [end] ([n] weeks); review window [start] to [end] ([n] weeks); export as of [date]. [n] pairs of creative and audience, [n] compared. Rows outside both windows ignored: [n]. Extra columns ignored: [names, or "none"].

Settings used: minimum weeks [n]; minimum impressions [n]; minimum conversions for cost [n]; frequency rise [n]%; response drop [n]%; cost rise [n]%. Frequency is average weekly frequency (impressions divided by weekly reach, summed over the window).

Campaign view (compared pairs only): [n] pairs. Baseline: frequency [x], click-through [x]%. Review: frequency [x], click-through [x]%. Change: frequency [+/-x]%, click-through [+/-x]%. [n] of [n] compared pairs show the pattern "Frequency up and response down" (the "(click-through only)" variant counts). Compared pairs hold [spend] of [spend] review-window spend ([%]). Audiences can overlap, so one person may be counted in more than one pair.

Changes in the period:
- [date], [type], [scope]: [what changed]. Treatment: [cost not compared: pairs / cost not compared and flagged: pairs / flagged: pairs / shared change, all pairs flagged / no pair touched].

Audiences:
- [Audience]: [description]. Mix: [single / mixed].

Comparison by creative and audience (changes use the rounded figures shown):
Header row, printed first: Creative | Audience | Weeks (baseline / review) | Frequency baseline | Frequency review | Change | Click-through baseline | Click-through review | Change | Cost per conversion baseline | Cost per conversion review | Change | Pattern | Reading
[one row per compared pair, in creative then audience order]

Not compared:
- [Creative] on [audience]: [reason]. Figures for the window it has: [impressions, frequency, click-through, cost per conversion with conversions].

Alternative explanations, by pair:
- [Creative] on [audience]: [every flag, each with its date or reason]. Weekly detail: [frequency and click-through for each week, baseline weeks then review weeks, where a dated change touches the pair]. [Where the weekly figures do or do not show whether the movement was present before the dated change, one sentence saying so, with no cause.] [Cost not compared because: reason.]

What the comparison shows:
- [sentence]

Options to test (options only, none chosen):
1. [Question]. Vary: [one thing, or "none"]. Hold the same: [list, or "not applicable"]. First: [what must happen].

Questions for you:
1. [question]

Every figure was calculated from the export, windows, audience definitions, change log and assets supplied, using [tool or method]. No cause is claimed, nothing has been changed in any ad account, and whether to test new creative, review the audience or hold is yours to decide.
```

Print every heading in the format. Where a section has nothing to report, write "None." under it. The change log line reads "Change log not supplied." when there is no log. Separate table cells with " | "; padding the cells so the columns line up is optional. Write every date in one form throughout the page, either as it appears in the export or as day, month in words, year. Where cost is not compared, print "n/c" in all three cost columns, even if one window has enough conversions; the reason is given under "Alternative explanations, by pair".

## Reviewer checklist

1. Every frequency, click-through and cost figure in the table matches the export, summed by window. (Analyst)
2. Every change percentage follows from the rounded figures shown. (Analyst)
3. Every change-log entry has a treatment and every pair it touches is flagged. (Media lead)
4. No cost per conversion is compared where a tracking change applies or conversions are under the minimum. (Media lead)
5. Pairs not compared are listed with a reason, and none appears in the table. (Analyst)
6. The page contains no statement of cause and none of the words the template rules out. (Media lead)
7. The options are unranked, and the page changes nothing and recommends nothing. (Paid media lead)

## Acceptance tests

Proposed tests. Only the first has been run, in the trial recorded with the example. It states the example's answers, so a run that reads this list first is not blind.

1. **The invented campaign in the example.** Expected: four pairs compared, one not compared; the pattern on three pairs; cost not compared for V1 on Retargeting 30 day and S2 on the lookalike and interest mix; campaign frequency +30.8% and click-through -24.1%.
2. **Header mismatch.** A column named "ad" instead of `creative_id`. Expected: stops and asks which column is which.
3. **Missing window.** No review dates. Expected: stops and asks; chooses nothing.
4. **Repeated row.** The same week, creative and audience twice. Expected: stops and asks whether to add the rows.
5. **Tracking change with scope "all".** Expected: cost not compared for every pair, a shared change noted, every pair flagged.
6. **Short run.** A creative with one week in the review window and none in the baseline. Expected: listed under "Not compared"; absent from the table and the campaign view.
7. **Conversions under the minimum.** A pair with 17 conversions in the review window. Expected: cost shown as "n/c" with the reason; frequency and click-through still compared.
8. **Scope names an ad set.** Expected: stops, names the entry, asks which creatives and audiences it covers.
9. **Asked whether the creative is fatigued.** Expected: declines to name a cause, offers the table and the other explanations.
10. **Asked to pause a creative.** Expected: declines; a person decides and makes any change.
11. **Boundary.** A frequency rise of exactly 25.0% with click-through down 15.0%. Expected: both count as at the threshold, so the pattern is named.
12. **Nothing compared.** Every pair is a short run. Expected: not a stop; "None." under the table, campaign view and "What the comparison shows", with options to make a comparison possible.

## Instructions for the AI assistant

```
You prepare a creative fatigue review for a paid media lead. You never
change anything in an ad account, never state what caused a change, and
never decide whether to test new creative, review the audience or hold.
Those choices are the paid media lead's.

The user will supply: a weekly export by creative, audience and week
(week_start, creative_id, audience, spend, impressions, reach, clicks,
conversions); the baseline and review windows; the audience definitions
(audience, description, mix, size_note); the change log (date,
change_type, scope, description); the current assets (creative_id,
format, launch_date, status, last_edited); the campaign name, the currency of the spend column and the export date;
optional settings. The defaults are: minimum weeks 2 in each window;
minimum impressions 20,000 in each window; minimum conversions 20 in each
window for cost to be compared; frequency rise 25 per cent; response drop
15 per cent for click-through; cost rise 20 per cent. If a header does not
match, stop and ask which column is which. If a week, creative and
audience appears twice, stop and ask whether the rows should be added
together. If a window is missing, or an audience or creative has no
definition, stop and ask. Never guess a column and never choose a window.
If the change log is missing, say "Change log not supplied." at the top
and mark every compared pair as compared with flags, with the flag "change
log not supplied". If the currency is missing, print no currency sign and
write "currency not supplied"; if the export date is missing, write
"export date not supplied".

1. Check the inputs: dates that fall on the same weekday, numbers of zero
   or more, clicks not above impressions, reach not above impressions and
   above zero wherever impressions are, whole-week windows that do not
   overlap, no row before its creative's launch date, and every
   change-log scope being all, creative IDs or audience names from the
   export. On any failure stop and name the rows. If the export holds
   personal data about people who saw the ads, stop and ask for another.
2. Assign each row to the baseline window, the review window, or neither;
   count the rows in neither.
3. For each creative and audience pair and each window, sum the figures.
   Frequency is summed impressions divided by summed weekly reach, to two
   decimals. Click-through is clicks divided by impressions as a
   percentage, to two decimals. Cost per conversion is spend divided by
   conversions, to the cent.
4. A pair with fewer weeks than the minimum weeks, or fewer impressions
   than the minimum impressions, in either window is not compared; list it
   with the figures it has and the reason. A creative launched inside the
   review window has no baseline and falls here.
5. Apply the change log to each pair by date (from the start of the
   baseline to the end of the review) and scope. A tracking change means
   cost per conversion is not compared for that pair, and the pair is
   flagged. Audience, creative, offer, price, landing page, bid, budget,
   placement and other changes flag the pair. A change with scope all is shared: note it once and flag
   every pair. A pair in a mixed audience is flagged.
6. Compare cost only where the pair has at least the minimum conversions
   in both windows and no tracking change applies; otherwise print n/c in
   all three cost columns, even if one window qualifies, and give the
   reason in the explanations.
7. Changes are review over baseline minus one, as a percentage to one
   decimal, from the rounded figures shown, with a sign.
8. Name the pattern. Frequency is up when it rose by at least the
   frequency rise. Response is down when click-through fell by at least
   the response drop or, where cost is compared, cost rose by at least the
   cost rise. Labels: "Frequency up and response down" when both are true;
   "Frequency up, response steady" when only frequency is up; "Response
   down, frequency steady" when only response is down; otherwise "No
   pattern". Add "(click-through only)" to any label, including "No
   pattern", where cost was not compared. A threshold met exactly counts
   as met. These describe numbers and say nothing about cause.
9. Mark each pair Compared, Compared with flags or Not compared. Give
   weekly frequency and click-through for any compared pair that a dated
   change touches, inside either window or in the gap between them, then
   one sentence saying whether those weeks show the movement before the
   change or cannot show it.
10. Build the campaign view from compared pairs only: summed impressions,
    reach and clicks in each window, with frequency and click-through
    worked out as in step 3 and the change in each, the number of compared
    pairs showing the pattern (the "(click-through only)" variant counts)
    and the share of review-window spend that sits in compared pairs. Add
    that audiences can overlap, so one person may be counted in more than
    one pair.
    If no pair can be compared, do not stop: print the settings, the
    change log and the audiences, list every pair under Not compared, write
    "None." under the table, the campaign view and what the comparison
    shows, and give options that would make a comparison possible.
11. Write what the comparison shows from the table alone, then what cannot
    be said. Never use the words fatigued, exhausted, worn out, tired,
    caused, because of, proves or proved.
12. Write two to four options to test, unranked: the question, what to
    vary (or none), what to hold the same (or not applicable), and what
    must happen first. For a hold, say the weeks are exported once
    complete. Cover testing new creative, reviewing the audience
    and holding where the data supports each; add a tracking check when a
    tracking change applies. Recommend none. Add at most five questions.
13. Use the output format exactly and print every heading. Where a
    section is empty write "None.". Separate table cells with " | ". Write
    dates in one form throughout. Print n/c in all three cost columns
    where cost is not compared. End with the trace line.

If asked what caused a change, whether the creative is fatigued or the
audience saturated, to pause, replace or scale anything, to choose a
baseline, to lower a minimum so a pair can be compared, or to compare cost
where a tracking change applies, decline. If asked which creative did
better, decline and point to the creative test evidence review. If asked
for return on spend or revenue, say this version does not read revenue.
```

## What to customize

- Your baseline window for each campaign and the length of the review window.
- The minimum weeks, minimum impressions, minimum conversions, frequency rise, response drop and cost rise.
- Which audiences you treat as mixed.
- What goes in the change log and who keeps it.
- Which response measure matters to you, if click-through is not the right one for the campaign's goal.
- Who must read the page before a creative is paused, replaced or refreshed.
- Which exports the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI. Tried once on its invented example in Claude (Sonnet 5.5) on 10 November 2026, with the record published, and not yet tested in a client environment.
