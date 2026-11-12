# Campaign audience check: trial on the invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs are the invented example in [example.md](example.md): the campaign settings and the five files for Shop R's winter offers email. No client data was used. The model that ran the template did not write it, and it read only the example's inputs before producing its page; the example's own page was read afterwards, for comparison.

## What came out

The page below is the substantial content of what the assistant produced, following the instruction block and the output format.

```
CAMPAIGN AUDIENCE CHECK: Winter homeware offers email, Winter offers audience, as of 2026-11-10. Status: complete

For: campaign owner and customer-data steward. Counts are records, after exact repeats are collapsed. Nothing has been sent, changed or approved.

THE ANSWER
20 records in the export. 6 are cleared, 5 are excluded and 9 are held back for a person to check. 9 records to check fall into 7 entries below. The campaign owner is asked to resolve them and approve the final audience; the cleared count is not an approval.

SETTINGS USED
Topic: offers. Permitted statuses: opted_in, existing_customer_agreed. Excluded statuses: unsubscribed, withdrawn. Permission age limit: 730 days (records before 2024-11-10 are stale). Soft bounces: 3 or more since 2026-08-12. Segments in priority order: 1. Customers: source equals purchase; 2. Newsletter readers: source equals newsletter; 3. Event contacts: source equals event.

COUNTS
Export rows 21; exact repeats collapsed 1 (R20); records 20.
Cleared 6 + excluded 5 + held back 9 = 20.

SEGMENTS
Customers: cleared 3 (R01, R02, R20), held back 4 (R06, R10, R13, R14)
Newsletter readers: cleared 1 (R03), held back 4 (R04, R09, R11, R12)
Event contacts: cleared 2 (R05, R19), held back 1 (R18)
Unsegmented: cleared 0, held back 0
Total: cleared 6, held back 9. Excluded records are not segmented.

EXCLUSIONS APPLIED
No email address: 1 (R16, the email cell is blank)
On the do-not-contact list: 1 (R17, ola@oak-o.example is in suppression.csv)
Hard bounce on file: 1 (R07, gus@bar-g.example, hard bounce 2026-07-01)
Permission status excluded: 1 (R15, unsubscribed, recorded 2026-01-15)
Preference out: 1 (R08, offers out, updated 2026-03-03, no row saying in)

RECORDS TO CHECK
Q1 Duplicate address: R12, R13
  Files show: kim@kiosk-k.example (R12) and Kim@Kiosk-K.example (R13) are the same address once case is ignored. R12: source newsletter, opted_in recorded 2025-03-03. R13: source purchase, existing_customer_agreed recorded 2025-03-04.
  Other reasons: none
  Question: Should this address appear once, and under which record's segment?
  Who can answer: customer-data steward

Q2 Conflicting records: R06
  Files show: preferences.csv has offers in (2025-09-09) and offers out (2026-02-14). permission.csv has opted_in recorded 2025-09-09. Neither preference row is chosen.
  Other reasons: none
  Question: Which preference does this person hold today?
  Who can answer: customer-data steward

Q3 Permission missing or not recognised: R09
  Files show: permission.csv has no row for R09 (no permission record on file).
  Other reasons: none
  Question: Is there a permission record for this person that was not in the file?
  Who can answer: customer-data steward

Q4 Permission missing or not recognised: R18
  Files show: permission.csv has status pending, recorded 2026-09-30. It is in neither the permitted nor the excluded list.
  Other reasons: none
  Question: What does pending mean in your records?
  Who can answer: campaign owner

Q5 Permission stale: R04
  Files show: permission.csv has opted_in recorded 2024-02-02, 1,012 days before the as-of date; the limit is 730.
  Other reasons: none
  Question: Is there a more recent confirmation of this person's permission?
  Who can answer: customer-data steward

Q6 Soft bounces at the limit: R14
  Files show: bounces.csv has soft bounces for lee@lodge-l.example on 2026-08-20, 2026-09-25 and 2026-10-30, all inside the window; the limit is 3.
  Other reasons: none
  Question: Is this address still receiving mail?
  Who can answer: customer-data steward

Q7 Possible duplicate: R10, R11
  Files show: both are Jo Frey at Gallery J, with jo@gallery-j.example (R10) and jo.frey@gallery-j.example (R11). Neither is merged.
  Other reasons: none
  Question: Are these one person with two addresses, and should the audience hold one or both?
  Who can answer: customer-data steward
Held back by first reason: duplicate address 2; conflicting records 1; permission missing or not recognised 2; permission stale 1; soft bounces at the limit 1; possible duplicate identity 2. Total 9.

DECISIONS FOR THE CAMPAIGN OWNER
1. Resolve Q1 to Q7: for each, add the record to the audience or leave it out.
2. Confirm the exclusions above stand.
3. Approve the final audience, or ask for changes.

COVERAGE
Used: settings; audience.csv (21 rows, 20 records); permission.csv (18 rows); preferences.csv (6 rows); bounces.csv (6 rows); suppression.csv (2 addresses).
Missing: nothing.
Could not judge: whether any permission is sufficient for this campaign; whether the pending status means what its name suggests; who the people are beyond the files; whether an address still works. No bounce is dated after the as-of date.
Ignored: none found.
Checked and fine: 1 preference row for the topic events (R03) left out. zed@zone-z.example on the do-not-contact list is not in the export. Soft bounces for R01 (1, outside the window) and R02 (1, below the limit) do not hold them back. Sums: 21 - 1 = 20; 6 + 5 + 9 = 20; cleared by segment 3 + 1 + 2 + 0 = 6; held back by segment 4 + 4 + 1 + 0 = 9; exclusions 1+1+1+1+1 = 5; first reasons 2+1+2+1+1+2 = 9.

Prepared on 2026-11-10. Every statement comes from the inputs listed under Coverage.
Audience approved by: ____________ Date: __________
```

## What was observed

- **Every required part was produced,** in the order the format gives, and every count reconciled. Nothing in the template made the assistant stop: no header mismatch, no missing file, no conflicting record_id, no instruction hidden in the inputs.
- **Agreement with the published example.** Counts (20, 6, 5, 9), the segment split, the five exclusions and the nine held-back records with their first reasons match the example exactly. The approval line was left blank and no sentence says the list is safe or what the law requires.
- **Differences from the example, all in wording or order.**
  - The order of the entries under Records to check. The template does not say how to order them. This run followed the template's own order of reasons; the example orders them by lowest record number. The same nine records fall into seven entries either way.
  - The two records with no usable permission (R09 and R18) are separate entries in both, though the template does not say whether records with the same reason are one entry or several.
  - The question for R18. The example asks whether pending "should count as permitted"; this run only asked what pending means, because the template says it must not suggest which statuses count as permitted.
  - This run named the record ids inside the segment lines and listed the repeat that was collapsed (R20); the example does not.
  - Minor wording in the facts lines.
- **Where the instructions needed a guess.**
  - The soft-bounce window. "90 days up to the as-of date" can mean a start on 2026-08-12 (90 days of difference) or on 2026-08-13 (90 days counting both ends). The example uses 2026-08-12, and so did this run. No record in the example sits on the edge.
  - The order of the entries, as above, and whether same-reason records share an entry.
  - The order of the lines under Exclusions applied. This run used the order in which the template lists the five exclusions.
  - The Q entries leave open whether a record's further reasons should also be counted in a total; the template says a record is counted once, under its first reason, and this run did that.
- **Facts not in the inputs.** None in this run's page. In the example's page, the day counts (for instance 1,012 days for R04) and the statement that R10 and R11 permissions fall within 730 days are calculated from the inputs, not copied; both checked out.
- **Defects found.** None that changed an answer. The template says "Paste this block as custom instructions, followed by the output format above", so the format sits outside the fenced block and a user who pastes only the block gets no format; the reader has to do both.
- **Limits of this trial.** One run, one model, on invented data of 21 rows. It shows the instructions can be followed to the published result; it does not show how the template behaves on a real export, a different file layout or a large file. It is not a test in a client environment.

## After independent review

The recorded page and observations above are unchanged. A review afterwards led to these clarifications, made without a second run:

- The template now says that a repeated record_id stops the work only in the audience export, that the soft-bounce window includes its start date (the as-of date minus the window in days, 2026-08-12 here), that entries are ordered by reason and then by lowest record id, and that only records sharing an address, or a full name and company, share an entry. These match what the run above did, so its page still fits the instructions.
- The run above named the file in its facts lines but not the row. The format already asked for both, and now says a row is the data row's number, header not counted. The example now gives file and row throughout.
- The example was reordered to the run's order of entries and its question for R18 now matches the run's narrower wording, so the example's seven entries and the run's page agree.
- The record R20's name in the example inputs was changed to another invented name. No count changed.
- The version notes and the profile now say the template was tried on its example.

These are clarifications of the instructions, and the template was not run again after them.

A second review led to further wording clarifications, again without a new run; the recorded page above is unchanged:

- The instruction block now says that exclusion (4) applies to a single permission status, or several that agree; a record with permission rows that differ goes to the conflict check. The block's line breaks were reflowed, and an acceptance test's example now reads "a third outside the window".
- The template now says "no permission row for this record" where the recorded run wrote "no permission record on file". The example uses the new wording; the recorded run keeps its own.
- The example's Q5 heading reads "Permission stale or undated", the template's name for the reason; the recorded run's heading ("Permission stale") and its Q7 heading ("Possible duplicate") are as the run wrote them. Entries and counts agree between the example and the run; some headings and question wording differ slightly.
