# Campaign build sheet: an invented example

*Illustrative example with invented data.* The business, its web addresses (on the reserved example domain), the roles, the platforms, the dates and every figure below are invented. Client M is an invented chain of garden centres planning a spring bulb sale. The paid media operator at the agency ran the workflow template once the client's marketing manager had approved the brief. First come the inputs the operator supplied, in full, then the build sheet the workflow template returned.

## The inputs

### 1. Build settings

```
Business: Client M (an invented garden centre chain)
Campaign: Spring bulb sale
Brief approved by: Marketing manager, 2026-11-02
Operator: Paid media operator
Authorized owner: Marketing manager
As-of date: 2026-11-10
Currency: USD
Start date: 2027-03-01
End date: 2027-03-28
Total spending limit: 6000
Daily limit per line: 150
Maximum name length: 40
Campaign-wide exclusions: existing customers list; staff
Required other settings: bid strategy; location
Campaign name pattern: {brand_code}-{campaign_code}-{start_yyyymm}
Audience name pattern: {campaign_code}-{channel_code}-{audience_code}
Ad name pattern: {audience_code}-{creative_ref}
brand_code: CM
campaign_code: BULB
```

### 2. Brief lines (brief_lines.csv)

```
line_id,channel,channel_code,audience_code,audience_description,include_rules,exclusions,destination_ref,budget_type,budget_amount,line_start,line_end,creative_refs,conversion_event,other_settings
L1,Platform A search,PA,KWBULB,People searching for spring bulbs,"Keyword themes: tulip bulbs; daffodil bulbs; buy spring bulbs",existing customers list; staff,D1,daily,120,2027-03-01,2027-03-28,C1; C2,E1,bid strategy: maximise clicks; location: within 40 miles of the store
L2,Platform B social,PB,LOCALGARD,Gardeners near the store,Interest in gardening; age 30 and over,existing customers list,D2,daily,90,2027-03-01,2027-03-21,C3; C4,E1,bid strategy: lowest cost
L3,Platform B social retargeting,PB,SITEVISIT,Visitors to the bulbs page in the past 30 days,Site visitors in the past 30 days,existing customers list; staff; purchasers,D3,lifetime,900,2027-03-08,2027-03-28,C3; C5,E2,bid strategy: lowest cost; location: within 40 miles of the store
```

### 3. Destinations (destinations.csv)

```
destination_ref,url,status,tracking_parameters,owner
D1,https://clientm.example/bulbs,live,utm_source=platform-a&utm_medium=search&utm_campaign=bulb-spring,Web developer
D2,https://clientm.example/bulbs/spring-sale,staging,,Web developer
D3,https://clientm.example/bulbs,live,utm_source=platform-b&utm_medium=retargeting&utm_campaign=bulb-spring,Web developer
```

### 4. Assets (assets.csv)

```
asset_ref,asset_type,description,status,approved_by
C1,text ad,Search headline set A,approved,Marketing manager
C2,text ad,Search headline set B,approved,Marketing manager
C3,image,Tulip field photo 1080 by 1080,approved,Marketing manager
C4,image,Daffodil photo 1080 by 1080,missing,
C5,image,Retargeting offer banner,in progress,
```

### 5. Measurement (measurement.csv)

```
conversion_event,definition,where_recorded,status,owner
E1,Completed online order,Shop checkout confirmation page,confirmed,Web developer
E2,Click on the Reserve in store button,,unconfirmed,Web developer
```

## The build sheet

```
CAMPAIGN BUILD SHEET: Spring bulb sale, Client M (an invented garden centre chain)

For: Paid media operator. Brief approved by Marketing manager, 2026-11-02. As of 2026-11-10. Authorized owner: Marketing manager.

CAMPAIGN
Name: CM-BULB-202703
Dates: 2027-03-01 to 2027-03-28 (28 days)
Currency: USD
Spending limit: 6,000. Planned total: 6,150 (complete). Over the limit by 150.
Campaign-wide exclusions: existing customers list; staff
Names: 10 built, longest 17 characters of 40, none duplicated. 0 not built.

LINES

L1: Platform A search
Names: audience BULB-PA-KWBULB. Ads KWBULB-C1, KWBULB-C2.
Audience: People searching for spring bulbs. Includes: Keyword themes: tulip bulbs; daffodil bulbs; buy spring bulbs
Exclusions: existing customers list; staff. Campaign-wide missing: none. Line-specific: none
Destination: D1, https://clientm.example/bulbs, status live, tracking utm_source=platform-a&utm_medium=search&utm_campaign=bulb-spring
Budget: daily 120, 2027-03-01 to 2027-03-28 (28 days) = 3,360
Creative: C1 (text ad, approved), C2 (text ad, approved)
Measurement: E1, Completed online order, recorded at Shop checkout confirmation page, status confirmed
Other settings: bid strategy: maximise clicks; location: within 40 miles of the store
Gaps: none

L2: Platform B social
Names: audience BULB-PB-LOCALGARD. Ads LOCALGARD-C3, LOCALGARD-C4.
Audience: Gardeners near the store. Includes: Interest in gardening; age 30 and over
Exclusions: existing customers list. Campaign-wide missing: staff. Line-specific: none
Destination: D2, https://clientm.example/bulbs/spring-sale, status staging, tracking none supplied
Budget: daily 90, 2027-03-01 to 2027-03-21 (21 days) = 1,890
Creative: C3 (image, approved), C4 (image, missing)
Measurement: E1, Completed online order, recorded at Shop checkout confirmation page, status confirmed
Other settings: bid strategy: lowest cost; location: not supplied
Gaps: 2, 3, 4, 5, 6

L3: Platform B social retargeting
Names: audience BULB-PB-SITEVISIT. Ads SITEVISIT-C3, SITEVISIT-C5.
Audience: Visitors to the bulbs page in the past 30 days. Includes: Site visitors in the past 30 days
Exclusions: existing customers list; staff; purchasers. Campaign-wide missing: none. Line-specific: purchasers
Destination: D3, https://clientm.example/bulbs, status live, tracking utm_source=platform-b&utm_medium=retargeting&utm_campaign=bulb-spring
Budget: lifetime 900, 2027-03-08 to 2027-03-28 (21 days) = 900
Creative: C3 (image, approved), C5 (image, in progress)
Measurement: E2, Click on the Reserve in store button, recorded at not stated, status unconfirmed
Other settings: bid strategy: lowest cost; location: within 40 miles of the store
Gaps: 7, 8

GAP REGISTER

1. Campaign, budget: planned total 6,150 is over the spending limit of 6,000 by 150 (L1 3,360; L2 1,890; L3 900). To resolve: a decision on which line's budget or dates change, or a higher limit. Who can supply: Marketing manager (brief approver).
2. L2, exclusions: the campaign-wide exclusion "staff" is not on the line. To resolve: confirm that "staff" applies to L2. Who can supply: Marketing manager (brief approver).
3. L2, destination D2: status is staging, not live. To resolve: the page made live, or another destination named. Who can supply: Web developer.
4. L2, destination D2: no tracking parameters supplied. To resolve: the tracking parameters for D2. Who can supply: Web developer.
5. L2, creative C4: status is missing. To resolve: the approved image delivered. Who can supply: not stated.
6. L2, other settings: required setting "location" has no value. To resolve: the location for L2. Who can supply: Marketing manager (brief approver).
7. L3, creative C5: status is in progress. To resolve: the banner finished and approved. Who can supply: not stated.
8. L3, measurement E2: status is unconfirmed, and where it is recorded is not stated. To resolve: confirmation that the event records, and where. Who can supply: Web developer.

Lines with no gaps: 1 of 3 (L1). Gaps in all: 8.
Next step: Paid media operator checks every value against the brief approved on 2026-11-02. Marketing manager approves any account creation or change. No account has been created, changed or connected.

Every figure and value traces to the build settings for Spring bulb sale and the brief lines, destinations, assets and measurement list supplied. The sheet changes nothing, launches nothing and spends nothing.
```
