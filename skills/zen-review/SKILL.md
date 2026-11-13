---
name: zen-review
description: Use when reviewing a coherent code change or evaluating review feedback for correctness, completeness, maintainability, and readiness.
---

# Zen Review

Review whether the change works and leaves less for the next programmer to understand.

Optimize for correctness, clarity, simplicity, explicitness, maintainability, then appropriate performance. Minimize unnecessary complexity, not line count.

## Read the actual change

Read requirements, the diff including relevant uncommitted work, callers, tests,
and repository conventions. Check the integrated behavior, not only isolated
functions. Keep a review-only task read-only and preserve existing work.

## Is it correct?

- Does the requested behavior work through its real entry point?
- Are affected callers, configuration, fixtures, migrations, and documentation complete?
- Are public contracts and saved-data compatibility preserved?
- Are validation, error context, cleanup, and failure recovery intact?
- Are required security, accessibility, and data protections retained?
- Do tests check behavior with independent expectations and relevant failure cases?
- Does the reported verification cover the actual changed state?

Check real interactions where mocks could hide an incompatible interface.
Performance claims need measurements. Distinguish existing failures from new
ones and identify missing required checks.

## Can anything disappear?

Look for unnecessary:

- classes, interfaces, and inheritance used only for code reuse;
- wrappers that add no policy, transformation, isolation, or compatibility;
- configuration options, dependencies, and speculative extension points;
- repeated decisions that must remain consistent;
- obsolete code and public aliases that no supported caller needs.

Do not remove required behavior or protections to reduce code. Similar lines
may encode independent policies. An abstraction is useful when it simplifies
callers and reduces the whole system's burden.

## Can anything become clearer?

- Replace vague names with domain language.
- Flatten confusing flow where it helps; do not split functions to meet a line limit.
- Make inputs, mutation, effects, ownership, and failures easy to find.
- Question silent recovery and flags selecting unrelated behavior.
- Use test complexity as a signal: deep mock chains may reveal hidden coupling.

Prefer practical improvements to pattern compliance or personal style. Consider
the maintenance cost of the proposed remedy as well as the problem it addresses.

## Give useful findings

For each actionable finding, state the location, triggering condition,
consequence, and smallest adequate remedy. Separate defects from optional
improvements. Avoid turning a focused review into a repository rewrite.

When asked to address feedback, verify it against the code, correct valid
in-scope defects, explain rejected findings, and recheck affected behavior.
Optional suggestions do not silently enlarge the task.

Use independent review when required or justified and authorized. An assigned
reviewer performs the review without recursively commissioning more reviewers.
If required review is unavailable, state that gap; identify self-review honestly.

## Before finishing

Read amended behavior and resolve or clearly report blocking findings. Stop
repeating review when it adds no evidence; a round limit never proves readiness.
Return the findings and verification limits, with a clear readiness assessment.
