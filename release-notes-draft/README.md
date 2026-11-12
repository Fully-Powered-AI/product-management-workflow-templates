# Release notes draft

The product owner gets draft release notes for one shipped release, in words users recognize: what is new, changed, removed and fixed, the steps users must take, and the known limitations. Only what was supplied is described. The owner checks and publishes.

*Workflow template · Product management · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/release-notes-draft/)*

## The outcome

A release lands, and the people who use the product need to know what is different on their screen today. This workflow template turns the sheet of what shipped, the known issues and the glossary into one page written for the reader of the notes, not for the team that built the release.

Each entry says what the user will notice, who it affects and where to find it. Anything a user has to do, such as moving to a new file format or renaming a column in a spreadsheet, comes first, with the steps in order. Known limitations are stated plainly beside the feature they touch. Work that is planned, switched off for most users or invisible to users is left out, and the draft lists it, with the reason, so the owner can see what was not said.

The product owner confirms that every entry is accurate, answers the questions the draft raises, and publishes. The assistant publishes nothing.

## Who starts the work, and when

The product owner starts it once the scope of a release is confirmed and the notes are due, usually on the day it ships or just before. Engineering fills in the rows of the items sheet and confirms the steps users must take. Support reads the draft for the limitations and for the help route it names.

## What they supply

- A short release brief: the product, the release name or number, the ship date, who reads the notes, and where users get help.
- A sheet of release items, one row each, with what changed for users, who is affected, where to find it, whether the user must act and the steps, the status, and the evidence for any claim about speed or security.
- A sheet of known issues, with the workaround for each.
- A short glossary of the internal names the team uses and the words users see instead.
- The date the draft is prepared.

## What comes out

One draft in a fixed order. The notes for readers come first: what you need to do, what is new, what has changed, what has been removed, what has been fixed, known limitations, and where to get help. After them come the pages for the owner only: what was held out and why, checks on the inputs, numbered questions, and approval lines. When a section has nothing in it, it says so.

The draft describes only what the sheets say. A claim that something is faster or safer appears only with the evidence supplied for it. If the steps for a change that needs user action are missing, the draft says it is not ready, rather than guessing them.

It is not the launch plan, which is the [Launch checklist](https://fullypowered.ai/workflows/launch-checklist/), and it is not the message to staff about a change inside your own company, which is the [Internal change announcement](https://fullypowered.ai/workflows/internal-change-announcement/). It is the user-facing account of what changed in the product.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Product management](https://fullypowered.ai/functions/product-management/), where the owner has to turn a list of shipped work into something users can follow.
- [Customer support and service](https://fullypowered.ai/functions/customer-support-and-service/), where the first questions after a release come from what the notes left unsaid.
- [Software and technology](https://fullypowered.ai/industries/software-technology/), where releases are frequent and users meet the change before they read about it.
- [Hardware and physical technology](https://fullypowered.ai/industries/hardware-and-physical-technology/), where an update to firmware or an app companion needs steps a customer can follow.
- [Ecommerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/), where a change to a store's tools or integrations has to be explained to the shop's own staff.
- [Consumer brands](https://fullypowered.ai/industries/consumer-brands/), where an app or portal update reaches customers who will never read a technical changelog.
- [Startups and new ventures](https://fullypowered.ai/situations/startups-and-new-ventures/), where the founder writes the notes between other tasks on the same afternoon.
- [Growth and scaling](https://fullypowered.ai/situations/growth-and-scaling/), when release frequency outgrows notes written from memory.

## What has to change for your company

Decide who reads the notes and in which place they are published, since that sets the tone and the length. Fill in the glossary with your own internal names so entries use the words your users see. Set your list of change types and statuses if yours differ, the maximum number of items in one set of notes, and the words your company never uses in a promise. Name who confirms accuracy and who approves publication, so each approval line has a person. It runs in ChatGPT, Claude, Copilot or Gemini from the sheets you supply; it needs no access to your product or your code and asks for no password or login code.

## What has been checked

Fully Powered AI wrote this workflow template. It was editorially reviewed on 10 November 2026. It was tried on its invented example in Claude on 10 November 2026, and the record of that run is published with the template. After an independent review the same day, the template and its example were corrected and the run was repeated on the revised text; the record says what changed. It has not yet been tested in a client environment. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a release your team has already written notes for by hand, with hard cases written in advance: an item marked shipped that users cannot see, a speed claim with no measurement, a change that needs user action but has no steps, a known issue that names a feature missing from the sheet, a feature still behind a switch. The product owner and an engineer check every entry against what shipped before anyone relies on the draft. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/) sets those cases up, and [what we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/) describes the record we keep.

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

- [Launch checklist](https://fullypowered.ai/workflows/launch-checklist/)
- [Internal change announcement](https://fullypowered.ai/workflows/internal-change-announcement/)
- [Help article from a resolved issue](https://fullypowered.ai/workflows/help-article-from-a-resolved-issue/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
