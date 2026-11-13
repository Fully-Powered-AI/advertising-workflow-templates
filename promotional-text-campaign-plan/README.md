# Promotional text campaign plan

Before a promotional text campaign goes out, the marketing lead gets one plan: draft messages built only from the approved offer, the eligible audience as your own consent records define it, how often each person would be texted, the opt-out path and every open question. A person approves and sends.

*Workflow template · Advertising and lead generation · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/promotional-text-campaign-plan/)*

## The outcome

A text lands on someone's phone, so it has to earn its place. This plan makes sure every message does. The marketing lead sees, on one page, the messages as they would read, each with its character count and the offer facts it rests on; who can receive them under your own messaging policy, reconciled from the consent export; how many texts each person would get against your cap; and exactly what happens when someone replies STOP.

Nothing is left to a guess. A consent status the policy does not name, a number that appears on two records, a consent with no date or source, a contact who has already had their fill of texts this month: each one is held back and written up as a question for the person who can answer it. A missing status is never read as a yes, and nobody is added because someone asked.

The marketing lead and your designated policy reviewer approve the audience, the wording and the send plan. The workflow template sends nothing, schedules nothing, loads no list and changes no record, and it takes no view on what any law or carrier rule requires. Your policy and your advisers set those rules; the plan applies the ones you give it.

## Who starts the work, and when

The marketing lead, or a marketer for them, starts it when a promotional text campaign is being considered, once the offer is approved and before anything goes near the texting tool. The marketing coordinator, or whoever keeps the consent records, answers questions about records. The person your company names to own its messaging rules answers the policy questions. Run it again when the offer, the dates or the export change.

## What they supply

- **The campaign brief.** The offer in its approved wording, with dates, any code and the terms that must appear; the link; the audience segments; the purpose and proposed time of each message; the recipients' time zone; the date the consent export was taken.
- **Your text messaging policy.** The consent statuses that count as permitted and the countries you text, plus your send window, frequency cap, opt-out wording and keywords, the replies to STOP and HELP, who records opt-outs, and who sends. Where a setting is missing, the plan uses a stated default and asks about it.
- **The consent export,** one row per contact, with the number, country, segment, consent status, source and date, and how many promotional texts each received in the last 30 days.
- **The opt-out list** from your texting tool, if it is kept separately.

## What comes out

One plan in a fixed order: the plan in brief, the settings used and where each came from, the numbered offer facts, the draft messages with their send times and character counts, the audience reconciled from the export to eligible, excluded, held back and outside, the frequency check, the opt-out and help path, the open questions with who answers each, the decisions for the marketing lead, and what the plan could not judge. Phone numbers appear only by their last four digits. It ends with two blank approval lines, one for the marketing lead and one for the policy reviewer.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Advertising and lead generation](https://fullypowered.ai/functions/advertising-and-lead-generation/), where a text campaign joins the paid and email plans for an offer.
- [Marketing and content](https://fullypowered.ai/functions/marketing-and-content/), where the team that writes the offer wants every short message to say only what is true.
- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/), where a sale weekend or a restock is worth a text to customers who asked for them.
- [Consumer brands](https://fullypowered.ai/industries/consumer-brands/), where loyalty members and online buyers sit in one list with different consent histories.
- [Hospitality](https://fullypowered.ai/industries/hospitality/), where a quiet midweek night or a seasonal menu is announced to guests who signed up for offers.
- [Marketing and advertising](https://fullypowered.ai/industries/marketing-and-advertising/), where an agency plans a client's text campaign and the client approves it.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/), when texting starts to matter and nobody has written the rules down yet.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/), when years of sign-up forms have left consent records in several shapes.

It does not write emails ([email sequence drafting](https://fullypowered.ai/workflows/email-sequence-drafting/)), check an email audience record by record ([campaign audience check](https://fullypowered.ai/workflows/campaign-audience-check/)) or choose which lapsed customers to win back ([lapsed-customer win-back](https://fullypowered.ai/workflows/lapsed-customer-win-back/)). It starts with an approved offer and ends with a plan ready for approval.

## What has to change for your company

Write your text messaging policy down if it is not already: which consent statuses permit promotional texts, which exclude a person, which countries you text, your send window and cap, your opt-out and help wording, who records opt-outs and who sends. Your policy reviewer and your own advisers set those rules; the workflow template only applies them. Map the columns your texting or customer tool exports to the defaults once. Decide which offer terms must appear in every message, who approves, and who presses send.

## What has been checked

Fully Powered AI wrote this workflow template. It was editorially reviewed on 11 November 2026. It was tried on its invented example on 11 November 2026 in Claude; the record is published with it. It has not yet been tested in a client environment. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a past text campaign whose problems you already know: a status your policy does not name, a number on two records, a contact who opted out but still shows as subscribed, a send time after your window closes. The person who keeps the consent records recomputes every count before the plan is relied on. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/) builds that test set, and [What we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/) shows the record.

- Written by Fully Powered AI.
- Sources and rights reviewed.
- Editorially reviewed on 11 November 2026.
- Package format checked by script on every release.
- Tried once on its invented example in Claude on 11 November 2026. The record is in [TRIAL.md](TRIAL.md).
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

- [Campaign audience check](../campaign-audience-check/)
- [Email sequence drafting](https://fullypowered.ai/workflows/email-sequence-drafting/)
- [Lapsed-customer win-back](https://fullypowered.ai/workflows/lapsed-customer-win-back/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
