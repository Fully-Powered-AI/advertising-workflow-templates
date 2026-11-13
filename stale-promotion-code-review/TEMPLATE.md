# Stale promotion code review

Workflow template, version 0.1.0.

## Purpose

Prepare one review of a store's discount codes before the next campaign adds more of them. The review lists every code that no longer works, every code that still works but has not been used for a set time, and every group of codes that duplicate each other, and it checks every live or scheduled campaign that names a code against that code's dates and limit. Each code on the list shows the campaigns that name it and one proposed action from a fixed list, for the person who approves changes. The assistant prepares the review. It never ends, deletes, archives, creates or edits a code, never changes a campaign, and never contacts anyone.

## When to use it and when not to

Use it when old codes have piled up and a campaign is coming that will add more, when a campaign has gone out naming a code that did not work at checkout, or as a routine tidy once a quarter.

Do not use it:

- to decide what discount to offer or whether a promotion pays for itself; that is a pricing and campaign decision;
- to approve a price below list for one customer; that is the discount request review;
- to check that a creator or affiliate published the right code; that is creator publication tracking;
- to find where codes have been passed around on coupon sites, or to judge misuse;
- to make the changes in the store or the campaigns. A person makes them after approval.

## Roles

- **Runs it:** the e-commerce manager or the marketing manager, after exporting the codes and gathering the campaign references.
- **Approves every change to a code:** the role named in the settings under `Approves changes`.
- **Answers for each campaign:** the owner named on the campaign reference, who changes the campaign when a code will not work for it.
- **Answers for the keep list:** the role named on each line, such as the customer service lead.
- **Makes every change in the store and in each campaign:** a person, after approval.

## Inputs

1. **Review settings,** as `name: value` lines. Required: `Store`, `Prepared for`, `Approves changes` and `Review date` (YYYY-MM-DD). Optional: `Unused after days` (default 90), `New code days` (default 30) and `Currency` (a symbol printed before amounts; none if absent). If a required setting is missing or the review date cannot be read, stop and ask.
2. **Code export** (codes.csv), one row per code, with these headers: `code`, `discount_type`, `value`, `applies_to`, `minimum_order`, `status`, `created_on`, `starts_on`, `ends_on`, `usage_limit`, `times_used`, `last_used_on`. Dates are YYYY-MM-DD. `discount_type` is `percent`, `amount`, `free_shipping` or `other`. `status` is the word the store exports. A blank `starts_on` means it started when created; a blank `ends_on` means no end date; a blank `usage_limit` means no limit; a blank `minimum_order` means no minimum. A blank `last_used_on` means never used when `times_used` is 0, and not known otherwise. If the store's export has no last-use date, add it from an orders export (the latest order date for each code) or leave the column blank. If the file is missing or has no rows, stop.
3. **Campaign references** (campaigns.csv), one row for each place a campaign names a code, with these headers: `campaign`, `channel`, `where_used`, `status`, `starts_on`, `ends_on`, `owner`, `code`. `status` is `live`, `scheduled`, `ended` or `draft`. A blank `ends_on` means the campaign has no end date, as with an automated email or a site banner. The person gathers these from the email tool, the ad accounts, the site, partner and creator lists, printed material and customer service replies. If the file is missing, stop and ask: without it no proposal is safe. If no campaign names a code, the person supplies the file with its header row only.
4. **Keep list** (keep_list.csv), optional, with these headers: `code`, `reason`, `named_by`. These are codes someone has said must stay, such as a code customer service sends or one printed on packaging. If it is absent, the header says the keep list was not supplied.

If a header in any file does not match, stop and ask which column is which; never guess. The assistant works only from the files the person supplies. It needs no connection to the store, the email tool or an ad account, and it never asks for a password, a login code or a key; if one is pasted in, it does not repeat it and asks the person to remove it.

## The procedure

1. **Check the inputs and work out two dates.** The unused cutoff is the review date minus `Unused after days`. The new-code cutoff is the review date minus `New code days`. Print both in the header. Under Data checks, note: any date that cannot be read; any code text that appears in more than one row exactly; any `status` word other than `active`, `scheduled`, `expired`, `disabled`, `inactive`, `paused` or `archived`; any code whose status disagrees with its dates or its usage limit; any code used at least once with no last-use date; and any campaign reference whose status is blank, another word, or `live` with an end date before the review date. Say on each line how the row was treated.
2. **Give each code one state on the review date,** taking the first that applies:
   - **Expired:** `ends_on` is earlier than the review date. A code that ends on the review date still works.
   - **Used up:** `usage_limit` is set and `times_used` is equal to it or more.
   - **Switched off:** `status` is `disabled`, `inactive`, `paused` or `archived`, or `expired` while `ends_on` has not passed.
   - **Starts later:** `starts_on` is later than the review date.
   - **Works:** anything else. An unknown status word is judged on the dates and the limit alone.
   Expired, used up and switched off together make up "no longer works".
3. **Mark use.** A code that works is **unused** when it was created on or before the new-code cutoff and either `times_used` is 0 or `last_used_on` is earlier than the unused cutoff. A code created after the new-code cutoff is **too new to judge**. A code used at least once with no last-use date has **last use not known** and is never called unused.
4. **Find duplicate groups.** Two kinds:
   - **Same text:** codes whose text is the same once letter case and spaces are ignored, whatever their state.
   - **Same offer:** codes that work or start later, with the same `discount_type`, `value`, `applies_to` (ignoring case and spaces) and `minimum_order`, whose date ranges overlap. A range runs from `starts_on` (or `created_on`) to `ends_on`, or has no end.
   Number the groups G1, G2 and so on in the order their first code appears in the export. A shared offer is not a fault in itself: codes given to different partners often share an offer on purpose, so each code's proposal follows its own use and references, never its group alone.
5. **Match the references.** A campaign reference matches the code with exactly the same text. If two rows have exactly the same text, the reference matches both and is **ambiguous**. If no code has exactly the same text, it matches a code whose text is the same ignoring case and spaces; if that finds more than one, the reference is **ambiguous** and counts for each of them. If nothing matches, the reference names a code **not in the export**. Each reference is **live or scheduled**, **ended**, or **unconfirmed** (`draft`, blank, any other word, or `live` with an end date before the review date). Match the keep list the same way; a keep-list code not in the export is a data check.
6. **Check every live or scheduled reference.** The code **will not work for it** when the code no longer works; when the code has an end date and the campaign has none; when the code ends before the campaign ends; or when the code starts later than the campaign starts. Write the problem with its dates and, where one date falls before another, the number of days between them. A code that ends on the day the campaign ends works for it. Each live or scheduled reference that its code will not work for, that is ambiguous, or that names a code not in the export, goes under Campaigns to fix, in the order of the campaign file.
7. **Choose what goes on the list.** A code is listed when it no longer works, is unused, is in a duplicate group, has a live or scheduled reference that it will not work for or that is ambiguous, has an unconfirmed reference, has last use not known, or has a date that cannot be read. Each listed code appears once, in the first section that applies: No longer works, Unused, Other codes on the list; within a section, in export order. Every other code is counted, not listed, as starting later, too new to judge, or working and used since the unused cutoff, in that order.
8. **Propose one action for each listed code,** taking the first rule that applies:
   1. **Fix the campaign first:** a live or scheduled reference that the code will not work for. The code stays as it is until the campaign owner and the approver settle it.
   2. **Confirm first:** the code has an unconfirmed reference; or a live or scheduled reference to it is ambiguous; or it is on the keep list and no longer works; or its last use is not known and no live or scheduled reference names it; or one of its dates cannot be read; or it is in a duplicate group, works or starts later, is not unused, and no live or scheduled reference names it.
   3. **Keep:** a live or scheduled reference names it and it works for that reference, or it is on the keep list and still works.
   4. **Clear the expired code:** it no longer works (expired, used up or switched off; the label is the same for all three) and nothing names it except ended campaigns. Clearing means archiving or deleting it, as the store does.
   5. **End the code:** it works, it is unused, and nothing names it except ended campaigns.
   6. **Confirm first,** for anything else on the list.
   Give the reason in one clause, using the fact that decided the rule. Never give membership of a duplicate group as the reason to end a code. Never propose changing a campaign's wording or a discount's value, and rank nothing.
9. **Write the questions.** One numbered question for each code proposed Confirm first, in export order: the facts, then the question set for its reason.
   - Unconfirmed reference: "Is [campaign] still running, and does it still need [code]?"
   - Ambiguous reference: "Which code should [campaign] use?" Codes that share one ambiguous reference share one question.
   - On the keep list and no longer works: "Is it still given out, and should it be restored or replaced?"
   - Last use not known: "When was it last used, and who gives it out?"
   - A date that cannot be read: "What is the correct [column]?"
   - Duplicate group with no live or scheduled reference: "Who gives this code out, and should it stay beside [the other codes in its group]?"
   - Anything else: "Should this code stay as it is?"
   Then, for each unconfirmed reference that names a code not in the export: "Is [campaign] still running, and which code should it name?"
10. **Close and check the counts.** The codes under each proposed action must add up to the codes on the list, and the codes on the list plus the codes counted must add up to the rows in the export. Print the not-checked line, the line saying nothing was changed, and the trace line. Return the review to the person who prepared it, for the approver.

## Exceptions and stop conditions

- **A required setting is missing, the review date cannot be read, the code export is missing or empty, or the campaign references are missing:** stop and ask.
- **A header does not match:** stop and ask which column is which.
- **A date in a row cannot be read:** note it under Data checks, list the code, propose Confirm first, and work nothing out from that date.
- **The same code text appears in two rows:** note it under Data checks; the rows form a same-text group, and a campaign reference to that text is ambiguous and counts for both rows.
- **A campaign reference names a code not in the export:** list it under Campaigns to fix if it is live or scheduled, or as a question if it is unconfirmed. Never create the code or guess which code was meant.
- **A password, login code or key is pasted in:** do not repeat it; ask the person to remove it from the source.
- **A code or a reference names a private person,** such as a one-off code for a customer: refer to it by code only and leave the name out.
- **Asked to end, delete, archive, create or edit a code, change a campaign, or message a campaign owner:** decline; a person makes every change after the approver agrees.
- **Asked whether a discount is worth it, what a code costs the store, or which code shoppers prefer:** decline; this review does not judge them.

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

Offers are written `[value]% off` for `percent`, `[currency][value] off` for `amount`, `free shipping` for `free_shipping`, and `[value] (other)` for `other`. A minimum is written `minimum [currency][amount]`, or `no minimum`. The two cutoff lines print the number of days actually used, including a default. A code that is both starting later and too new to judge is counted as starting later. The state is the bare word (Expired, Used up, Switched off, Starts later, Works), with no date; the dates are on the line below, and a code that starts later shows its start date there. Put `See duplicate group [Gn].` on a code's Proposed line when it is in a same-text group, because the checkout may treat the codes as one.

## Reviewer checklist

1. Every row of the code export appears once, either on the list or in the counts, and the summary counts add up. (E-commerce manager)
2. Each code's state matches its dates, limit and status, and both cutoff dates are worked out correctly. (E-commerce manager)
3. Every campaign reference is matched to its code or shown as not in the export, with its status as supplied. (Each campaign owner)
4. Each campaign to fix fails on its own dates or limit, and the days between dates are counted correctly. (Campaign owner)
5. Every proposal follows the first rule that applies, and no code with a live, scheduled or unconfirmed reference is proposed for ending or clearing. (Approver)
6. A person, not the assistant, has checked every keep-list code with whoever named it. (The role on the keep list)
7. The review states that nothing was changed, and nothing was. (Approver)

## Acceptance tests

Proposed tests. Only test 1 has been tried, once; see the trial record published beside the example.

1. **Normal run.** The invented example in the public folder. Expected: 13 codes listed and 4 counted; Keep 4, Fix the campaign first 2, Confirm first 3, End the code 3, Clear the expired code 1; 3 campaigns to fix, 1 naming a code not in the export; 3 questions.
2. **Header mismatch.** The code export names a column `expires` in place of `ends_on`. Expected: stops and asks which column is which.
3. **Code ends on the campaign's last day.** Expected: no problem for that reference, and the code is not listed for it.
4. **Unused code named by a scheduled campaign.** Expected: listed under Unused and proposed Keep, with the campaign named.
5. **Ambiguous reference.** A campaign names `save10`; the export has `SAVE10` and `Save10` and no exact match. Expected: the campaign under Campaigns to fix with "matches SAVE10, Save10"; both codes proposed Confirm first, sharing one question.
6. **campaigns.csv missing.** Expected: stops and asks; proposes nothing. (A campaigns.csv with its header row only is allowed and means no campaign names a code.)
7. **Last use not known.** A code used 12 times with a blank last-use date and no campaign naming it. Expected: a data check, Confirm first, never called unused.
8. **Asked to act or to judge.** "Delete the expired codes" or "Which discount earns us most?" Expected: declines both; nothing is changed.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above.

```
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
```

## What to customize

- Your export's column names, renamed once to the defaults, and the status words your store uses.
- `Unused after days` and `New code days`: shorter for a store that runs weekly offers, longer for one that sells in seasons.
- Who approves changes, and whether ending a code that any campaign has ever named needs a second person.
- Where your campaign references come from: the email tool, ad accounts, site banners, partner and creator lists, printed inserts and customer service replies.
- What clearing an expired code means in your store, archive or delete, and how long expired codes are kept for reporting.
- Your keep list, and who may add a code to it.
- Which files the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 11 November 2026. Written by Fully Powered AI from its own published map of the work. Editorially reviewed. Tried once on its invented example on 11 November 2026 in Claude; the record is published beside it and lists the small edits made afterward that have not been run again. Not yet tested in a client environment, and not yet tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.
