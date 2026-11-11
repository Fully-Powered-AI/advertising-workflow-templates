# Ad to page check: tried on its invented example

- **Product:** Claude, run in Claude Code

Model: Claude Sonnet 5.5 (claude-sonnet-5-5). Date: 2026-11-10.

The inputs were the invented example in [example.md](example.md): the check settings, ad copy, approved offer terms and page capture for Client Q, an invented subscription tea company. No client data was used. The assistant that ran the template had not written it. It read the template and only the inputs of the example, produced the output, and only then compared it with the example's findings list and the template's reviewer checklist.

## What came out

The assistant followed the fenced instruction block and the output format. The full output was:

```
AD-TO-PAGE CHECK: Starter box spring launch, Client Q (an invented subscription tea company)

For: Acquisition manager. As of 2027-02-15. Launch date: 2027-03-01. Conversion goal: Completed starter box order. Page owner: Web developer.

PAGE STATES
D1: desktop captured; mobile captured; form-error unknown; confirmation captured. Findings: 1
D2: desktop captured; mobile captured; form-error unknown; confirmation unknown. Findings: 2, 3

ADS

A1: Platform A search, destination D1
Ad: "Starter tea box for $19" / "Six teas to try. Free delivery on your first box." / call to action "Order now"
Message: desktop same ("Starter tea box for $19"); mobile same ("Starter tea box for $19"). Other promises beyond the offer claims: none.
Offer:
  price (approved $19, first box only): ad $19. Desktop agrees ("price: $19 for your first box"), condition shown. Mobile agrees ("price: $19 for your first box"), condition shown. Term ends 2027-03-31, after launch.
  delivery (approved free, first box only): ad "free on first box". Desktop agrees ("delivery: free"), condition not shown. Mobile page silent, condition not shown. Term ends 2027-02-28, 1 day before launch.
  contents (approved six teas, no conditions): ad "six teas". Desktop agrees ("Six teas to try, delivered to your door"), condition not required. Mobile page silent, condition not required. No end date.
Form: desktop 7 fields (3 required, 4 optional, 0 blank labels); mobile 6 fields (3 required, 3 optional, 0 blank labels). Limit 6: desktop over. Labels in one view only: Date of birth (desktop). Error state unknown.
Next step: ad "Order now". Desktop first call to action "Order now", same. Mobile first call to action "Order now", same. Confirmation: "Thanks. Your box ships within 3 working days and you will get a tracking email." Names a next step: yes (a time and a tracking email).
Findings: 4, 5, 6, 7, 8

A2: Platform B social, destination D2
Ad: "Try six teas for $19" / "Cancel any time." / call to action "Shop the box"
Message: desktop same ("Try six teas for $24"); mobile same ("Try six teas for $24"). Other promises beyond the offer claims: none.
Offer:
  price (approved $19, first box only): ad $19. Desktop differs ("price: $24 first box"), condition shown. Mobile differs ("Try six teas for $24"), condition not shown. Term ends 2027-03-31, after launch.
  cancellation (approved any time, no conditions): ad "any time". Desktop page silent, condition not required. Mobile page silent, condition not required. No end date.
Form: desktop 2 fields (2 required, 0 optional, 0 blank labels); mobile 2 fields (2 required, 0 optional, 0 blank labels). Limit 6: within. Same fields in both views. Error state unknown.
Next step: ad "Shop the box". Desktop first call to action "Start my box", differs. Mobile first call to action "Start my box", differs. Confirmation: not captured, unknown.
Findings: 9, 10, 11

FINDINGS

1. Unknown. D1 (used by A1), form-error state. Ad: not applicable. Page: no rows captured for D1 in state form-error. To settle: a capture of the D1 form after a failed submission. Who can supply: Web developer. Decision: open.
2. Unknown. D2 (used by A2), form-error state. Ad: not applicable. Page: no rows captured for D2 in state form-error. To settle: a capture of the D2 form after a failed submission. Who can supply: Web developer. Decision: open.
3. Unknown. D2 (used by A2), confirmation state. Ad: not applicable. Page: no rows captured for D2 in state confirmation. To settle: a capture of the D2 page after a completed order. Who can supply: Web developer. Decision: open.
4. Missing on page. A1, offer, delivery. Ad: "Free delivery on your first box." Page: desktop "delivery: free" without the condition "first box only"; mobile says nothing about delivery. To settle: the page shows the first-box condition on desktop and states delivery on mobile, or the ad changes. Who can supply: Web developer. Decision: open.
5. Timing conflict. A1, offer, delivery. Ad: "Free delivery on your first box." The approved delivery term ends 2027-02-28, 1 day before the launch date 2027-03-01. Page: desktop "delivery: free"; mobile silent. To settle: the term's end date is confirmed or extended, or the ad and page change. Who can supply: Acquisition manager (the term's owner). Decision: open.
6. Missing on page. A1, offer, contents. Ad: "Six teas to try." Page: desktop subheadline "Six teas to try, delivered to your door"; mobile says nothing about the contents. To settle: the mobile page states the contents, or the ad changes. Who can supply: Web developer. Decision: open.
7. Form friction. A1, form, desktop. Page: 7 fields (Email, Full name, Delivery address, Phone number, Tea preference, Date of birth, Gift message), against the limit of 6. To settle: a decision to remove a field or keep the limit as it stands. Who can supply: not stated. Decision: open.
8. Differs. A1, form, desktop against mobile. Page: desktop has 7 fields, mobile has 6; Date of birth appears on desktop only. To settle: the two forms are confirmed as intended or made to match. Who can supply: Web developer. Decision: open.
9. Differs. A2, offer, price. Ad: "Try six teas for $19". Approved: $19, first box only. Page: desktop "price: $24 first box"; mobile headline "Try six teas for $24", with no condition shown. To settle: the page price and the mobile condition are corrected, or the approved term changes. Who can supply: Web developer (page), Acquisition manager (term). Decision: open.
10. Missing on page. A2, offer, cancellation. Ad: "Cancel any time." Approved: any time. Page: neither desktop nor mobile states it. To settle: the page states the cancellation term, or the ad changes. Who can supply: Web developer. Decision: open.
11. Differs. A2, next step. Ad: call to action "Shop the box". Page: desktop and mobile first call to action "Start my box". To settle: the wording is aligned or the difference is accepted. Who can supply: Web developer. Decision: open.

Findings in all: 11. Unknown 3; Missing on page 3; Differs 3; Timing conflict 1; Form friction 1.
Not checked: page speed, tracking, accessibility, whether any claim is allowed,
and how the page will convert.
Next step: the Acquisition manager decides, finding by finding, which must be fixed before launch. No page, ad or account has been changed.

Every statement traces to the check settings, the ad copy, the approved offer
terms and the page capture supplied. Nothing marked unknown was assumed to be fine.
```

## What was observed

- **Every required part was produced.** The run reached eleven findings, three Unknown, three Missing on page, three Differs, one Timing conflict and one Form friction, which is what the template's first acceptance test expects. It stopped for nothing: the settings were complete, no header mismatched, no `ad_id` repeated and no date was unreadable.
- **It matched the published example in substance.** The page states, all eleven findings, their headings and their numbering, the counts, and the 1-day timing conflict agree with the example. Comparing quotations and arithmetic against the inputs found no error in either output.
- **Differences from the published example, all in wording or detail:**
  - The example adds "(page-state finding 1 also applies)" to each ad's findings line. The output format does not ask for it, so this run left it out.
  - The example leaves the condition result off lines where the page is silent or no condition exists. The format asks for one, so this run wrote "condition not shown" for a silent page and "condition not required" where the term has no conditions.
  - The example's A2 message line carries a note that amounts are checked under Offer. This run did not add it.
  - Finding 7: the example names "Acquisition manager (decision), Web developer (page)" as who can supply. This run wrote "not stated", because the template says to name the page owner for the page and the terms file's owner for a term, and a field limit is neither. The settings file does not say who can supply it.
  - Findings 4 and 6 quote the ad's sentence ("Free delivery on your first box.", "Six teas to try.") where the example quotes the claim; the contents finding in the example quotes only "six teas".
  - The example's finding 4 and 5 do not both say what mobile showed; this run named both views in both findings.
  - The example's finding 7 also gives the required count (3); this run did not.
- **Facts not in the inputs.** None found in either output. The example's "Who can supply" for finding 7 names the acquisition manager as the decider, which comes from the template's roles rather than from the inputs.
- **Where the instructions were ambiguous and a guess was needed:**
  - The procedure never says which heading a `page silent` result or a `condition not shown` result gets. This run used Missing on page, which fits the example but is an inference.
  - Step 4 compares "the ad's value with the approved value", but the ad's delivery value is "free on first box" and the approved value is "free" with the condition "first box only". The run treated the ad's wording as the same as the approved term; the template does not say how to treat a condition written inside the ad's value.
  - The contents claim: the page has no row beginning `contents:`, but the desktop subheadline gives the value. The run counted that as the page stating the item, as step 4 allows for subheadline text. A reader could ask whether "Six teas to try" covers it, and the template says to mark `differs` when unsure whether a row concerns the item.
  - Whether "Six teas to try." in the ad body is covered by the contents claim, or is another promise to look for in the headline and subheadline. The run treated it as covered.
  - The Unknown findings need an "Ad" line in the format. The template does not say what to put there for a page-state finding; this run wrote "not applicable", as the example does.
  - Step 8 puts the form findings in the order friction, then Differs, only by implication (the list order in step 5). The run followed the order in step 5.
  - The ad block's "Findings:" line: it is unclear whether the page-state finding numbers should be repeated there. The format says only "numbers, or none".
  - The format's Next step line asks for "whether it names a next step" but not what to write when the answer is yes; the run added what it named.
  - The trace line says the check "traces" every statement to the inputs, which is true here, but the finding text "Who can supply" for a Form friction finding has no rule behind it, as noted above.
- **Note added after an independent review (the run itself is unchanged).** After this run the template's wording was clarified on the points marked above as ambiguous (the heading for page silent and condition not shown, a condition written into the ad's value, who can supply a form finding, and the ad block's findings line), and the example's findings list was brought into line with the output format. That is why the differences listed above no longer all exist in the published example. The template was not run again after those changes, so this record describes the run on the earlier wording only. A second review then asked for further wording changes, which were also not re-run: finding Ad lines are `not applicable` for page-state and form findings, an `Approved:` element for offer findings, the heading when one item both differs and has a condition not shown, the order of form findings, calls to action compared ignoring case and punctuation, and writing what a confirmation names. The recorded output above, including its missing `Ad:` on findings 7 and 8, is unchanged.
- **Reviewer checklist.** The assistant checked its output against the seven items. Items 1 to 6 hold. Item 7 holds: nothing is ranked, rewritten, judged or predicted, and the output says nothing was changed.
- **Shortcomings.** This is one run, by one model, on one invented example, scored by the same assistant that produced the output. It shows the template can be followed to the expected result on this input. It does not show how the template behaves on a real campaign, with messy captures or with another product.
