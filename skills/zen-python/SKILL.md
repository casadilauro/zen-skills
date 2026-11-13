---
name: zen-python
description: Use when implementing, refactoring, reviewing, debugging, or designing Python code, or changing Python project tooling. Applies Zen of Python principles to choices about clarity, abstraction, data models, errors, tests, performance, and idioms.
---

# Zen Python

Use the Zen of Python as practical engineering guidance. Optimize for
correctness, clarity, simplicity, explicitness, maintainability, then appropriate
performance. Minimize unnecessary complexity, not line count.

## Principles

- Readability counts: beautiful, sparse, unsurprising code beats clever density.
- Explicit is better than implicit; make inputs, outputs, mutation, effects,
  and failure behavior easy to find.
- Simple beats complex; necessary complexity should remain explainable.
- Prefer flat control flow and cohesive namespaces to layers of indirection.
- Special cases do not justify arbitrary inconsistency; practicality beats purity.
- Errors must not disappear accidentally. Silence only as part of an explicit contract.
- Investigate ambiguity. Prefer one obvious public way to do an operation.
- Avoid rushed abstractions and speculative extension points. If a design is
  hard to explain plainly, reconsider it.

Start with an expression or function. Add cohesive functions, a module, a data
structure, a stateful class, composition, a protocol, or a framework only as
concrete requirements justify the additional concepts.

## Repository first

Inspect the relevant code, callers, tests, types, and project configuration,
including `pyproject.toml`, supported Python versions, and selected tools.
Trace the actual flow before choosing a pattern or fixing a symptom. Reuse
reasonable repository conventions and existing helpers. Check the standard
library before adding utilities or dependencies.

Follow the user's task and repository instructions. These are defaults, not
permission to expand scope, rewrite unrelated code, or override framework contracts.

## Load guidance selectively

1. Classify the task using the table below. This table is the bundled guide index;
   do not read the entire reference directory to discover its contents.
2. Check available skill names and descriptions for a more specific match
   (for example, Pydantic, Django, NumPy, pytest, or asyncio). Prefer installed
   specialized guidance for library behavior. Do not install skills just to route.
   If no index exists, inspect frontmatter in known skill directories before bodies.
3. Read one primary guide or specialized skill. Add a secondary guide only when
   a separate concern materially changes a decision; usually use one or two,
   rarely three. Do not preload the subtree or automatically load overlapping guides.
4. Resolve the links below relative to this installed `SKILL.md`, not the working
   repository. Use the host's file reader; no particular invocation tool is required.
   If a selected file is unavailable, report the gap and apply the core guidance.

| Task or decision | Guide to read |
| --- | --- |
| Ordinary functions, naming, control flow, mutation, APIs | [implementation](references/implementation.md) |
| Python expression choices, iteration, generators, stdlib | [idioms](references/idioms.md) |
| Architecture, abstraction, classes, composition, removing layers | [design](references/design.md) |
| Structured data, typing, schemas, validation models | [data-modeling](references/data-modeling.md) |
| Failure contracts, exceptions, validation, I/O, resources, retries | [errors-boundaries](references/errors-boundaries.md) |
| Regressions, tests, review, behavior-preserving refactoring | [testing-refactoring](references/testing-refactoring.md) |
| Explicit performance work, scale constraints, async or concurrency changes | [performance-concurrency](references/performance-concurrency.md) |
| Packaging, formatters, linters, type checkers, test configuration | [tooling](references/tooling.md) |

Examples: group orders → implementation; simplify a service → design, with
testing-refactoring if behavior preservation needs attention; model an API →
an installed framework skill, adding data-modeling or errors-boundaries only
for uncovered concerns; diagnose a slow async pipeline → performance-concurrency.
Exception semantics can warrant errors-boundaries even in pure parsing code.
Do not load performance guidance merely because speed might matter someday.

## Before finishing

Verify the changed behavior with relevant repository checks and report what ran
and any limits. Ask whether a simpler implementation preserves correctness,
comprehensibility, and maintainability. Prefer it when the answer is yes.
