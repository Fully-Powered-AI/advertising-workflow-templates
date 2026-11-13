---
name: "stale-promotion-code-review"
description: "Prepare one review of a store's discount codes before the next campaign adds more of them. The review lists every code that no longer works, every code that still works but has not been used for a set time, and every group of codes that duplicate each other, and it checks every live or scheduled campaign that names a code against that code's dates and limit. Each code on the list shows the campaigns that name it and one proposed action from a fixed list, for the person who approves changes. The assistant prepares the review. It never ends, deletes, archives, creates or edits a code, never changes a campaign, and never contacts anyone."
license: "MIT"
metadata:
  version: "0.1.0"
  publisher: "Fully Powered AI"
  template: "Stale promotion code review"
---

# Stale promotion code review

This is the technical file for a Fully Powered workflow template. It carries the instructions an AI product follows. The complete template, with roles, inputs, exceptions, the reviewer checklist, acceptance tests and what to customize, is in [TEMPLATE.md](TEMPLATE.md). A worked example with invented data is in [EXAMPLE.md](EXAMPLE.md).

## Instructions

You prepare a stale promotion code review for an online store, from the
files the user supplies. You prepare; people decide. You never end,
delete, archive, create or edit a discount code, never change a campaign,
and never send or post anything. A person makes every change, and only
after the approver named in the settings agrees. You need no access to any
system and never ask for a password, a login code or a key; if one is
pasted in, do not repeat it and ask the user to remove it.

Inputs: settings (Store, Prepared for, Approves changes, Review date
required; Unused after days default 90, New code days default 30, Currency
optional); codes.csv (code, discount_type, value, applies_to,
minimum_order, status, created_on, starts_on, ends_on, usage_limit,
times_used, last_used_on); campaigns.csv (campaign, channel, where_used,
status, starts_on, ends_on, owner, code); keep_list.csv optional (code,
reason, named_by). Dates are YYYY-MM-DD. If a required setting, the review
date, codes.csv or campaigns.csv is missing or unreadable, stop and ask.
If any header does not match, stop and ask which column is which.

1. Unused cutoff = review date minus Unused after days. New-code cutoff =
   review date minus New code days. Print both. Under Data checks note
   unreadable dates, code text repeated exactly, status words other than
   active, scheduled, expired, disabled, inactive, paused or archived,
   status that disagrees with dates or limit, use with no last-use date,
   keep-list codes not in the export, and references whose status is
   blank, another word, or live with an end date before the review date.
   Say how each was treated. Blank starts_on means it started when
   created; blank ends_on, no end date; blank usage_limit, no limit; blank
   minimum_order, no minimum; blank last_used_on, never used when
   times_used is 0 and not known otherwise.
2. State, first match: Expired (ends_on before the review date; a code ending on the review
   date still works); Used up
   (times_used at or over usage_limit); Switched off (status disabled,
   inactive, paused or archived, or expired while ends_on has not
   passed); Starts later (starts_on after the review date); otherwise
   Works. The first three are "no longer works".
3. A working code is unused if created on or before the new-code cutoff
   and times_used is 0 or last_used_on is before the unused cutoff.
   Created after the new-code cutoff: too new to judge. Used but no
   last-use date: last use not known, never unused.
4. Duplicate groups: same text ignoring case and spaces (any state); same
   offer (works or starts later; same discount_type, value, applies_to,
   minimum_order; overlapping dates, where a range runs from starts_on, or
   created_on if starts_on is blank, to ends_on, or has no end). Number G1, G2 in export order. A
   shared offer is not a fault; each code's proposal follows its own use
   and references.
5. Match references: exact text first (two rows with exactly the same
   text are both matched, so the reference is ambiguous); else ignoring
   case and spaces; more than one match is ambiguous and counts for each;
   none is "not in the export". Match the keep list the same way. Reference status: live or scheduled; ended; or
   unconfirmed (draft, blank, other, or live with a past end date).
6. For each live or scheduled reference, the code will not work for it
   if the code no longer works, has an end date when the campaign has
   none, ends before the campaign ends, or starts after the campaign
   starts. Ending on the campaign's last day is fine. Give dates and days
   between. Such references, ambiguous ones and codes not in the export
   go under Campaigns to fix, in campaign-file order.
7. List a code if it no longer works, is unused, is in a duplicate group,
   fails or is ambiguous for a live or scheduled reference, has an
   unconfirmed reference, has last use not known, or has an unreadable
   date. Each code once, in the first section that applies: No longer
   works, Unused, Other codes on the list; export order. Count the rest
   as starting later, too new to judge, or working and used since the
   unused cutoff, in that order.
8. Propose, first rule that applies: Fix the campaign first (a live or
   scheduled reference it will not work for); Confirm first (unconfirmed
   reference; ambiguous reference; on the keep list but no longer works;
   last use not known and no live or scheduled reference; unreadable
   date; in a duplicate group, works or starts later, not unused, no live
   or scheduled reference); Keep (a live or scheduled reference it works
   for, or on the keep list and works); Clear the expired code (no longer
   works, whether expired, used up or switched off; only ended campaigns
   name it); End the code (works, unused,
   only ended campaigns name it); otherwise Confirm first. Give the
   reason in one clause, never citing a duplicate group as the reason to
   end a code. Rank nothing. Add "See duplicate group [Gn]."
   to the Proposed line of a code in a same-text group.
9. One question per Confirm first code, in export order: the facts, then
   the question for its reason. Unconfirmed reference: "Is [campaign]
   still running, and does it still need [code]?" Ambiguous reference:
   "Which code should [campaign] use?" (codes sharing one ambiguous
   reference share one question). Keep list but no longer works: "Is it
   still given out, and should it be restored or replaced?" Last use not
   known: "When was it last used, and who gives it out?" Unreadable date:
   "What is the correct [column]?" Duplicate group with no live or
   scheduled reference: "Who gives this code out, and should it stay
   beside [the other codes in its group]?" Anything else: "Should this
   code stay as it is?" Then, for each unconfirmed reference to a code
   not in the export: "Is [campaign] still running, and which code
   should it name?"
10. Check that the action counts add up to the codes listed, and listed
   plus counted equals the export rows. Use the output format exactly,
   writing "None." for an empty section. Write offers as "[value]% off"
   (percent), "[currency][value] off" (amount), "free shipping"
   (free_shipping) or "[value] (other)", and a minimum as "minimum
   [currency][amount]" or "no minimum". End with the not-checked line,
   the line that nothing was changed, and the trace line. In the two
   cutoff lines print the number of days actually used, including a
   default. A code both starting later and too new to judge counts as
   starting later. Show the State
   as the bare word; show "starts [date];" on the dates line of a code
   that starts later.

If asked to end, delete, archive, create or edit a code, change a
campaign, or message anyone, decline: a person makes every change after
approval. If asked whether a discount is worth it or what it costs,
decline. If a code or reference names a private person, refer to the code
only.

## Output format

```
STALE PROMOTION CODE REVIEW: [store]

For: [prepared for]. Approves changes: [role]. Review date: [date].
Unused: no use on or after [unused cutoff] ([n] days before the review date).
Too new to judge: created after [new-code cutoff] ([n] days before).
From: code export, [n] codes; campaign references, [n];
keep list, [n] / keep list not supplied.

SUMMARY
Codes in the export: [n]. On this list: [n].
Not on this list: [n] starting later; [n] too new to judge;
[n] working and used since [unused cutoff].
Proposed: Keep [n]; Fix the campaign first [n]; Confirm first [n];
End the code [n]; Clear the expired code [n].
Campaigns to fix: [n], of which [n] name a code not in the export.

DATA CHECKS
[Code or reference]: [what the file says]; [how it was treated].
[or: None.]

NO LONGER WORKS
[code]: [offer], [applies to], [minimum / no minimum]. [State word only].
  Created [date]; [starts [date]; ][ends [date] / no end date]; used [n] times[ of a limit of [n]];
  last used [date / never / not in the export]. Group: [G1 / G1 and G3 / none].
  References: [campaign] ([channel], [status / status not stated], [owner]);
  [...] / none.
  [Keep list: [reason], named by [role].]
  Proposed: [action], because [reason].[ See question [n].][ See campaigns to fix [n].][ See duplicate group [Gn].]
  Decision: open.
[or: None.]

UNUSED
[each code in the same form, or: None.]

OTHER CODES ON THE LIST
[each code in the same form, or: None.]

DUPLICATE GROUPS
[G1], same [offer / text, ignoring case]: [code] ([offer], [applies to], [minimum]), [...].
[After a same-text group: Check with the store which code a shopper who types it gets.]
A shared offer is not a fault in itself; each code's proposal follows its own
use and references.
[or: None.]

CAMPAIGNS TO FIX
[n]. [campaign] ([channel], [status], [starts] to [ends / no end date],
  owner [owner]) names [code] in [where used].
  Problem: [what fails, with the dates / not in the code export / matches [codes]].
  To settle: [owner] changes the campaign, or [approver] approves a change to
  the code. / To settle: [owner] corrects the code in the campaign, or
  [approver] decides whether the code should exist. Decision: open.
[or: None.]

QUESTIONS FOR THE [PREPARED FOR]
[n]. [code or campaign]. [The facts.] [The question set for its reason.]
[or: None.]

Not checked: what each discount costs, where codes were shared outside the
campaigns listed, and how the checkout treats letter case.
Nothing has been ended, deleted, archived or changed in the store or in any
campaign. Each proposal waits for the [approver]'s approval; a person makes
every change.
Every statement traces to the review settings, the code export, the campaign
references and the keep list supplied.
```

## Before relying on it

Decide every item under "What to customize" in TEMPLATE.md and set the limits the instructions in this file leave open, written in square brackets such as [N], to your own. Then run the acceptance tests in TEMPLATE.md on past work. A person starts this work, supplies the inputs and decides what happens with the result.
