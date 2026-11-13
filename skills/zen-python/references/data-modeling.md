# Data Modeling

When the problem is primarily data, model it as data.

Consider:

- ordinary dictionaries
- dataclasses
- NamedTuple
- TypedDict
- enums
- Pydantic models at validation boundaries

before creating behavioral class hierarchies.

## Classes

Use behavioral classes when they encapsulate meaningful:

- state
- identity
- invariants
- lifecycle
- coordinated behavior
- polymorphism

Avoid objects consisting primarily of boilerplate accessors.

## Types

Use type annotations to communicate contracts.

Prioritize:

- public APIs
- important boundaries
- domain models
- non-obvious return values

Do not make the type system harder to understand than the implementation.

## Any

Do not use `Any` merely because modeling data is inconvenient.

Use it deliberately at genuinely dynamic boundaries.

Do not construct elaborate generic machinery solely to eliminate every `Any`.

## Validation

Validate external data at boundaries.

Examples:

- API input
- files
- environment variables
- database results
- CLI input
- external service responses

Once validated, avoid repeatedly revalidating the same invariant internally.

## Pydantic

Use Pydantic when runtime validation or serialization boundaries justify it.

Do not turn every internal data object into a Pydantic model automatically.

## Invalid States

When practical, structure types so invalid states are difficult to construct.

Do not create excessive wrapper types for trivial invariants.
