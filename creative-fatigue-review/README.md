# Creative fatigue review

When a campaign's reach or response pattern prompts a creative review, the paid media lead gets frequency and response set against the campaign's own baseline, by creative and audience, with other explanations marked and options to test.

*Workflow template · Advertising and lead generation · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/creative-fatigue-review/)*

## The outcome

The conversation about whether the creative has run its course starts from one page instead of a hunch. For every creative in every audience, the page shows how often the same people were reached each week and how they responded, once in the campaign's own baseline window and once in the recent review window, with the change between them.

Beside each comparison sit the other things that could explain it: a tracking change, a run too short to read, an audience that mixes several groups or was edited, a bid or creative edit. Where one applies, the page says so and, where it would make the number misleading, declines to compare cost. It does not say why response moved, because a lower rate alone cannot show that. It ends with a short list of options to test, and the paid media lead chooses whether to test new creative, review the audience or hold.

## Who starts the work, and when

The paid media lead, or a media analyst for them, starts it when a campaign's reach or response pattern prompts a look at the creative: frequency creeping up, click-through easing, cost per result rising. The paid media lead reads it, with the creative owner, before deciding what to do.

## What they supply

- An export with one row per creative, audience and week: spend, impressions, reach, clicks and conversions.
- The baseline window the campaign should be judged against, and the recent review window.
- The audience definitions, saying which audiences mix several groups.
- The campaign change log: tracking, audience, bid, budget, offer, landing page and creative edits.
- The list of current assets, with launch dates and whether each is live.
- The campaign name, the currency of the spend column and the date of the export.
- Optionally, your own thresholds for how big a change is worth discussing.

## What comes out

One page in a fixed order: the settings and windows used, a campaign-level view, the changes in the period, the audience definitions, a table of frequency, click-through rate and cost per conversion by creative and audience with the change from baseline, the pairs that could not be compared and why, the alternative explanations for each pair, what the comparison shows, two to four options to test and questions for the lead. Where a section is empty it says so. The page claims no cause and changes nothing in any account.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Advertising and lead generation](https://fullypowered.ai/functions/advertising-and-lead-generation/), where creative runs against live spend and someone has to decide whether to refresh it.
- [Marketing and content](https://fullypowered.ai/functions/marketing-and-content/), where the people who make the creative need to know what the numbers can and cannot say.
- [Analytics and reporting](https://fullypowered.ai/functions/analytics-and-reporting/), for keeping tracking changes and audience edits beside the results.
- [Marketing and advertising](https://fullypowered.ai/industries/marketing-and-advertising/), where an agency watches creative across several clients.
- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/), where always-on campaigns reach the same shoppers for weeks.
- [Consumer brands](https://fullypowered.ai/industries/consumer-brands/), where one creative is often shown to a broad audience for a long run.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/), when spend is rising and the same audience is reached more often.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/), when an in-house team runs long-lived campaigns with a creative library that has not been refreshed on a schedule.

It is not a test of which creative did better (see [creative test evidence review](https://fullypowered.ai/workflows/creative-test-evidence-review/)) and not a report to a client ([client campaign performance report](https://fullypowered.ai/workflows/client-campaign-performance-report/)).

## What has to change for your company

Choose the baseline window for each campaign and the length of the review window. Set the size of change in frequency, click-through and cost that is worth discussing, and the minimum weeks, impressions and conversions a pair needs before it is compared. Agree which audiences you treat as mixed. Decide what goes in the change log, and who keeps it. Name the people who must read the page before anyone pauses, replaces or refreshes a creative.

## What has been checked

Fully Powered AI wrote this workflow template. It was editorially reviewed on 10 November 2026. It was tried once on its invented example in Claude on 10 November 2026, and the record is published with it. It has not yet been tested in a client environment, and it has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a past campaign whose story you already know: one where a creative really did tire, one where a tracking change made response look worse, and one with a mixed audience. The media lead should recompute every figure in the table from the export before the page is relied on.

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

- [Creative test evidence review](https://fullypowered.ai/workflows/creative-test-evidence-review/)
- [Client campaign performance report](https://fullypowered.ai/workflows/client-campaign-performance-report/)
- [Inherited campaign audit](https://fullypowered.ai/workflows/inherited-campaign-audit/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
