# Stale promotion code review

Review a store's expired, unused and duplicate discount codes against the campaigns that still name them, with a proposal for a person to approve.

> [!TIP]
> **Missing a template that is not listed here, or want these customized for your organization? Reach out to us.** This is a template, made to be customized and deployed. FullyPowered AI customizes and builds AI workflows, connects them to your business systems, installs them in your agents and puts them in the hands of the people who own the work. [See Stale promotion code review on our website](https://fullypowered.ai/workflows/stale-promotion-code-review/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review). Not sure where to start? Email hello@fullypowered.ai and a person will answer.

**Quick start**

1. Read EXAMPLE.md to see what a good result looks like.
2. Copy all of TEMPLATE.md into your assistant, then give it your own inputs, or the sample ones from EXAMPLE.md.
3. Read what comes back. It marks what it checked and what is left for you.

*Workflow template · Advertising and lead generation · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/stale-promotion-code-review/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review)*

## The outcome

Every store collects discount codes: one for each season, each creator, each apology, each banner. After a year or two nobody can say which still matter, and the next campaign adds more. This workflow template sorts them before that happens.

Each code gets one state on the review date: expired, used up, switched off, starting later, or working. Working codes nobody has used for a set time are called unused. Codes that repeat each other are grouped, whether they share the same text in different letter case or give the same offer under different names. Then every live or scheduled campaign that names a code is checked against that code's dates and limit, so a pop-up still offering a code that ran out of uses months ago, or a launch email naming a code that ends ten days before the campaign does, is caught before a shopper finds it at checkout.

Every code on the list carries one proposal from a short, fixed list: keep it, fix the campaign first, confirm first, end the code, or clear the expired code. A code that a campaign still needs is never proposed for ending. The approver decides each line, and a person makes every change.

## Who starts the work, and when

The e-commerce manager or the marketing manager runs it when old codes have piled up and a campaign is coming, when a campaign has gone out naming a code that did not work, or as a routine tidy once a quarter.

Whoever approves changes to codes reads the review and decides each line. Each campaign owner answers for their own campaigns, and whoever named a code on the keep list, such as the customer service lead, confirms it.

## What they supply

- **Review settings:** the store, who it is prepared for, who approves changes, the review date, and how many days without use make a code unused (90 unless you set another number).
- **The code export** from the store, one row per code: the offer, what it applies to, the minimum order, its status, its dates, its usage limit, how often it has been used and when it was last used.
- **Campaign references,** one row for each place a campaign names a code: the campaign, its channel, where the code appears, its status, its dates and its owner. Emails, ads, site banners, creator posts, printed inserts and customer service replies all count.
- **A keep list,** if you have one: codes someone has said must stay, with the reason and who said so.

The column headers are checked first. If one does not match, the work stops and asks which column is which. Nothing is opened or connected, and the workflow template never asks for a password, a login code or a key.

## What comes out

One review in a fixed order. It opens with the date lines and a summary that counts every code, so the list and the counts can be checked against the export. Then come the data checks, where the export disagrees with itself. The codes follow under three headings (no longer works, unused, and other codes on the list), each with its offer, dates, use, duplicate group, the campaigns that name it and its proposal. After them come the duplicate groups, the campaigns to fix, each with its owner and what would settle it, and the questions for the person the review is prepared for. An empty section says "None."

Each line ends with "Decision: open." The review closes by saying what it did not check and that nothing in the store or any campaign has been changed.

See the worked example in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Advertising and lead generation](https://fullypowered.ai/functions/advertising-and-lead-generation/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review), where an ad that sends shoppers to a code that no longer works wastes the spend behind it.
- [Marketing and content](https://fullypowered.ai/functions/marketing-and-content/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review), where welcome emails, banners and creator posts keep naming codes long after anyone remembers making them.
- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review), where every season, partner and apology adds another code to the store.
- [Consumer brands](https://fullypowered.ai/industries/consumer-brands/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review), where codes printed on packaging and handed to creators outlive the campaigns that made them.
- [Marketing and advertising](https://fullypowered.ai/industries/marketing-and-advertising/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review), where an agency tidies a client's codes before launching a campaign of its own.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review), where years of codes have piled up and nobody is sure which are safe to end.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review), when more channels and partners mean more codes than one person can hold in mind.

It sits beside [affiliate onboarding](https://fullypowered.ai/workflows/affiliate-onboarding/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review), which checks a new partner's code before it goes out, and [creator publication tracking](https://fullypowered.ai/workflows/creator-publication-tracking/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review), which checks the code in each published post. Setting up a new campaign is the [campaign build sheet](https://fullypowered.ai/workflows/campaign-build-sheet/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review), and a price below list for one customer is the [discount request review](https://fullypowered.ai/workflows/discount-request-review/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review).

## What has to change for your company

- **Your export,** with its column names renamed once to the defaults, and the status words your store uses.
- **Your numbers:** how many days without use make a code unused, and how new a code must be before it is judged. A store with weekly offers may want shorter windows than one that sells in seasons.
- **Your sources of campaign references:** the email tool, the ad accounts, site banners, partner and creator lists, printed inserts and customer service replies. A code a campaign names but nobody lists is the one that breaks.
- **Who approves,** and whether ending a code that any campaign has ever named needs a second person.
- **What clearing means for you:** archive or delete, and how long expired codes are kept for reporting.
- **Your AI product.** It runs in ChatGPT, Claude, Copilot or Gemini from the files you supply. It needs no connection to your store and changes no code.

## What has been checked

FullyPowered AI wrote this workflow template from its own published map of e-commerce and retail work. It was editorially reviewed on 11 November 2026. It was tried on its example on 11 November 2026 in Claude; the record is published with it, and lists the small edits made afterward that have not been run again. It has not yet been tested in a client environment, and has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a past export your e-commerce manager knows well, plus hard cases written in advance: an export with a renamed column, a code that ends on the campaign's last day, an unused code a scheduled campaign still needs, a campaign that names a code in different letter case, a code used often with no last-use date. The e-commerce manager checks every state and every date against the store before anyone approves a change. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review) sets those cases up, and [what we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review) describes the record we keep.

- Written by FullyPowered AI.
- Sources and rights reviewed.
- Editorially reviewed on 11 November 2026.
- Package format checked by script on every release.
- Tried once on its example in Claude on 11 November 2026. The record is in [TRIAL.md](TRIAL.md).
- Not yet tested in a client environment.

## What is in this folder

- [TEMPLATE.md](TEMPLATE.md): the complete workflow template. Roles, inputs, the procedure, exceptions and stop conditions, the output format, a reviewer checklist, acceptance tests, the instructions for an AI assistant and what to customize.
- [EXAMPLE.md](EXAMPLE.md): a worked example.
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

- [Affiliate onboarding](https://fullypowered.ai/workflows/affiliate-onboarding/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review)
- [Creator publication tracking](https://fullypowered.ai/workflows/creator-publication-tracking/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review)
- [Campaign build sheet](../campaign-build-sheet/)
- [Discount request review](https://fullypowered.ai/workflows/discount-request-review/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review)

## Make it yours

This workflow template is an example and a starting point. FullyPowered AI adapts it to how your company works, proves it on real work and rolls it out to the roles that use it. We can also build any other workflow for your company, including one that runs several steps, in a Workflow Sprint or a scoped implementation. [Talk with us](https://fullypowered.ai/contact/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-stale-promotion-code-review&from=gh-stale-promotion-code-review).
