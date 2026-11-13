# Python Idioms

Write Python rather than patterns mechanically translated from other
languages.

Prefer language and standard-library features when they improve readability.

Commonly useful tools include:

- direct iteration
- `enumerate`
- `zip`
- `any`
- `all`
- `sum`
- `min`
- `max`
- unpacking
- comprehensions
- generators
- `pathlib`
- context managers
- `collections`
- `itertools`
- `functools`

## Direct Iteration

Prefer:

    for user in users:

over:

    for i in range(len(users)):
        user = users[i]

unless indexing itself matters.

## Comprehensions

Use comprehensions for simple transformations and filtering.

Prefer ordinary loops when comprehensions become:

- nested
- side-effecting
- difficult to scan
- full of business logic

Sparse is better than dense.

## Generators

Use generators when:

- data can be consumed incrementally
- collections may be large
- callers do not require indexing
- laziness naturally represents the operation

Return concrete collections when callers reasonably expect:

- indexing
- repeated iteration
- known length
- eager validation

Do not use generators merely because they seem more advanced.

## Context Managers

Use context managers when a resource requires deterministic cleanup.

Typical examples:

- files
- locks
- transactions
- temporary resources

## Standard Library First

Before adding a utility or dependency, check whether Python already provides
a clear solution.

Do not reject a useful external dependency merely for purity.

## Cleverness

"Pythonic" does not mean code golf.

Prefer the form an experienced Python developer can understand immediately.
