# Python Implementation

Prefer straightforward code with explicit inputs, outputs, and effects.

## Functions

A function should represent one coherent operation.

Prefer functions that:

- have intention-revealing names
- operate at roughly one conceptual level
- take explicit inputs
- return explicit outputs
- minimize hidden state
- remain understandable in isolation

Do not split functions merely to reduce line count.

Extract when the new function represents:

- a meaningful operation
- a reusable operation
- a coherent algorithm
- an effect boundary
- a useful domain concept

Avoid one-line wrappers without semantic value.

## Naming

Use names that reveal intent.

Prefer:

- nouns for values
- verbs for operations
- `is_`, `has_`, `can_`, `should_` for predicates
- established domain terminology

Avoid vague names such as:

- `data`
- `obj`
- `thing`
- `manager`
- `handler`
- `process`

when something more precise exists.

Use one term for one concept.

Do not casually alternate between `get`, `fetch`, `load`, and `retrieve`
unless those operations differ.

## Boolean Flags

Treat boolean arguments that substantially alter behavior as a smell.

Prefer:

    render_html(report)
    render_text(report)

over:

    render(report, html=True)

Boolean values representing actual data are fine.

## Control Flow

Prefer flat control flow.

Use guard clauses and early returns where they improve readability.

Avoid unnecessary nesting.

Do not mechanically use early returns if another structure reads more clearly.

## Intermediate Variables

Use meaningful intermediate variables when they clarify intent.

Do not optimize for minimum statement count.

## Mutation

Mutation is acceptable.

Hidden or surprising mutation is not.

Make in-place behavior apparent from the API.

Avoid functions whose names imply pure computation but unexpectedly modify
their arguments.

## Constants

Give meaningful domain values names.

Do not create constants merely to eliminate every literal.

## Public APIs

Prefer one obvious public path for an operation.

Avoid aliases and compatibility wrappers unless required.

Keep public surface area small.

## Configuration

Do not make everything configurable.

Every option creates:

- additional states
- documentation burden
- testing burden
- maintenance cost

Expose configuration only when a real use case requires it.

## Comments

Code explains what.

Comments explain why.

Useful comments describe:

- external constraints
- surprising domain rules
- tradeoffs
- compatibility requirements
- non-obvious algorithmic reasoning

Do not narrate obvious code.

Delete dead commented-out code.

## Scope

Do not turn a focused task into a repository-wide rewrite.

Change the smallest coherent area necessary.
