---
name: "lead-quality-pattern-review"
description: "Prepare, for one period, a review of the leads an acquisition program produced and what became of them, split by source, landing page, location, device and timing. The review shows where the share of useful leads sits well below the overall share, how those patterns overlap, which measurement faults could produce a pattern, and a short list of cases the acquisition lead can check with sales. The assistant prepares; it never changes targeting, pauses or edits anything, contacts anyone, states a cause or says a source is dishonest. The acquisition lead decides what is investigated, and verifies each finding with sales before any targeting change."
license: "MIT"
metadata:
  version: "0.1.0"
  publisher: "Fully Powered AI"
  template: "Lead quality pattern review"
---

# Lead quality pattern review

This is the technical file for a Fully Powered workflow template. It carries the instructions an AI product follows. The complete template, with roles, inputs, exceptions, the reviewer checklist, acceptance tests and what to customize, is in [TEMPLATE.md](TEMPLATE.md). A worked example with invented data is in [EXAMPLE.md](EXAMPLE.md).

## Instructions

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

## Before relying on it

Decide every item under "What to customize" in TEMPLATE.md and set the limits the instructions in this file leave open, written in square brackets such as [N], to your own. Then run the acceptance tests in TEMPLATE.md on past work. A person starts this work, supplies the inputs and decides what happens with the result.
