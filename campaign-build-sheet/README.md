# Campaign build sheet

When an approved campaign brief is ready to become a setup specification, the campaign operator gets one build sheet: names, audiences, exclusions, destinations, budgets and measurement fields, with every unresolved setting and missing asset marked as a gap. Nothing is built or spent.

*Workflow template · Advertising and lead generation · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/campaign-build-sheet/)*

## The outcome

The person setting up a paid campaign works from one sheet instead of a brief, three spreadsheets and a chat thread. Every campaign, audience and ad has a name built from your own naming convention. Every audience shows who is included and who is left out. Every ad points to a destination, a budget with its dates and the conversion it is meant to produce.

Where something is not settled, the sheet says so in the place it belongs and again in a numbered list of gaps: a destination that is not live, an image that has not arrived, a conversion nobody has confirmed, a plan that adds up to more than the spending limit. Nothing is guessed, defaulted or rounded off to make a line look finished.

The operator checks every value and the authorized owner decides what is created or changed in the account. The AI assistant connects to no ad account, launches nothing and spends nothing.

## Who starts the work, and when

The campaign operator, or whoever sets up paid campaigns for your company or for a client, starts it once the brief is approved and before anyone opens the ad account to build. It can be run again whenever a gap is closed or the brief changes, so the sheet always shows what is still open.

The person who approved the brief answers questions about audiences, budgets and dates. The authorized owner of the account approves any account creation or change.

## What they supply

- **Build settings:** the campaign name, the dates, the currency, the total spending limit, who approved the brief, the exclusions that apply to every line, the naming patterns and any further settings your account needs on each line.
- **The approved brief, line by line,** as a file: channel, audience, exclusions, destination, budget, dates, creative and conversion for each ad group or ad set.
- **The destinations,** with each address, whether it is live and its tracking parameters.
- **The asset list:** each image, video or text set and whether it is approved, in progress or missing.
- **The measurement list:** each conversion, what it means and where it is recorded.

No connection to an ad account or website is needed, and the workflow template never asks for a password, a login code or a key.

## What comes out

One build sheet in a fixed order. It opens with the campaign's totals and names, shows a block for each line in the order of the brief, and ends with the numbered gap register, a count of lines with no gaps open and the approval step. Each gap says where it is, what is wrong, what would resolve it and who in your own inputs can supply it.

A good sheet lets the operator build straight from it for every line without a gap, and shows the owner exactly what is still open on the rest.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Advertising and lead generation](https://fullypowered.ai/functions/advertising-and-lead-generation/), where a paid campaign has to be set up exactly as approved.
- [Marketing and content](https://fullypowered.ai/functions/marketing-and-content/), whose campaign briefs become instructions someone else has to carry out.
- [Marketing and advertising](https://fullypowered.ai/industries/marketing-and-advertising/), the agencies whose operators build for several clients in different accounts.
- [Ecommerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/), where seasonal campaigns have many lines, short dates and product pages that are not always ready.
- [Consumer brands](https://fullypowered.ai/industries/consumer-brands/), where one launch runs across several channels and audiences at once.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/), when campaigns multiply and set-up by memory starts to cost money.

It is not a plan for a creator campaign ([creator campaign plan](https://fullypowered.ai/workflows/creator-campaign-plan/)), a plan for the quarter ([ninety-day marketing plan](https://fullypowered.ai/workflows/ninety-day-marketing-plan/)) or a checklist for the day a launch goes out ([launch checklist](https://fullypowered.ai/workflows/launch-checklist/)). It starts after the brief is approved and ends with a sheet.

## What has to change for your company

- **Your naming patterns.** Write them once as patterns with the codes you already use, and set the length limit your platforms accept.
- **Your standing exclusions.** List the audiences that must be left out of every line, such as existing customers or staff.
- **Your required settings.** Name the further settings your account needs on each line, such as a bidding approach or a location, so the sheet can show when one is absent.
- **Your limits.** Set the total spending limit and, if you have one, a daily limit per line.
- **Your owners.** Decide who answers for the brief, for each destination and measurement, and who is the authorized owner of the account.
- **Your files.** Use the column names your tools export, or rename them once to the defaults. When a header does not match, the assistant stops and asks.

## What has been checked

Fully Powered AI wrote this workflow template. It was editorially reviewed on 10 November 2026. It was tried once on its invented example in Claude on 10 November 2026; that run was not blind to the published output, and a blind run is still to do. The record is published with it. It has not yet been tested in a client environment, or as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a campaign your operator has already built, with cases written in advance: a plan that goes over the limit, an exclusion missing from one line, a destination not yet live, an asset not yet delivered, a name that runs too long. The operator checks every value against the approved brief before anyone relies on it. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/) sets those cases up, and [what we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/) describes the record we keep.

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

- [Creator campaign plan](https://fullypowered.ai/workflows/creator-campaign-plan/)
- [Ninety-day marketing plan](https://fullypowered.ai/workflows/ninety-day-marketing-plan/)
- [Launch checklist](https://fullypowered.ai/workflows/launch-checklist/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
