# Stale promotion code review: an invented example

*Illustrative example with invented data.* The store, the roles, the platform, the codes, the campaigns, the dates and every figure below are invented. Store K is an invented online candle shop with seventeen discount codes built up over two years. Its e-commerce manager ran the workflow template a few days before a spring launch. First come the inputs the e-commerce manager supplied, in full, then the review the workflow template returned.

## The inputs

### 1. Review settings

```
Store: Store K (an invented online candle shop)
Prepared for: E-commerce manager
Approves changes: E-commerce manager
Review date: 2027-03-15
Unused after days: 90
New code days: 30
Currency: $
```

### 2. Code export (codes.csv)

```
code,discount_type,value,applies_to,minimum_order,status,created_on,starts_on,ends_on,usage_limit,times_used,last_used_on
WELCOME10,percent,10,All products,,active,2025-06-01,2025-06-01,,,412,2027-03-14
FREESHIP50,free_shipping,,All products,50,active,2025-09-01,2025-09-01,,,950,2027-03-14
REFILL5,amount,5,Refills,,active,2025-08-01,2025-08-01,,,230,2027-03-13
HOLIDAY25,percent,25,All products,,expired,2026-11-20,2026-11-25,2026-12-31,,388,2026-12-31
VIP20,percent,20,All products,,active,2026-02-14,2026-02-14,,,61,2026-10-02
SORRY10,amount,10,All products,,expired,2026-02-01,2026-02-01,2027-01-31,,22,2027-01-29
SHIPFREE50,free_shipping,,All products,50,active,2026-04-02,2026-04-02,,,3,2026-08-19
SUMMER20,percent,20,Summer range,,disabled,2026-05-20,2026-06-01,,,210,2026-08-30
BUNDLE20,percent,20,Bundles,,active,2026-06-01,2026-06-01,,,97,2027-03-10
CREATORA15,percent,15,All products,,active,2026-09-01,2026-09-01,,,140,2027-03-12
CREATORB15,percent,15,All products,,active,2026-09-01,2026-09-01,,,0,
FIRST100,amount,15,All products,,active,2026-10-01,2026-10-01,,100,100,2026-10-09
GIFTSET,amount,5,Gift sets,,active,2025-11-01,2025-11-01,,,75,2026-12-20
giftset,amount,8,Gift sets,,active,2026-11-15,2026-11-15,,,0,
PRESS15,percent,15,Candles,,active,2026-03-01,2026-03-01,,,12,
GIFTING10,percent,10,Gift sets,,active,2027-03-05,2027-03-05,2027-03-28,,4,2027-03-14
SPRING15,percent,15,All products,40,scheduled,2027-03-01,2027-03-20,2027-03-31,,0,
```

### 3. Campaign references (campaigns.csv)

Gathered by the e-commerce manager from the email tool, the ad account on Platform A, the site, the creator list and the packaging file.

```
campaign,channel,where_used,status,starts_on,ends_on,owner,code
Welcome flow,Email,Welcome email 1,live,2025-06-01,,Email marketer,WELCOME10
Free shipping banner,Website,Site-wide banner,live,2026-01-10,,E-commerce manager,FREESHIP50
Refill reminder,Email,Reminder email,live,2025-08-01,,Email marketer,REFILL5
Holiday gift guide,Email,Gift guide email,ended,2026-11-25,2026-12-31,Email marketer,HOLIDAY25
Holiday ads,Platform A,Ad text,ended,2026-11-25,2026-12-31,Paid media lead,HOLIDAY25
VIP early access,Email,VIP email,scheduled,2027-04-01,2027-04-07,Email marketer,VIP20
Summer range insert,Packaging,Printed insert card,,2026-06-01,,E-commerce manager,SUMMER20
Creator A programme,Creator posts,Captions and link,live,2026-09-01,,Creator programme lead,CREATORA15
Creator B programme,Creator posts,Captions and link,ended,2026-09-01,2026-12-31,Creator programme lead,CREATORB15
First order pop-up,Website,Home page pop-up,live,2026-10-01,,E-commerce manager,FIRST100
Gift set search ads,Platform A,Ad text,live,2026-11-15,2027-03-31,Paid media lead,GIFTSET
Spring gifting,Platform A,Ad text,live,2027-03-05,2027-03-28,Paid media lead,GIFTING10
Spring launch,Email,Launch email,scheduled,2027-03-20,2027-04-10,Email marketer,SPRING15
Spring launch,Email,Launch email,scheduled,2027-03-20,2027-04-10,Email marketer,SPRINGSHIP
```

### 4. Keep list (keep_list.csv)

```
code,reason,named_by
SORRY10,Customer service sends it after a late delivery,Customer service lead
```

## The review

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
FIRST100: status "active", but 100 of a limit of 100 uses made; treated as used up.
PRESS15: used 12 times with no last-use date; treated as last use not known, not unused.
Summer range insert, naming SUMMER20: status blank; treated as unconfirmed.

NO LONGER WORKS
HOLIDAY25: 25% off, All products, no minimum. Expired.
  Created 2026-11-20; ends 2026-12-31; used 388 times;
  last used 2026-12-31. Group: none.
  References: Holiday gift guide (Email, ended, Email marketer);
  Holiday ads (Platform A, ended, Paid media lead).
  Proposed: Clear the expired code, because it ended on 2026-12-31 and only
  ended campaigns name it.
  Decision: open.
SORRY10: $10 off, All products, no minimum. Expired.
  Created 2026-02-01; ends 2027-01-31; used 22 times;
  last used 2027-01-29. Group: none.
  References: none.
  Keep list: Customer service sends it after a late delivery, named by Customer service lead.
  Proposed: Confirm first, because it is on the keep list but ended on 2027-01-31. See question 1.
  Decision: open.
SUMMER20: 20% off, Summer range, no minimum. Switched off.
  Created 2026-05-20; no end date; used 210 times;
  last used 2026-08-30. Group: none.
  References: Summer range insert (Packaging, status not stated, E-commerce manager).
  Proposed: Confirm first, because a reference with no status may still be in use. See question 2.
  Decision: open.
FIRST100: $15 off, All products, no minimum. Used up.
  Created 2026-10-01; no end date; used 100 times of a limit of 100;
  last used 2026-10-09. Group: none.
  References: First order pop-up (Website, live, E-commerce manager).
  Proposed: Fix the campaign first, because a live campaign names a code that no
  longer works. See campaigns to fix 1.
  Decision: open.

UNUSED
VIP20: 20% off, All products, no minimum. Works.
  Created 2026-02-14; no end date; used 61 times;
  last used 2026-10-02. Group: none.
  References: VIP early access (Email, scheduled, Email marketer).
  Proposed: Keep, because a scheduled campaign names it and it works for that
  campaign's dates.
  Decision: open.
SHIPFREE50: free shipping, All products, minimum $50. Works.
  Created 2026-04-02; no end date; used 3 times;
  last used 2026-08-19. Group: G1.
  References: none.
  Proposed: End the code, because it has not been used since 2026-08-19 and
  nothing names it.
  Decision: open.
CREATORB15: 15% off, All products, no minimum. Works.
  Created 2026-09-01; no end date; used 0 times;
  last used never. Group: G2.
  References: Creator B programme (Creator posts, ended, Creator programme lead).
  Proposed: End the code, because it has never been used and only an ended
  campaign names it.
  Decision: open.
giftset: $8 off, Gift sets, no minimum. Works.
  Created 2026-11-15; no end date; used 0 times;
  last used never. Group: G3.
  References: none.
  Proposed: End the code, because it has never been used and nothing names it. See duplicate group G3.
  Decision: open.

OTHER CODES ON THE LIST
FREESHIP50: free shipping, All products, minimum $50. Works.
  Created 2025-09-01; no end date; used 950 times;
  last used 2027-03-14. Group: G1.
  References: Free shipping banner (Website, live, E-commerce manager).
  Proposed: Keep, because a live campaign names it and it works for that
  campaign's dates.
  Decision: open.
CREATORA15: 15% off, All products, no minimum. Works.
  Created 2026-09-01; no end date; used 140 times;
  last used 2027-03-12. Group: G2.
  References: Creator A programme (Creator posts, live, Creator programme lead).
  Proposed: Keep, because a live campaign names it and it works for that
  campaign's dates.
  Decision: open.
GIFTSET: $5 off, Gift sets, no minimum. Works.
  Created 2025-11-01; no end date; used 75 times;
  last used 2026-12-20. Group: G3.
  References: Gift set search ads (Platform A, live, Paid media lead).
  Proposed: Keep, because a live campaign names it and it works for that
  campaign's dates. See duplicate group G3.
  Decision: open.
PRESS15: 15% off, Candles, no minimum. Works.
  Created 2026-03-01; no end date; used 12 times;
  last used not in the export. Group: none.
  References: none.
  Proposed: Confirm first, because its last use is not known and no live or
  scheduled campaign names it. See question 3.
  Decision: open.
SPRING15: 15% off, All products, minimum $40. Starts later.
  Created 2027-03-01; starts 2027-03-20; ends 2027-03-31; used 0 times;
  last used never. Group: none.
  References: Spring launch (Email, scheduled, Email marketer).
  Proposed: Fix the campaign first, because the code ends before a scheduled
  campaign that names it. See campaigns to fix 2.
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
  Problem: the code is used up, 100 of a limit of 100; last used 2026-10-09.
  To settle: E-commerce manager changes the campaign, or E-commerce manager
  approves a change to the code. Decision: open.
2. Spring launch (Email, scheduled, 2027-03-20 to 2027-04-10,
  owner Email marketer) names SPRING15 in Launch email.
  Problem: the code ends 2027-03-31, 10 days before the campaign ends on 2027-04-10.
  To settle: Email marketer changes the campaign, or E-commerce manager approves
  a change to the code. Decision: open.
3. Spring launch (Email, scheduled, 2027-03-20 to 2027-04-10,
  owner Email marketer) names SPRINGSHIP in Launch email.
  Problem: not in the code export.
  To settle: Email marketer corrects the code in the campaign, or E-commerce
  manager decides whether the code should exist. Decision: open.

QUESTIONS FOR THE E-COMMERCE MANAGER
1. SORRY10. The keep list says customer service sends it after a late delivery,
  named by Customer service lead. It expired on 2027-01-31. Is it still given
  out, and should it be restored or replaced?
2. SUMMER20. Switched off, with status disabled. Summer range insert (Packaging,
  Printed insert card, owner E-commerce manager) names it with no status. Is
  Summer range insert still running, and does it still need SUMMER20?
3. PRESS15. Used 12 times; the export gives no last-use date, and no campaign
  names it. When was it last used, and who gives it out?

Not checked: what each discount costs, where codes were shared outside the
campaigns listed, and how the checkout treats letter case.
Nothing has been ended, deleted, archived or changed in the store or in any
campaign. Each proposal waits for the E-commerce manager's approval; a person
makes every change.
Every statement traces to the review settings, the code export, the campaign
references and the keep list supplied.
```

How the figures were reached, for checking by hand: the review date, 15 March 2027, less 90 days is 15 December 2026, and less 30 days is 13 February 2027. The three codes counted as working and used since 15 December are WELCOME10, REFILL5 and BUNDLE20; GIFTING10, created on 5 March 2027, is the one too new to judge. Thirteen listed plus four counted makes seventeen, and the proposals (4 + 2 + 3 + 3 + 1) make thirteen. Spring launch runs to 10 April and SPRING15 ends on 31 March: ten days apart. GIFTING10 ends on 28 March, the same day as Spring gifting, so it works for that campaign and is not listed.
