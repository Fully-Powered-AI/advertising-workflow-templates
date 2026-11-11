# Trial: Lead quality pattern review, run once on its invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs are the invented example in `public/example.md` (section "The inputs": settings, scope, known changes, the 88-row lead outcomes export and the three sales notes). No client data was used.

## How this run differs from a clean one

The run was meant to be blind: read the template and the example's inputs only, produce the output, then compare. It was not blind. The example file was opened whole, so the published review was read before the output was produced. What was done independently is the arithmetic: a short script (kept outside the repository, run on the inputs only) recomputed every count, rate, difference, overlap, busiest day and case list, and the instruction block and output format were followed step by step. The text below is the review in the template's output format with those recomputed figures. Its wording was not drafted independently of the published example, so this trial tests the template's numbers and rules, not how freely an assistant would phrase it.

## What came out

```
LEAD QUALITY PATTERN REVIEW: Client Q, 2026-10-01 to 2026-10-31

For: the acquisition lead. Period 2026-10-01 to 2026-10-31; as of 2026-11-09. Settings: minimum 10 settled leads to read a segment, flag gap 15 points, outcome window 14 days.

DATA CHECK
Rows received: 88. Removed as repeats of a lead_id already seen: 1 (L017). Excluded as outside the period: 1 (L087 dated 2026-11-02). Leads reviewed: 86.
Settled leads: 76 (44 useful, 32 not useful). Open leads: 10 (9 created on or after 2026-10-26, 1 older).
Overall useful rate: 44 of 76 settled (57.9%).
Values read as the same after ignoring capitals and spaces at the ends: Source "search general " read as "Search general" (1 lead).

KNOWN CHANGES IN THE PERIOD
2026-10-14: the quote request form moved to a new form tool. Before: 32 settled, 19 useful (59.4%). From that date: 44 settled, 25 useful (56.8%). Both sides have at least 10 settled leads, so both are shown; the review draws no conclusion from the two figures.

SEGMENTS
A segment with no leads is not listed.
Within a dimension, segments run from most leads to fewest.

Source
Social paid: 32 leads, 28 settled, 9 useful (32.1%), -25.8 points against overall. Below overall: pattern 1.
Search general: 23 leads, 20 settled, 12 useful (60.0%), +2.1 points against overall. Within the gap.
Search brand: 18 leads, 16 settled, 13 useful (81.2%), +23.4 points against overall. Above overall.
Partner: 13 leads, 12 settled, 10 useful (83.3%), +25.4 points against overall. Above overall.

Landing page
/quote: 42 leads, 37 settled, 26 useful (70.3%), +12.4 points against overall. Within the gap.
/spring-offer: 28 leads, 24 settled, 7 useful (29.2%), -28.7 points against overall. Below overall: pattern 2.
/contact: 16 leads, 15 settled, 11 useful (73.3%), +15.4 points against overall. Above overall.

Location
North Metro: 37 leads, 34 settled, 23 useful (67.6%), +9.8 points against overall. Within the gap.
South Metro: 22 leads, 19 settled, 12 useful (63.2%), +5.3 points against overall. Within the gap.
Coastal: 15 leads, 13 settled, 8 useful (61.5%), +3.6 points against overall. Within the gap.
Outside service area: 12 leads, 10 settled, 1 useful (10.0%), -47.9 points against overall. Below overall: pattern 3.

Device
mobile: 44 leads, 38 settled, 16 useful (42.1%), -15.8 points against overall. Below overall: pattern 4.
desktop: 36 leads, 33 settled, 26 useful (78.8%), +20.9 points against overall. Above overall.
tablet: 4 leads, 4 settled, 2 useful. Too few to read.
(blank): 2 leads, 1 settled, 0 useful. Too few to read.

Day part
Morning: 26 leads, 23 settled, 17 useful (73.9%), +16.0 points against overall. Above overall.
Afternoon: 32 leads, 29 settled, 16 useful (55.2%), -2.7 points against overall. Within the gap.
Evening: 28 leads, 24 settled, 11 useful (45.8%), -12.1 points against overall. Within the gap.

Week
week of 2026-09-28: 10 leads, 10 settled, 7 useful (70.0%), +12.1 points against overall. Within the gap.
week of 2026-10-05: 19 leads, 19 settled, 11 useful (57.9%), +0.0 points against overall. Within the gap.
week of 2026-10-12: 11 leads, 11 settled, 6 useful (54.5%), -3.3 points against overall. Within the gap.
week of 2026-10-19: 22 leads, 21 settled, 13 useful (61.9%), +4.0 points against overall. Within the gap.
week of 2026-10-26: 24 leads, 15 settled, 7 useful (46.7%), -11.2 points against overall. Within the gap.

PATTERNS

1. Source: Social paid
Facts: 32 leads, 28 settled, 9 useful (32.1%), -25.8 points against overall (57.9%). Useful leads: 9 against 16.2 at the overall rate, 7.2 fewer.
Busiest day: 2026-10-19, 8 of 32 leads (25.0%).
Overlaps: pattern 2 (Landing page: /spring-offer): 24 settled leads in both, 7 useful (29.2%), 100.0% of the smaller pattern's settled leads; pattern 3 (Location: Outside service area): 10 settled leads in both, 1 useful (10.0%), 100.0% of the smaller pattern's settled leads; pattern 4 (Device: mobile): 19 settled leads in both, 4 useful (21.1%), 67.9% of the smaller pattern's settled leads.
Checks that touch this pattern: none.
Cases to verify with sales: L004 (2026-10-01 21:26, Unreachable); L005 (2026-10-01 22:44, Not qualified); L019 (2026-10-08 13:31, Not qualified); L025 (2026-10-09 20:47, Marked invalid); L026 (2026-10-09 23:51, Unreachable). Ask sales what the contact found and whether the outcome label matches what happened.
Question for the acquisition lead: take this pattern to sales with these cases, hold it, or set it aside? The review proposes no targeting change and states no cause.

2. Landing page: /spring-offer
Facts: 28 leads, 24 settled, 7 useful (29.2%), -28.7 points against overall (57.9%). Useful leads: 7 against 13.9 at the overall rate, 6.9 fewer.
Busiest day: 2026-10-19, 8 of 28 leads (28.6%).
Overlaps: pattern 1 (Source: Social paid): 24 settled leads in both, 7 useful (29.2%), 100.0% of the smaller pattern's settled leads; pattern 3 (Location: Outside service area): 10 settled leads in both, 1 useful (10.0%), 100.0% of the smaller pattern's settled leads; pattern 4 (Device: mobile): 19 settled leads in both, 4 useful (21.1%), 79.2% of the smaller pattern's settled leads.
Checks that touch this pattern: none.
Cases to verify with sales: L004 (2026-10-01 21:26, Unreachable); L005 (2026-10-01 22:44, Not qualified); L019 (2026-10-08 13:31, Not qualified); L025 (2026-10-09 20:47, Marked invalid); L026 (2026-10-09 23:51, Unreachable). Ask sales what the contact found and whether the outcome label matches what happened.
Question for the acquisition lead: take this pattern to sales with these cases, hold it, or set it aside? The review proposes no targeting change and states no cause.

3. Location: Outside service area
Facts: 12 leads, 10 settled, 1 useful (10.0%), -47.9 points against overall (57.9%). Useful leads: 1 against 5.8 at the overall rate, 4.8 fewer.
Busiest day: 2026-10-19, 7 of 12 leads (58.3%).
Overlaps: pattern 1 (Source: Social paid): 10 settled leads in both, 1 useful (10.0%), 100.0% of the smaller pattern's settled leads; pattern 2 (Landing page: /spring-offer): 10 settled leads in both, 1 useful (10.0%), 100.0% of the smaller pattern's settled leads; pattern 4 (Device: mobile): 10 settled leads in both, 1 useful (10.0%), 100.0% of the smaller pattern's settled leads.
Checks that touch this pattern: the value is not in the location scope supplied; 7 of 12 leads fall on one day (2026-10-19, 58.3%).
Cases to verify with sales: L019 (2026-10-08 13:31, Not qualified); L043 (2026-10-19 22:55, Wrong service); L044 (2026-10-19 23:22, Unreachable); L045 (2026-10-19 23:29, Wrong service); L046 (2026-10-19 23:36, Not qualified). Ask sales what the contact found and whether the outcome label matches what happened.
Question for the acquisition lead: take this pattern to sales with these cases, hold it, or set it aside? The review proposes no targeting change and states no cause. The tracking owner can be asked about the check named above.

4. Device: mobile
Facts: 44 leads, 38 settled, 16 useful (42.1%), -15.8 points against overall (57.9%). Useful leads: 16 against 22.0 at the overall rate, 6.0 fewer.
Busiest day: 2026-10-19, 8 of 44 leads (18.2%).
Overlaps: pattern 1 (Source: Social paid): 19 settled leads in both, 4 useful (21.1%), 67.9% of the smaller pattern's settled leads; pattern 2 (Landing page: /spring-offer): 19 settled leads in both, 4 useful (21.1%), 79.2% of the smaller pattern's settled leads; pattern 3 (Location: Outside service area): 10 settled leads in both, 1 useful (10.0%), 100.0% of the smaller pattern's settled leads.
Checks that touch this pattern: 1 repeated row removed from this segment (L017).
Cases to verify with sales: L004 (2026-10-01 21:26, Unreachable); L005 (2026-10-01 22:44, Not qualified); L011 (2026-10-05 14:41, Marked invalid); L016 (2026-10-07 17:40, Not qualified); L019 (2026-10-08 13:31, Not qualified). Ask sales what the contact found and whether the outcome label matches what happened.
Question for the acquisition lead: take this pattern to sales with these cases, hold it, or set it aside? The review proposes no targeting change and states no cause. The tracking owner can be asked about the check named above.

Segments above overall, for context only: Source Search brand (81.2%); Source Partner (83.3%); Landing page /contact (73.3%); Device desktop (78.8%); Day part Morning (73.9%). No cases are listed for them.

POSSIBLE MEASUREMENT FAULTS
1. Repeated lead_id: 1 row removed (L017); an identical row. Who can verify: the tracking owner, on whether the form or tag can send one lead twice.
2. Dated outside the period: 1 row excluded (L087, 2026-11-02 10:15). Who can verify: the tracking owner, on whether the date is the submission date.
3. Blank values: Source 0 (0.0%); Landing page 0 (0.0%); Location 0 (0.0%); Device 2 (2.3%). None is at 10 percent or more of leads reviewed. Who can verify: the tracking owner, for the 2 blank device values.
4. Values not in the scope supplied: Source 0; Landing page 0; Location 12 (14.0%; Outside service area). This is a difference between the records and the scope, not a finding about those leads. Who can verify: the acquisition lead, on whether the targeted locations list is current.
5. Open leads older than 14 days: 1 (L062 In contact). Who can verify: sales development, on whether the outcome was never updated.

SALES FEEDBACK
F1 (2026-10-22, Sales development rep): "Two Social paid leads said on the call they had not asked for a quote."
L005: 2026-10-01 22:44, source Social paid, page /spring-offer, location North Metro, device mobile, outcome Not qualified; falls in patterns 1, 2, 4.
L030: 2026-10-12 13:17, source Social paid, page /quote, location Coastal, device tablet, outcome Unreachable; falls in pattern 1.
F2 (2026-10-29, Sales manager): "Fewer people who came in on a phone are picking up when we ring."
No lead_ids given, so no cases to check. Ask the sender which leads they mean.
F3 (2026-10-30, Sales development rep): "One lead from the end of the month was a duplicate of an earlier caller."
L130: not in the export for this period. Ask the sender for the date and source.

Not assessed: Tablet (4 settled) and blank device (1 settled), too few to read. Open leads are left out of every rate.

Every figure traces to the lead outcomes export for 2026-10-01 to 2026-10-31, the settings, the scope, the known changes and the sales notes supplied. The review changes no targeting and no record, accuses no source of anything and sends nothing; the acquisition lead decides what is investigated and verifies findings with sales before any targeting change.
```

## What was observed

- **Every required part was produced.** Data check, known changes, six dimensions of segments, four patterns with facts, busiest day, overlaps, checks and cases, the context line, all five measurement faults, three sales notes, and the close with the trace line. Nothing in the run made the assistant stop: every header matched, every outcome value was on one of the three lists, and `created_at` was in the stated shape.
- **The figures matched the published example.** Recomputed from the inputs: 88 rows received, one repeat (L017) and one row outside the period (L087) removed, 86 reviewed, 76 settled (44 useful), 57.9 percent overall, four patterns (Social paid, /spring-offer, Outside service area, mobile), the same overlaps, busiest days, cases, fault counts and known-change figures. No numeric difference was found.
- **One difference in the text.** The published example's "Not assessed" line adds "Cost, spend and call recordings were not supplied." The output format does not ask for that sentence and the inputs do not mention cost or recordings, so it was left out here. It is a statement of absence, not a figure, but it is not in the inputs.
- **No other fact in either output was missing from the inputs.** Every id, time, outcome, count and date traces to the export, the settings, the scope, the known changes or the notes.
- **Ambiguities, where a choice had to be made:**
  - Check four (one day holding 40 percent or more) says the segment must have "at least the minimum number of leads". The procedure and the instruction block say "leads", while the minimum is defined in settled leads. Read as all leads here; the result is the same on this data (Outside service area has 12 leads and 10 settled).
  - A repeated row is "removed from this segment" only through the value on the removed row. The template does not say to use the removed row's own values. That was assumed, and it puts L017 (mobile) in the mobile pattern.
  - Mobile is below overall by 15.79 points against a 15-point gap, so the unrounded comparison matters. Rounded to one place (15.8) it gives the same flag, but a reader checking only the printed figures cannot see how close it is.
  - The week of 2026-09-28 holds only 1 to 4 October leads, because earlier days are outside the period. The template does not say whether to label such a part-week differently.
  - The overall rate (57.9) is subtracted before rounding, so the printed points (for example +0.0 for the week of 2026-10-05) can differ in the last digit from the difference of the printed rates. The template says to round percentages, but not whether points are rounded from unrounded figures; unrounded was assumed.
  - "Overnight" is a day part with no leads and so is not listed, which follows the rule that empty segments are omitted.
- **Shortcomings.** The invented example is easy for the rules: the four patterns overlap almost completely (all of Social paid, /spring-offer and Outside service area sit together), which the review reports as overlap and not as an explanation, as required. The template has not been tried where two patterns partly overlap, where a segment sits just under the minimum, or on an export with a mis-spelled outcome. Cases where the template stops (header mismatch, unknown outcome, a request to name a cause) were not exercised in this run. The 15-point flag and the 10-lead minimum are the example's settings, not the defaults (20 and 15), so the defaults were not run either.

## Notes added after the run

The run's output and observations above are as recorded and have not been changed. After an independent review, the following were noted or changed; none was run again.

- The sentence "Cost, spend and call recordings were not supplied." described above was in the published example when the run was made. It was removed from the example afterwards, so a reader will not find it there now.
- Search brand is 13 of 16, exactly 81.25 percent, and the run printed 81.2. The instruction block now says an exact tie rounds to the even digit, which gives the same 81.2; the run did not state that rule.
- The run's data check did not make the device-against-scope check ("Device 0"), which the output format and the published example include. The version notes say so.
- The run was not blind, and the stop conditions and the defaults were not exercised, as stated above. This is weaker evidence than a clean run.
