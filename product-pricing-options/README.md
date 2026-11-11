# Product pricing options

A product owner weighing how to price or package a product gets one options brief: what each customer group uses, the willingness-to-pay evidence held with stated kept apart from observed, what each option would bill every account, the uncertainties and the tests. It recommends no price.

*Capability template · Product management · version 0.1.0 · [Capabilities Directory](https://fullypowered.ai/capabilities/product-pricing-options/)*

## The outcome

The product owner walks into the pricing conversation with the options side by side and the evidence behind them. For each customer group the brief shows what they actually use, so the choice of what a price should scale with is made on data. For each option it shows what every account would be billed against what it pays today, how many accounts pay more, the same or less, and the gross margin where approved costs were supplied.

It is plain about what is not known. What customers said they would pay is held apart from what they were seen to do, and neither is stretched into a range the rows do not support. The brief ends with the uncertainties and the tests that would reduce them. The owner chooses what to recommend; the people who approve prices and terms decide the rest.

## Who starts the work, and when

The product owner starts it when a price or a package comes up for review: a new product, a new plan, a change in what is included, or a question about what the price should scale with. The brief comes back to the product owner only, who brings it to the pricing conversation; it goes to the commercial authority or finance only if the product owner sends it.

## What they supply

- The current package definitions: name, monthly price and what each package includes.
- A usage export with one row per customer account.
- The cost inputs finance has approved, each with the name of who approved it.
- A customer research log: what customers said and what they did, each row dated.
- The options to compare, each written as a bill formula, and a few settings such as the age limit for evidence.

## What comes out

One options brief in a fixed order: the packages today, the value measures for each customer group, the willingness-to-pay evidence held, every option billed account by account against today, option totals with gross margin, how each option sits against the evidence, the uncertainties, proposed tests and the questions for the owner. Every figure is worked out in view. If a column is missing or a rule cannot be applied, the capability stops and asks instead of guessing.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Product management](https://fullypowered.ai/functions/product-management/), where pricing and packaging sit beside scope and priorities.
- [Finance and accounting](https://fullypowered.ai/functions/finance-and-accounting/), which approves the cost inputs and the margin the options leave.
- [Sales](https://fullypowered.ai/functions/sales/), which holds many of the quotes won and lost that count as evidence.
- [Software & technology](https://fullypowered.ai/industries/software-technology/), where packages scale with seats and usage.
- [Consumer brands](https://fullypowered.ai/industries/consumer-brands/), where a pack size or a subscription plan is a pricing choice.
- [E-commerce & retail](https://fullypowered.ai/industries/ecommerce-and-retail/), where bundles and memberships are weighed the same way.
- [New business lines](https://fullypowered.ai/situations/new-business-lines/), when a first price has to be set with little history.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/), when packages no longer fit the customers who have arrived.
- [Startups & new ventures](https://fullypowered.ai/situations/startups-and-new-ventures/), when the first paying customers are the only evidence.

To check what a change to a price already in the market does to margin and sales, use [price change review](https://fullypowered.ai/capabilities/price-change-review/). To look at how a packaged offer reads to a buyer, use [offer review](https://fullypowered.ai/capabilities/offer-review/). To weigh a discount request, use [discount request review](https://fullypowered.ai/capabilities/discount-request-review/).

## What has to change for your company

Write your packages and your options as the bill formula the template uses, or tell it how your price is built. Name the unit your customers use, such as documents, orders or projects. Set the age limit for evidence, the number of rows a range needs and the smallest customer group worth a figure. Agree who approves cost inputs and who the commercial authority is. Decide which customer groups you track. It runs in ChatGPT, Claude, Copilot or Gemini from files you supply and needs no connection to your billing system.

## What has been checked

Fully Powered AI wrote this capability template. It was editorially reviewed on 10 November 2026. It was tried once on its invented example in Claude on 10 November 2026, by a model that did not write it, and the record of that run is published with it. The run was not fully blind: part of the example's output had been seen before the brief was written. Edits made after the run have not been run again: observed willingness-to-pay rows are no longer given one range across accepted and declined, several small ambiguities in the template were settled, and the example's uncertainties and tests were corrected. After a second review the instruction block was completed with rules the template already held, the rounding of halves was settled, and the example was made to match the output format; these edits have not been run again either. It has not yet been tested in a client environment or as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a pricing question you already settled, with hard cases written in advance: a renamed column, a cost nobody approved, research rows that are too old, an option that does not fit the formula. The product owner recomputes every bill by hand before anyone relies on the brief. [Pilot acceptance-test preparation](https://fullypowered.ai/capabilities/pilot-acceptance-test-preparation/) builds that test set, and [what we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/) describes the record we keep.

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

- [Price change review](https://fullypowered.ai/capabilities/price-change-review/)
- [Offer review](https://fullypowered.ai/capabilities/offer-review/)
- [Discount request review](https://fullypowered.ai/capabilities/discount-request-review/)

## Make it yours

This is the starting version. Fully Powered AI adapts capabilities to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
