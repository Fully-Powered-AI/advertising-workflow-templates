# Search exclusion conflict check

The paid search specialist gets a list of live keywords that a live exclusion may be blocking, each with the level where the exclusion applies and the campaign intent it touches. They are clues from the text; the specialist decides what to change.

*Capability template · Advertising and lead generation · version 0.1.0 · [Capabilities Directory](https://fullypowered.ai/capabilities/search-exclusion-conflict-check/)*

## The outcome

Exclusion lists grow for years, written by different people for different reasons, at the account, in shared lists, on campaigns and on single ad groups. Somewhere in them is a word that was added to keep out one kind of search and now sits across a keyword someone is paying to win. Nobody finds it by reading the lists, because the keyword and the exclusion are in different files.

This sets the two side by side. For every live keyword it asks whether any live exclusion that reaches that keyword shares its words, and it lists each match with the level the exclusion applies at, the reason the exclusion was added if anyone wrote one down, and what the campaign is meant to capture.

The list is a set of clues. Matching text is not proof that a single search was lost, and an exclusion that is blocking something on purpose stays in place unless the specialist says otherwise. The specialist checks each clue against the account's own records and decides whether any exclusion should change.

## Who starts the work, and when

The paid search specialist starts it: on taking over an account, around a round of new exclusions, when a campaign's impressions fall for no clear reason, or regularly where the lists are long. The account owner is told what the specialist decides.

The template edits no list, connects to no account and spends nothing. Every change to a list is made by a person in the platform.

## What they supply

- **The keywords,** one row each: campaign, ad group, keyword, match type and status.
- **The exclusions,** one row each: the level (account, shared list, campaign or ad group), where it applies, the words, the match type, the status and, if known, why it was added.
- **The campaigns:** each one's status and, in the specialist's own words, what it is meant to capture.
- **Which shared lists are attached to which campaigns,** when shared lists are used.
- **A few settings:** the account name, the as-of date and who decides.

The files are exports or copies the specialist makes. No connection to an ad account is needed and no sign-in details are asked for.

## What comes out

One document in a fixed order: the answer with counts, the numbered conflicts, the rows that were not compared, and the coverage. Each conflict names the keyword, the exclusion, the level it applies at, the reason given for it, the campaign intent and the one thing worth checking. A "direct" conflict is about the keyword's own wording sitting under the exclusion's words; the keyword may still serve other searches. Direct conflicts come first; narrow ones, where only the identical search would be blocked, follow.

Good looks like this: the specialist can open any conflict, see which two rows it rests on, and know within a minute what to look for in the account's own search records.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Advertising and lead generation](https://fullypowered.ai/functions/advertising-and-lead-generation/), where keyword and exclusion lists are maintained by several hands.
- [Marketing and advertising](https://fullypowered.ai/industries/marketing-and-advertising/), where agencies inherit long lists and inherit the reasons for them too.
- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/), where exclusions added for a sale, a stock gap or a retired range outlive the reason.
- [Consumer brands](https://fullypowered.ai/industries/consumer-brands/), where several people add exclusions to protect the brand and the brand's own searches can end up in the way.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/), when the account has outgrown anyone's memory of why each exclusion exists.

It is not a campaign report ([client campaign performance report](https://fullypowered.ai/capabilities/client-campaign-performance-report/)) and it is not a review of an inherited account ([inherited campaign audit](https://fullypowered.ai/capabilities/inherited-campaign-audit/)). It reads no results and judges no performance.

## What has to change for your company

- **Your column names.** The assistant reads the files by the default headers in the template; map yours to them, or reshape the export once. When a header does not match, it stops and asks.
- **Your levels.** The template knows four: account, shared list, campaign and ad group. Add or drop one if your platform differs.
- **Your intent wording.** Write, for each campaign, what it is meant to capture. The template quotes your words and does not judge them.
- **Your reasons.** Ask the people who add exclusions to record why. A reason in the file lets the specialist see at once which conflicts are deliberate.
- **Who decides,** and how an agreed change is made and recorded.
- **Your platform.** It is written for ChatGPT, Claude, Copilot or Gemini and works from files you supply. Decide which exports the assistant may read.

## What has been checked

Fully Powered AI wrote this capability template. It was editorially reviewed on 10 November 2026. It was tried once on its invented example, in Claude on 10 November 2026, on an earlier wording of the instructions; the record is published beside it. The wording has since been clarified and has not been run again. It has not yet been tested in a client environment. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on an account your specialist knows well, with cases written in advance: an exclusion added on purpose that sits across a keyword, a shared list attached to only one campaign, a paused exclusion, a keyword in a paused campaign, a header that does not match. The specialist checks every conflict against the account's own records before anyone relies on it. [Pilot acceptance-test preparation](https://fullypowered.ai/capabilities/pilot-acceptance-test-preparation/) sets those cases up, and [what we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/) describes the record we keep.

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

- [Inherited campaign audit](https://fullypowered.ai/capabilities/inherited-campaign-audit/)
- [Client campaign performance report](https://fullypowered.ai/capabilities/client-campaign-performance-report/)
- [Campaign claim evidence register](https://fullypowered.ai/capabilities/campaign-claim-evidence-register/)

## Make it yours

This is the starting version. Fully Powered AI adapts capabilities to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
