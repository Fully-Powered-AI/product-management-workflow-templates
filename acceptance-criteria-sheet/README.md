# Acceptance criteria sheet

A story handed over with its definition of done: testable behaviours, error and edge cases, and open questions. The product owner confirms every line.

> [!TIP]
> **Missing a template that is not listed here, or want these customized for your organization? Reach out to us.** This is a template, made to be customized and deployed. FullyPowered AI customizes and builds AI workflows, connects them to your business systems, installs them in your agents and puts them in the hands of the people who own the work. [See Acceptance criteria sheet on our website](https://fullypowered.ai/workflows/acceptance-criteria-sheet/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-acceptance-criteria-sheet&from=gh-acceptance-criteria-sheet). Not sure where to start? Email hello@fullypowered.ai and a person will answer.

**Quick start**

1. Read EXAMPLE.md to see what a good result looks like.
2. Copy all of TEMPLATE.md into your assistant, then give it your own inputs, or the invented ones from EXAMPLE.md.
3. Read what comes back. It marks what it checked and what is left for you.

*Workflow template · Product management · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/acceptance-criteria-sheet/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-acceptance-criteria-sheet&from=gh-acceptance-criteria-sheet)*

## The outcome

The people building a feature and the people checking it work from the same sheet. Each line says what the user does, what must happen, and how anyone can see that it did. Where the story is vague, the sheet says so and asks the question, instead of leaving the builder to guess and the owner to find out at review.

The product owner confirms every line. Nothing on the sheet counts as agreed until the owner, engineering and whoever checks the work have said so.

## Who starts the work, and when

The product owner starts it when a story is ready for refinement, or just before it is handed to a developer or an agency. Engineering and the person who will check the finished work read the draft and answer its open questions.

## What they supply

- The story: who wants what, and why.
- The business rules that apply, numbered, in the owner's words.
- The design states: the screens or steps the user will see, including messages the design already words.
- The known failure conditions: what is known to go wrong, or to be unavailable.

## What comes out

One sheet per story, in a fixed order: expected behaviours, error cases, edge cases, words that need a number, conflicts between the inputs, a coverage line showing which rule or state each criterion answers, and the questions only the owner can settle. A criterion that waits on an answer is marked as blocked, so nobody builds to a guess. It ends with a confirmation block left blank for the owner, engineering and the test owner.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Product management](https://fullypowered.ai/functions/product-management/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-acceptance-criteria-sheet&from=gh-acceptance-criteria-sheet), where a story is only as clear as the definition of done beside it.
- [Software & technology](https://fullypowered.ai/industries/software-technology/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-acceptance-criteria-sheet&from=gh-acceptance-criteria-sheet), for teams handing stories to engineers or an outside studio.
- [E-commerce & retail](https://fullypowered.ai/industries/ecommerce-and-retail/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-acceptance-criteria-sheet&from=gh-acceptance-criteria-sheet), where checkout, pricing and fulfilment rules produce many edge cases.
- [Hardware & physical technology](https://fullypowered.ai/industries/hardware-and-physical-technology/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-acceptance-criteria-sheet&from=gh-acceptance-criteria-sheet), for companion apps and device settings with states that must be pinned down.
- [Startups & new ventures](https://fullypowered.ai/situations/startups-and-new-ventures/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-acceptance-criteria-sheet&from=gh-acceptance-criteria-sheet), where a founder is the product owner and the developer is a contractor.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-acceptance-criteria-sheet&from=gh-acceptance-criteria-sheet), when more people touch each story and unwritten assumptions start to cost time.

This is different from [pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-acceptance-criteria-sheet&from=gh-acceptance-criteria-sheet), which readies a decision on an operations pilot, and from [project handover readiness check](https://fullypowered.ai/workflows/project-handover-readiness-check/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-acceptance-criteria-sheet&from=gh-acceptance-criteria-sheet), which checks a finished project before it changes hands. This one defines done for a single story before it is built.

## What has to change for your company

Decide how your stories are written and how criteria are numbered. List the vague words your team has argued about, and add them to the default list. Decide the largest number of criteria one story should carry before it is split. Agree who counts as engineering and test owner on each team, and where the confirmed sheet is kept. If your design tool words error messages, say whether the sheet quotes them or points to them.

## What has been checked

FullyPowered AI wrote this workflow template. It was editorially reviewed on 10 November 2026. It was tried on its invented example in Claude on 10 November 2026; the record is published with it. The points that run found open were settled the same day, after an independent review, without a rerun; the record lists them and says where the recorded output differs from the template as it now stands. It has not yet been tested in a client environment. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on stories your team has already built and shipped, then comparing the sheet with the defects and rework that followed. The product owner reads every line before anyone builds from it. The sheet writes no code and no test scripts, and it decides nothing.

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

- [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-acceptance-criteria-sheet&from=gh-acceptance-criteria-sheet)
- [Project handover readiness check](https://fullypowered.ai/workflows/project-handover-readiness-check/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-acceptance-criteria-sheet&from=gh-acceptance-criteria-sheet)
- [Scope change impact review](https://fullypowered.ai/workflows/scope-change-impact-review/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-acceptance-criteria-sheet&from=gh-acceptance-criteria-sheet)

## Make it yours

This workflow template is an example and a starting point. FullyPowered AI adapts it to how your company works, proves it on real work and rolls it out to the roles that use it. We can also build any other workflow for your company, including one that runs several steps, in a Workflow Sprint or a scoped implementation. [Talk with us](https://fullypowered.ai/contact/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=product-management-acceptance-criteria-sheet&from=gh-acceptance-criteria-sheet).
