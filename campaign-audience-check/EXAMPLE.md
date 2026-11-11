# Campaign audience check: an invented example

*Illustrative example with invented data.* The company, the people, the addresses (all on the reserved .example domain), the dates and the counts below are invented. Shop R is an invented online seller of homeware to cafes, hotels and small businesses. Its campaign owner has an audience export for a winter offers email and ran the check, with the customer-data steward answering questions about records. First come the inputs the campaign owner supplied, in full, then the page the capability returned.

## The inputs

### 1. Campaign settings

```
Campaign: Winter homeware offers email
Audience: Winter offers audience
As-of date: 2026-11-10
Topic: offers
Permitted statuses: opted_in, existing_customer_agreed
Excluded statuses: unsubscribed, withdrawn
Permission age limit: 730 days
Soft bounces: 3 or more in the 90 days up to the as-of date
Segments in priority order:
  1. Customers: source equals purchase
  2. Newsletter readers: source equals newsletter
  3. Event contacts: source equals event
Page goes to: campaign owner and customer-data steward
```

### 2. Audience export (audience.csv)

```
record_id,email,full_name,company,country,source,created_on,last_engaged_on
R01,ana@cafe-a.example,Ana Ruiz,Cafe A,US,purchase,2023-03-01,2026-09-14
R02,ben@cafe-b.example,Ben Okoye,Cafe B,US,purchase,2022-05-10,2026-10-02
R03,carla@studio-c.example,Carla Dent,Studio C,CA,newsletter,2025-01-20,2026-08-30
R04,dev@shop-d.example,Dev Rao,Shop D,US,newsletter,2024-02-02,2026-06-01
R05,eli@hotel-e.example,Eli Marsh,Hotel E,GB,event,2025-06-11,2026-10-20
R06,fay@hotel-f.example,Fay Lind,Hotel F,GB,purchase,2021-09-09,2026-03-03
R07,gus@bar-g.example,Gus Hale,Bar G,US,purchase,2020-12-12,2026-10-30
R08,hugo@bar-h.example,Hugo Pike,Bar H,US,event,2025-04-04,2026-04-04
R09,ines@inn-i.example,Ines Cole,Inn I,GB,newsletter,2025-09-09,2026-09-09
R10,jo@gallery-j.example,Jo Frey,Gallery J,US,purchase,2024-08-08,2026-10-10
R11,jo.frey@gallery-j.example,Jo Frey,Gallery J,US,newsletter,2025-02-02,2026-05-05
R12,kim@kiosk-k.example,Kim Vale,Kiosk K,CA,newsletter,2025-03-03,2026-07-07
R13,Kim@Kiosk-K.example,Kim Vale,Kiosk K,CA,purchase,2025-03-04,2026-08-08
R14,lee@lodge-l.example,Lee Armas,Lodge L,CA,purchase,2025-10-01,2026-10-30
R15,mo@mill-m.example,Mo Berg,Mill M,US,newsletter,2022-02-02,2026-01-15
R16,,Nia Tran,Nook N,US,event,2025-12-12,2026-02-02
R17,ola@oak-o.example,Ola Beck,Oak O,GB,purchase,2025-07-07,2026-09-01
R18,pat@pier-p.example,Pat Ito,Pier P,US,event,2026-09-30,2026-09-30
R19,quin@quay-q.example,Quin Shaw,Quay Q,GB,event,2026-02-02,2026-10-12
R20,rae@reef-r.example,Rae Lomas,Reef R,US,purchase,2025-11-11,2026-11-01
R20,rae@reef-r.example,Rae Lomas,Reef R,US,purchase,2025-11-11,2026-11-01
```

### 3. Permission records (permission.csv)

```
record_id,permission_status,permission_basis,recorded_on
R01,opted_in,signup form,2025-03-01
R02,existing_customer_agreed,checkout tick box,2025-05-10
R03,opted_in,signup form,2025-01-20
R04,opted_in,signup form,2024-02-02
R05,opted_in,event card,2025-06-11
R06,opted_in,signup form,2025-09-09
R07,opted_in,signup form,2025-01-01
R08,opted_in,event card,2025-04-04
R10,opted_in,signup form,2025-08-08
R11,opted_in,signup form,2025-02-02
R12,opted_in,signup form,2025-03-03
R13,existing_customer_agreed,checkout tick box,2025-03-04
R14,opted_in,signup form,2025-10-01
R15,unsubscribed,unsubscribe link,2026-01-15
R17,opted_in,signup form,2025-07-07
R18,pending,signup form,2026-09-30
R19,opted_in,event card,2026-02-02
R20,existing_customer_agreed,checkout tick box,2025-11-11
```

### 4. Preference records (preferences.csv)

```
record_id,topic,choice,updated_on
R01,offers,in,2025-03-01
R03,events,out,2026-01-01
R05,offers,in,2025-06-11
R06,offers,in,2025-09-09
R06,offers,out,2026-02-14
R08,offers,out,2026-03-03
```

### 5. Bounce history (bounces.csv)

```
email,bounce_type,bounced_on
ana@cafe-a.example,soft,2026-03-01
ben@cafe-b.example,soft,2026-10-15
gus@bar-g.example,hard,2026-07-01
lee@lodge-l.example,soft,2026-08-20
lee@lodge-l.example,soft,2026-09-25
lee@lodge-l.example,soft,2026-10-30
```

### 6. Do-not-contact list (suppression.csv)

```
email
ola@oak-o.example
zed@zone-z.example
```

## The page the capability returned

**CAMPAIGN AUDIENCE CHECK: Winter homeware offers email, Winter offers audience, as of 2026-11-10. Status: complete**

For: campaign owner and customer-data steward. Counts are records, after exact repeats are collapsed. Nothing has been sent, changed or approved.

**THE ANSWER**

20 records in the export. 6 are cleared, 5 are excluded and 9 are held back for a person to check. The 9 records to check fall into 7 entries below. The campaign owner is asked to resolve them and approve the final audience; the cleared count is not an approval.

**SETTINGS USED**

Topic: offers. Permitted statuses: opted_in, existing_customer_agreed. Excluded statuses: unsubscribed, withdrawn. Permission age limit: 730 days (records before 2024-11-10 are stale). Soft bounces: 3 or more since 2026-08-12. Segments in priority order: 1. Customers: source equals purchase; 2. Newsletter readers: source equals newsletter; 3. Event contacts: source equals event.

**COUNTS**

Export rows 21; exact repeats collapsed 1; records 20.
Cleared 6 + excluded 5 + held back 9 = 20.

**SEGMENTS**

Customers: cleared 3, held back 4
Newsletter readers: cleared 1, held back 4
Event contacts: cleared 2, held back 1
Unsegmented: cleared 0, held back 0
Total: cleared 6, held back 9. Excluded records are not segmented.

**EXCLUSIONS APPLIED**

No email address: 1 (R16, audience.csv row 16, the email cell is blank)
On the do-not-contact list: 1 (R17, ola@oak-o.example, audience.csv row 17 and suppression.csv row 1)
Hard bounce on file: 1 (R07, gus@bar-g.example, bounces.csv row 3, hard bounce 2026-07-01)
Permission status excluded: 1 (R15, permission.csv row 14, unsubscribed, recorded 2026-01-15)
Preference out: 1 (R08, preferences.csv row 6, offers out, updated 2026-03-03, no row saying in)

**RECORDS TO CHECK**

Q1 Duplicate address: R12, R13
  Files show: kim@kiosk-k.example (audience.csv row 12, R12) and Kim@Kiosk-K.example (audience.csv row 13, R13) are the same address once case is ignored. R12: source newsletter, opted_in recorded 2025-03-03 (permission.csv row 11). R13: source purchase, existing_customer_agreed recorded 2025-03-04 (permission.csv row 12). Neither is removed.
  Other reasons: none.
  Question: Should this address appear once, and under which record's segment?
  Who can answer: customer-data steward.

Q2 Conflicting records: R06
  Files show: preferences.csv row 4 has offers in (2025-09-09) and row 5 has offers out (2026-02-14). permission.csv row 6 has opted_in, recorded 2025-09-09. Neither preference row is chosen.
  Other reasons: none.
  Question: Which preference does this person hold today?
  Who can answer: customer-data steward.

Q3 Permission missing or not recognised: R09
  Files show: permission.csv has no row for R09 (no permission row for this record); the record is audience.csv row 9.
  Other reasons: none.
  Question: Is there a permission record for this person that was not in the file?
  Who can answer: customer-data steward.

Q4 Permission missing or not recognised: R18
  Files show: permission.csv row 16 has status pending, recorded 2026-09-30. It is in neither the permitted nor the excluded list.
  Other reasons: none.
  Question: What does pending mean in your records?
  Who can answer: campaign owner.

Q5 Permission stale or undated: R04
  Files show: permission.csv row 4 has opted_in recorded 2024-02-02, which is 1,012 days before the as-of date; the limit is 730.
  Other reasons: none.
  Question: Is there a more recent confirmation of this person's permission?
  Who can answer: customer-data steward.

Q6 Soft bounces at the limit: R14
  Files show: bounces.csv rows 4, 5 and 6 have soft bounces for lee@lodge-l.example on 2026-08-20, 2026-09-25 and 2026-10-30 (3 within the window; the limit is 3). permission.csv row 13 has opted_in, recorded 2025-10-01.
  Other reasons: none.
  Question: Is this address still receiving mail?
  Who can answer: customer-data steward.

Q7 Possible duplicate identity: R10, R11
  Files show: both are Jo Frey at Gallery J, with addresses jo@gallery-j.example (audience.csv row 10, R10) and jo.frey@gallery-j.example (audience.csv row 11, R11). Both have opted_in permission recorded in the last 730 days (permission.csv rows 9 and 10: 2025-08-08 and 2025-02-02). Neither is merged.
  Other reasons: none.
  Question: Are these one person with two addresses, and should the audience hold one or both?
  Who can answer: customer-data steward.

Held back by first reason: duplicate address 2 (R12, R13); conflicting records 1 (R06); permission missing or not recognised 2 (R09, R18); permission stale 1 (R04); soft bounces at the limit 1 (R14); possible duplicate identity 2 (R10, R11). Total 9.

**DECISIONS FOR THE CAMPAIGN OWNER**

1. Resolve Q1 to Q7: for each, add the record to the audience or leave it out.
2. Confirm the exclusions above stand.
3. Approve the final audience, or ask for changes.

**COVERAGE**

Used: settings; audience.csv (21 rows, 20 records); permission.csv (18 rows); preferences.csv (6 rows); bounces.csv (6 rows); suppression.csv (2 addresses).
Missing: nothing.
Could not judge: whether any permission is sufficient for this campaign; whether the pending status means what its name suggests; who the people are beyond the files; whether an address still works; and bounces dated after the as-of date (none in the file).
Ignored: none found.
Checked and fine: 1 preference row is for the topic events, not offers, and was left out (R03). 1 do-not-contact address (zed@zone-z.example) is not in the export. Soft bounces for R01 (1, outside the window) and R02 (1, below the limit of 3) do not hold them back. Sums: 21 rows less 1 repeat = 20 records; 6 + 5 + 9 = 20; cleared by segment 3 + 1 + 2 + 0 = 6; held back by segment 4 + 4 + 1 + 0 = 9; exclusions 1 + 1 + 1 + 1 + 1 = 5; first reasons 2 + 1 + 2 + 1 + 1 + 2 = 9.

Prepared on 2026-11-10. Every statement comes from the inputs listed under Coverage.
Audience approved by: ____________ Date: __________
