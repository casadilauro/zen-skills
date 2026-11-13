---
name: zen-debug
description: Use when software shows unexpected behavior, a failing test or build, an integration failure, or an unexplained performance problem.
---

# Zen Debug

Understand the failure before choosing the correction.

Optimize for correctness, clarity, simplicity, explicitness, maintainability, then appropriate performance. Minimize unnecessary complexity, not line count.

## Follow the evidence

Read the error, relevant code, callers, tests, configuration, and recent changes.
Follow the user's scope and repository conventions. Trace the actual data and
control flow rather than guessing from a function name.

- State expected and observed behavior.
- Reproduce the failure with the smallest informative case.
- Compare a failing case with a working one when it distinguishes causes.
- Name a specific explanation and a check that could disprove it.
- Change one causal factor at a time where practical.

If the problem is intermittent or inaccessible, gather targeted diagnostics.
Keep useful context without exposing secrets. Repeated failed attempts mean
revisit the evidence; they do not establish that the architecture needs replacing.

## Keep failures honest

- Catch the narrowest meaningful error; broad recovery needs an explicit reason.
- Preserve the original cause when translating errors.
- Return absence only when absence is normal behavior. Do not use an empty value to conceal an unrelated failure.
- Make fallback behavior part of an explicit contract.
- Retry only failures likely to be transient, with bounded attempts or duration and appropriate backoff. Check that repeating the operation is safe.

A timeout followed by an empty result may hide a failure rather than fix it.
A wider exception handler is not evidence that the cause is understood.

## Correct the cause

Fix the shared cause where affected callers share the same contract. Keep
independent policies separate. Prefer a focused correction using existing
facilities over a new layer or unrelated cleanup.

Preserve boundary validation, error context, resource cleanup, compatibility,
security, accessibility, and data protection. Complete affected callers and
fixtures; do not leave one entry point behaving differently by accident.

Urgent mitigation can be useful when authorized. Label it as containment,
preserve evidence, and report the unresolved cause.

## Performance failures

Measure representative work. Look first for a better algorithm, unnecessary
computation or I/O, excessive materialization, or opportunities to batch.
Use caching, concurrency, or specialized code when their measured benefit
justifies their consistency and maintenance costs.

## Before finishing

- Add a focused regression check when feasible. Show that it catches the original bug and passes with the fix when practical.
- Derive expectations from the intended contract; verify normal and relevant failure behavior.
- Run affected and project-required checks, including real integration where isolation would miss the failure.
- For performance, compare before and after under comparable conditions while preserving correctness.
- Remove temporary experiments and inspect the final diff.

Report the supported cause, correction, actual checks, and remaining uncertainty.
Separate existing failures and unavailable checks. One unexplained successful
run does not establish a fix. Ask whether the correction can be simpler without
losing the behavior or protection it needs.
