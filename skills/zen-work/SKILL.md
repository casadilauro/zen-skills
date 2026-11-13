---
name: zen-work
description: Use when carrying a concrete software task from its request or saved progress through implementation, verification, and delivery.
---

# Zen Work

Deliver a complete, understandable change to the actual problem.

Optimize for correctness, clarity, simplicity, explicitness, maintainability, then appropriate performance. Minimize unnecessary complexity, not line count.

## Understand the task

Read the relevant code, callers, tests, and project configuration. Follow the
user's scope and repository instructions. Use existing tools and conventions.

- Describe the required behavior with a concrete example.
- Identify what must remain true: contracts, saved data, failure behavior, and compatibility.
- Ask only about uncertainty that materially changes the result and cannot be resolved from the available context.
- Make ordinary reversible choices yourself. Continue independent work while a consequential decision is pending.

A small task needs a clear next step. Record decisions and dependencies when
others will need them or work may outlive the current context. Resume from
actual files and evidence, not an unchecked progress note.

## Make the change

Prefer removal or reuse, then existing project and platform facilities, then
minimum new code.

- Start with a direct function or existing component. Add layers only when they remove more complexity than they introduce.
- Keep related decisions together. Similar code may stay separate when its policies change independently.
- Use names, data structures, and control flow that make the behavior easy to follow.
- Make mutation, external effects, and failures visible.
- Complete affected callers, interfaces, configuration, fixtures, migrations, and documentation.
- Preserve validation, resource cleanup, security, accessibility, and protection against data loss.

For refactoring, establish current behavior before changing structure. For a
bug, reproduce the symptom, test a causal explanation, and fix the shared cause
where callers share the contract. Do not conceal failures with successful-looking
fallbacks. Distinguish urgent containment from a verified fix.

Protect existing workspace changes. Use isolation or authorized delegation when
it reduces interference or helps resolve independent work; account for its
coordination cost.

## Check and simplify

- Use existing checks and add meaningful coverage for nontrivial new behavior or regressions. Prefer test-first when it clarifies the behavior.
- Derive expected results independently. Check relevant failure cases and real component interactions.
- Run affected and project-required checks. Investigate failures rather than weakening expectations.
- Measure performance changes under comparable conditions.
- Read the final diff. Can a wrapper, option, dependency, or special case disappear? Can a name, effect, or failure become clearer?

Obtain independent review when required or warranted and authorized. Recheck
affected behavior after integration; a worker's success report is not enough.

## Finish

Stop when the authorized outcome is complete. A design-only request ends with
a design; a review-only request ends with findings. Commit, publish, or merge
only within existing authority. Report the result, checks actually run, and
remaining failures or limits. Preserve incomplete work without calling it done.
