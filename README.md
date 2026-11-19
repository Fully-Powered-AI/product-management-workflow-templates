# AI workflow templates for product managers and product owners

FullyPowered Workflow Templates for product management teams turn the AI your company already pays for into a team that knows how the work is done: a product owner with the release notes drafted in words users recognize, a developer with the acceptance criteria written down before the work starts, a founder with the first release scoped to one user outcome. 6 workflow templates, made to be customized and deployed. All plain Markdown, all free, MIT license.

We are FullyPowered AI. We build AI workflows for companies, and these are the templates we start from. We publish them because a good starting point should be open to everyone. Copy one. Change it. Make it yours.

> [!TIP]
> **Missing a template that is not listed here, or want these customized for your organization? Reach out to us.** These are templates, made to be customized and deployed. FullyPowered AI customizes and builds AI workflows, connects them to your business systems, installs them in your agents and puts them in the hands of the people who own the work. [See more examples for product management teams](https://fullypowered.ai/functions/product-management/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-readme&from=gh-product-management-readme) · [Have one built for your team](https://fullypowered.ai/pricing/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-readme&from=gh-product-management-readme). Not sure where to start? Email hello@fullypowered.ai and a person will answer.

**Who this is for**

- Founders and heads of product who want their roadmap decisions laid out clearly before they decide.
- Product leads who want a careful way for their team to prepare every release.
- The product owner who does the work, gets a precise way to prepare it and still decides.

**What these are for**

- **Your best way of doing it, for the whole team.** One piece of work, written down precisely enough that an assistant prepares it the same way every time.
- **Work you can check.** Every template says what it needs, what it produces, what it checked and what it could not.
- **A person decides.** Anything that sends, posts, pays or changes a record waits for someone to approve it.
- **Tied into your business systems.** A workflow can be designed to pull from the systems your company already runs, and even push data back into them, with guardrails and a person approving. [Browse the Connectors Directory](https://fullypowered.ai/connectors/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-readme&from=gh-product-management-readme).
- **Free, open and portable.** MIT-licensed plain instructions that run in the assistant or agent your team already uses: ChatGPT, Claude, Claude Code, Claude Cowork, Codex, Copilot, Gemini, Grok, Perplexity.

**Quick start**

1. **Draft release notes from your own list of changes.** Open ChatGPT, Claude, Copilot or Gemini. Copy the text below into it, replace the square brackets with your own details, and send it. You need only a list of what shipped.

   ```text
   You prepare draft release notes for a product owner. Use only what I
   supply. Never invent a change, a benefit or a date, and never say
   anything is faster, safer or better unless I gave evidence. Include only
   items that have shipped. Hold out anything planned, partly built or
   behind a switch, and say why. Write these sections: what users must do,
   what is new, what changed, what was removed, what was fixed, known
   limitations, where to get help, items held out, and questions for me.
   Describe each item in my wording. Mark the draft as not approved.
   Nothing is sent or published; I check it and decide.

   Product and release: [name, version, date shipped]
   Readers: [who will read the notes]
   Where users get help: [route]
   Items: [one line each: what changed for users, who is affected, whether
   they must act, shipped or not]
   Known issues: [one line each, with any workaround]
   ```

2. Read what comes back. It marks what it checked and what is left for you. What comes out, with invented data:

   ```text
   RELEASE NOTES DRAFT: Fennel Rota 4.2

   Prepared 10 November 2026 for the product owner. Readers: shop and cafe managers who build rotas, and staff who read them. Shipped 9 November 2026. Status: DRAFT, not approved. Blockers: none.
   In this release: 1 new, 1 changed, 1 removed, 1 fixed; 2 of these need action from the user. Known limitations: 2.
   Item codes in square brackets are for the checker. Delete them before publishing. Sections 1 to 7 are the notes; sections 8 to 11 are for the product owner only.

   1. WHAT YOU NEED TO DO
   Rota download [R2]. Who: Managers. Where: Rota page: Download menu. Steps: 1. Open any saved spreadsheet that reads the rota download. 2. Change the column name it looks for from Name to Staff member.
   Version 1 import template [R3]. Who: Managers. Where: Rota page: Import, then Download template. Steps: 1. In Import, choose Download template. 2. Copy your staff and shifts into the new file. 3. Import it.

   2. WHAT IS NEW
   Shift swaps [R1]. Staff can offer one of their shifts to a named colleague. The colleague accepts or declines, and the manager approves the swap before the rota changes. Who: Managers and staff. Where: My Rota: open a shift and choose Offer shift.
   ```

3. Stop there. You will know if this is for you. When you want it fitted to your company, or built into your agents, [that is what we do](https://fullypowered.ai/pricing/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-readme&from=gh-product-management-readme).

In every workflow the product owner starts the work, supplies the inputs and makes the decision, and the template only prepares and checks.

These are samples and a starting point, made to be customized to how your team works. Work that is not listed here can be built too, as one step or as many.

## The workflow templates here today

- **[Acceptance criteria sheet](acceptance-criteria-sheet/)**: Hand a developer or agency a story with its definition of done written down: testable expected behaviours, error cases and edge cases, each traced to a rule or design state, with the unclear terms and open questions listed for the product owner.
- **[Assumption map](assumption-map/)**: For a product owner whose plan rests on beliefs nobody has tested: each belief is written down, set against the evidence you hold, ranked by what it would do to the plan, and given a cheap test to choose from. You decide what to test; no evidence is invented.
- **[Product pricing options](product-pricing-options/)**: A product owner weighing how to price or package a product gets one options brief: what each customer group uses, the willingness-to-pay evidence held with stated kept apart from observed, what each option would bill every account, the uncertainties and the tests. It recommends no price.
- **[Release notes draft](release-notes-draft/)**: The product owner gets draft release notes for one shipped release, in words users recognize: what is new, changed, removed and fixed, the steps users must take, and the known limitations. Only what was supplied is described. The owner checks and publishes.
- **[Roadmap tradeoff review](roadmap-tradeoff-review/)**: When a new priority arrives, the product owner sees what the roadmap would have to give up to hold it: the capacity gap by team, the work that could move, the commitments and dependencies that move with it, and the questions still open. The owner decides.
- **[Smallest useful release scope](smallest-useful-release-scope/)**: A product owner or founder with more features than capacity gets one page: what is in the first release and what is deferred, all tied to one user outcome, with the reason for each cut. The owner decides the scope; no effort is estimated beyond what is supplied.

## How to use one

Open a folder and start with its README. Every folder stands alone, so copy the one you want and leave the rest. The templates are written for ChatGPT, Claude, Copilot and Gemini: paste the instruction block and the output format in as custom instructions, or load the folder in a product that reads `SKILL.md` packages.

To take the whole collection, press **Use this template** at the top of this page: it copies every folder into a repository in your own account, yours to change.

In every template a person starts the work, supplies the inputs and decides. The template prepares and checks. Anything that sends, posts, pays or changes a record waits for a person to approve it.

## What SKILL.md is

Each folder holds a file named `SKILL.md`. It is the technical file: the same instructions and output format as the template, in the packaged form that AI products which load instructions from a folder read. It is generated from `TEMPLATE.md`, so the two always agree. The workflow template is the whole folder; `SKILL.md` is one way of loading it. If your AI product does not read that format, use `TEMPLATE.md`.

## What "checked" means here

Each folder says exactly what was checked and when: who wrote it, that its sources and rights were reviewed, the date of its editorial review, and whether it has been tried on its invented example in a named AI product. Nothing is described as tested for a client unless it was. Test a template on your own past work before your team relies on it; each one comes with acceptance tests for that.

## More workflow templates

The [FullyPowered Workflows Directory](https://fullypowered.ai/workflows/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-readme&from=gh-product-management-readme) lists every workflow template across functions and industries, with search. A machine-readable list of this repository is in [index.json](index.json).

For the work these templates come from, by team and by task, see [AI workflow examples for product managers](https://fullypowered.ai/functions/product-management/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-readme&from=gh-product-management-readme).

## Licence and credits

MIT, in [LICENSE](LICENSE) and in every folder. Each folder's SOURCES.md names what the workflow template drew on. Published by [FullyPowered AI](https://fullypowered.ai/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-readme&from=gh-product-management-readme).
