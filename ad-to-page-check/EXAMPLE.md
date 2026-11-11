# Ad to page check: an invented example

*Illustrative example with invented data.* The business, the roles, the platforms, the dates and every figure below are invented. Client Q is an invented subscription tea company preparing a spring starter box campaign. The acquisition manager ran the capability after the web developer captured the two landing pages. First come the inputs, in full, then the findings list the capability returned.

## The inputs

### 1. Check settings

```
Business: Client Q (an invented subscription tea company)
Campaign: Starter box spring launch
Prepared for: Acquisition manager
Page owner: Web developer
As-of date: 2027-02-15
Launch date: 2027-03-01
Conversion goal: Completed starter box order
Required page states: desktop; mobile; form-error; confirmation
Form field limit: 6
Form expected: yes
```

### 2. Ad copy (ad_copy.csv)

```
ad_id,channel,headline,body,call_to_action,destination_ref,offer_claims
A1,Platform A search,Starter tea box for $19,Six teas to try. Free delivery on your first box.,Order now,D1,price: $19; delivery: free on first box; contents: six teas
A2,Platform B social,Try six teas for $19,Cancel any time.,Shop the box,D2,price: $19; cancellation: any time
```

### 3. Approved offer terms (offer_terms.csv)

```
offer_item,approved_value,conditions,end_date,owner
price,$19,first box only,2027-03-31,Acquisition manager
delivery,free,first box only,2027-02-28,Acquisition manager
contents,six teas,,,Acquisition manager
cancellation,any time,,,Acquisition manager
```

### 4. Page capture (page_capture.csv)

```
page_ref,state,order,element_type,content,required,note
D1,desktop,1,headline,Starter tea box for $19,,
D1,desktop,2,subheadline,"Six teas to try, delivered to your door",,
D1,desktop,3,offer,price: $19 for your first box,,
D1,desktop,4,offer,delivery: free,,
D1,desktop,5,cta,Order now,,
D1,desktop,6,form_field,Email,yes,
D1,desktop,7,form_field,Full name,yes,
D1,desktop,8,form_field,Delivery address,yes,
D1,desktop,9,form_field,Phone number,no,
D1,desktop,10,form_field,Tea preference,no,
D1,desktop,11,form_field,Date of birth,no,
D1,desktop,12,form_field,Gift message,no,
D1,mobile,1,headline,Starter tea box for $19,,
D1,mobile,2,cta,Order now,,
D1,mobile,3,offer,price: $19 for your first box,,
D1,mobile,4,form_field,Email,yes,
D1,mobile,5,form_field,Full name,yes,
D1,mobile,6,form_field,Delivery address,yes,
D1,mobile,7,form_field,Phone number,no,
D1,mobile,8,form_field,Tea preference,no,
D1,mobile,9,form_field,Gift message,no,
D1,confirmation,1,confirmation,Thanks. Your box ships within 3 working days and you will get a tracking email.,,
D2,desktop,1,headline,Try six teas for $24,,
D2,desktop,2,offer,price: $24 first box,,
D2,desktop,3,cta,Start my box,,
D2,desktop,4,form_field,Email,yes,
D2,desktop,5,form_field,Delivery address,yes,
D2,mobile,1,headline,Try six teas for $24,,
D2,mobile,2,cta,Start my box,,
D2,mobile,3,form_field,Email,yes,
D2,mobile,4,form_field,Delivery address,yes,
```

## The findings list

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
Next step: ad "Shop the box". Desktop first call to action "Start my box", differs. Mobile first call to action "Start my box", differs. Confirmation not captured, unknown.
Findings: 9, 10, 11

FINDINGS

1. Unknown. D1 (A1), form-error state. Ad: not applicable. Page: no rows captured for D1 in state form-error. To settle: a capture of the D1 form after a failed submission. Who can supply: Web developer. Decision: open.
2. Unknown. D2 (A2), form-error state. Ad: not applicable. Page: no rows captured for D2 in state form-error. To settle: a capture of the D2 form after a failed submission. Who can supply: Web developer. Decision: open.
3. Unknown. D2 (A2), confirmation state. Ad: not applicable. Page: no rows captured for D2 in state confirmation. To settle: a capture of the D2 page after a completed order. Who can supply: Web developer. Decision: open.
4. Missing on page. A1, offer, delivery. Ad: "Free delivery on your first box". Approved: free, first box only. Page: desktop "delivery: free" with no condition; mobile has no delivery statement. To settle: the page states the first-box condition on desktop and delivery on mobile, or the ad changes. Who can supply: Web developer. Decision: open.
5. Timing conflict. A1, offer, delivery. Ad: "Free delivery on your first box". Approved: free, first box only, ending 2027-02-28, 1 day before the launch date 2027-03-01. Page: desktop "delivery: free". To settle: the term's end date is confirmed or extended, or the ad and page change. Who can supply: Acquisition manager (term owner). Decision: open.
6. Missing on page. A1, offer, contents. Ad: "six teas". Approved: six teas, no conditions. Page: desktop "Six teas to try, delivered to your door"; mobile has no statement of the contents. To settle: the mobile page states the contents, or the ad changes. Who can supply: Web developer. Decision: open.
7. Form friction. A1, form, desktop. Ad: not applicable. Page: 7 fields (Email, Full name, Delivery address, Phone number, Tea preference, Date of birth, Gift message), 3 required, against the limit of 6. To settle: a decision whether a field comes off the desktop form or the limit stands. Who can supply: Web developer. Decision: open.
8. Differs. A1, form, desktop against mobile. Ad: not applicable. Page: desktop has 7 fields and mobile has 6; Date of birth appears on desktop only. To settle: the two forms are confirmed as intended or made to match. Who can supply: Web developer. Decision: open.
9. Differs. A2, offer, price. Ad: "Try six teas for $19" (price: $19). Approved: $19, first box only. Page: desktop "price: $24 first box"; mobile "Try six teas for $24" with no condition shown. To settle: the page price and the mobile condition are corrected, or the approved term changes. Who can supply: Web developer (page), Acquisition manager (term). Decision: open.
10. Missing on page. A2, offer, cancellation. Ad: "Cancel any time." Approved: any time, no conditions. Page: neither desktop nor mobile states it. To settle: the page states the cancellation term, or the ad changes. Who can supply: Web developer. Decision: open.
11. Differs. A2, next step. Ad: call to action "Shop the box". Page: desktop and mobile first call to action "Start my box". To settle: the acquisition manager accepts the difference or the wording is aligned. Who can supply: Web developer. Decision: open.

Findings in all: 11. Unknown 3; Missing on page 3; Differs 3; Timing conflict 1; Form friction 1.
Not checked: page speed, tracking, accessibility, whether any claim is allowed,
and how the page will convert.
Next step: the acquisition manager decides, finding by finding, which must be fixed before launch. No page, ad or account has been changed.

Every statement traces to the check settings, the ad copy, the approved offer
terms and the page capture supplied. Nothing marked unknown was assumed to be fine.
```
