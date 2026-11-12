# Ad to page check

Workflow template, version 0.1.0.

## Purpose

Compare each ad in a campaign with the landing page it sends people to, as captured, before the campaign goes live, and give the acquisition owner one numbered findings list. The comparison covers four things on desktop and mobile: whether the page is about what the ad is about, whether each offer detail matches the approved offer terms, what the form asks of the visitor, and whether the next step the ad names is the one the page offers. A page state nobody captured is marked unknown, never assumed fine. The assistant prepares the list. It changes no page or ad, predicts no conversion, judges no claim and fills no gap with a guess.

## When to use it and when not to

Use it when the ads are written, the destination page is built and captured, and the campaign has not yet been switched on. Run it again after the page changes or an offer term moves.

Do not use it:

- to set the campaign up in an account; that is the campaign build sheet;
- to judge each form field's purpose or propose new labels; that is the lead form field review;
- to tie each claim to its evidence or decide whether wording may be released; that is the campaign claim evidence register;
- to rewrite the ad or the page; that is copy edit with a change list;
- to audit a campaign taken over from someone else, with its running ads and disagreeing destinations; that is the inherited campaign audit, whereas this check is the prelaunch comparison of ads you are about to switch on;
- to measure page speed, tracking, accessibility or conversion.

## Roles

- **Starts it and decides which findings must be fixed before launch:** the acquisition owner.
- **Owns the page and supplies the capture:** the page owner named in the settings.
- **Confirms the approved offer terms:** the owner named in the terms file.

## Inputs

1. **Check settings,** as `name: value` lines. Required: `Business`, `Campaign`, `Prepared for`, `Page owner`, `Conversion goal`. Optional: `As-of date` (YYYY-MM-DD), `Launch date` (YYYY-MM-DD), `Required page states` (items separated by semicolons; default `desktop; mobile`), `Form field limit` (a whole number; none if absent) and `Form expected` (`yes` or `no`). If a required setting is missing, stop and ask.
2. **Ad copy** (ad_copy.csv), one row per ad, with these headers: `ad_id`, `channel`, `headline`, `body`, `call_to_action`, `destination_ref`, `offer_claims`. `offer_claims` holds the offer details the ad states as `item: value` pairs separated by semicolons. If a header does not match, stop and ask which column is which; never guess. If the file is missing or has no rows, stop.
3. **Approved offer terms** (offer_terms.csv), with these headers: `offer_item`, `approved_value`, `conditions`, `end_date`, `owner`. `end_date` is YYYY-MM-DD or blank. If the file is missing, every offer claim is an unknown. If a header does not match, stop and ask.
4. **Page capture** (page_capture.csv), one row per element as seen, with these headers: `page_ref`, `state`, `order`, `element_type`, `content`, `required`, `note`. `state` is `desktop`, `mobile`, `form-error` or `confirmation`; any other word is listed but not checked. `order` is the element's position from the top of the page within its state. `element_type` is `headline`, `subheadline`, `offer`, `cta`, `form_field`, `error_message`, `confirmation` or `other`. Offer rows are written `item: value`. For a form field, `content` is its label and `required` is `yes` or `no`. If the file is missing, every state of every destination is unknown. If a header does not match, stop and ask.

The assistant works from what the person supplies. It opens no address, needs no connection to an ad platform, website or analytics tool, and never asks for a password, a login code or a key; if one is pasted in, it does not copy it and tells the person to remove it.

## The procedure

1. **Check the inputs.** Match `destination_ref` and `page_ref`, and offer items, by exact text after trimming spaces and ignoring case. Stop if `ad_id` repeats. Take the launch date from `Launch date`, or from `As-of date` if there is no launch date; with neither, skip the date check and say so.
2. **Find the page states.** For each destination used by an ad, and for each required state, the state is captured if the capture has at least one row for that destination and state; otherwise it is unknown. Raise one finding per destination and state, headed Unknown, listing the ads that use it. Nothing is compared in an unknown state; write `unknown` in its place.
3. **Check the message.** Take the ad headline and remove its amounts, dates and offer-claim values; what remains is the subject. In each captured desktop and mobile state, compare it with the page's headline row: `same` when it names the same thing in the same words or plainly the same meaning; `differs` when it names something else, quoting both; `missing` when the state has no headline row. When unsure whether two phrasings mean the same, mark `differs` and quote both. Any sentence of the body that is not covered by an offer claim is another promise: look for it in the state's headline and subheadline rows and mark it same, differs or not on page. Do not judge whether a promise is true or allowed.
4. **Check each offer claim.** For each `item: value` in the ad's `offer_claims`, find the item in the terms. An item not in the terms, or a claim with no colon, is an Unknown finding, because it cannot be compared. Otherwise, in each captured desktop and mobile state, find what the page says: a row that begins with `item:`, or, in headline, subheadline and cta rows, text that gives a value for that same item. Compare as written; amounts are compared as numbers, so `$19` and `$19.00` agree. Mark the state `agrees`, `differs` (quote the page and the approved value), or `page silent`. When unsure whether a row concerns the item, quote it and mark `differs`. Also compare the ad's own value with the approved value, and raise a Differs finding quoting both when they differ. If the ad's value carries a condition, such as `free on first box`, read it as the value (`free`) plus the condition (`first box only`): the value is compared with the approved value and the condition with the term's `conditions`, and neither is a finding when it agrees. A `page silent` result is raised as Missing on page. If the terms give `conditions`, the page shows them when the same row states them in the same words or plainly the same meaning; otherwise write `condition not shown`, which is also raised as Missing on page. Write `condition not required` when the term has no conditions. If the term has an `end_date` earlier than the launch date, raise a Timing conflict finding that gives both dates and the number of days between them. A term that ends on the launch date is not in conflict.
5. **Check the form.** For each captured desktop and mobile state, count the `form_field` rows, the rows marked `yes` as required, the rest as optional, and the rows with a blank label. If a form field limit is set and a state has more fields, raise a Form friction finding listing the labels. If the desktop and mobile labels differ, raise a Differs finding naming the labels that appear in one view only. If `Form expected` is `yes` and a captured state has no form rows, raise a Missing on page finding. A blank label is a Missing on page finding. If the form-error state is captured, show each `error_message` row; a captured form-error state with no `error_message` row, or with a blank one, is a Missing on page finding. Judge nothing about what a field is for.
6. **Check the next step.** Take the lowest-numbered `cta` row in each captured desktop and mobile state. It is `same` as the ad's `call_to_action` when the words are the same, ignoring case and punctuation; otherwise it is `differs`, quoting both. No `cta` row is `missing`. If the confirmation state is captured, quote its text and state whether it names a next step, meaning an action, a time or a contact; if it names none, raise a Missing on page finding.
7. **Compare the views.** Where a check has a different result on desktop and on mobile, say so in the finding. Never carry a result from one view to the other.
8. **Number the findings.** Page-state findings come first, in the order destinations appear in the ad file. Then each ad in file order, and within an ad: message, offer (in claim order, the date finding after the page finding for the same item), form (in the order of step 5: Form friction, then Differs, then Missing on page), next step. Raise one finding per ad and item or area, covering both views. When one item has both a `differs` result and a `condition not shown` result, raise one Differs finding that names both. If two ads share a destination, raise the form and page-state findings once and write `see finding n` in the second ad's block. Each finding has a heading from this fixed list: Unknown, Missing on page, Differs, Timing conflict, Form friction. A result of `differs` is raised under Differs, and `missing`, `page silent` and `condition not shown` under Missing on page. For each, give where, what the ad says (`not applicable` for a page-state or form finding, which has no ad text to quote), for an offer finding the approved value and conditions, what the page shows, what would settle it and who can supply it: the page owner for the page, including every form finding, the terms file's owner for a term, and otherwise `not stated`. The person who decides is not named there; the Decision line is the acquisition owner's. The `Findings:` line in an ad's block lists only the findings raised in that block, not the page-state findings, which appear under PAGE STATES.
9. **Close.** Count findings in all and under each heading. List what was not checked: page speed, tracking, accessibility, whether any claim is allowed, and how the page will convert. State that no page, ad or account was changed, and give the trace line.

## Exceptions and stop conditions

- **A required setting is missing, the ad file is missing or empty, or `ad_id` repeats:** stop and ask.
- **A header does not match the default:** stop and ask which column is which.
- **A state, destination or capture is missing:** mark it unknown and continue.
- **An offer item is not in the terms:** raise an Unknown finding for that claim and continue.
- **A date cannot be read as YYYY-MM-DD:** raise an Unknown finding and work nothing out from it.
- **A password, login code or key is pasted in:** do not copy it; ask the person to remove it.
- **Asked to change a page or ad, predict conversion, judge whether a claim is allowed, rank findings by importance, call the page good enough, or decide what must be fixed:** decline; the acquisition owner decides.

## Output format

```
AD-TO-PAGE CHECK: [campaign], [business]

For: [prepared for]. As of [date or not stated]. Launch date: [date or not stated]. Conversion goal: [goal]. Page owner: [owner].

PAGE STATES
[destination]: [state] [captured or unknown]; [state] [captured or unknown]; and so on. Findings: [numbers, or none]

ADS

[ad_id]: [channel], destination [destination]
Ad: "[headline]" / "[body]" / call to action "[call to action]"
Message: desktop [same, differs, missing or unknown] ("[page headline]"); mobile [same, differs, missing or unknown] ("[page headline]"). Other promises beyond the offer claims: [list with result, or none].
Offer:
  [item] (approved [value], [conditions or no conditions]): ad [ad value]. Desktop [agrees, differs or page silent] ("[page text]"), condition [shown, not shown or not required]. Mobile [same form]. Term ends [date] [n days before launch, or after launch], or no end date.
  [one line for each offer claim]
Form: desktop [n] fields ([n] required, [n] optional, [n] blank labels), or unknown; mobile [same form]. Limit [n or none]: [within, desktop over, mobile over, or not set]. [Labels in one view only, or same fields in both views.] Error state [captured with its messages, or unknown].
Next step: ad "[call to action]". Desktop first call to action "[text]", [same or differs]. Mobile first call to action "[text]", [same or differs]. Confirmation: ["[text]" and whether it names a next step, with what it names if it does, or not captured, unknown].
Findings: [numbers, or none]

[repeat for every ad in the order of the file]

FINDINGS

[n]. [Heading]. [Where]. Ad: "[ad text]", or not applicable. [For an offer finding: Approved: [approved value, conditions or no conditions].] Page: [what the page shows, by view]. To settle: [what would resolve it]. Who can supply: [role or not stated]. Decision: open.
[or: No findings.]

Findings in all: [n]. Unknown [n]; Missing on page [n]; Differs [n]; Timing conflict [n]; Form friction [n].
Not checked: page speed, tracking, accessibility, whether any claim is allowed,
and how the page will convert.
Next step: the [prepared for] decides, finding by finding, which must be fixed before launch. No page, ad or account has been changed.

Every statement traces to the check settings, the ad copy, the approved offer
terms and the page capture supplied. Nothing marked unknown was assumed to be fine.
```

## Reviewer checklist

1. Every quotation of the ad and of the page appears word for word in the inputs. (Acquisition owner)
2. Every state with no captured rows is marked unknown, and nothing was compared in it. (Page owner)
3. Each offer comparison uses the approved value from the terms file, and amounts and dates are worked out correctly. (Term owner)
4. The form counts, the limit result and the labels in one view only match the capture. (Page owner)
5. Desktop and mobile results are never merged or carried across. (Acquisition owner)
6. Every finding has one heading from the fixed list, a place, a settling step and a person who can supply it. (Acquisition owner)
7. The list ranks nothing, rewrites nothing, judges no claim, predicts no conversion and states that nothing was changed. (Acquisition owner)

## Acceptance tests

Proposed tests. None has been run.

1. **Normal run.** The invented example in the public folder. Expected: eleven findings, three Unknown, three Missing on page, three Differs, one Timing conflict, one Form friction.
2. **Header mismatch.** The capture names a column `view` in place of `state`. Expected: stops and asks which column is which.
3. **No mobile capture.** One destination has desktop rows only. Expected: mobile marked unknown, one Unknown finding, and no mobile result anywhere for it.
4. **Term ends on launch day.** An offer term's end date equals the launch date. Expected: no Timing conflict.
5. **Offer item not in the terms.** An ad claims `bonus: free mug` and the terms file has no bonus row. Expected: an Unknown finding for that claim; the run continues.
6. **Blank form label.** One desktop form field has an empty label. Expected: a Missing on page finding and the blank counted.
7. **Shared destination.** Two ads use the same page. Expected: the page-state and form findings raised once, with `see finding n` in the second ad's block.
8. **Asked to decide or predict.** "Which of these matter most?" or "Will this convert?" Expected: declines both; the acquisition owner decides.

## Instructions for the AI assistant

```
You prepare an ad to page check for the acquisition owner: each ad in a
campaign set beside its captured landing page, as one numbered findings
list. You change no page, ad or account, you predict no conversion, you
judge no claim and you never fill a gap with a guess. The acquisition owner
decides which findings must be fixed before launch. Never ask for a
password, a login code or a key; if one is pasted in, do not copy it and say
to remove it.

The user will supply: check settings (name: value lines); ad_copy.csv
(ad_id, channel, headline, body, call_to_action, destination_ref,
offer_claims); offer_terms.csv (offer_item, approved_value, conditions,
end_date, owner); page_capture.csv (page_ref, state, order, element_type,
content, required, note). Match references by exact text after trimming
spaces, ignoring case. Required settings: Business, Campaign, Prepared for,
Page owner, Conversion goal. Optional settings: As-of date, Launch date
(YYYY-MM-DD), Required page states (default desktop; mobile), Form field limit
(a whole number; none if absent) and Form expected (yes or no). The launch
date is Launch date, else As-of date; with neither, skip the date check and
say so. A date that cannot be read as YYYY-MM-DD is an Unknown finding; work
nothing out from it. If a required setting is missing, the ad file is missing
or empty, or ad_id repeats, stop and ask. If a header does not match, stop and
ask which column is which. If offer_terms.csv is missing, every offer claim is
an Unknown finding; if page_capture.csv is missing, every state is unknown.
Never open an address.

Steps:
1. Page states: for each destination and required state (default desktop and
   mobile), it is captured if the capture has a row for it, otherwise
   unknown. One Unknown finding per destination and state. Compare nothing
   in an unknown state. A state word other than desktop, mobile, form-error
   or confirmation is listed but not checked. If two ads share a destination, raise the page-state
   and form findings once and write "see finding n" in the second ad's block.
2. Message: remove amounts, dates and offer values from the ad headline;
   compare the rest with the page headline in each captured desktop and
   mobile state: same, differs (quote both) or missing. When unsure, differs.
   Check any body promise not covered by an offer claim the same way.
3. Offer: for each item: value claim, find the item in the terms (not found:
   Unknown finding). In each captured view compare the page with the approved
   value: agrees, differs or page silent, and whether the conditions are
   shown, not shown or not required. Page silent and condition not shown are
   Missing on page. Also compare the ad's own value with the approved value:
   differs is a Differs finding quoting both; a condition inside the ad's
   value (free on first box) is read as the value plus the condition and
   compared with the term's conditions. Amounts are compared as numbers. An end date earlier than the
   launch date (or the as-of date if no launch date) is a Timing conflict
   with both dates and the days between.
4. Form: per view count fields, required, optional and blank labels. Over the
   field limit is Form friction. Labels in one view only is Differs. A blank
   label, a form-error state with no message, or no form where one is
   expected is Missing on page. Judge no field's purpose.
5. Next step: the lowest-numbered cta row in each view against the ad's: same
   (same words, ignoring case and punctuation) or differs; no cta row is
   missing. Quote the confirmation text and say whether it names an action,
   time or contact, and which; if none, Missing on page.
6. Never carry a result from desktop to mobile or the reverse.
7. Number the findings: page states first, then each ad in file order and
   within it message, offer, form (Form friction, then Differs, then Missing
   on page), next step. Headings: Unknown, Missing on
   page, Differs, Timing conflict, Form friction. For each give where, ad
   text (not applicable for a page-state or form finding), for an offer
   finding the approved value and conditions, page text by view, what would settle it, who can supply it (the page
   owner for the page, including form findings; the terms owner for a term;
   otherwise not stated), and Decision: open. A differs result is a Differs
   finding; missing, page silent and condition not shown are Missing on page.
   An item with both differs and condition not shown is one Differs finding
   naming both.
   An ad block's Findings line lists only that block's findings, not the
   page-state ones. Rank nothing.
8. Use the output format exactly. End with counts, the not-checked line, the
   next-step line (the person it is prepared for decides which findings
   must be fixed before launch; nothing was changed), and the trace line.

If asked to change a page or ad, predict conversion, judge whether a claim
is allowed, rank findings or decide what must be fixed, decline; the
acquisition owner decides.
```

## What to customize

- The page states you can capture, and which are required.
- Your offer items and the wording of each approved value.
- Your form field limit, or none.
- Whether a form is expected on your pages.
- The words your tools use for page elements, if you rename the capture columns once to the defaults.
- Who owns the page, who confirms each term and who decides at launch.
- Which exports the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI. Tried once on its invented example, in Claude on 10 November 2026, with the record published beside it. Not yet tested in a client environment.
