# AI workflow templates for advertising and lead generation

FullyPowered Workflow Templates for paid advertising and lead generation teams turn the AI your company already pays for into a team that knows how the work is done: a paid media lead with the creative fatigue review laid out by creative and audience, a campaign operator with the approved brief turned into one build sheet, a marketing manager with the stale discount codes reviewed before the next campaign. 8 workflow templates, made to be customized and deployed. All plain Markdown, all free, MIT license.

We are FullyPowered AI. We build AI workflows for companies, and these are the templates we start from. We publish them because a good starting point should be open to everyone. Copy one. Change it. Make it yours.

> [!TIP]
> **Missing a template that is not listed here, or want these customized for your organization? Reach out to us.** These are templates, made to be customized and deployed. FullyPowered AI customizes and builds AI workflows, connects them to your business systems, installs them in your agents and puts them in the hands of the people who own the work. [See more examples for paid advertising and lead generation teams](https://fullypowered.ai/functions/advertising-and-lead-generation/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-readme&from=gh-advertising-readme) · [Have one built for your team](https://fullypowered.ai/pricing/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-readme&from=gh-advertising-readme). Not sure where to start? Email hello@fullypowered.ai and a person will answer.

**Who this is for**

- Owners and CEOs who pay for advertising and want every campaign launched carefully and checked the same way.
- Heads of acquisition and marketing who want their team to run a precise campaign check this week.
- The campaign operator or paid search specialist, who gets a clear findings list and still decides what changes.

**What these are for**

- **Your best way of doing it, for the whole team.** One piece of work, written down precisely enough that an assistant prepares it the same way every time.
- **Work you can check.** Every template says what it needs, what it produces, what it checked and what it could not.
- **A person decides.** Anything that sends, posts, pays or changes a record waits for someone to approve it.
- **Tied into your business systems.** A workflow can be designed to pull from the systems your company already runs, and even push data back into them, with guardrails and a person approving. [Browse the Connectors Directory](https://fullypowered.ai/connectors/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-readme&from=gh-advertising-readme).
- **Free, open and portable.** MIT-licensed plain instructions that run in the assistant or agent your team already uses: ChatGPT, Claude, Claude Code, Claude Cowork, Codex, Copilot, Gemini, Grok, Perplexity.

**Quick start**

1. **Check your search exclusions in a few minutes.** Open ChatGPT, Claude, Copilot or Gemini. Copy the text below into a new chat, then paste in your keyword list, your exclusion list and one line on what each campaign is for. Use a copy of your lists, not a login.

   ```text
   You are preparing a search exclusion conflict check for a paid search
   specialist. I will paste my live keywords (campaign, ad group, keyword,
   match type, status), my exclusions (level, campaign, exclusion, match
   type, status, and the reason it was added if known) and one line on what
   each campaign is meant to capture. Compare only enabled rows, whole
   words only, with no plurals or close variants. List each keyword that an
   exclusion reaches and shares words with. For each one show the keyword,
   the exclusion, where the exclusion applies, the reason given or "not
   stated", the campaign's purpose, and what I should check. Call every
   result a clue from text, not proof that a search was blocked. Ask me if
   a column is unclear. Change nothing and recommend no change. I decide
   what happens next.
   ```

2. Read what comes back. It marks what it checked and what is left for you. What comes back, for a dog-bed shop:

   ```text
   **THE ANSWER**

   9 live keywords and 8 live exclusions compared. 5 conflicts: 4 direct, 1 narrow. By level: account 1, shared list 1, campaign 2, ad group 1. 5 keywords have a conflict; 4 do not. Every conflict is a clue from the text. None shows that a search was blocked, and no change is proposed.

   **CONFLICTS**

   C1 Direct. Keyword "client r dog beds" (phrase), campaign Brand, ad group Shop name (keywords row 2).
     Exclusion "dog" (broad), level: campaign Brand (negatives row 8).
     Purpose as supplied: not stated
     Campaign intent as supplied: People searching for the shop by name
     Why flagged: the exclusion's one word, "dog", is a word of the keyword.
     To check: whether searches matching this keyword are being blocked by this exclusion, in the account's own search records.
   ```

3. Stop there. You will know if this is for you. When you want it fitted to your company, or built into your agents, [that is what we do](https://fullypowered.ai/pricing/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-readme&from=gh-advertising-readme).

In every workflow a person starts the work, supplies the files and decides what to do, while the template only prepares and checks, so nothing is sent, spent, launched or changed for you.

These are samples to customize for your own accounts, rules and files, and they are not a complete list of what can be done. A workflow can be a single check or many steps, and we can build any workflow for a company, around what that company does.

## The workflow templates here today

- **[Ad to page check](ad-to-page-check/)**: When a campaign's landing page is ready for a prelaunch check, the acquisition owner gets a findings list that sets each ad beside the captured page: message, offer details, form and next step, on mobile and desktop. Page states nobody captured are marked unknown.
- **[Campaign audience check](campaign-audience-check/)**: When an audience export is ready for review, the campaign owner gets it segmented with reconciled counts, the exclusions applied and the records whose contact status needs checking, with conflicts, stale records and duplicates kept visible.
- **[Campaign build sheet](campaign-build-sheet/)**: When an approved campaign brief is ready to become a setup specification, the campaign operator gets one build sheet: names, audiences, exclusions, destinations, budgets and measurement fields, with every unresolved setting and missing asset marked as a gap. Nothing is built or spent.
- **[Creative fatigue review](creative-fatigue-review/)**: When a campaign's reach or response pattern prompts a creative review, the paid media lead gets frequency and response set against the campaign's own baseline, by creative and audience, with other explanations marked and options to test.
- **[Lead quality pattern review](lead-quality-pattern-review/)**: When sales feedback or results raise a lead-quality concern, the acquisition lead gets a review of leads and their outcomes by source, page, location, device and timing, with cases to verify with sales and possible measurement faults listed.
- **[Promotional text campaign plan](promotional-text-campaign-plan/)**: Before a promotional text campaign goes out, the marketing lead gets one plan: draft messages built only from the approved offer, the eligible audience as your own consent records define it, how often each person would be texted, the opt-out path and every open question. A person approves and sends.
- **[Search exclusion conflict check](search-exclusion-conflict-check/)**: The paid search specialist gets a list of live keywords that a live exclusion may be blocking, each with the level where the exclusion applies and the campaign intent it touches. They are clues from the text; the specialist decides what to change.
- **[Stale promotion code review](stale-promotion-code-review/)**: Before the next campaign, the marketing or e-commerce manager gets one review of the store's discount codes: every expired, unused or duplicate code, the live and scheduled campaigns that still name each one, and a proposed action for a person to approve. It ends, deletes and changes nothing.

## How to use one

Open a folder and start with its README. Every folder stands alone, so copy the one you want and leave the rest. The templates are written for ChatGPT, Claude, Copilot and Gemini: paste the instruction block and the output format in as custom instructions, or load the folder in a product that reads `SKILL.md` packages.

To take the whole collection, press **Use this template** at the top of this page: it copies every folder into a repository in your own account, yours to change.

In every template a person starts the work, supplies the inputs and decides. The template prepares and checks. Anything that sends, posts, pays or changes a record waits for a person to approve it.

## What SKILL.md is

Each folder holds a file named `SKILL.md`. It is the technical file: the same instructions and output format as the template, in the packaged form that AI products which load instructions from a folder read. It is generated from `TEMPLATE.md`, so the two always agree. The workflow template is the whole folder; `SKILL.md` is one way of loading it. If your AI product does not read that format, use `TEMPLATE.md`.

## What "checked" means here

Each folder says exactly what was checked and when: who wrote it, that its sources and rights were reviewed, the date of its editorial review, and whether it has been tried on its example in a named AI product. Nothing is described as tested for a client unless it was. Test a template on your own past work before your team relies on it; each one comes with acceptance tests for that.

## More workflow templates

The [FullyPowered Workflows Directory](https://fullypowered.ai/workflows/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-readme&from=gh-advertising-readme) lists every workflow template across functions and industries, with search. A machine-readable list of this repository is in [index.json](index.json).

For the work these templates come from, by team and by task, see [AI workflow examples for advertising and lead generation teams](https://fullypowered.ai/functions/advertising-and-lead-generation/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-readme&from=gh-advertising-readme).

## Licence and credits

MIT, in [LICENSE](LICENSE) and in every folder. Each folder's SOURCES.md names what the workflow template drew on. Published by [FullyPowered AI](https://fullypowered.ai/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=advertising-readme&from=gh-advertising-readme).
