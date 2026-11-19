# Campaign audience check

Review an email audience export with reconciled counts, exclusions applied and records to check. The campaign owner decides; nothing is sent.

> [!TIP]
> **Missing a template that is not listed here, or want these customized for your organization? Reach out to us.** This is a template, made to be customized and deployed. FullyPowered AI customizes and builds AI workflows, connects them to your business systems, installs them in your agents and puts them in the hands of the people who own the work. [See Campaign audience check on our website](https://fullypowered.ai/workflows/campaign-audience-check/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-campaign-audience-check&from=gh-advertising-campaign-audience-check). Not sure where to start? Email hello@fullypowered.ai and a person will answer.

**Quick start**

1. Read EXAMPLE.md to see what a good result looks like.
2. Copy all of TEMPLATE.md into your assistant, then give it your own inputs, or the invented ones from EXAMPLE.md.
3. Read what comes back. It marks what it checked and what is left for you.

*Workflow template · Advertising and lead generation · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/campaign-audience-check/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-campaign-audience-check&from=gh-advertising-campaign-audience-check)*

## The outcome

Nobody approves an email audience on the strength of a row count. The campaign owner gets one page that says how many records the export held, how many are cleared to go into each segment, how many were taken out and why, and how many are being held back until a person looks at them. The three groups add up to the export, and the page shows the sum.

The records that need a decision stay in plain sight. Two preference rows that disagree, a permission record that is old, an address that appears twice under different records, a record with no permission on file at all: each is listed with what the files show and a question for a named person. The page never settles one of them by guessing, and it never treats a missing permission as a yes.

The owner resolves the uncertain records, signs off the final audience, and decides what happens next. The page sends nothing, changes no list and takes no view on what the law requires of the campaign.

## Who starts the work, and when

The campaign owner, or someone on the marketing team for them, starts it when an audience export for a campaign is ready for review and before anything is scheduled. The customer-data steward, where there is one, answers the questions about records. The owner reads the page and approves the final audience.

## What they supply

- The audience export from your email marketing tool, or the list you keep, one row per record, with the address and the fields the segments use.
- The permission records for those people: what status each holds and when it was recorded.
- The preference records for the campaign's topic.
- The bounce history from your email marketing tool, by address.
- Optionally, your own do-not-contact list.
- The campaign's settings: the as-of date, the topic, which permission statuses you count as permitted and which as excluded, how old a permission record may be, and the segment rules in priority order.

## What comes out

One page in a fixed order: the answer in a few lines, the settings used, the counts reconciled from the export to the three groups, the segments with cleared and held-back counts, the exclusions applied with their record numbers, a numbered list of records to check, the decisions for the campaign owner, and what the page could not judge. Where a section is empty it says so. A final line leaves a place for the owner's approval of the audience.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Advertising and lead generation](https://fullypowered.ai/functions/advertising-and-lead-generation/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-campaign-audience-check&from=gh-advertising-campaign-audience-check), where an audience is built, reviewed and approved before it is used.
- [Marketing and content](https://fullypowered.ai/functions/marketing-and-content/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-campaign-audience-check&from=gh-advertising-campaign-audience-check), where the team that writes the message wants to know exactly who it is going to.
- [Marketing and advertising](https://fullypowered.ai/industries/marketing-and-advertising/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-campaign-audience-check&from=gh-advertising-campaign-audience-check), where an agency reviews a client's audience before a send.
- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-campaign-audience-check&from=gh-advertising-campaign-audience-check), where buyers, newsletter sign-ups and event contacts sit in the same list.
- [Consumer brands](https://fullypowered.ai/industries/consumer-brands/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-campaign-audience-check&from=gh-advertising-campaign-audience-check), where lists grow from many sources and preferences change often.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-campaign-audience-check&from=gh-advertising-campaign-audience-check), when the list is growing faster than anyone can keep track of it.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-campaign-audience-check&from=gh-advertising-campaign-audience-check), when years of imports have left a list nobody fully trusts.

It does not choose who to win back ([lapsed-customer win-back](https://fullypowered.ai/workflows/lapsed-customer-win-back/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-campaign-audience-check&from=gh-advertising-campaign-audience-check)), build a list of prospects ([prospect list by role and firm type](https://fullypowered.ai/workflows/prospect-list-by-role-and-firm-type/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-campaign-audience-check&from=gh-advertising-campaign-audience-check)) or set up the campaign itself ([campaign build sheet](https://fullypowered.ai/workflows/campaign-build-sheet/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-campaign-audience-check&from=gh-advertising-campaign-audience-check)). It starts when a list already exists and ends with a checked audience.

## What has to change for your company

Name the permission statuses your records use, and say which count as permitted and which as excluded; a status left in neither list is held back for a question. Decide how old a permission record can be before it is looked at again, and how many soft bounces in what period call for a check. Write your segments as rules on the columns your export holds, in priority order. Agree who answers for record questions and who approves the final audience. If a rule about permission applies to your campaign, your own advisers set it; the workflow template only applies the statuses you give it.

## What has been checked

FullyPowered AI wrote this workflow template. It was editorially reviewed on 10 November 2026. It was tried on its invented example on 10 November 2026 in Claude; the record is published with it. It has not yet been tested in a client environment. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a past audience whose problems you already know: a record with two disagreeing preferences, an address held twice, a permission record years old, and an address that bounced. The steward should recompute every count from the export before the page is relied on.

- Written by FullyPowered AI.
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

- [Lapsed-customer win-back](https://fullypowered.ai/workflows/lapsed-customer-win-back/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-campaign-audience-check&from=gh-advertising-campaign-audience-check)
- [Prospect list by role and firm type](https://fullypowered.ai/workflows/prospect-list-by-role-and-firm-type/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-campaign-audience-check&from=gh-advertising-campaign-audience-check)
- [Campaign build sheet](../campaign-build-sheet/)

## Make it yours

This workflow template is an example and a starting point. FullyPowered AI adapts it to how your company works, proves it on real work and rolls it out to the roles that use it. We can also build any other workflow for your company, including one that runs several steps, in a Workflow Sprint or a scoped implementation. [Talk with us](https://fullypowered.ai/contact/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-campaign-audience-check&from=gh-advertising-campaign-audience-check).
