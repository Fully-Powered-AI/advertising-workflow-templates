# Search exclusion conflict check: an invented example

*Illustrative example with invented data.* The shop, the campaigns, the keywords, the exclusions, the reasons and the dates below are all invented. Client R is an invented online dog-bed shop. The paid search specialist supplied four files and the settings; first come the inputs in full, then the document the capability returned.

## The inputs

### 1. Settings

```
Account: Client R (an invented online dog-bed shop)
As-of date: 2026-11-10
Deciding role: paid search specialist
```

### 2. keywords.csv

```
campaign,ad_group,keyword,match_type,status
Brand,Shop name,client r,exact,enabled
Brand,Shop name,client r dog beds,phrase,enabled
Beds - shopping,Orthopedic,orthopedic dog bed,phrase,enabled
Beds - shopping,Orthopedic,memory foam dog bed,exact,enabled
Beds - shopping,Cooling,cooling dog bed,broad,enabled
Beds - research,Comparisons,best dog beds,phrase,enabled
Beds - research,Comparisons,dog bed vs crate pad,broad,enabled
Beds - research,Free guides,free dog bed buying guide,phrase,enabled
Gift cards,Gift cards,pet gift card,exact,enabled
Gift cards,Gift cards,dog bed gift card,phrase,paused
Old season,Autumn,autumn dog bed sale,phrase,enabled
```

### 3. negatives.csv

```
level,list_name,campaign,ad_group,negative,match_type,status,purpose
account,,,,free,broad,enabled,Block people looking for free items
account,,,,jobs,broad,enabled,Block job seekers
shared_list,Shopping blocks,,,reviews,broad,enabled,Keep shopping ads off review searches
shared_list,Shopping blocks,,,cooling dog,phrase,enabled,
campaign,,Beds - shopping,,memory foam,broad,enabled,Memory foam range is out of stock
campaign,,Beds - research,,cooling,broad,enabled,Cooling beds are covered by another campaign
ad_group,,Beds - research,Comparisons,dog bed vs crate pad,exact,enabled,Retired comparison page
campaign,,Brand,,dog,broad,enabled,
campaign,,Gift cards,,pet gift card,exact,paused,Old rule
```

### 4. campaigns.csv

```
campaign,status,intent
Brand,enabled,People searching for the shop by name
Beds - shopping,enabled,People ready to buy dog beds
Beds - research,enabled,People comparing dog bed types before buying
Gift cards,enabled,People buying a gift card for a pet owner
Old season,paused,Autumn sale that has ended
```

### 5. attachments.csv

```
list_name,campaign
Shopping blocks,Beds - shopping
Shopping blocks,Gift cards
```

## The document the capability returned

**SEARCH EXCLUSION CONFLICT CHECK: Client R, as of 2026-11-10**

For: paid search specialist. Prepared 2026-11-10 from keywords.csv (11 rows), negatives.csv (9 rows), campaigns.csv (5 rows), attachments.csv (2 rows). Purpose column present.

**THE ANSWER**

9 live keywords and 8 live exclusions compared. 5 conflicts: 4 direct, 1 narrow. By level: account 1, shared list 1, campaign 2, ad group 1. 5 keywords have a conflict; 4 do not. Every conflict is a clue from the text. None shows that a search was blocked, and no change is proposed.

**CONFLICTS**

C1 Direct. Keyword "client r dog beds" (phrase), campaign Brand, ad group Shop name (keywords row 2).
  Exclusion "dog" (broad), level: campaign Brand (negatives row 8).
  Purpose as supplied: not stated
  Campaign intent as supplied: People searching for the shop by name
  Why flagged: the exclusion's one word, "dog", is a word of the keyword.
  To check: whether searches matching this keyword are being blocked by this exclusion, in the account's own search records.

C2 Direct. Keyword "memory foam dog bed" (exact), campaign Beds - shopping, ad group Orthopedic (keywords row 4).
  Exclusion "memory foam" (broad), level: campaign Beds - shopping (negatives row 5).
  Purpose as supplied: Memory foam range is out of stock
  Campaign intent as supplied: People ready to buy dog beds
  Why flagged: both words of the exclusion, "memory" and "foam", are words of the keyword.
  To check: whether searches matching this keyword are being blocked by this exclusion, in the account's own search records.

C3 Direct. Keyword "cooling dog bed" (broad), campaign Beds - shopping, ad group Cooling (keywords row 5).
  Exclusion "cooling dog" (phrase), level: shared list Shopping blocks (attached to Beds - shopping, Gift cards) (negatives row 4).
  Purpose as supplied: not stated
  Campaign intent as supplied: People ready to buy dog beds
  Why flagged: the exclusion's words "cooling dog" appear together, in that order, inside the keyword.
  To check: whether searches matching this keyword are being blocked by this exclusion, in the account's own search records.

C4 Direct. Keyword "free dog bed buying guide" (phrase), campaign Beds - research, ad group Free guides (keywords row 8).
  Exclusion "free" (broad), level: account (negatives row 1).
  Purpose as supplied: Block people looking for free items
  Campaign intent as supplied: People comparing dog bed types before buying
  Why flagged: the exclusion's one word, "free", is a word of the keyword.
  To check: whether searches matching this keyword are being blocked by this exclusion, in the account's own search records.

C5 Narrow. Keyword "dog bed vs crate pad" (broad), campaign Beds - research, ad group Comparisons (keywords row 7).
  Exclusion "dog bed vs crate pad" (exact), level: ad group Comparisons in Beds - research (negatives row 7).
  Purpose as supplied: Retired comparison page
  Campaign intent as supplied: People comparing dog bed types before buying
  Why flagged: the exclusion's words are identical to the keyword's, and the keyword is broad, so only the identical search is covered.
  To check: whether blocking the identical search is meant, while the keyword's other searches stay open.

**NOT COMPARED**

keywords.csv, row 10, "dog bed gift card": keyword paused.
keywords.csv, row 11, "autumn dog bed sale": campaign Old season is paused.
negatives.csv, row 9, "pet gift card": exclusion paused.

**COVERAGE**

Used: keywords.csv, 11 rows; negatives.csv, 9 rows; campaigns.csv, 5 rows; attachments.csv, 2 rows.
Could not judge: whether any search was in fact blocked or served; plurals, spelling variants, synonyms and each platform's own matching; the state of the ad groups, which were not supplied; exclusions held anywhere outside these files; results, spend and quality of any kind.
Ignored: None.
Checked and fine: every required header was present in every file; no keyword or exclusion text carried brackets, quote marks or plus signs; every campaign in keywords.csv and negatives.csv is in campaigns.csv; both attachments name a campaign in campaigns.csv; keywords 11 rows = 9 live + 2 not compared; exclusions 9 rows = 8 live + 1 not compared; 9 live keywords = 5 with a conflict + 4 without; 8 live exclusions = 5 in a conflict + 3 not (rows 2, 3 and 6); 5 conflicts = 4 direct + 1 narrow = 1 account + 1 shared list + 2 campaign + 1 ad group. Exclusion row 6, "cooling" in Beds - research, reaches no keyword that contains it, because "cooling dog bed" sits in Beds - shopping.

Draft for the paid search specialist. Nothing has been edited, paused, sent or spent; the specialist checks each conflict and decides what, if anything, changes.
