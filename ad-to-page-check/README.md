# Ad to page check

When a campaign's landing page is ready for a prelaunch check, the acquisition owner gets a findings list that sets each ad beside the captured page: message, offer details, form and next step, on mobile and desktop. Page states nobody captured are marked unknown.

*Capability template · Advertising and lead generation · version 0.1.0 · [Capabilities Directory](https://fullypowered.ai/capabilities/ad-to-page-check/)*

## The outcome

A visitor clicks an ad, lands on a page and either finds what the ad promised or does not. This capability template puts the ad and the page side by side before the campaign goes live, so the acquisition owner sees the gaps while they are still cheap to close.

For every ad, the check compares four things on the page as captured: whether the page is about what the ad is about, whether each offer detail matches your approved offer terms, how much the form asks of the visitor, and whether the next step the ad names is the next step the page offers. It does this separately for the desktop and mobile captures.

Each difference is a numbered finding that quotes the ad and the page. Anything nobody captured, such as the form's error state or the confirmation page, is marked unknown and never assumed fine. The acquisition owner decides which findings must be fixed before launch. The check changes no page, predicts no conversion and does not judge whether a claim is allowed.

## Who starts the work, and when

The acquisition owner, or whoever signs off a campaign for your company or a client, starts it when the ads are written and the destination page is built and captured, before the campaign is switched on. Run it again after the page changes or a term moves.

The page owner answers for the page and supplies the capture. Whoever owns the offer confirms the approved terms.

## What they supply

- **Check settings:** the campaign, the conversion goal, who it is prepared for, who owns the page, the launch date, the page states that must be captured and, if you want one, a limit on form fields.
- **The ad copy,** one row per ad: headline, body, call to action, destination and the offer details the ad states.
- **The approved offer terms:** each offer item, its approved value, any conditions and the date the term ends.
- **The page capture,** one row per element on the page, for each state: desktop, mobile and, where you have them, the form's error state and the confirmation after submitting.

Nothing is opened or connected. The capability never asks for a password, a login code or a key.

## What comes out

One findings list in a fixed order. It opens with which page states were captured, then shows a block for each ad with its message, offer, form and next-step results for desktop and mobile, then numbers every finding. Each finding says where it is, what the ad says, what the page shows, what would settle it and who can supply that. A closing count shows how many findings fall under each heading, and a line lists what the check did not look at.

Every finding carries an open decision line for the acquisition owner: fix before launch, or accept.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Advertising and lead generation](https://fullypowered.ai/functions/advertising-and-lead-generation/), where the last check before spend starts is whether the page keeps the ad's promise.
- [Marketing and content](https://fullypowered.ai/functions/marketing-and-content/), where the ad copy and the page are often written by different people.
- [Design and user experience](https://fullypowered.ai/functions/design-and-user-experience/), where the mobile and desktop views of the same page have to agree.
- [Marketing and advertising](https://fullypowered.ai/industries/marketing-and-advertising/), where an agency checks pages it did not build.
- [Ecommerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/), where prices, delivery terms and end dates change often.
- [Software and technology](https://fullypowered.ai/industries/software-technology/), where trial and sign-up pages carry the offer.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/), when campaigns multiply faster than anyone can click through each one.

It does not set the campaign up ([campaign build sheet](https://fullypowered.ai/capabilities/campaign-build-sheet/)), review each form field's purpose ([lead form field review](https://fullypowered.ai/capabilities/lead-form-field-review/)) or tie each claim to its evidence ([campaign claim evidence register](https://fullypowered.ai/capabilities/campaign-claim-evidence-register/)). It compares the ad with the page and stops there. It is also not the audit of a campaign taken over from someone else ([inherited campaign audit](https://fullypowered.ai/capabilities/inherited-campaign-audit/)); this check comes before launch, on ads and a page you are about to switch on.

## What has to change for your company

- **Your page states.** List the states you can capture: desktop and mobile at least, and the form's error state and confirmation if the page has them.
- **Your offer items.** Name the offer details you advertise, such as price, delivery, trial length and cancellation, with the wording of each approved value.
- **Your form limit.** Set a number of fields if you have a house rule, or leave it blank.
- **Your owners.** Decide who owns the page, who confirms the offer terms and who decides at launch.
- **Your files.** Use the column names your tools export, or rename them once to the defaults. When a header does not match, the assistant stops and asks.

## What has been checked

Fully Powered AI wrote this capability template. It was editorially reviewed on 10 November 2026. It was tried once on its invented example, in Claude on 10 November 2026, and the record is published with it. It has not been tested in a client environment or as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a campaign whose page you already know, with cases written in advance: a price that differs between ad and page, a delivery term that ends before launch, a mobile view that drops an offer, a form with more fields than your limit, a state nobody captured. The acquisition owner checks every finding against the live page before relying on it. [Pilot acceptance-test preparation](https://fullypowered.ai/capabilities/pilot-acceptance-test-preparation/) sets those cases up, and [what we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/) describes the record we keep.

- Written by Fully Powered AI.
- Sources and rights reviewed.
- Editorially reviewed on 10 November 2026.
- Package format checked by script on every release.
- Tried once on its invented example in Claude on 10 November 2026. The record is in [TRIAL.md](TRIAL.md).
- Not yet tested in a client environment.

## What is in this folder

- [TEMPLATE.md](TEMPLATE.md): the complete capability template. Roles, inputs, the procedure, exceptions and stop conditions, the output format, a reviewer checklist, acceptance tests, the instructions for an AI assistant and what to customize.
- [EXAMPLE.md](EXAMPLE.md): a worked example with invented data.
- [TRIAL.md](TRIAL.md): what came out when the template was tried on its example.
- [SKILL.md](SKILL.md): the technical file, for AI products that load packaged instructions from a folder.
- [SOURCES.md](SOURCES.md): what the capability drew on, with licences.
- [LICENSE](LICENSE): MIT. Use it, change it, make it yours.

## Start using it

1. Read [EXAMPLE.md](EXAMPLE.md) to see what a good result looks like.
2. Open [TEMPLATE.md](TEMPLATE.md) and set every item under "What to customize" to your own rules, roles and limits.
3. Give your AI assistant the instruction block and the output format from the template, with your own limits in place of the ones the instructions leave open in square brackets. Paste them in as custom instructions in ChatGPT, Claude, Copilot or Gemini, or copy this whole folder into a product that loads `SKILL.md` packages. This folder stands alone; you do not need the rest of the repository.
4. Run it on past work first, using the reviewer checklist and acceptance tests in the template, before anyone relies on it.

## Related capabilities

- [Campaign build sheet](../campaign-build-sheet/)
- [Lead form field review](https://fullypowered.ai/capabilities/lead-form-field-review/)
- [Campaign claim evidence register](https://fullypowered.ai/capabilities/campaign-claim-evidence-register/)

## Make it yours

This is the starting version. Fully Powered AI adapts capabilities to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
