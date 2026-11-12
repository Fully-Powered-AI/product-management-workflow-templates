# Fully Powered Workflow Templates: Product Management

Ship the thing that matters, and know why. These workflow templates take the framing and scoping behind a product decision and give an AI assistant a precise way to prepare it from your own evidence, with the product owner making every call.

This repository holds 6 workflow templates for product managers and the founders who do the job themselves. Each one is a single piece of work with its own folder: what it is for and who starts it, the complete template an AI assistant follows, a worked example with invented data, what to change for your company, what has been checked, and its sources.

## The workflow templates

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

The [Fully Powered Workflows Directory](https://fullypowered.ai/workflow templates/) lists every workflow template across functions and industries, with search. A machine-readable list of this repository is in [index.json](index.json).

## Licence and credits

MIT, in [LICENSE](LICENSE) and in every folder. Each folder's SOURCES.md names what the workflow template drew on. Published by [Fully Powered AI](https://fullypowered.ai/).
