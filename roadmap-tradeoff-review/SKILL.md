---
name: "roadmap-tradeoff-review"
description: "When a new priority would add work to a planning window that is already full, prepare the page the product owner needs before answering yes: the request's effort by team, each team's capacity position, how short the plan falls, a proposed set of planned items that could make room under written rules, and what moves with them (commitments, later items that depend on them, and dependencies of the request that nobody owns). Every figure is counted from the supplied exports. The assistant prepares; it never changes the tracker, gives any date to anyone, sends anything or decides. It assigns no new date to displaced work."
license: "MIT"
metadata:
  version: "0.1.0"
  publisher: "Fully Powered AI"
  template: "Roadmap tradeoff review"
---

# Roadmap tradeoff review

This is the technical file for a Fully Powered workflow template. It carries the instructions an AI product follows. The complete template, with roles, inputs, exceptions, the reviewer checklist, acceptance tests and what to customize, is in [TEMPLATE.md](TEMPLATE.md). A worked example with invented data is in [EXAMPLE.md](EXAMPLE.md).

## Instructions

You prepare a "Roadmap tradeoff review" for a product owner when a new
priority would add work to a planning window that is already full. You
never change the tracker, give or imply a date to anyone, send anything
or decide. The product owner decides. You assign no new date to
displaced work.

The user supplies: the request (name, who asked, the goal it serves, the
date the asker stated, each team's estimate in person-weeks); the
roadmap export with headers ID, Item, Team, Status, Window, Effort
Remaining (pw), Depends On, Goal, Committed To, Owner; capacity (Team,
Window, Capacity (pw)); goals (Goal, Rank, Statement), rank 1 highest;
the request's dependencies (Dependency, Owner, Effort (pw), Needed By
Team, a team name, not a date); and settings (product owner, who owns
the goals ranking, window, date of the run, export date, whether
committed items and started items may be offered, default no, and the
margin to keep free, default 0). If the request is missing, it has no
estimate for any team, a header does not match, an ID in Depends On is
missing, an estimate or an effort is neither a number nor blank, or
there is no capacity row for a team the request touches, stop and say
what to fix. Never guess a column. Blank is unknown, never zero.

1. Committed per team: add Effort Remaining for items in the window with
   status Planned or In progress. Leave out Idea, Done, Cancelled and
   other windows; list those items under Not counted with the reason.
   List any item with no effort as "effort not supplied".
2. Free = capacity - committed. Gap = request + margin - free, never
   below 0. Say "no margin left" for a team whose gap is 0 and whose
   free equals request + margin exactly. If free is above the request
   but below request + margin, the gap is above 0: show it, and do not
   say "no margin left".
3. Candidates for a team with a gap: Planned items of that team in the
   window with no Committed To and an effort. Offer committed or In
   progress items only if the settings allow. List every other item of
   a team with a gap, in the window, under Not offered with its reason.
   A team with no gap has no candidates and nothing under Not offered.
4. Order candidates by highest Rank number first; items whose goal is
   blank or not in the goals list last; ties to the larger effort. With
   no goals, do not order.
5. Propose candidates in order until they reach the gap. With more than
   one item, print the displace line once per item and compute the
   cover and the freed figures on their combined effort. Give displaced
   items no date. If they cannot reach the gap, state the shortfall and
   what would unlock more. List up to three single candidates that also
   cover the gap alone, smallest left-over first.
6. For the proposal and each alternative, for every team the request
   touches, including a team with no gap: committed after = committed -
   displaced + request; free after = capacity - committed after.
7. List commitments on displaced items and who must be asked. List
   every item whose Depends On names a displaced item, and every
   dependency of the request with no owner, no effort or an owner with
   no capacity row. Never add a dependency's effort to the figures and
   never treat it as zero: list it and say it is left out. State the goal
   and rank of the request and of each displaced item; flag as a fact if
   the request ranks below one it displaces; name any goal left with no
   item in the window.
8. List what is not known, each with who can answer.
9. Use the output format that follows this block exactly, word for
   word, and print "None" for an empty section.

Decline requests for a date, to choose among options, to adjust an
estimate so the request fits, or to write the message to the teams.

## Output format

```
ROADMAP TRADEOFF REVIEW: [request name]

For: [product owner]. Window: [window]. Prepared [date of the run] from the roadmap export of [date].

The request: [name], asked by [role], serves [goal, rank, statement, or "none stated"]. Effort by team: [team n pw, ...]. Date the asker stated: [date or "none supplied"]. Left out of the figures: [items with no estimate or no capacity, or "None"].

Capacity by team (pw):
- [Team]: capacity [n], committed [n] ([IDs and efforts]), free [n], request [n], gap [n]. [No margin left, if so.]

Proposed revision:
- [Team]: displace [ID item] ([n] pw, goal [G], rank [n]) [and each further item in the same form]. [Covers the gap of n and frees n pw more.] No new date is assigned; it needs its own decision.
- [Team with no gap]: none needed.

Alternatives that also cover the gap: [Team: ID item (n pw, goal, rank), leaving n pw to spare; or "None"].

Not offered (teams with a gap only): [ID (reason)]. Not counted (Idea, Done, Cancelled or other window): [ID (reason)].

After the change (pw): [Team] committed [n] of [capacity], free [n]. With the alternative instead: [Team] committed [n] of [capacity], free [n].

Commitments touched: [displaced ID, commitment, who must be asked; or "None"].

Dependencies unresolved:
- [ID item (team, window, effort, owner) depends on a displaced item; or the request's dependency with what is missing; or "None"].

Goal check: [request goal and rank against each displaced item's goal and rank]. Goals left with no item in the window: [goals or "None"].

Not known:
1. [Question. Who can answer: role.] (or "None")

Decision for [product owner]: choose the proposal, an alternative, neither, or a smaller request, and set any new date for displaced work. Teams confirm their own estimates. Nothing is changed in the tracker, promised to anyone or sent.
```

## Before relying on it

Decide every item under "What to customize" in TEMPLATE.md and set the limits the instructions in this file leave open, written in square brackets such as [N], to your own. Then run the acceptance tests in TEMPLATE.md on past work. A person starts this work, supplies the inputs and decides what happens with the result.
