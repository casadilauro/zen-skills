# Python Design

Every abstraction has a cognitive cost.

It must remove more complexity than it adds.

## Abstraction Ladder

Prefer, in order:

1. Function.
2. Several cohesive functions.
3. Module.
4. Data structure.
5. Stateful class.
6. Composition.
7. Protocol/interface.
8. Framework-like abstraction.

Do not skip levels without reason.

## Abstraction Test

Before introducing an abstraction ask:

1. What concrete problem does it solve?
2. Does the problem exist today?
3. Could functions solve it more clearly?
4. How many implementations exist?
5. Does the abstraction reduce complexity?
6. Can someone explain why it exists?

Prefer making a second implementation easy to add over pretending it already
exists.

## Architecture by Vocabulary

Names do not justify abstractions.

Be suspicious of:

- Manager
- Factory
- Provider
- Registry
- Coordinator
- Handler
- Strategy
- Service
- Repository
- Engine

Determine what responsibility actually exists.

If a layer only forwards another call, question whether it should exist.

## Composition

Prefer composition to inheritance.

Use inheritance when substitutable "is-a" semantics are genuinely useful.

Avoid inheritance solely for code reuse.

## Protocols

Do not introduce protocols or abstract base classes because multiple
implementations might theoretically exist.

Add them when polymorphism is real.

## DRY

DRY means avoiding duplicated knowledge.

It does not mean eliminating every repeated line.

Prefer a little duplication over the wrong abstraction.

## Separation of Concerns

Separate code when responsibilities genuinely differ.

Keep things together when they change together.

Do not automatically create controller/service/repository/schema layers for
every feature.

## Modules

Modules are namespaces.

Organize around coherent responsibilities.

Do not split files merely because of arbitrary line counts or one-class-per-
file rules.

## Speculative Extension Points

Avoid premature:

- registries
- hooks
- callbacks
- factories
- plugin systems
- event buses
- generic strategies

Build extension points when extension becomes a requirement.

## Wrapper Cascades

Every wrapper should add something meaningful:

- policy
- contract
- transformation
- isolation
- compatibility

Otherwise remove it.
