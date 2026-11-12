# Lead quality pattern review

When sales feedback or results raise a lead-quality concern, the acquisition lead gets a review of leads and their outcomes by source, page, location, device and timing, with cases to verify with sales and possible measurement faults listed.

*Workflow template · Advertising and lead generation · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflow templates/lead-quality-pattern-review/)*

## The outcome

"Those leads are not any good" turns into something the team can look at. Every lead in the period is set beside what happened to it afterwards, and the review shows where the share of useful leads sits well below the overall share: which source, which page, which location, which device, which part of the day or which week. It shows when the same leads sit in several of those places at once, so nobody reads one pattern as separate from the others.

Each pattern comes with a short list of real leads for sales to look at, and the review lists the measurement faults that could produce a pattern: repeated records, blank or unexpected values, dates outside the period, outcomes never updated. It does not say why a pattern exists, it accuses no source of anything, and it proposes no change to targeting. Unusual numbers are a place to look, and sales is asked what they actually found.

## Who starts the work, and when

The acquisition lead starts it when sales says leads have stopped being worth the call, or when results show conversions that do not become useful leads. Sales development checks the cases, the tracking owner checks the measurement faults, and the acquisition lead decides what is investigated and what, if anything, is taken forward after sales has confirmed it.

## What they supply

- **Settings:** the period, the as-of date, how a lead is defined, and which outcome words count as useful, not useful and still open.
- **The lead outcomes export** for the period: one row per lead with an id, the date and time it arrived, its source, landing page, location, device and outcome. No names, emails or phone numbers are needed.
- **The scope:** the sources, pages and locations the program is meant to use.
- **Known changes** to a form, tag, page or budget inside the period, if any.
- **Sales feedback** notes, with lead ids where sales has them.

No connection to an ad platform or the analytics tool is needed, and no sign-in details are asked for.

## What comes out

One document in a fixed order: a data check, any known changes, every segment with its counts and its position against the overall share, numbered patterns with their cases to verify, a list of possible measurement faults, how each sales note lines up with the records, and what could not be assessed.

Good looks like this: sales can take the cases, check them against what they know and say whether the outcome labels are right, and the tracking owner can see exactly which records to look at.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Advertising and lead generation](https://fullypowered.ai/functions/advertising-and-lead-generation/), where a lead is paid for before anyone knows whether it was worth having.
- [Analytics and reporting](https://fullypowered.ai/functions/analytics-and-reporting/), which owns the conversion definitions and the records behind them.
- [Sales](https://fullypowered.ai/functions/sales/), whose contact with the leads is the only check on what the numbers suggest.
- [Marketing and advertising](https://fullypowered.ai/industries/marketing-and-advertising/), where an account lead has to answer a client when leads disappoint.
- [Software technology](https://fullypowered.ai/industries/software-technology/), where demo requests arrive from many sources and sales soon has views on them.
- [Professional services](https://fullypowered.ai/industries/professional-services/), where each enquiry is a real person to call and a poor batch is felt at once.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/), when budgets and channels have multiplied faster than anyone has checked them.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/), where the same programs have run for years and nobody has looked at their outcomes lately.

It is not a handover audit of someone else's campaign account ([inherited campaign audit](https://fullypowered.ai/workflows/inherited-campaign-audit/)), a field-by-field look at a form ([lead form field review](https://fullypowered.ai/workflows/lead-form-field-review/)), or an explanation of why two reports disagree ([metric definition reconciliation](https://fullypowered.ai/workflows/metric-definition-reconciliation/)).

## What has to change for your company

- **Your outcome words.** List exactly which outcomes in your sales records count as useful, not useful and still open. The review stops when it meets a word on none of the lists.
- **Your export.** Use the column names your tools give you, or rename them once to the defaults. When a header does not match, the assistant stops and asks.
- **Your thresholds.** The defaults read a segment only with 20 settled leads and flag it when its useful share is 15 points below the overall share. Set the levels your team can act on.
- **Your scope.** List the sources, pages and locations you mean to use, so values outside them are noticed.
- **Your day parts.** Change the four time bands if your business hours differ.
- **Your owners.** Decide who verifies cases with sales, who checks tracking and who may approve a change to targeting afterwards.
- **Your platform.** It is written for ChatGPT, Claude, Copilot or Gemini and works from files you supply. Decide which exports the assistant may read.

## What has been checked

Fully Powered AI wrote this workflow template. It was editorially reviewed on 10 November 2026. It was tried once on its invented example, in Claude on 10 November 2026, and the record is published with it (the run was not blind: only its arithmetic was independent); it was edited in small ways after an independent review, and those edits were not run again. It has not yet been tested in a client environment or as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a past period your acquisition lead and sales team already know well, with cases written in advance: an outcome word on no list, a segment too small to read, a lead id sales mentions that is not in the export, a repeated record. Your analyst checks every figure against the export before anyone relies on it. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/) sets those cases up, and [what we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/) describes the record we keep.

- Written by Fully Powered AI.
- Sources and rights reviewed.
- Editorially reviewed on 10 November 2026.
- Package format checked by script on every release.
- Tried once on its invented example in Claude on 10 November 2026. The record is in [TRIAL.md](TRIAL.md).
- Not yet tested in a client environment.

## What is in this folder

- [TEMPLATE.md](TEMPLATE.md): the complete workflow template. Roles, inputs, the procedure, exceptions and stop conditions, the output format, a reviewer checklist, acceptance tests, the instructions for an AI assistant and what to customize.
- [EXAMPLE.md](EXAMPLE.md): a worked example with invented data.
- [TRIAL.md](TRIAL.md): what came out when the template was tried on its example.
- [SKILL.md](SKILL.md): the technical file, for AI products that load packaged instructions from a folder.
- [SOURCES.md](SOURCES.md): what the workflow template drew on, with licences.
- [LICENSE](LICENSE): MIT. Use it, change it, make it yours.

## Start using it

1. Read [EXAMPLE.md](EXAMPLE.md) to see what a good result looks like.
2. Open [TEMPLATE.md](TEMPLATE.md) and set every item under "What to customize" to your own rules, roles and limits.
3. Give your AI assistant the instruction block and the output format from the template, with your own limits in place of the ones the instructions leave open in square brackets. Paste them in as custom instructions in ChatGPT, Claude, Copilot or Gemini, or copy this whole folder into a product that loads `SKILL.md` packages. This folder stands alone; you do not need the rest of the repository.
4. Run it on past work first, using the reviewer checklist and acceptance tests in the template, before anyone relies on it.

## Related workflow templates

- [Lead form field review](https://fullypowered.ai/workflow templates/lead-form-field-review/)
- [Metric definition reconciliation](https://fullypowered.ai/workflow templates/metric-definition-reconciliation/)
- [Tracking event plan](https://fullypowered.ai/workflow templates/tracking-event-plan/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
