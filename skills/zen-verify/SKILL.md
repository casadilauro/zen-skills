---
name: zen-verify
description: Use when choosing meaningful software tests and checks or evaluating whether implementation, refactoring, or bug-fix claims have sufficient evidence.
---

# Zen Verify

Tests should protect behavior and make changes easier to trust.

Optimize for correctness, clarity, simplicity, explicitness, maintainability, then appropriate performance. Minimize unnecessary complexity, not line count.

## Start with the contract

Read the requested behavior, relevant callers, existing tests, and project
configuration. Follow the repository's tools and required checks. Reuse useful
coverage before creating another test fixture or testing layer.

Prefer tests for:

- domain rules and public contracts;
- important boundaries and failure semantics;
- regressions;
- interactions with real components and persistent state.

Every new test should catch a plausible defect. Avoid assertions about private
function names or call sequences unless those details are part of the contract.

## Make expectations independent

Use specified examples, known results, or meaningful invariants. Do not calculate
the expected answer with the same algorithm under test.

Check normal behavior and relevant edge cases: empty or malformed inputs,
limits, missing values, and unavailable services. Check the state left behind
on failure, including cleanup and protection against partial writes or data loss.
Include required security, accessibility, and compatibility checks.

For nontrivial new behavior, retain a meaningful automated test or repeatable
self-check. Prefer test-first when it clarifies the behavior. For bugs, reproduce
the failure and establish that the regression check catches it when practical.
For refactoring, establish a baseline and preserve observable behavior. Trivial
mechanical changes may need only direct inspection or validation.

## Let tests inform design

If simple behavior needs deep mock chains, many global patches, or unrelated
application setup, inspect the design for hidden state or coupled responsibilities.

- Mock external boundaries when useful, rather than every internal function.
- Keep fixtures small enough to explain the case.
- Control time, randomness, and shared state when they affect the result.
- Retain real integration coverage for assumptions about external interfaces.
- Exercise the user-facing path when isolated checks cannot establish the assembled behavior.

Do not discard working code merely because tests came afterward. Strengthen
the evidence with independent examples and safe counterexamples. Do not weaken
expectations merely to match implementation; change them when the contract changes.

## Before finishing

Run the smallest relevant checks during iteration, then broader checks required
by the repository or impact of the change. Include relevant compiler, type,
lint, and formatting checks. Inspect actual results and rerun affected checks
after changes to the tested state.

Performance claims need representative before/after measurements and correctness
checks. An improved local metric alone does not establish an overall improvement.

Can the tests become clearer or lose unnecessary setup while retaining useful
protection? Report what ran, what failed, and what remains unavailable. A focused
passing run does not establish a clean full suite; unresolved required checks
remain a completion gap.
