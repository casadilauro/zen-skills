---
name: zen-design
description: Use when an unresolved software requirement, interface, architecture, migration, or delivery sequence materially changes what should be built. Also use for an explicitly requested design or implementation plan.
---

# Zen Design

Every abstraction has a cognitive cost. It should remove more complexity than it adds.

Optimize for correctness, clarity, simplicity, explicitness, maintainability, then appropriate performance. Minimize unnecessary complexity, not line count.

## Repository first

Read the existing implementation, callers, data, tests, and framework contracts.
Follow the user's scope and repository conventions. Identify the present need
and the behavior that must remain compatible before choosing a pattern.

## Start with fewer concepts

Consider a function first, then cohesive functions, a module, a data structure,
a stateful component, composition, an interface, or a framework as requirements
justify them. This is a guide to increasing cost, not a mandatory sequence or
a reason to fight the language or framework.

Before adding an abstraction, ask:

- What concrete problem exists today?
- Could functions or ordinary data solve it more clearly?
- Is the variation real, or merely possible?
- Do callers become simpler?
- Can another programmer explain why it exists?

A name such as Manager, Factory, Registry, or Service does not establish a
responsibility. A wrapper should add meaningful policy, transformation,
isolation, compatibility, or a contract. Question layers that only forward calls.

## Model the problem

- When the problem is data, start with the language's ordinary records, collections, and enums.
- Use classes for meaningful state, identity, invariants, lifecycle, or coordinated behavior.
- Use types to explain important contracts; avoid type machinery harder to understand than the behavior.
- Make invalid states difficult to construct where practical, without wrapping every trivial value.
- Prefer composition for combining behavior. Use inheritance when substitutability is useful, not merely to reuse code.

Validate external data at its boundary. Keep internal assumptions clear without
rechecking the same established invariant everywhere.

## Keep boundaries useful

- Design from the caller's inputs, outputs, and failure contract.
- Keep decisions together when they change together; separate responsibilities when their changes interfere.
- Share duplicated knowledge. Allow similar lines to remain separate when they encode independent policies.
- Make ownership, mutation, effects, and dependency direction apparent. Avoid cycles.
- Keep public APIs small. Add configuration and extension points for actual use cases.
- Preserve established formats and guarantees through compatible evolution or deliberate versioning.

Count wiring, deployment, configuration, and caller effort in the design cost.
A smaller module can create a larger system. Preserve required security,
accessibility, failure recovery, and data protection.

## Resolve and stop

Compare alternatives when tradeoffs matter. Use a small experiment when it
cheaply answers a technical question. Resolve consequential ambiguity without
reopening settled choices.

Record what the implementer cannot safely infer: contracts, affected areas,
dependent steps, and concrete success and failure examples. Identify suitable
verification. A routine choice needs a short explanation, not a design dossier.

Before finishing, trace a representative request through the design. Can anything
disappear or become clearer? Deliver the requested design; proceed to building
only when implementation is already authorized and sufficiently understood.
