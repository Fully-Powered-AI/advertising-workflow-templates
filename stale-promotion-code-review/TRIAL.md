# Stale promotion code review: tried on its invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-11

The inputs were the invented example in [example.md](example.md) (Store K, an invented online candle shop): the review settings, the code export of seventeen codes, the fourteen campaign references and the one-line keep list. No client data was used. The assistant was given the template's instructions block and output format, and it was run once, by a model that had not written the template. It was not shown the published output until after it had produced its own.

## What came out

The full review follows, as produced.

```
STALE PROMOTION CODE REVIEW: Store K (an invented online candle shop)

For: E-commerce manager. Approves changes: E-commerce manager. Review date: 2027-03-15.
Unused: no use on or after 2026-12-15 (90 days before the review date).
Too new to judge: created after 2027-02-13 (30 days before).
From: code export, 17 codes; campaign references, 14;
keep list, 1.

SUMMARY
Codes in the export: 17. On this list: 13.
Not on this list: 0 starting later; 1 too new to judge;
3 working and used since 2026-12-15.
Proposed: Keep 4; Fix the campaign first 2; Confirm first 3;
End the code 3; Clear the expired code 1.
Campaigns to fix: 3, of which 1 name a code not in the export.

DATA CHECKS
FIRST100: status is active, but 100 of a limit of 100 uses are recorded; treated as used up on the dates and the limit.
PRESS15: used 12 times with no last-use date; last use not known, never called unused.
Summer range insert (SUMMER20): campaign status is blank; treated as an unconfirmed reference.

NO LONGER WORKS
HOLIDAY25: 25% off, All products, no minimum. Expired on 2026-12-31.
  Created 2026-11-20; ends 2026-12-31; used 388 times; last used 2026-12-31. Group: none.
  References: Holiday gift guide (Email, ended, Email marketer); Holiday ads (Platform A, ended, Paid media lead).
  Proposed: Clear the expired code, because it ended on 2026-12-31 and only ended campaigns name it.
  Decision: open.

SORRY10: $10 off, All products, no minimum. Expired on 2027-01-31.
  Created 2026-02-01; ends 2027-01-31; used 22 times; last used 2027-01-29. Group: none.
  References: none.
  Keep list: Customer service sends it after a late delivery, named by Customer service lead.
  Proposed: Confirm first, because it is on the keep list and no longer works. See question 1.
  Decision: open.

SUMMER20: 20% off, Summer range, no minimum. Switched off (status disabled).
  Created 2026-05-20; no end date; used 210 times; last used 2026-08-30. Group: none.
  References: Summer range insert (Packaging, status not stated, E-commerce manager).
  Proposed: Confirm first, because its only reference has no stated status. See question 2.
  Decision: open.

FIRST100: $15 off, All products, no minimum. Used up (100 of a limit of 100).
  Created 2026-10-01; no end date; used 100 times of a limit of 100; last used 2026-10-09. Group: none.
  References: First order pop-up (Website, live, E-commerce manager).
  Proposed: Fix the campaign first, because the live pop-up names a code that is used up. See campaigns to fix 1.
  Decision: open.

UNUSED
VIP20: 20% off, All products, no minimum. Works.
  Created 2026-02-14; no end date; used 61 times; last used 2026-10-02. Group: none.
  References: VIP early access (Email, scheduled, Email marketer).
  Proposed: Keep, because the scheduled VIP early access email (2027-04-01 to 2027-04-07) names it and it works for those dates.
  Decision: open.

SHIPFREE50: free shipping, All products, minimum $50. Works.
  Created 2026-04-02; no end date; used 3 times; last used 2026-08-19. Group: G1.
  References: none.
  Proposed: End the code, because it is unused since 2026-08-19, no campaign names it, and FREESHIP50 gives the same offer.
  Decision: open.

CREATORB15: 15% off, All products, no minimum. Works.
  Created 2026-09-01; no end date; used 0 times; last used never. Group: G2.
  References: Creator B programme (Creator posts, ended, Creator programme lead).
  Proposed: End the code, because it has never been used and only an ended campaign names it.
  Decision: open.

giftset: $8 off, Gift sets, no minimum. Works.
  Created 2026-11-15; no end date; used 0 times; last used never. Group: G3.
  References: none.
  Proposed: End the code, because it has never been used and no campaign names it.
  Decision: open.

OTHER CODES ON THE LIST
FREESHIP50: free shipping, All products, minimum $50. Works.
  Created 2025-09-01; no end date; used 950 times; last used 2027-03-14. Group: G1.
  References: Free shipping banner (Website, live, E-commerce manager).
  Proposed: Keep, because the live site banner names it and it works for it.
  Decision: open.

CREATORA15: 15% off, All products, no minimum. Works.
  Created 2026-09-01; no end date; used 140 times; last used 2027-03-12. Group: G2.
  References: Creator A programme (Creator posts, live, Creator programme lead).
  Proposed: Keep, because the live Creator A programme names it and it works for it.
  Decision: open.

GIFTSET: $5 off, Gift sets, no minimum. Works.
  Created 2025-11-01; no end date; used 75 times; last used 2026-12-20. Group: G3.
  References: Gift set search ads (Platform A, live, Paid media lead).
  Proposed: Keep, because the live Gift set search ads name it and it works for them.
  Decision: open.

PRESS15: 15% off, Candles, no minimum. Works.
  Created 2026-03-01; no end date; used 12 times; last used not in the export. Group: none.
  References: none.
  Proposed: Confirm first, because its last use is not known and no live or scheduled campaign names it. See question 3.
  Decision: open.

SPRING15: 15% off, All products, minimum $40. Starts later (2027-03-20).
  Created 2027-03-01; starts 2027-03-20; ends 2027-03-31; used 0 times; last used never. Group: none.
  References: Spring launch (Email, scheduled, Email marketer).
  Proposed: Fix the campaign first, because it ends 10 days before the Spring launch email ends. See campaigns to fix 2.
  Decision: open.

DUPLICATE GROUPS
G1, same offer: FREESHIP50 (free shipping, All products, minimum $50), SHIPFREE50 (free shipping, All products, minimum $50).
G2, same offer: CREATORA15 (15% off, All products, no minimum), CREATORB15 (15% off, All products, no minimum).
G3, same text, ignoring case: GIFTSET ($5 off, Gift sets, no minimum), giftset ($8 off, Gift sets, no minimum).
Check with the store which code a shopper who types it gets.
A shared offer is not a fault in itself; each code's proposal follows its own
use and references.

CAMPAIGNS TO FIX
1. First order pop-up (Website, live, 2026-10-01 to no end date,
  owner E-commerce manager) names FIRST100 in Home page pop-up.
  Problem: FIRST100 is used up (100 of a limit of 100) and no longer works; the pop-up has no end date.
  To settle: E-commerce manager changes the campaign, or E-commerce manager approves a change to
  the code. Decision: open.
2. Spring launch (Email, scheduled, 2027-03-20 to 2027-04-10,
  owner Email marketer) names SPRING15 in Launch email.
  Problem: SPRING15 ends 2027-03-31, 10 days before the campaign ends on 2027-04-10.
  To settle: Email marketer changes the campaign, or E-commerce manager approves a change to
  the code. Decision: open.
3. Spring launch (Email, scheduled, 2027-03-20 to 2027-04-10,
  owner Email marketer) names SPRINGSHIP in Launch email.
  Problem: SPRINGSHIP is not in the code export.
  To settle: Email marketer corrects the code in the campaign, or
  E-commerce manager approves creating it. Decision: open.

QUESTIONS FOR THE E-COMMERCE MANAGER
1. SORRY10. It expired on 2027-01-31, was used 22 times (last on 2027-01-29), and is on the keep list for customer service after a late delivery. Is it still given out, and should it be restored or replaced?
2. SUMMER20. It has been disabled, last used 2026-08-30, and the Summer range insert (Packaging) has no stated status. Is Summer range insert still running, and does it still need SUMMER20?
3. PRESS15. It was used 12 times but the export has no last-use date, and no live or scheduled campaign names it. When was it last used, and who gives it out?

Not checked: what each discount costs, where codes were shared outside the
campaigns listed, and how the checkout treats letter case.
Nothing has been ended, deleted, archived or changed in the store or in any
campaign. Each proposal waits for the E-commerce manager's approval; a person makes
every change.
Every statement traces to the review settings, the code export, the campaign
references and the keep list supplied.
```

## What was observed

- **Every required part was produced,** in the order of the output format: header, summary, data checks, the three code sections, duplicate groups, campaigns to fix, questions, and the three closing lines. Nothing in the template told the assistant to stop, and none of its stop conditions applied to these inputs.
- **The counts match the template's own expected result for this example:** 17 codes, 13 listed and 4 counted; Keep 4, Fix the campaign first 2, Confirm first 3, End the code 3, Clear the expired code 1; 3 campaigns to fix, 1 naming a code not in the export; 3 questions. Both cutoff dates (2026-12-15 and 2027-02-13) were worked out independently and agreed with the example.
- **Every code got the same section and the same proposed action as in the published example.** The same three data checks were found, the same three duplicate groups were numbered in the same order, and the days between the SPRING15 end date and the campaign end date (10) agreed.
- **Differences from the published example are in wording only.** The reasons are phrased differently in places, and the assistant added a few facts already in the inputs: the start date of SPRING15, the expiry date on the state line of two codes, and the reason that FREESHIP50 gives the same offer as SHIPFREE50. The summary line reads "of which 1 name a code" because the format says "name"; the example says "names". Neither output contains a fact that is not in the inputs.
- **Where the instructions were ambiguous and the assistant had to choose:**
  1. The format has one "[State]." slot. The template does not say whether it holds the bare state word or the state with its date, so the assistant gave dates for expired and starts-later codes. The example uses the bare word.
  2. A "starts later" code is shown with "ends" and "created" dates but no start date in the format, so the one fact that makes it "starts later" has no slot. The assistant added it.
  3. The "Not on this list" line must show a count for each of three kinds in a fixed order, and a code can be both starting later and too new to judge (SPRING15). The template resolves this by listing order, but the summary line does not say so.
  4. The giftset proposal. Ending the lower-case giftset code is correct by the first rule that applies, but if the checkout ignores letter case, ending it could change what shoppers who type GIFTSET receive. The template's own "Not checked" line admits it does not know how the checkout treats case, and the "Check with the store" line is attached to the group. The proposal is still End the code with no warning on the code itself.
  5. The format shows "To settle" for a code missing from the export as "approver approves creating it". The assistant followed it, though it sits oddly beside the rule that the assistant never proposes creating a code.
  6. The "[n] days before" in the two cutoff lines repeats the setting; the template does not say what to print if the setting is the default.
- **Shortcomings of the template that this one run shows:** the reviewer checklist item 6 (check each keep-list code with whoever named it) cannot be done by the assistant and is not marked as the person's job; the template's own version note still says it is not tried on its example, which this record supersedes; and a single run on one invented example shows that the instructions can be followed, not that they hold for a real store's export, where column names, status words and campaign lists will differ.
- **Nothing was changed in any store or campaign,** and the assistant asked for nothing it could not do from the files given.

## Changed after the run, and not run again

Changed on 11 and 12 November 2026 after review feedback on the draft template from an independent reviewer, and not run again. The output and the observations above are as recorded and describe the template and the example as they stood at the run:

- The version note, the profile and the answer to "What has been checked?" now say the template was tried once on its invented example; they said it had not been tried.
- The code line in the output format has a slot for the start date of a code that starts later, and the example shows SPRING15 with its start date.
- The state in the output format is the bare word, with no date.
- The summary line in the example now reads "name", as the format does.
- The rule for Clear the expired code says it covers codes that are expired, used up or switched off.
- A code in a same-text group carries "See duplicate group" on its Proposed line (giftset and GIFTSET in the example; the first edit covered only giftset, and GIFTSET was corrected on 12 November).
- The instruction block now lists the known status words and says what a blank starts_on, ends_on, usage_limit, minimum_order and last_used_on mean.
- Two ambiguities noted above are now settled in the template: a code both starting later and too new to judge is counted as starting later, and the cutoff lines print the number of days actually used, default or not.
- The acceptance tests now say that only test 1 has been tried, and test 6 reads "campaigns.csv missing".
- The "To settle" clause for a code missing from the export now reads "decides whether the code should exist" in place of "approves creating it".
- Reviewer checklist item 6 says a person, not the assistant, does the check.
- Added on 12 November 2026, also not run again: the instructions now say never to give membership of a duplicate group as the reason to end a code (in the run above, the assistant gave "FREESHIP50 gives the same offer" as part of the reason to end SHIPFREE50, which sits against the rule that a proposal follows a code's own use and references, never its group alone); a reference to text that appears exactly in two rows matches both and is ambiguous; the keep list is matched the same way as references; a range of dates for the same-offer check is defined in the instruction block; and the block says that a code ending on the review date still works. These are clarifications: the example's inputs, its output and the counts are unchanged.
