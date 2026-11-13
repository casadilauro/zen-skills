# Testing and Refactoring

Tests should protect behavior.

Refactoring should improve clarity without unnecessary churn.

## Test Behavior

Prefer testing:

- domain rules
- important edge cases
- error semantics
- public contracts
- regressions
- integration boundaries

Avoid tests coupled tightly to internal implementation structure.

## Testability as Feedback

If simple behavior requires:

- many global patches
- deep mock chains
- unrelated application setup
- hidden state manipulation

reconsider the design.

## Mocking

Mock external boundaries when useful.

Avoid mocking every internal function merely because it can be mocked.

## Refactoring

Before changing structure, understand:

- current behavior
- callers
- tests
- public APIs
- compatibility requirements

Then simplify.

For a regression, first reproduce the failure with the smallest relevant check.
Trace all callers of the affected function and fix the shared cause when they
share the same contract. Verify normal behavior and the failing case; do not
hide the symptom by swallowing exceptions or patching only one caller.

Look for:

- unclear names
- deep nesting
- duplicated knowledge
- unnecessary wrappers
- hidden effects
- speculative abstractions
- broad exceptions
- obsolete code

## Scope

Do not rewrite unrelated working code during a focused refactor.

## Simplicity Review

Before finishing ask:

### Can anything disappear?

- class
- wrapper
- helper
- interface
- configuration
- dependency
- compatibility layer
- comment
- public API

### Can anything become clearer?

- name
- control flow
- effects
- mutation
- failure behavior
- vocabulary

If two implementations behave equally well, prefer the one with fewer
concepts.
