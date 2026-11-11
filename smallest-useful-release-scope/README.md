# Smallest useful release scope

A product owner or founder with more features than capacity gets one page: what is in the first release and what is deferred, all tied to one user outcome, with the reason for each cut. The owner decides the scope; no effort is estimated beyond what is supplied.

*Capability template · Product management · version 0.1.0 · [Capabilities Directory](https://fullypowered.ai/capabilities/smallest-useful-release-scope/)*

## The outcome

The feature list stops being a wish list and becomes a first release with a purpose. You state one thing a user should be able to do when the release ships, and every feature is placed against it: in because the user cannot get there without it, or deferred with a stated reason and what the user does in the meantime. Where the capacity you supplied is exceeded, the page says by how much and what each possible removal would cost, and leaves the choice to you.

## Who starts the work, and when

The product owner, or the founder who does that work, starts it when the list of wanted features is longer than the time available and a release has to be agreed. Engineering reads the result before the owner approves the scope, to confirm what can be built in what order.

## What they supply

- One user outcome, written as what a named kind of user can do, and the measure that would show it happened.
- The steps the user takes to reach it, in order.
- The feature list, one row per feature, with the step it serves, what kind of feature it is, the effort engineering has given it, what it depends on, and what people do without it for now.
- The capacity for the release, in the same unit as the effort.
- Any limits engineering has stated, in the owner’s words.

## What comes out

One page: the outcome and its path, the features in scope with the reason each is in, the features deferred with the reason each is out and what happens meanwhile, a capacity check from the supplied figures only, the questions the page cannot settle, what engineering is asked to confirm, and a line for the owner’s decision. Blank effort is shown as not supplied, never filled in.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Product management](https://fullypowered.ai/functions/product-management/), where the first release is the first test of what customers value.
- [Software technology](https://fullypowered.ai/industries/software-technology/), where the list is always longer than the sprint.
- [Consumer brands](https://fullypowered.ai/industries/consumer-brands/), when a brand launches its first app or digital service.
- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/), when a store feature has to ship before a season.
- [Startups & new ventures](https://fullypowered.ai/situations/startups-and-new-ventures/), where the first release is most of the budget.
- [New business lines](https://fullypowered.ai/situations/new-business-lines/), when an established company builds a first version of something new.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/), when requests arrive faster than the team can ship them.

## What has to change for your company

Decide the unit of effort and use it everywhere. Choose who is the owner and who in engineering confirms. Keep or change the six kinds of feature, and decide which are always in or never in for your product, such as sign-in or a way to undo. Set how the measure is stated. Add the limits your team always carries into a release, such as an approval an outside provider takes time to give. It runs in ChatGPT, Claude, Copilot or Gemini from the brief and the list you type or paste; it needs no connection to any system.

## What has been checked

Fully Powered AI wrote this capability template in its own words. It was editorially reviewed on 10 November 2026. It was tried once on its invented example in Claude on 10 November 2026; the record is published with it, and lists the small edits made afterward that have not been run again. It has not been tested in a client environment or as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a release you shipped before, with the list as it stood then and cases written in advance: a feature with no effort, a feature that depends on one you would defer, two outcomes in one brief, a list over capacity. The owner and engineering check every placement against the list before anyone relies on it. [Scope change impact review](https://fullypowered.ai/capabilities/scope-change-impact-review/) takes over once the scope is agreed and new work arrives, and [Project scope baseline](https://fullypowered.ai/capabilities/project-scope-baseline/) records an agreed scope for a project.

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
- [Project scope baseline](https://fullypowered.ai/capabilities/project-scope-baseline/)
- [Scope change impact review](https://fullypowered.ai/capabilities/scope-change-impact-review/)

## Make it yours

This is the starting version. Fully Powered AI adapts capabilities to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
