---
name: zen-improve
description: Use when authoring or revising development skills, or investigating observed friction in an agent workflow. Routine software changes do not require a process retrospective.
---

# Zen Improve

Improve the workflow by removing observed friction, one useful change at a time.

Optimize for correctness, clarity, simplicity, explicitness, maintainability, then appropriate performance. Minimize unnecessary complexity, not line count.

## Observe

Read the relevant instructions and authorized task evidence. Follow the user's
scope; a process improvement is not permission to change unrelated configuration.

Find a concrete problem:

- repeated mistakes or incomplete changes;
- confusing instructions or handoffs;
- unnecessary waiting or duplicated work;
- rules that create more effort than useful protection.

Separate what happened from your explanation of why. Investigate causes before
adding another instruction. Cosmetic inconsistency alone does not justify churn.

## Change one thing

Prefer removing or clarifying an existing rule before adding a rule, skill,
script, or stage. Keep useful safeguards and delete obsolete material only after
checking its use.

- State the desired behavior directly.
- Give concrete decision criteria and a short example when ambiguity matters.
- Treat defaults as defaults; allow justified exceptions.
- Reserve mandatory steps for real contracts or consequential failure modes.
- Keep each skill self-contained, with the guidance its task actually needs.
- Update affected skills consistently when a common principle changes.

For example, if handoffs repeatedly omit failure behavior, add the required error
contract to the handoff. Do not introduce an entire planning framework without
evidence that it solves the problem.

Automate recurring, error-prone work when maintaining the automation is simpler
than performing the work. Keep entry points and ownership easy to find.

## Check the effect

Use representative tasks and cases where the instruction should stay out of the
way. Compare old and new behavior under comparable conditions. Inspect actual
artifacts, not only the agent's account of its work.

- Did the observed problem become less frequent or easier to resolve?
- Did the change introduce more waiting, complexity, or unnecessary work?
- Were correctness, security, accessibility, compatibility, and data protection preserved?

Check metadata and references for skill edits. These checks establish structural
integrity, not better engineering decisions. Repeat ambiguous or consequential
evaluations when needed; report untested behavior honestly.

## Keep, revise, or discard

Retain a change when the benefit justifies its cost. Revise or discard an
unsuccessful change rather than layering more rules around it. Keep a usable
previous version for changes being tried in practice.

Before finishing, ask what can disappear or become clearer. Record material
limits and conditions for revisiting them. Deliver the requested proposal or
revision; install or publish only within existing authority.
