# Lead quality pattern review

Capability template, version 0.1.0.

## Purpose

Prepare, for one period, a review of the leads an acquisition program produced and what became of them, split by source, landing page, location, device and timing. The review shows where the share of useful leads sits well below the overall share, how those patterns overlap, which measurement faults could produce a pattern, and a short list of cases the acquisition lead can check with sales. The assistant prepares; it never changes targeting, pauses or edits anything, contacts anyone, states a cause or says a source is dishonest. The acquisition lead decides what is investigated, and verifies each finding with sales before any targeting change.

## When to use it and when not to

Use it when sales feedback or campaign results raise a lead-quality concern and a lead outcomes export for a stated period is available. Run it again on a later period to see whether a pattern held.

Do not use it:

- to audit a campaign account that someone else built; that is the inherited campaign audit;
- to review what a form asks for and where people leave it; that is the lead form field review;
- to explain why two reports show different totals; that is the metric definition reconciliation;
- to decide that a source, a page or a location should be switched off. The review shows patterns in the records supplied. A pattern is a place to look, never a reason by itself;
- to decide whether a source is fraudulent. If asked, decline: unusual behaviour in a set of records is not proof of that, and the review lists measurement faults and unverified cases instead.

## Roles

- **Runs it:** the acquisition lead, or the analyst who reports to them.
- **Decides what is investigated:** the acquisition lead.
- **Verifies cases and findings:** sales development, or whoever contacted the leads. Nothing is taken to targeting until they have.
- **Checks measurement faults:** the tracking owner.
- **Approves any change to targeting, budget or pages:** the acquisition lead, afterwards, outside this capability.

## Inputs

1. **Review settings,** as plain text: the business; how a lead is defined (what has to happen for a row to exist); the period; the as-of date; the outcomes that count as useful, as not useful and as open, each as a list of the exact words in the export; the time zone of `created_at`; and the acquisition lead. Defaults, said aloud when used: outcome window 14 days, minimum 20 settled leads to read a segment, flag gap 15 percentage points. If the period, the as-of date or any of the three outcome lists is missing, stop and ask.
2. **Scope,** as plain text: the sources in use, the landing pages in use, the targeted locations and the devices expected (a device list of "all" checks nothing). If missing, run without it and say that no value could be checked against a scope.
3. **Known changes,** as dated lines: a form, tag, page, budget or targeting change inside the period. Optional; if none, say none were supplied.
4. **Lead outcomes export** (leads.csv), one row per lead, with these headers: `lead_id`, `created_at`, `source`, `landing_page`, `location`, `device`, `outcome`. `created_at` is `YYYY-MM-DD HH:MM`. If the file is missing, stop. If a header does not match, stop and ask which column is which; never guess. If `created_at` is in another shape, stop and ask. Ask for no names, emails or phone numbers; if some are pasted, do not copy them into the review.
5. **Sales feedback** (feedback.csv), one row per note, with these headers: `note_id`, `date`, `from_role`, `lead_ids`, `note`. `lead_ids` may be empty or hold several ids separated by semicolons. Optional; if missing, write that none was supplied. If a header does not match, stop and ask.

The assistant works from the files and notes the person supplies. It needs no connection to the ad platforms, the analytics tool or the customer records, and never asks for a password or a login code.

## The procedure

1. **Check the inputs.** Confirm one period and one export. Compare every `outcome` value, ignoring capitals and spaces at the ends, with the three lists in the settings. A value in none of them stops the review: ask which list it belongs to. A blank outcome is treated as open.
2. **Clean the rows, in this order.**
   - Where a `lead_id` appears more than once, keep the first row in file order and remove the others. Count them and list their ids. A removed row counts toward a segment by its own values.
   - Exclude rows whose date is before the period start or after the period end. Count them and list their ids and dates.
   - Treat values that differ only in capitals or spaces at the ends as one value, printed in the spelling first seen. List each merge. A blank dimension value is printed as `(blank)`.
3. **Class each lead.** A lead is useful or not useful if its outcome is on that list; these are the settled leads. It is open if its outcome is on the open list or blank. An open lead created on or after the as-of date minus the outcome window is recent; an older open lead is stalled. Open leads stay in lead counts and are left out of every rate. Once the rows are cleaned and classed, if there are no settled leads, or fewer than the minimum, stop and say so.
4. **Overall rate.** Useful settled leads divided by settled leads. Round percentages and points to one decimal place, always from the unrounded figures (a figure exactly halfway rounds to the even digit, so 81.25 prints as 81.2), and compare against the flag gap using the unrounded figures.
5. **Segments.** Split the leads by six dimensions, each segment being one value of one dimension:
   - source, landing_page, location and device, as they appear in the export after step 2;
   - day part of `created_at`: Overnight 00:00 to 05:59, Morning 06:00 to 11:59, Afternoon 12:00 to 17:59, Evening 18:00 to 23:59;
   - week, labelled "week of" and the Monday date; a week cut short by the start or end of the period keeps that label, is not marked differently and is counted as it stands.
   For each segment give leads, settled, useful and the useful rate. List segments with at least one lead only. Within a dimension, run from most leads to fewest (ties by name), except day parts in clock order and weeks in date order. A segment with fewer settled leads than the minimum is "Too few to read": show its counts and no rate, and judge nothing from it.
6. **Status of each segment.** Difference is the segment's rate minus the overall rate, in points. If the difference is at least the flag gap below, the segment is "Below overall" and becomes a numbered pattern, numbered in the order the segments are printed. At least the flag gap above: "Above overall", context only. Otherwise "Within the gap". Weeks and day parts are judged the same way.
7. **For each pattern, write:**
   - **Facts:** leads, settled, useful, rate, points against overall, and the useful leads against the number expected at the overall rate (settled times the overall rate, one decimal place), with the difference. Say "fewer"; never "lost" or "wasted".
   - **Busiest day:** the date with the most of the segment's leads (earliest on a tie), the count and the share of the segment's leads.
   - **Overlaps:** for each other pattern in a different dimension, the settled leads in both, how many were useful, and the share of the smaller pattern's settled leads they make. List the pair only at 50 percent or more; otherwise "none at 50 percent or more". Overlap shows that the same leads sit in both segments. It never says which one matters.
   - **Checks that touch this pattern:** list each that applies: a repeated row removed from this segment; the segment's value is not in the scope supplied; open leads are 25 percent or more of the segment's leads; one day holds 40 percent or more of the segment's leads and the segment has at least the minimum number of settled leads. Otherwise "none".
   - **Cases to verify with sales:** up to five of the segment's not-useful leads, earliest first (by `created_at`, then `lead_id`), each as the id, the time and the outcome exactly as supplied. Say what to ask sales: what the contact found, and whether the outcome label matches what happened.
   - **Question for the acquisition lead:** take the pattern to sales with the cases, hold it, or set it aside. State that the review proposes no targeting change and gives no cause. Where a check touches the pattern, add that the tracking owner can be asked about it.
8. **Context line.** List the segments that are "Above overall", with their rates, and say no cases are listed for them.
9. **Possible measurement faults.** Report these five, each with a count and who can verify it:
   - repeated `lead_id`s removed (the tracking owner);
   - rows dated outside the period (the tracking owner);
   - blank values by dimension, with the share of leads reviewed, saying which are at 10 percent or more (the tracking owner);
   - values not in the scope supplied (source, landing page, location, device), by dimension, with the share and the values. State that this is a difference between records and scope, not a finding about those leads (the acquisition lead, on whether the scope is current);
   - stalled open leads, with their ids (sales development).
10. **Known changes.** For each change supplied, show settled and useful leads, and the rate, for the period before its date and from its date. If either side has fewer settled leads than the minimum, write "too few to compare" with the counts. Draw no conclusion from the two figures.
11. **Sales feedback.** Quote each note as supplied. For each `lead_id` in it, give the lead's time, source, page, location, device and outcome, and the patterns it falls in. An id not in the export is "not in the export for this period"; ask the sender for the date and source. A note with no ids gets no cases; ask the sender which leads they mean.
12. **Close.** List what was not assessed (segments too few to read, anything not supplied) and end with the trace line. Return the draft to the person who ran it only.

## Exceptions and stop conditions

- **A header does not match the default:** stop and ask which column is which.
- **An outcome value is on no list:** stop and ask which list it belongs to.
- **No settled leads, or fewer than the minimum overall, once the rows are cleaned:** stop and say so.
- **`created_at` is not in the stated shape:** stop and ask.
- **No scope supplied:** run on; write that no value was checked against a scope.
- **Segment under the minimum:** "Too few to read"; no rate, no pattern.
- **Asked to say a source is fraudulent, to name a cause, to say what a pattern means for a source's quality, to rank sources by what should be cut, to change or pause targeting, or to contact sales or a vendor:** decline. The acquisition lead decides, after verifying with sales. Offer the cases and the faults list instead.
- **Names or contact details pasted in:** do not copy them; ask for the lead_id only.

## Output format

```
LEAD QUALITY PATTERN REVIEW: [business], [from] to [to]

For: [acquisition lead]. Period [from] to [to]; as of [date]. Settings: minimum [n] settled leads to read a segment, flag gap [n] points, outcome window [n] days.

DATA CHECK
Rows received: [n]. Removed as repeats of a lead_id already seen: [n] ([ids], or none). Excluded as outside the period: [n] ([ids with dates], or none). Leads reviewed: [n].
Settled leads: [n] ([n] useful, [n] not useful). Open leads: [n] ([n] created on or after [date], [n] older).
Overall useful rate: [n] of [n] settled ([%]).
Values read as the same after ignoring capitals and spaces at the ends: [list, or none].

KNOWN CHANGES IN THE PERIOD
[date]: [change]. Before: [n] settled, [n] useful ([%]). From that date: [n] settled, [n] useful ([%]). [Note on the minimum.] (Or "None supplied.")

SEGMENTS
A segment with no leads is not listed.
Within a dimension, segments run from most leads to fewest, except day parts in clock order and weeks in date order.

[Dimension]
[segment]: [n] leads, [n] settled, [n] useful ([%]), [+/-n.n] points against overall. [Below overall: pattern n. / Above overall. / Within the gap.]
[segment]: [n] leads, [n] settled, [n] useful. Too few to read.
(one block per dimension: Source, Landing page, Location, Device, Day part, Week)

PATTERNS

[n]. [Dimension]: [segment]
Facts: [n] leads, [n] settled, [n] useful ([%]), [+/-n.n] points against overall ([%]). Useful leads: [n] against [n.n] at the overall rate, [n.n] fewer.
Busiest day: [date], [n] of [n] leads ([%]).
Overlaps: [pattern n ([Dimension]: [segment]): [n] settled leads in both, [n] useful ([%]), [%] of the smaller pattern's settled leads; ...], or none at 50 percent or more.
Checks that touch this pattern: [list, or none].
Cases to verify with sales: [lead_id ([created_at], [outcome]); ...]. Ask sales what the contact found and whether the outcome label matches what happened.
Question for the acquisition lead: take this pattern to sales with these cases, hold it, or set it aside? The review proposes no targeting change and states no cause. [The tracking owner can be asked about the check named above.]

(If there is no pattern: "No segment is below overall by the flag gap." in place of the numbered blocks.)

Segments above overall, for context only: [dimension, segment ([%]); ...], or none. No cases are listed for them.

POSSIBLE MEASUREMENT FAULTS
1. Repeated lead_id: [n] rows removed ([ids]). Who can verify: the tracking owner, [what to ask].
2. Dated outside the period: [n] rows excluded ([ids, times]). Who can verify: the tracking owner, [what to ask].
3. Blank values: Source [n] ([%]); Landing page [n] ([%]); Location [n] ([%]); Device [n] ([%]). [Which are at 10 percent or more, or "None is at 10 percent or more of leads reviewed."] Who can verify: the tracking owner.
4. Values not in the scope supplied: Source [n]; Landing page [n]; Location [n] ([%]; [values]); Device [n]. This is a difference between the records and the scope, not a finding about those leads. Who can verify: the acquisition lead, on whether the scope is current. (Or "No scope supplied; nothing was checked.")
5. Open leads older than [n] days: [n] ([ids with outcome]). Who can verify: sales development, on whether the outcome was never updated.

SALES FEEDBACK
[note_id] ([date], [role]): "[note]"
[lead_id]: [created_at], source [..], page [..], location [..], device [..], outcome [..]; falls in pattern(s) [n, or none].
[or "[lead_id]: not in the export for this period. Ask the sender for the date and source."]
[or "No lead_ids given, so no cases to check. Ask the sender which leads they mean."]
(Or "None supplied.")

Not assessed: [segments too few to read; anything not supplied; "Open leads are left out of every rate."]

Every figure traces to the lead outcomes export for [period], the settings, the scope, the known changes and the sales notes supplied. The review changes no targeting and no record, accuses no source of anything and sends nothing; the acquisition lead decides what is investigated and verifies findings with sales before any targeting change.
```

## Reviewer checklist

1. The overall rate and every segment rate match their two counts, and each flag was applied to the unrounded difference. (Analyst)
2. Segment counts within a dimension add to the leads reviewed, except for open leads, which are in lead counts but not in rates. (Analyst)
3. Every pattern is a segment at least the flag gap below overall with enough settled leads; none is a segment that was too few to read. (Acquisition lead)
4. Each case is a real lead_id from the export, with its outcome as supplied. (Sales development)
5. No sentence states a cause, a motive or a reason for a pattern, calls a source dishonest, or recommends changing targeting. (Acquisition lead)
6. The measurement faults list has all five entries, each with a count and an owner. (Tracking owner)
7. Overlaps are reported as overlaps, never as one pattern explaining another. (Analyst)
8. The review changes and sends nothing, and names no person from the leads. (Acquisition lead)

## Acceptance tests

Proposed tests. None has been run.

1. **Normal run.** The invented example in the public folder. Expected: 86 leads reviewed, 76 settled, overall 57.9 percent, four patterns, five faults, three sales notes handled.
2. **Header mismatch.** The export names a column `result` in place of `outcome`. Expected: stops and asks which column is which.
3. **Unknown outcome.** A row with the outcome "Callback". Expected: stops and asks which list it belongs to.
4. **Small segment.** A segment with 6 settled leads and none useful. Expected: "Too few to read"; no pattern.
5. **No pattern.** Every segment within the gap. Expected: the no-pattern line, the faults list and the close, with nothing invented.
6. **No scope.** The scope is missing. Expected: runs on; fault 4 says nothing was checked.
7. **Asked for a cause.** "Is the Social paid source sending fake leads?" Expected: declines; offers the cases and the faults list.
8. **Note with an unknown id.** A feedback note names a lead that is not in the export. Expected: "not in the export for this period" and a request for the date and source.

## Instructions for the AI assistant

```
You prepare a lead quality pattern review for the acquisition lead. You
never change or pause targeting, edit any account or record, contact anyone
or send the review, and you never decide anything: the acquisition lead
chooses what is investigated and verifies findings with sales before any
targeting change is approved. You state no cause, give no motive, and say
no source, page, location or person is dishonest or fraudulent.

The user will supply: review settings; a scope; known changes; a lead
outcomes export; sales feedback. Defaults if not given, said aloud: outcome
window 14 days, minimum 20 settled leads to read a segment, flag gap 15
points. Default headers: leads.csv has lead_id, created_at, source,
landing_page, location, device, outcome, with created_at as YYYY-MM-DD
HH:MM; feedback.csv has note_id, date, from_role, lead_ids, note. If a
header does not match, stop and ask which column is which. If the period,
the as-of date or any outcome list is missing, or the export is missing,
stop and say so. Ask for no names or contact details and do not copy any
into the review.

1. Compare each outcome, ignoring capitals and end spaces, with the useful,
   not useful and open lists. A value on no list: stop and ask. A blank
   outcome is open.
2. Remove repeated lead_ids (keep the first row in file order; count and
   list them; a removed row counts toward a segment by its own values). Exclude rows dated outside the period (count and list them).
   Treat values that differ only in capitals or end spaces as one value in
   the spelling first seen, and list each merge. Print a blank value as
   (blank).
3. Settled leads are useful or not useful. Open leads (open list or blank)
   are recent if created on or after the as-of date minus the window,
   otherwise stalled. Open leads stay in lead counts and out of every rate. After cleaning and
   classing, no settled leads, or fewer than the minimum: stop.
4. Overall rate is useful over settled. Round percentages and points to one
   decimal place from unrounded figures (exactly halfway rounds to the even
   digit, so 81.25 prints 81.2); compare to the flag gap unrounded.
5. Segment by source, landing_page, location, device, day part (Overnight
   00:00 to 05:59, Morning 06:00 to 11:59, Afternoon 12:00 to 17:59,
   Evening 18:00 to 23:59) and week (labelled "week of" and the Monday
   date; a week cut short by the period keeps that label, unmarked). List only segments with a lead. Order by most leads, ties by
   name; day parts in clock order; weeks in date order. Under the minimum
   settled: "Too few to read", counts only, no rate.
6. A segment at least the flag gap below overall is a numbered pattern, in
   print order. At least the gap above is context only. Otherwise within
   the gap.
7. For each pattern write: facts (counts, rate, points against overall,
   useful against expected at the overall rate, "fewer"); busiest day;
   overlaps with patterns in other dimensions, listed at 50 percent or more
   of the smaller pattern's settled leads, never as an explanation; checks
   that touch it (repeated row removed from it, value not in scope, open
   leads 25 percent or more, one day holding 40 percent or more of a
   segment with at least the minimum number of settled leads); up to five earliest not-useful lead ids
   as cases for sales with outcomes as supplied; and one question for the
   acquisition lead: take it to sales, hold it, or set it aside, with no
   targeting change proposed and no cause given.
8. List segments above overall as context only, with no cases.
9. List the five measurement faults (repeats, outside the period, blanks,
   values not in scope: source, page, location, device; stalled open leads), each with a count and who can
   verify it. A value not in scope is a difference between records and
   scope, not a finding about those leads.
10. For each known change show settled, useful and rate before it and
    from it; "too few to compare" under the minimum; no conclusion.
11. Quote each sales note, then each lead in it with its details and
    patterns; an unknown id is "not in the export for this period"; a note
    with no ids gets no cases.
12. Use the output format exactly. Empty parts say what is empty and why.
    Return the draft to the person who ran it only.

Never say what a pattern means for a source's quality, name a cause or a
motive, or call anything fraud. If asked to, or asked to rank sources for
cutting, change or pause targeting, or contact anyone, decline and offer
the cases and the faults list.
```

Paste this block as custom instructions, followed by the output format above.

## What to customize

- Your column names, or rename them once to the defaults.
- Your outcome words, and which are useful, not useful and open.
- The outcome window, the minimum settled leads and the flag gap.
- Your day parts, if your business hours differ from the defaults.
- Your scope lists and where you keep the known-changes log.
- Who verifies with sales, who owns tracking, and who may approve a targeting change afterwards.
- Which exports the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI from its own published map of the work. Tried once on its invented example, in Claude on 10 November 2026, with the record published beside it. Edited after an independent review and not run again: the minimum-leads test now follows cleaning, check four counts settled leads, a removed repeat row counts by its own values, points round from unrounded figures with an exact tie going to the even digit, a part-week keeps its label, the device is checked against the scope, and the segment-order line names the exceptions. Each settles a point in the way the run already chose, except the device check, which the run did not make. Not yet tested in a client environment.
