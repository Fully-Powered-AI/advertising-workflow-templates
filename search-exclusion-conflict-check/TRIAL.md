# Search exclusion conflict check: trial on the example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs were the invented example's own: the settings, keywords.csv, negatives.csv, campaigns.csv and attachments.csv in `public/example.md`. No client data was used. The one who ran it did not write the template, and read the example's output only after producing its own.

## What came out

**SEARCH EXCLUSION CONFLICT CHECK: Client R, as of 2026-11-10**

For: paid search specialist. Prepared 2026-11-10 from keywords.csv (11 rows), negatives.csv (9 rows), campaigns.csv (5 rows), attachments.csv (2 rows). Purpose column present.

**THE ANSWER.** 9 live keywords and 8 live exclusions compared. 5 conflicts: 4 direct, 1 narrow. By level: account 1, shared list 1, campaign 2, ad group 1. 5 keywords have a conflict; 4 do not. Every conflict is a clue from the text. None shows that a search was blocked, and no change is proposed.

**CONFLICTS**

- C1 Direct. Keyword "client r dog beds" (phrase), campaign Brand, ad group Shop name (keywords row 2). Exclusion "dog" (broad), level: campaign Brand (negatives row 8). Purpose: not stated. Intent: People searching for the shop by name. Why flagged: the exclusion's one word, "dog", is a word of the keyword.
- C2 Direct. Keyword "memory foam dog bed" (exact), campaign Beds - shopping, ad group Orthopedic (keywords row 4). Exclusion "memory foam" (broad), level: campaign Beds - shopping (negatives row 5). Purpose: Memory foam range is out of stock. Intent: People ready to buy dog beds. Why flagged: both exclusion words, "memory" and "foam", are words of the keyword.
- C3 Direct. Keyword "cooling dog bed" (broad), campaign Beds - shopping, ad group Cooling (keywords row 5). Exclusion "cooling dog" (phrase), level: shared list Shopping blocks (attached to Beds - shopping, Gift cards) (negatives row 4). Purpose: not stated. Intent: People ready to buy dog beds. Why flagged: "cooling dog" appears together, in order, inside the keyword.
- C4 Direct. Keyword "free dog bed buying guide" (phrase), campaign Beds - research, ad group Free guides (keywords row 8). Exclusion "free" (broad), level: account (negatives row 1). Purpose: Block people looking for free items. Intent: People comparing dog bed types before buying. Why flagged: the exclusion's one word, "free", is a word of the keyword.
- C5 Narrow. Keyword "dog bed vs crate pad" (broad), campaign Beds - research, ad group Comparisons (keywords row 7). Exclusion "dog bed vs crate pad" (exact), level: ad group Comparisons in Beds - research (negatives row 7). Purpose: Retired comparison page. Intent: People comparing dog bed types before buying. Why flagged: the words are identical and the keyword is broad, so only the identical search is covered.

Each Direct conflict carried the fixed "To check" sentence about searches being blocked, and C5 the fixed Narrow sentence.

**NOT COMPARED:** keywords.csv row 10 "dog bed gift card" (keyword paused); row 11 "autumn dog bed sale" (campaign Old season paused); negatives.csv row 9 "pet gift card" (exclusion paused).

**COVERAGE.** All four files used. Could not judge: whether any search was blocked, plurals and variants, ad-group state, exclusions outside the files, results and spend. Ignored: None. Checked and fine: headers present; no brackets, quotes or plus signs; 11 keywords = 9 live + 2 not compared; 9 exclusions = 8 live + 1 not compared; 9 live keywords = 5 with a conflict + 4 without; 8 live exclusions = 5 in a conflict + 3 not (rows 2, 3, 6); 5 conflicts = 4 direct + 1 narrow = 1 + 1 + 2 + 1 by level.

The full closing line was included: nothing edited, paused, sent or spent.

## What was observed

- Every required part of the output format was produced, and nothing in the inputs triggered a stop.
- The result matched the published example on every conflict, class, count, row number and Not compared entry. The only differences were layout (this record compresses each conflict to a line).
- No fact appeared in either output that is not in the inputs.
- The checklist held: words matched the files, scope followed each level (the shared list reached only its two attached campaigns), purposes were quoted as supplied, and the wording claimed no more than a clue.

Where the template left room to guess:

- Row numbers: it says "row in keywords.csv" but not whether the header counts. I numbered data rows from 1 (header excluded), as the example does. The template should say so.
- The output format has no slot for the live-exclusion split (in a conflict versus not), though step 8 asks for it. I put it under "Checked and fine".
- "Checked and fine" is free-form, so what to list there is a judgment.
- Counting "keywords with a conflict" counts each keyword once even if several exclusions hit it; the template does not say this.
- A campaign-level exclusion's blank ad_group and a shared list's blank campaign are expected, but "a field its level needs left blank" is only implied by the input list.

This was one trial on one invented example. It shows the instructions can be followed to the published output, not that they work on real account exports or in other products.
