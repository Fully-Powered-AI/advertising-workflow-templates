# Campaign build sheet

Workflow template, version 0.1.0.

## Purpose

Turn one approved campaign brief into one build sheet the campaign operator can set up from: a campaign name, an audience name and ad names built from the company's naming patterns, the audience each line includes and leaves out, the destination, the budget with its dates, the creative, the conversion to measure and any further settings the account needs. Anything not settled is shown as a numbered gap in the place it belongs and again in a register. The assistant prepares; it connects to no ad account, creates or changes nothing, launches nothing, spends nothing and fills no gap with a guess.

## When to use it and when not to

Use it when a campaign brief has been approved by a named person and the setup of the campaign is about to begin. Run it again whenever a gap is closed or the brief changes.

Do not use it:

- to write or approve the brief, choose channels or set budgets; the brief comes first and a person approves it;
- to plan a creator campaign, a quarter's marketing or a launch day; those are the creator campaign plan, the ninety-day marketing plan and the launch checklist;
- to check that ad wording is true, that a page matches its ad or that an audience list may be used; those are separate pieces of work;
- when the brief has not been approved.

## Roles

- **Runs it and checks every value:** the campaign operator.
- **Approved the brief and answers questions about audiences, budgets, dates and further settings:** the brief approver named in the settings.
- **Approves any account creation or change, and any spend:** the authorized owner of the account.
- **Supplies destinations, measurement and assets:** the owners named in those files.

## Inputs

1. **Build settings,** as a list of `name: value` lines. Required: `Business`, `Campaign`, `Brief approved by` (a person or role and a date), `Operator`, `Authorized owner`, `Currency`, `Start date` and `End date` (as YYYY-MM-DD; the end date may be `open`), `Total spending limit`, `Campaign name pattern`, `Audience name pattern` and `Ad name pattern`. Optional: `Daily limit per line`, `Maximum name length` (default 40), `Campaign-wide exclusions` (items separated by semicolons), `Required other settings` (names separated by semicolons), `As-of date` (when it is not supplied, the sheet's "As of" line reads `not supplied`; the assistant never uses today's date), and any code the patterns use, such as `brand_code`. If a required setting is missing, stop and ask. If `Brief approved by` is blank, stop: an unapproved brief is not built from.
2. **Brief lines** (brief_lines.csv), one row per ad group or ad set, with these headers: `line_id`, `channel`, `channel_code`, `audience_code`, `audience_description`, `include_rules`, `exclusions`, `destination_ref`, `budget_type`, `budget_amount`, `line_start`, `line_end`, `creative_refs`, `conversion_event`, `other_settings`. `budget_type` is `daily` or `lifetime`. `exclusions` and `creative_refs` hold items separated by semicolons. `other_settings` holds `name: value` pairs separated by semicolons. A blank `line_start` or `line_end` takes the campaign's date, and the Budget line says so by adding `(campaign dates)` after the dates. If the file is missing, stop. If a header does not match, stop and ask which column is which; never guess.
3. **Destinations** (destinations.csv), with these headers: `destination_ref`, `url`, `status`, `tracking_parameters`, `owner`. `status` is `live` when the page is ready for visitors; any other word is shown as given. The assistant reads the supplied status and never opens the address. If the file is missing, every destination is a gap. If a header does not match, stop and ask.
4. **Assets** (assets.csv), with these headers: `asset_ref`, `asset_type`, `description`, `status`, `approved_by`. `status` is `approved` when a person has signed the asset off; any other word is shown as given. If the file is missing, every creative reference is a gap. If a header does not match, stop and ask.
5. **Measurement** (measurement.csv), with these headers: `conversion_event`, `definition`, `where_recorded`, `status`, `owner`. `status` is `confirmed` when someone has seen the event recorded; any other word is shown as given. If the file is missing, every conversion is a gap. If a header does not match, stop and ask.

The assistant works from the settings, files and notes the person supplies. It needs no connection to an ad account, website or analytics tool, and never asks for a password, a login code or a key; if one is pasted in, it does not copy it into the sheet and tells the person to remove it.

## The procedure

1. **Check the inputs.** Confirm one campaign. Match references across the files by exact text after trimming spaces and ignoring case. Stop if `line_id` repeats or the brief has no lines. A `destination_ref`, creative reference or `conversion_event` that is not in its file is a gap, not a stop.
2. **Work out the dates.** The campaign has the days from `Start date` to `End date`, counting both ends. A line takes its own dates, or the campaign's if blank. A line date outside the campaign's dates is a gap that names both. A date that cannot be read as YYYY-MM-DD is a gap, and no day count is worked out from it. If the end date is `open`, no total can be worked out for a daily budget and that is a gap.
3. **Build the names.** Replace each `{token}` in a pattern with its value. A token takes its value from the build settings or from the brief line; two are worked out: `start_yyyymm` is the year and month of `Start date` written as six digits, and `creative_ref` is each reference in `creative_refs`, one ad name per reference. A campaign name is built once, an audience name once per line and an ad name once per creative reference. A token with no value means no name is built: print `name not built` and raise a gap that names the token. Never shorten, abbreviate or invent a code. Count every character of a built name, including hyphens, underscores and spaces. A name longer than the maximum, or a name that appears twice at the same level, is a gap. The "longest" figure in the campaign block is the longest of all names built, at all three levels.
4. **Show the audience.** Copy `audience_description` and `include_rules` as supplied; a blank `include_rules` is a gap. Show the line's exclusions. For each campaign-wide exclusion, check whether the line lists it; one that is absent is a gap that names it. Exclusions on the line beyond the campaign-wide list are shown as line-specific. Never add, remove or reword an exclusion, and do not judge whether a targeting choice is wise.
5. **Show the destination.** Show the address, status and tracking parameters from the destinations file. A blank address is a gap. A status other than `live` is a gap that gives the status. Blank tracking parameters are a separate gap, so a destination that is not live and has no tracking parameters has two gaps. (The measurement step is different: one event is one gap.) Print the parameters exactly as supplied and never write or correct them.
6. **Work out the budget.** For a `daily` budget, the planned total is the amount multiplied by the number of days on the line. For a `lifetime` budget, it is the amount. A daily amount over `Daily limit per line`, when one is set, is a gap. A missing or unreadable amount or type is a gap, and the line is left out of the campaign total, which is then marked partial. Add the planned totals of the lines. If the sum is over `Total spending limit`, raise a campaign-level gap that gives both figures and the difference; if it is under, or exactly equal, show the headroom (which is 0 when equal). In the over-limit gap, give each line's planned total after the difference, for example `(L1 3,360; L2 1,890)`. Never reduce, rebalance or round any line to fit the limit.
7. **Show the creative.** List each creative reference with its asset type and status. A status other than `approved` is a gap that gives the status. A reference not in the asset list is a gap.
8. **Show the measurement.** Show the line's conversion event with its definition and where it is recorded. A status other than `confirmed`, or a blank `where_recorded`, is one gap for the event. A blank `conversion_event` on a line is a gap.
9. **Show the other settings.** For each name in `Required other settings`, show the value from the line's `other_settings`. A name with no value is a gap. Settings the line lists that are not required are shown as given.
10. **Number the gaps.** Number them in the order they appear on the sheet: campaign level first, then each line in the order of the brief, and within a line in the order of its block (names, exclusions, destination, budget, creative, measurement, other settings). Raise one gap per field per item. For each gap give where it is, what is wrong, what would resolve it and who can supply it. Who can supply is the `owner` for a destination or a conversion, and `approved_by` for an asset if it is filled. An asset gap whose `approved_by` is blank is `not stated`, even though the creative reference came from the brief. For anything else that comes from the brief, it is the brief approver; if the inputs name nobody, write `not stated`.
11. **Close.** Count the lines with no gap and the gaps in all. State that no account has been created, changed or connected. End with the trace line and return the sheet to the operator only.

## Exceptions and stop conditions

- **A required setting is missing, or `Brief approved by` is blank:** stop and ask.
- **A header does not match the default:** stop and ask which column is which.
- **`line_id` repeats, or there are no lines:** stop and report which.
- **A reference is not in its file:** raise a gap; do not stop.
- **A name token has no value:** do not build the name; raise a gap.
- **The plan is over the spending limit:** show it as a gap and change no line.
- **A date, amount or budget type cannot be read:** raise a gap and work nothing out from it.
- **A password, login code or key is pasted in:** do not copy it; ask the person to remove it.
- **Asked to create or change anything in an account, connect to one, launch, schedule, spend, fill a gap with a plausible value, rebalance a budget, judge a targeting choice or change the brief:** decline; the operator checks and the authorized owner approves.

## Output format

```
CAMPAIGN BUILD SHEET: [campaign], [business]

For: [operator]. Brief approved by [approver and date]. As of [date, or not supplied]. Authorized owner: [owner].

CAMPAIGN
Name: [campaign name, or name not built]
Dates: [start] to [end] ([n] days, or no day count when the end is open)
Currency: [currency]
Spending limit: [limit]. Planned total: [sum] ([complete or partial]). [Over the limit by [amount]. or Headroom [amount].]
Campaign-wide exclusions: [list, or none supplied]
Names: [n] built, longest [n] characters of [maximum], [duplicates or none duplicated]. [n] not built.

LINES

[line_id]: [channel]
Names: audience [name]. Ads [names].
Audience: [audience description]. Includes: [include rules]
Exclusions: [list]. Campaign-wide missing: [list, or none]. Line-specific: [list, or none]
Destination: [ref], [address], status [status], tracking [parameters, or none supplied]
Budget: [type] [amount], [dates and days, with (campaign dates) after any date taken from the campaign] = [planned total]
Creative: [ref (type, status)], and so on
Measurement: [event], [definition], recorded at [place], status [status]
Other settings: [name: value], and so on
Gaps: [numbers, or none]

[repeat for every line in the order of the brief]

GAP REGISTER

[n]. [Where]: [what is wrong]. To resolve: [what is needed]. Who can supply: [role or not stated].
[or: No gaps.]

Lines with no gaps: [n] of [n] ([ids, or none]). Gaps in all: [n].
Next step: [operator] checks every value against the brief approved on [date]. [Authorized owner] approves any account creation or change. No account has been created, changed or connected.

Every figure and value traces to the build settings for [campaign] and the brief lines, destinations, assets and measurement list supplied. The sheet changes nothing, launches nothing and spends nothing.
```

## Reviewer checklist

1. Every name follows its pattern exactly, and no code was invented where a value was missing. (Operator)
2. The day counts and planned totals are arithmetically correct, and the campaign total is the sum of the lines. (Operator)
3. Every campaign-wide exclusion is either shown on a line or raised as a gap for that line. (Brief approver)
4. Every destination, asset and conversion status is as supplied, and nothing marked live, approved or confirmed that was not. (Operator)
5. Every gap appears once in the register, in sheet order, with who can supply it. (Operator)
6. No value in the sheet is absent from the inputs. (Operator)
7. The sheet recommends no budget change, targeting choice or creative, and states that nothing was created or launched. (Authorized owner)

## Acceptance tests

Proposed tests. Only test 1 has been run, once, and not blind (see the trial record in the public folder); tests 2 to 8 have not been run.

1. **Normal run.** The invented example in the public folder. Expected: one campaign name, three audience names, six ad names, eight gaps, one line of three with no gaps, planned total 6,150 against a limit of 6,000.
2. **Brief not approved.** `Brief approved by` is blank. Expected: stops and builds nothing.
3. **Header mismatch.** The brief file names a column `spend` in place of `budget_amount`. Expected: stops and asks which column is which.
4. **Missing token.** A line has no `audience_code`. Expected: its audience and ad names print `name not built`, and a gap names the token.
5. **Name too long.** An audience name comes to 46 characters with a limit of 40. Expected: the name is shown unshortened and a gap gives both numbers.
6. **Open end date.** `End date: open` with a daily budget. Expected: no planned total for that line, a gap, and the campaign total marked partial.
7. **Reference not in its file.** A line names destination D9, which is not listed. Expected: a gap; the sheet continues.
8. **Asked to launch or fill a gap.** "Set it up in the account" or "just put a sensible location." Expected: declines both; the gap stays.

## Instructions for the AI assistant

```
You prepare a campaign build sheet for the campaign operator from an
approved campaign brief. You never connect to an ad account, create or
change anything in one, launch, schedule or spend, and you never fill a gap
with a guess. The operator checks every value and the authorized owner
approves any account creation or change. Never ask for a password, a login
code or a key; if one is pasted in, do not copy it and tell the person to
remove it.

The user will supply: build settings (name: value lines); brief lines
(brief_lines.csv); destinations (destinations.csv); assets (assets.csv);
measurement (measurement.csv). Required settings: Business, Campaign,
Brief approved by, Operator, Authorized owner, Currency, Start date, End
date (a date, or open), Total spending limit, and the three name patterns.
If one is missing, or Brief approved by is blank, stop and ask. Optional:
Daily limit per line, Maximum name length (default 40), Campaign-wide
exclusions, Required other settings, As-of date, and any code a pattern
uses. If a file header does not match the default headers listed under
Inputs (pasted after these instructions), stop and ask which column is
which. Stop if the brief file is missing, has no lines, or repeats a
line_id. If the destinations, assets or measurement file is missing, every
reference to it is a gap. Match references across files by exact text,
trimming spaces and ignoring case; a reference not found is a gap, not a
stop.

1. Dates: days run from the start date to the end date, counting both
   ends. A blank line date takes the campaign date; add "(campaign dates)"
   after the dates in that line's Budget line. A line date outside the
   campaign dates (name both), or one that cannot be read as YYYY-MM-DD, is
   a gap, and no day count is worked out from it. If the end date is open, print the Dates line as "[start] to open (no day count)";
   a daily budget gets no total and that is a gap.
2. Names: fill each {token} from the settings or the brief line;
   start_yyyymm is the year and month of the start date as six digits;
   creative_ref gives one ad name per reference. Build one campaign name,
   one audience name per line and one ad name per creative reference. If a
   token has no value, print "name not built" and raise a gap naming it.
   Never shorten, abbreviate or invent a code. Count every character,
   hyphens included. A name over the maximum length (default 40), or
   repeated at the same level, is a gap; show the name unshortened and give
   both numbers. The "longest" figure covers all names built, at all three
   levels.
3. Audience: copy the description and include rules as supplied; blank
   include rules are a gap. Show the line's exclusions. For each
   campaign-wide exclusion the line lacks, raise a gap naming it. Show
   exclusions beyond the campaign-wide list as line-specific. Add, remove
   and reword nothing, and do not judge targeting.
4. Destination: print address, status and tracking parameters as supplied.
   A blank address is a gap; a status other than live is a gap that gives
   the status; blank tracking is a separate gap. Never open the address or
   write or correct tracking parameters.
5. Budget: daily = amount x days on the line; lifetime = amount. A daily
   amount over the daily limit per line is a gap. A missing or unreadable
   amount or type is a gap; the line is left out of the sum and the total
   is marked partial. Sum the lines. If the sum is over the spending
   limit, raise a campaign-level gap giving both figures, the difference
   and each line's planned total; if it is under or exactly equal, show the
   headroom (0 when equal). Never reduce, rebalance or round a line to fit.
6. Creative: list each reference with its asset type and status. Any
   status other than approved, or a reference not in the asset list, is a
   gap.
7. Measurement: show the event, its definition and where it is recorded. A
   status other than confirmed or a blank place recorded is one gap for the
   event. A blank event on a line is a gap.
8. Other settings: for each required name, show the line's value; a name
   with no value is a gap. Show other listed settings as given.
9. Number the gaps in sheet order: campaign first, then each line in the
   brief's order and, within a line, in the order of its block (names,
   exclusions, destination, budget, creative, measurement, other settings).
   One gap per field per item. For each give where, what is wrong, what
   resolves it and who can supply it: the owner for a destination or
   conversion; approved_by for an asset if filled, otherwise "not stated"
   (even though the reference came from the brief); for other brief
   matters the brief approver; otherwise "not stated".
10. Output exactly the output format pasted after these instructions. If
   the As-of date was not supplied, write "As of not supplied"; never use
   today's date. Close with the count of lines with no gaps (listing their
   ids) and the gaps in all, say that no account has been created, changed
   or connected, and end with the trace line.

If asked to create or change anything in an account, connect to one,
launch, schedule, spend, fill a gap with a plausible value, rebalance a
budget, judge a targeting choice or change the brief, decline; a person
decides.
```

Paste this block as custom instructions, followed by the Inputs section and the output format above.

## What to customize

- Your three naming patterns, the codes they use and the maximum name length.
- Your campaign-wide exclusions.
- The further settings your account needs on every line.
- Your total spending limit and any daily limit per line.
- The words your tools use for a destination that is ready, an asset that is signed off and a conversion that is confirmed.
- Who approves the brief, who owns each destination and measurement, and who is the authorized owner of the account.
- Which exports the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI. Tried once on its invented example in Claude on 10 November 2026; that run was not blind to the published example output, and a blind run is still to do. Acceptance tests 2 to 8 have not been run. Not yet tested in a client environment.
