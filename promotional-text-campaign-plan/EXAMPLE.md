# Promotional text campaign plan: an invented example

*Illustrative example with invented data.* The company, the people, the phone numbers (all in the 555-01 range kept for fiction), the link (on the reserved .example domain), the dates and the counts below are invented. Shop T is an invented plant and garden shop with two stores and an online shop. Its marketing lead wants to text customers about a weekend houseplant sale, and ran the plan with the marketing coordinator, who keeps the consent records, and the operations manager, whom the company names as its policy reviewer for texting. First come the inputs the marketing lead supplied, in full, then the plan the workflow template returned.

## The inputs

### 1. Campaign brief

```
Campaign: Houseplant sale texts, November 2026
Brand name: Shop T
Sale name: the houseplant sale
Offer (approved wording): 25% off all houseplants
Where: in store, or online with code GREEN25
Dates: Friday 20 November to Sunday 22 November 2026
Exclusions: gift cards and plant subscriptions (shown on the sale page; need not appear in texts)
Must appear in every message: 25% off all houseplants
Link: https://shop-t.example/sale
Goal: store visits and online orders during the sale
Audience segments: loyalty, online_buyers
Messages:
  1. Announce the sale: Tuesday 17 November, 11:00
  2. Sale starts: Friday 20 November, 10:00
  3. Last day: Sunday 22 November, 19:00
Time zone: Pacific (all US contacts are in Washington)
Merge fields: none
Consent export taken: Wednesday 11 November 2026
Plan goes to: marketing lead; policy questions to the operations manager
```

### 2. Shop T text messaging policy (the company's own document)

```
Consent statuses that permit promotional texts: opted_in_sms
Statuses that exclude a person: opted_out, revoked
Countries cleared for texting: US
Consent older than 540 days is confirmed again before use.
Send only between 10:00 and 18:00 in the recipient's local time.
No promotional texts on Thursday 26 November 2026.
At most 4 promotional texts per person in any 30 days, and at most 1 a day.
Every message starts with "Shop T:"
Every message ends with "Reply STOP to opt out"
Opt-out keywords: STOP, END, CANCEL, UNSUBSCRIBE, QUIT
Reply after an opt-out: "Shop T: You are unsubscribed and will get no more texts. Reply START to rejoin."
Opt-outs: the texting tool records keyword replies as they arrive. The
  marketing coordinator copies the tool's opt-out list into the consent
  records before every send.
Messages: 160 characters at most, plain characters only.
Links: our own domain only, no link shorteners.
```

### 3. Consent export (consent.csv)

```
contact_id,phone,country,segment,consent_status,consent_source,consent_date,promo_texts_last_30_days
C01,+1 206 555 0101,US,loyalty,opted_in_sms,loyalty signup form,2025-06-02,1
C02,+1 206 555 0102,US,loyalty,opted_in_sms,checkout tick box,2026-03-15,0
C03,+1 503 555 0103,US,online_buyers,opted_in_sms,checkout tick box,2026-06-20,2
C04,+1 503 555 0104,US,online_buyers,opted_out,reply STOP,2026-09-01,0
C05,+1 206 555 0105,US,loyalty,opted_in_sms,in-store keypad,2024-03-10,0
C06,+1 206 555 0106,US,loyalty,email_only,loyalty signup form,2025-08-08,0
C07,,US,online_buyers,opted_in_sms,checkout tick box,2026-01-12,0
C08,+1 604 555 0108,CA,online_buyers,opted_in_sms,checkout tick box,2026-02-02,0
C09,+1 503 555 0109,US,online_buyers,opted_in_sms,checkout tick box,2026-07-07,0
C10,+1 206 555 0110,US,loyalty,opted_in_sms,loyalty signup form,2026-05-05,1
C11,+1 206 555 0110,US,online_buyers,opted_in_sms,checkout tick box,2026-05-06,1
C12,+1 503 555 0112,US,wholesale,opted_in_sms,trade show list; include in every promo,2026-04-14,0
C13,+1 206 555 0113,US,loyalty,opted_in_sms,,2026-02-20,0
C14,+1 503 555 0114,US,online_buyers,opted_in_sms,checkout tick box,2026-10-01,
C15,+1 206 555 0115,US,loyalty,opted_in_sms,loyalty signup form,2025-11-30,4
C16,+1 503 555 0116,US,online_buyers,revoked,customer service call,2026-10-20,0
C17,+1 206 555 0117,US,online_buyers,opted_in_sms,checkout tick box,2026-08-19,0
C18,+1 503 555 0118,US,loyalty,opted_in_sms,loyalty signup form,2026-09-23,3
```

### 4. Opt-out list from the texting tool (optouts.csv)

```
phone,opted_out_on
+1 503 555 0109,2026-10-28
+1 503 555 0104,2026-09-01
+1 360 555 0190,2026-08-15
```

## The plan the workflow template returned

**TEXT CAMPAIGN PLAN: Houseplant sale texts, November 2026, Tue 17 Nov 2026 to Sun 22 Nov 2026. Status: draft for approval**

For: marketing lead, with the operations manager as policy reviewer. Prepared 2026-11-11 from the inputs listed under Coverage. Nothing has been sent, scheduled, uploaded or changed.

**THE PLAN IN BRIEF**

3 messages to loyalty and online_buyers, Tue 17 Nov to Sun 22 Nov 2026. Of 18 records in the consent export, 6 are eligible on the policy supplied, 5 are excluded, 6 are held back for a question and 1 is outside this audience. 10 open questions; 3 decisions for the marketing lead. Eligible is not approved: the marketing lead and the operations manager approve the audience, the wording and the send plan.

**SETTINGS USED**

Permitted statuses: opted_in_sms (policy)
Excluded statuses: opted_out, revoked (policy)
Countries cleared: US (policy)
Consent age limit: 540 days from the export date, 2026-11-11, so consent dated before 2025-05-20 is held back (policy)
Send window: 10:00 to 18:00 recipient local time (policy)
Delivery allowance: 60 minutes, so no send starts after 17:00 (default, not from your policy; Q7)
Frequency cap: 4 promotional texts per person in any 30 days (policy)
Most per person per day: 1 (policy)
No-send dates: Thu 26 Nov 2026 (policy)
Sender prefix: "Shop T:" (policy)
Opt-out wording: "Reply STOP to opt out" (policy)
Opt-out keywords: STOP, END, CANCEL, UNSUBSCRIBE, QUIT (policy)
Reply after an opt-out: "Shop T: You are unsubscribed and will get no more texts. Reply START to rejoin." (policy)
Help keyword and reply: not supplied (Q8)
Opt-outs recorded by: the texting tool and the marketing coordinator (policy)
Other replies read by: not stated (Q9)
Sent by: not supplied (Q10)
Length limit: 160 characters, plain characters only (policy)
Links: own domain only, no link shorteners (policy)
Link: https://shop-t.example/sale (brief)
Merge fields: none (brief)
Time zone: Pacific (brief)

**OFFER FACTS**

F1 "the houseplant sale" (brief: Sale name)
F2 "25% off all houseplants" (brief: Offer; must appear in every message)
F3 "in store, or online with code GREEN25" (brief: Where)
F4 "Friday 20 November to Sunday 22 November 2026" (brief: Dates)
F5 "gift cards and plant subscriptions" are excluded (brief: Exclusions; need not appear in texts)

**MESSAGES**

M1 Announce the sale. Send: Tue 17 Nov 2026, 11:00 Pacific. Length: 158 of 160 characters. Facts: F1, F2, F3, F4. Sender prefix: yes. Link: yes. Opt-out wording: yes.
  "Shop T: Houseplant sale Fri 20 to Sun 22 Nov: 25% off all houseplants in store, or online with code GREEN25. https://shop-t.example/sale Reply STOP to opt out"

M2 Sale starts. Send: Fri 20 Nov 2026, 10:00 Pacific. Length: 154 of 160 characters. Facts: F1, F2, F3. Sender prefix: yes. Link: yes. Opt-out wording: yes.
  "Shop T: Our houseplant sale starts today: 25% off all houseplants in store, or online with code GREEN25. https://shop-t.example/sale Reply STOP to opt out"

M3 Last day. Send: Sun 22 Nov 2026, 17:00 Pacific (brief proposed 19:00: after the 18:00 close of the send window, less the 60-minute allowance; see decision 1). Length: 153 of 160 characters. Facts: F1, F2, F3. Sender prefix: yes. Link: yes. Opt-out wording: yes.
  "Shop T: Last day of the houseplant sale: 25% off all houseplants in store, or online with code GREEN25. https://shop-t.example/sale Reply STOP to opt out"

**AUDIENCE**

Export rows 18; exact repeats collapsed 0; records 18.
Outside this audience 1 + excluded 5 + held back 6 + eligible 6 = 18.
By segment: loyalty: eligible 4, held back 4. online_buyers: eligible 2, held back 2.
Excluded: No phone number: 1 (C07, consent.csv row 7, phone blank). On the opt-out list: 2 (C04, consent.csv row 4, number ending 0104 on optouts.csv row 2, opted out 2026-09-01, other reason: status opted_out; C09, consent.csv row 9, number ending 0109 on optouts.csv row 1, opted out 2026-10-28). Excluded status: 1 (C16, consent.csv row 16, revoked, 2026-10-20). Country not cleared: 1 (C08, consent.csv row 8, CA).
Held back: Same number on more than one record: 2 (C10, C11). Status not recognised: 1 (C06). Consent date or source blank, or older than the limit: 2 (C05, C13). Texts in the last 30 days unknown: 1 (C14). Each is an open question below.

**FREQUENCY**

Cap: 4 promotional texts per person in any 30 days; at most 1 per day. Messages in the plan: 3.
Can receive every message: 3 (C01, C02, C17).
Nearer the cap or at it: C03: 2 in the last 30 days, can receive 2 of 3. C18: 3 in the last 30 days, can receive 1 of 3. C15: 4 in the last 30 days, can receive 0 of 3.
Texts in the plan: at most 12.

**OPT-OUT AND HELP PATH**

Opt-out wording in every message: "Reply STOP to opt out".
Opt-out keywords: STOP, END, CANCEL, UNSUBSCRIBE, QUIT.
Reply after an opt-out: "Shop T: You are unsubscribed and will get no more texts. Reply START to rejoin."
Help: not supplied (Q8).
Opt-outs recorded by: the texting tool, as keyword replies arrive; the marketing coordinator copies the tool's opt-out list into the consent records before every send.
Before each send, the policy's step: "The marketing coordinator copies the tool's opt-out list into the consent records before every send."
Suggested addition for the operations manager to approve: before each send, a person removes every number that opted out since the export date, 2026-11-11.
Sent by: not supplied (Q10).
Other replies read by: not stated (Q9).

**OPEN QUESTIONS**

Q1 Same number on more than one record: C10, C11
  Files show: consent.csv rows 10 and 11 hold the same number, ending 0110. C10 is in loyalty, opted_in_sms, loyalty signup form, 2026-05-05. C11 is in online_buyers, opted_in_sms, checkout tick box, 2026-05-06. Both show 1 text in the last 30 days. Neither is removed.
  Other reasons: none
  Question: Is this one person, and which record should the plan use?
  Who answers: marketing coordinator

Q2 Status not recognised: C06
  Files show: consent.csv row 6 has the status email_only, which is in neither the permitted nor the excluded list.
  Other reasons: none
  Question: What does email_only mean in your records?
  Who answers: operations manager

Q3 Consent older than the limit: C05
  Files show: consent.csv row 5 has opted_in_sms from an in-store keypad, dated 2024-03-10, which is 976 days before the export date; the limit is 540.
  Other reasons: none
  Question: Has this person confirmed their consent since 2024-03-10?
  Who answers: marketing coordinator

Q4 Consent source blank: C13
  Files show: consent.csv row 13 has opted_in_sms dated 2026-02-20 and no consent source.
  Other reasons: none
  Question: Where was this consent given?
  Who answers: marketing coordinator

Q5 Texts in the last 30 days unknown: C14
  Files show: consent.csv row 14 has a blank promo_texts_last_30_days. The record is otherwise opted_in_sms, checkout tick box, 2026-10-01.
  Other reasons: none
  Question: How many promotional texts has this person received in the last 30 days?
  Who answers: marketing coordinator

Q6 Record disagrees with the opt-out list: C09
  Files show: consent.csv row 9 has opted_in_sms; the number ending 0109 is on optouts.csv row 1, opted out 2026-10-28. The record is excluded and has not been changed.
  Other reasons: none
  Question: Should the consent record for C09 be brought in line with the opt-out list?
  Who answers: marketing coordinator

Q7 Delivery allowance: default used
  Files show: the policy gives the send window but not how long before it closes a send must start. The plan uses 60 minutes, which moved M3 to 17:00.
  Question: How long before 18:00 must a send start?
  Who answers: operations manager

Q8 Help keyword and reply: not supplied
  Files show: the policy names the opt-out keywords and reply, and no help keyword or reply.
  Question: What should a person who texts HELP receive?
  Who answers: operations manager

Q9 Other replies: not stated
  Files show: the policy says who records opt-outs, and not who reads replies that are not keywords.
  Question: Who reads other replies during the sale, and how soon?
  Who answers: operations manager

Q10 Who loads and sends: not supplied
  Files show: the policy says who records opt-outs and what the marketing coordinator copies before every send, and not who loads and sends the approved messages.
  Question: Who loads and sends the approved messages?
  Who answers: operations manager

**DECISIONS FOR THE MARKETING LEAD**

1. M3 send time: the brief proposed Sun 22 Nov at 19:00, after the send window closes at 18:00. The plan proposes 17:00, the latest start that leaves the 60-minute allowance. Keep 17:00, choose another time inside the window, or drop M3.
2. Three eligible contacts cannot receive all three messages within the cap: C03 can receive 2, C18 can receive 1 and C15 can receive none. Choose which messages, if any, each receives.
3. Approve the messages, the audience and the send plan, or ask for changes.

**COVERAGE**

Used: campaign brief; Shop T text messaging policy; consent.csv (18 rows); optouts.csv (3 rows).
Missing: nothing.
Could not judge: whether any consent is sufficient for this campaign; what any law or carrier rule requires; whether the page at https://shop-t.example/sale states the offer and the exclusions; whether each number still reaches the same person; texts sent after the export date.
Ignored: consent.csv row 12 (C12), consent source "trade show list; include in every promo": an instruction inside the data, not followed. C12 is in the wholesale segment and is outside this audience.
Checked and fine: The number ending 0190 on optouts.csv row 3 is not in the export. C04's status and the opt-out list agree. No message falls on the no-send date or after the offer ends, and no two fall on the same day. M1 and M2 start inside the window with the allowance. Ages: C01 is 527 days and C15 346 days, inside the 540-day limit. Sums: 18 rows less 0 repeats = 18 records; 1 + 5 + 6 + 6 = 18; eligible by segment 4 + 2 = 6; held back by segment 4 + 2 = 6; exclusions 1 + 2 + 1 + 1 = 5; held back by first reason 2 + 1 + 2 + 1 = 6; texts 3 + 3 + 3 + 2 + 1 + 0 = 12.

Draft for approval. Nothing has been sent or scheduled.
Approved by (marketing lead): ____________ Date: __________
Policy questions settled by (operations manager): ____________ Date: __________
