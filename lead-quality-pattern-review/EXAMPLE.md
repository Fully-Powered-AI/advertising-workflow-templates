# Lead quality pattern review: an invented example

*Illustrative example with invented data.* The client, its leads, its pages, its locations, the roles, the dates and the notes below are all invented, and so is every count. Client Q is an invented regional flooring installer whose sales team has said that some leads are not worth the call. The acquisition lead ran the review. First come the inputs the acquisition lead supplied, in full, then the review the capability returned. The lead outcomes below are 88 invented rows, one per line, as the export would hold them.

## The inputs

### 1. Review settings

```
Business: Client Q (an invented regional flooring installer)
Lead defined as: a completed quote request form or a tracked call of over 60 seconds
Period: 2026-10-01 to 2026-10-31
As-of date: 2026-11-09
Useful outcomes: Qualified; Quote sent; Won
Not useful outcomes: Not qualified; Wrong service; Unreachable; Marked invalid
Open outcomes: New; In contact
Time zone of created_at: the business's local time
Outcome window: 14 days
Minimum settled leads to read a segment: 10
Flag gap: 15 points
Acquisition lead: Client Q's acquisition lead
Report goes to: the acquisition lead only
```

### 2. Scope

```
Sources in use: Search brand; Search general; Social paid; Partner
Landing pages in use: /quote; /spring-offer; /contact
Targeted locations: North Metro; South Metro; Coastal
Devices: all
```

### 3. Known changes

```
2026-10-14: the quote request form moved to a new form tool.
```

### 4. Lead outcomes export (leads.csv)

```
lead_id,created_at,source,landing_page,location,device,outcome
L001,2026-10-01 09:36,Search brand,/quote,South Metro,mobile,Qualified
L002,2026-10-01 14:48,Search general,/quote,North Metro,desktop,Marked invalid
L003,2026-10-01 17:21,Search general,/quote,Coastal,mobile,Won
L004,2026-10-01 21:26,Social paid,/spring-offer,North Metro,mobile,Unreachable
L005,2026-10-01 22:44,Social paid,/spring-offer,North Metro,mobile,Not qualified
L006,2026-10-02 08:12,Search brand,/quote,North Metro,desktop,Quote sent
L007,2026-10-02 17:25,Search brand,/quote,North Metro,desktop,Won
L008,2026-10-03 09:05,Search general,/quote,Coastal,mobile,Qualified
L009,2026-10-03 12:21,Search general,/quote,North Metro,desktop,Qualified
L010,2026-10-04 09:02,Partner,/quote,Coastal,desktop,Won
L011,2026-10-05 14:41,Search general,/contact,South Metro,mobile,Marked invalid
L012,2026-10-05 22:42,Social paid,/spring-offer,North Metro,mobile,Qualified
L013,2026-10-06 09:28,Search brand,/quote,North Metro,desktop,Qualified
L014,2026-10-07 10:47,Partner,/contact,North Metro,desktop,Quote sent
L015,2026-10-07 15:32,Search general,/contact,South Metro,mobile,Won
L016,2026-10-07 17:40,Search general,/quote,Coastal,mobile,Not qualified
L017,2026-10-07 19:49,Search general,/contact,South Metro,mobile,Quote sent
L017,2026-10-07 19:49,Search general,/contact,South Metro,mobile,Quote sent
L018,2026-10-08 08:38,Search general,/quote,Coastal,mobile,Quote sent
L019,2026-10-08 13:31,Social paid,/spring-offer,Outside service area,mobile,Not qualified
L020,2026-10-08 16:18,Search brand,/quote,South Metro,mobile,Quote sent
L021,2026-10-08 22:13,Social paid,/spring-offer,South Metro,desktop,Qualified
L022,2026-10-09 13:48,Search brand,/quote,South Metro,mobile,Qualified
L023,2026-10-09 14:52,Partner,/quote,Coastal,desktop,Qualified
L024,2026-10-09 17:19,Search general,/contact,South Metro,mobile,Not qualified
L025,2026-10-09 20:47,Social paid,/spring-offer,North Metro,mobile,Marked invalid
L026,2026-10-09 23:51,Social paid,/spring-offer,South Metro,desktop,Unreachable
L027,2026-10-10 09:38,Social paid,/spring-offer,North Metro,mobile,Not qualified
L028,2026-10-10 10:05,Search brand,/quote,North Metro,desktop,Qualified
L029,2026-10-10 15:00,Search brand,/quote,South Metro,mobile,Wrong service
L030,2026-10-12 13:17,Social paid,/quote,Coastal,tablet,Unreachable
L031,2026-10-13 09:25,Search general,/contact,South Metro,mobile,Wrong service
L032,2026-10-13 19:25,Search general,/quote,North Metro,desktop,Quote sent
L033,2026-10-14 09:36,Search general,/quote,North Metro,desktop,Not qualified
L034,2026-10-14 11:00,Search general,/contact,South Metro,mobile,Qualified
L035,2026-10-14 22:31,Social paid,/quote,Coastal,tablet,Quote sent
L036,2026-10-15 09:02,Social paid,/spring-offer,North Metro,mobile,Marked invalid
L037,2026-10-16 20:53,Social paid,/quote,Coastal,tablet,Qualified
L038,2026-10-17 11:40,Search brand,/quote,South Metro,mobile,Unreachable
L039,2026-10-17 22:42,Social paid,/spring-offer,South Metro,desktop,Quote sent
L040,2026-10-18 19:40,Search brand,/quote,North Metro,desktop,Quote sent
L041,2026-10-19 13:23,Social paid,/spring-offer,North Metro,mobile,Quote sent
L042,2026-10-19 22:05,Social paid,/spring-offer,Outside service area,mobile,Qualified
L043,2026-10-19 22:55,Social paid,/spring-offer,Outside service area,mobile,Wrong service
L044,2026-10-19 23:22,Social paid,/spring-offer,Outside service area,mobile,Unreachable
L045,2026-10-19 23:29,Social paid,/spring-offer,Outside service area,mobile,Wrong service
L046,2026-10-19 23:36,Social paid,/spring-offer,Outside service area,mobile,Not qualified
L047,2026-10-19 23:37,Social paid,/spring-offer,Outside service area,mobile,Not qualified
L048,2026-10-19 23:46,Social paid,/spring-offer,Outside service area,mobile,Marked invalid
L049,2026-10-20 11:46,Partner,/contact,North Metro,desktop,Qualified
L050,2026-10-20 23:01,Social paid,/spring-offer,Outside service area,mobile,Unreachable
L051,2026-10-21 10:19,Partner,/contact,North Metro,desktop,Qualified
L052,2026-10-21 11:49,Search general,/quote,North Metro,desktop,Qualified
L053,2026-10-21 12:26,Search brand,/quote,South Metro,mobile,Won
L054,2026-10-21 16:12,Partner,/contact,North Metro,desktop,Won
L055,2026-10-21 17:50,Search brand,/quote,North Metro,desktop,Won
L056,2026-10-22 09:29,Search brand,/quote,South Metro,mobile,Quote sent
L057,2026-10-22 12:21,Search general,/quote,North Metro,desktop,Won
L058,2026-10-22 14:56,Partner,/contact,North Metro,desktop,Won
L059,2026-10-24 17:41,Search brand,/quote,North Metro,desktop,Qualified
L060,2026-10-24 19:25,Partner,/quote,Coastal,desktop,Quote sent
L061,2026-10-24 22:37,Social paid,/spring-offer,North Metro,mobile,Wrong service
L062,2026-10-25 09:19,Social paid,/spring-offer,Outside service area,mobile,In contact
L063,2026-10-26 20:24,Social paid,/spring-offer,South Metro,desktop,Won
L064,2026-10-27 12:24,Search general,/quote,Coastal,mobile,Wrong service
L065,2026-10-27 13:28,Social paid,/quote,Coastal,tablet,Marked invalid
L066,2026-10-27 13:33,Social paid,/spring-offer,Outside service area,mobile,Marked invalid
L067,2026-10-27 16:04,Search brand,/quote,North Metro,desktop,Not qualified
L068,2026-10-27 17:08,Partner,/contact,North Metro,desktop,Qualified
L069,2026-10-28 11:59,Search general,/quote,North Metro,,New
L070,2026-10-28 14:11,Partner,/contact,North Metro,desktop,Wrong service
L071,2026-10-28 15:16,Search general,/quote,Coastal,mobile,New
L072,2026-10-28 17:00,Search brand,/quote,North Metro,desktop,New
L073,2026-10-28 18:35,search general ,/contact,South Metro,mobile,New
L074,2026-10-28 22:33,Social paid,/spring-offer,North Metro,mobile,New
L075,2026-10-28 23:42,Social paid,/spring-offer,South Metro,desktop,New
L076,2026-10-29 08:13,Search general,/contact,South Metro,mobile,Qualified
L077,2026-10-29 17:31,Partner,/quote,Coastal,desktop,Unreachable
L078,2026-10-30 08:30,Search general,/quote,North Metro,,Unreachable
L079,2026-10-30 09:08,Search general,/quote,North Metro,desktop,Quote sent
L080,2026-10-30 11:52,Partner,/contact,North Metro,desktop,Quote sent
L081,2026-10-30 23:57,Social paid,/spring-offer,South Metro,desktop,Wrong service
L082,2026-10-31 09:45,Search brand,/quote,South Metro,mobile,New
L083,2026-10-31 09:59,Social paid,/spring-offer,North Metro,mobile,Won
L084,2026-10-31 12:15,Partner,/quote,Coastal,desktop,New
L085,2026-10-31 15:41,Search brand,/quote,North Metro,desktop,Quote sent
L086,2026-10-31 23:16,Social paid,/spring-offer,Outside service area,mobile,New
L087,2026-11-02 10:15,Search brand,/quote,North Metro,desktop,Qualified
```

### 5. Sales feedback (feedback.csv)

```
note_id,date,from_role,lead_ids,note
F1,2026-10-22,Sales development rep,L005;L030,Two Social paid leads said on the call they had not asked for a quote.
F2,2026-10-29,Sales manager,,Fewer people who came in on a phone are picking up when we ring.
F3,2026-10-30,Sales development rep,L130,One lead from the end of the month was a duplicate of an earlier caller.
```

## The review

```
LEAD QUALITY PATTERN REVIEW: Client Q, 2026-10-01 to 2026-10-31

For: the acquisition lead. Period 2026-10-01 to 2026-10-31; as of 2026-11-09. Settings: minimum 10 settled leads to read a segment, flag gap 15 points, outcome window 14 days.

DATA CHECK
Rows received: 88. Removed as repeats of a lead_id already seen: 1 (L017). Excluded as outside the period: 1 (L087 dated 2026-11-02). Leads reviewed: 86.
Settled leads: 76 (44 useful, 32 not useful). Open leads: 10 (9 created on or after 2026-10-26, 1 older).
Overall useful rate: 44 of 76 settled (57.9%).
Values read as the same after ignoring capitals and spaces at the ends: Source "search general " read as "Search general" (1 lead).

KNOWN CHANGES IN THE PERIOD
2026-10-14: the quote request form moved to a new form tool. Before: 32 settled, 19 useful (59.4%). From that date: 44 settled, 25 useful (56.8%). Both sides have at least 10 settled leads, so both are shown; the review draws no conclusion from the two figures.

SEGMENTS
A segment with no leads is not listed.
Within a dimension, segments run from most leads to fewest; day parts run in clock order and weeks in date order.

Source
Social paid: 32 leads, 28 settled, 9 useful (32.1%), -25.8 points against overall. Below overall: pattern 1.
Search general: 23 leads, 20 settled, 12 useful (60.0%), +2.1 points against overall. Within the gap.
Search brand: 18 leads, 16 settled, 13 useful (81.2%), +23.4 points against overall. Above overall.
Partner: 13 leads, 12 settled, 10 useful (83.3%), +25.4 points against overall. Above overall.

Landing page
/quote: 42 leads, 37 settled, 26 useful (70.3%), +12.4 points against overall. Within the gap.
/spring-offer: 28 leads, 24 settled, 7 useful (29.2%), -28.7 points against overall. Below overall: pattern 2.
/contact: 16 leads, 15 settled, 11 useful (73.3%), +15.4 points against overall. Above overall.

Location
North Metro: 37 leads, 34 settled, 23 useful (67.6%), +9.8 points against overall. Within the gap.
South Metro: 22 leads, 19 settled, 12 useful (63.2%), +5.3 points against overall. Within the gap.
Coastal: 15 leads, 13 settled, 8 useful (61.5%), +3.6 points against overall. Within the gap.
Outside service area: 12 leads, 10 settled, 1 useful (10.0%), -47.9 points against overall. Below overall: pattern 3.

Device
mobile: 44 leads, 38 settled, 16 useful (42.1%), -15.8 points against overall. Below overall: pattern 4.
desktop: 36 leads, 33 settled, 26 useful (78.8%), +20.9 points against overall. Above overall.
tablet: 4 leads, 4 settled, 2 useful. Too few to read.
(blank): 2 leads, 1 settled, 0 useful. Too few to read.

Day part
Morning: 26 leads, 23 settled, 17 useful (73.9%), +16.0 points against overall. Above overall.
Afternoon: 32 leads, 29 settled, 16 useful (55.2%), -2.7 points against overall. Within the gap.
Evening: 28 leads, 24 settled, 11 useful (45.8%), -12.1 points against overall. Within the gap.

Week
week of 2026-09-28: 10 leads, 10 settled, 7 useful (70.0%), +12.1 points against overall. Within the gap.
week of 2026-10-05: 19 leads, 19 settled, 11 useful (57.9%), +0.0 points against overall. Within the gap.
week of 2026-10-12: 11 leads, 11 settled, 6 useful (54.5%), -3.3 points against overall. Within the gap.
week of 2026-10-19: 22 leads, 21 settled, 13 useful (61.9%), +4.0 points against overall. Within the gap.
week of 2026-10-26: 24 leads, 15 settled, 7 useful (46.7%), -11.2 points against overall. Within the gap.

PATTERNS

1. Source: Social paid
Facts: 32 leads, 28 settled, 9 useful (32.1%), -25.8 points against overall (57.9%). Useful leads: 9 against 16.2 at the overall rate, 7.2 fewer.
Busiest day: 2026-10-19, 8 of 32 leads (25.0%).
Overlaps: pattern 2 (Landing page: /spring-offer): 24 settled leads in both, 7 useful (29.2%), 100.0% of the smaller pattern's settled leads; pattern 3 (Location: Outside service area): 10 settled leads in both, 1 useful (10.0%), 100.0% of the smaller pattern's settled leads; pattern 4 (Device: mobile): 19 settled leads in both, 4 useful (21.1%), 67.9% of the smaller pattern's settled leads.
Checks that touch this pattern: none.
Cases to verify with sales: L004 (2026-10-01 21:26, Unreachable); L005 (2026-10-01 22:44, Not qualified); L019 (2026-10-08 13:31, Not qualified); L025 (2026-10-09 20:47, Marked invalid); L026 (2026-10-09 23:51, Unreachable). Ask sales what the contact found and whether the outcome label matches what happened.
Question for the acquisition lead: take this pattern to sales with these cases, hold it, or set it aside? The review proposes no targeting change and states no cause.

2. Landing page: /spring-offer
Facts: 28 leads, 24 settled, 7 useful (29.2%), -28.7 points against overall (57.9%). Useful leads: 7 against 13.9 at the overall rate, 6.9 fewer.
Busiest day: 2026-10-19, 8 of 28 leads (28.6%).
Overlaps: pattern 1 (Source: Social paid): 24 settled leads in both, 7 useful (29.2%), 100.0% of the smaller pattern's settled leads; pattern 3 (Location: Outside service area): 10 settled leads in both, 1 useful (10.0%), 100.0% of the smaller pattern's settled leads; pattern 4 (Device: mobile): 19 settled leads in both, 4 useful (21.1%), 79.2% of the smaller pattern's settled leads.
Checks that touch this pattern: none.
Cases to verify with sales: L004 (2026-10-01 21:26, Unreachable); L005 (2026-10-01 22:44, Not qualified); L019 (2026-10-08 13:31, Not qualified); L025 (2026-10-09 20:47, Marked invalid); L026 (2026-10-09 23:51, Unreachable). Ask sales what the contact found and whether the outcome label matches what happened.
Question for the acquisition lead: take this pattern to sales with these cases, hold it, or set it aside? The review proposes no targeting change and states no cause.

3. Location: Outside service area
Facts: 12 leads, 10 settled, 1 useful (10.0%), -47.9 points against overall (57.9%). Useful leads: 1 against 5.8 at the overall rate, 4.8 fewer.
Busiest day: 2026-10-19, 7 of 12 leads (58.3%).
Overlaps: pattern 1 (Source: Social paid): 10 settled leads in both, 1 useful (10.0%), 100.0% of the smaller pattern's settled leads; pattern 2 (Landing page: /spring-offer): 10 settled leads in both, 1 useful (10.0%), 100.0% of the smaller pattern's settled leads; pattern 4 (Device: mobile): 10 settled leads in both, 1 useful (10.0%), 100.0% of the smaller pattern's settled leads.
Checks that touch this pattern: the value is not in the location scope supplied; 7 of 12 leads fall on one day (2026-10-19, 58.3%).
Cases to verify with sales: L019 (2026-10-08 13:31, Not qualified); L043 (2026-10-19 22:55, Wrong service); L044 (2026-10-19 23:22, Unreachable); L045 (2026-10-19 23:29, Wrong service); L046 (2026-10-19 23:36, Not qualified). Ask sales what the contact found and whether the outcome label matches what happened.
Question for the acquisition lead: take this pattern to sales with these cases, hold it, or set it aside? The review proposes no targeting change and states no cause. The tracking owner can be asked about the check named above.

4. Device: mobile
Facts: 44 leads, 38 settled, 16 useful (42.1%), -15.8 points against overall (57.9%). Useful leads: 16 against 22.0 at the overall rate, 6.0 fewer.
Busiest day: 2026-10-19, 8 of 44 leads (18.2%).
Overlaps: pattern 1 (Source: Social paid): 19 settled leads in both, 4 useful (21.1%), 67.9% of the smaller pattern's settled leads; pattern 2 (Landing page: /spring-offer): 19 settled leads in both, 4 useful (21.1%), 79.2% of the smaller pattern's settled leads; pattern 3 (Location: Outside service area): 10 settled leads in both, 1 useful (10.0%), 100.0% of the smaller pattern's settled leads.
Checks that touch this pattern: 1 repeated row removed from this segment (L017).
Cases to verify with sales: L004 (2026-10-01 21:26, Unreachable); L005 (2026-10-01 22:44, Not qualified); L011 (2026-10-05 14:41, Marked invalid); L016 (2026-10-07 17:40, Not qualified); L019 (2026-10-08 13:31, Not qualified). Ask sales what the contact found and whether the outcome label matches what happened.
Question for the acquisition lead: take this pattern to sales with these cases, hold it, or set it aside? The review proposes no targeting change and states no cause. The tracking owner can be asked about the check named above.

Segments above overall, for context only: Source Search brand (81.2%); Source Partner (83.3%); Landing page /contact (73.3%); Device desktop (78.8%); Day part Morning (73.9%). No cases are listed for them.

POSSIBLE MEASUREMENT FAULTS
1. Repeated lead_id: 1 row removed (L017); an identical row. Who can verify: the tracking owner, on whether the form or tag can send one lead twice.
2. Dated outside the period: 1 row excluded (L087, 2026-11-02 10:15). Who can verify: the tracking owner, on whether the date is the submission date.
3. Blank values: Source 0 (0.0%); Landing page 0 (0.0%); Location 0 (0.0%); Device 2 (2.3%). None is at 10 percent or more of leads reviewed. Who can verify: the tracking owner, for the 2 blank device values.
4. Values not in the scope supplied: Source 0; Landing page 0; Location 12 (14.0%; Outside service area); Device 0. This is a difference between the records and the scope, not a finding about those leads. Who can verify: the acquisition lead, on whether the targeted locations list is current.
5. Open leads older than 14 days: 1 (L062 In contact). Who can verify: sales development, on whether the outcome was never updated.

SALES FEEDBACK
F1 (2026-10-22, Sales development rep): "Two Social paid leads said on the call they had not asked for a quote."
L005: 2026-10-01 22:44, source Social paid, page /spring-offer, location North Metro, device mobile, outcome Not qualified; falls in patterns 1, 2, 4.
L030: 2026-10-12 13:17, source Social paid, page /quote, location Coastal, device tablet, outcome Unreachable; falls in pattern 1.
F2 (2026-10-29, Sales manager): "Fewer people who came in on a phone are picking up when we ring."
No lead_ids given, so no cases to check. Ask the sender which leads they mean.
F3 (2026-10-30, Sales development rep): "One lead from the end of the month was a duplicate of an earlier caller."
L130: not in the export for this period. Ask the sender for the date and source.

Not assessed: tablet (4 settled) and blank device (1 settled), too few to read. Open leads are left out of every rate.

Every figure traces to the lead outcomes export for 2026-10-01 to 2026-10-31, the settings, the scope, the known changes and the sales notes supplied. The review changes no targeting and no record, accuses no source of anything and sends nothing; the acquisition lead decides what is investigated and verifies findings with sales before any targeting change.
```
