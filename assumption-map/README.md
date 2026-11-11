# Assumption map

For a product owner whose plan rests on beliefs nobody has tested: each belief is written down, set against the evidence you hold, ranked by what it would do to the plan, and given a cheap test to choose from. You decide what to test; no evidence is invented.

*Capability template · Product management · version 0.1.0 · [Capabilities Directory](https://fullypowered.ai/capabilities/assumption-map/)*

## The outcome

The product owner sees, on one page, what the plan is standing on. Every plan item is listed with the beliefs behind it, and every belief carries one of four marks: held, thin, contradicted or none. The mark follows a fixed rule from the evidence you supply, so a friendly interview cannot stand in for something people did, and bad news cannot be left out.

The beliefs that are not held come out in rank order. They are ranked first by what each would do to the plan, then by how little backs it. For the top few the page offers a cheap test suited to the kind of belief, and leaves the learning criteria empty for you to fill in before anything is run.

Nothing is decided for you. The page ends with a choice line for each belief shown: test now, later, or accept the risk. It adds no evidence of its own and reports no result it was not given.

## Who starts the work, and when

The product owner starts it when a concept becomes a plan with a date: before the build is approved, before a launch is committed, or when a plan item changes and the beliefs behind it may have changed too. Run it again when a test comes back, and the marks move.

The product owner lists the plan items, writes down the beliefs they depend on, and supplies what evidence exists. The AI assistant lays the map out and ranks it. The product owner confirms every belief, chooses what to test and sets what result would count.

## What they supply

- **A short brief.** The concept, who owns the decision, the decision and its date, the review date and any context worth knowing.
- **The plan,** one item per row: what the plan does or commits to.
- **The beliefs,** one per row: what has to be true, the kind of belief, which plan items depend on it, what happens to the plan if it is false, and a test idea if you already have one.
- **The evidence,** one item per row: what was seen, what kind it was, when, which beliefs it bears on, and whether it supports or contradicts them.

## What comes out

One page in a fixed order. The plan with the beliefs under each item and their marks; every belief with the evidence for it, against it and neither way, and what is missing; evidence not tied to any belief; the unheld beliefs in rank order; a cheap test for the first few, either yours as typed or a suggestion from a fixed list; the questions only the product owner can answer; and an empty choice line for each belief shown.

Where something is missing, such as a plan item with no belief or evidence with no date, the page says so and asks. It never fills the gap itself.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Product management](https://fullypowered.ai/functions/product-management/), when a roadmap item, launch or build rests on things no one has yet checked.
- [Software and technology](https://fullypowered.ai/industries/software-technology/), where a feature plan often runs ahead of what customers have been seen to do.
- [Hardware & physical technology](https://fullypowered.ai/industries/hardware-and-physical-technology/), where a wrong belief about supply, build or fit is dear to correct once tooling starts.
- [Consumer brands](https://fullypowered.ai/industries/consumer-brands/), when a new product or format is planned around how shoppers are assumed to behave.
- [Startups and new ventures](https://fullypowered.ai/situations/startups-and-new-ventures/), where most of the plan is still belief.
- [New business lines](https://fullypowered.ai/situations/new-business-lines/), before a team moves onto a line whose demand is assumed.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/), when what worked at one size is planned for another.

It is not the commercial review of a whole business model: [Business model assumptions review](https://fullypowered.ai/capabilities/business-model-assumptions-review/) does that. It does not imagine the plan failing in a workshop: [Premortem before a decision](https://fullypowered.ai/capabilities/premortem-before-a-decision/) does that. This one starts from the plan's own items and asks what each is standing on.

## What has to change for your company

Decide who owns the map and who may mark a belief as supported or contradicted. Keep or change how old evidence may be before it is rechecked (twelve months by default) and how many beliefs get a suggested test (three). Add your own kinds of evidence if some of your records count for more than the default four. Replace the suggested tests with the cheap tests your team can actually run, such as a pre-order page or a hand-run version of a step. Decide where the maps are kept, so the next one starts from the last and shows which beliefs moved. It runs in ChatGPT, Claude, Copilot or Gemini from the lists you type or paste; it needs no connection to any system.

## What has been checked

Fully Powered AI wrote this capability template. It was editorially reviewed on 10 November 2026. It was tried once on its invented example in Claude on 10 November 2026; the record is published with the template. It has not yet been tested in a client environment or as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a plan whose outcome you already know, with the beliefs and evidence written as they stood then, plus hard cases written in advance: a plan item with no belief, evidence with no date, an estimate that points against a belief, a rating outside the scale. The product owner checks every mark and the ranking against the lists before relying on the page. [Offer review](https://fullypowered.ai/capabilities/offer-review/) takes the offer behind a belief further.

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

- [Business model assumptions review](https://fullypowered.ai/capabilities/business-model-assumptions-review/)
- [Premortem before a decision](https://fullypowered.ai/capabilities/premortem-before-a-decision/)
- [Offer review](https://fullypowered.ai/capabilities/offer-review/)

## Make it yours

This is the starting version. Fully Powered AI adapts capabilities to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
