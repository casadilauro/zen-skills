---
name: zen-coordinate
description: Use when authorized delegation or independent review would benefit from separate contexts and ownership. Also use when explicitly asked to divide or integrate work across agents.
---

# Zen Coordinate

Another worker should remove more effort or uncertainty than its coordination introduces.

Optimize for correctness, clarity, simplicity, explicitness, maintainability, then appropriate performance. Minimize unnecessary complexity, not line count.

## Decide whether to divide

Read the task, dependencies, shared interfaces, and repository constraints.
Delegate only when authorized and useful.

Good candidates include independent investigations, distinct components with
stable contracts, and a separate review perspective. Keep a tightly coupled
change together when dividing it creates continual negotiation.

- Can the worker understand a complete, bounded question?
- Can it make progress without unfinished decisions elsewhere?
- Will combining the result cost less than doing the work directly?

More workers are not automatically more progress.

## Make ownership explicit

Give each worker:

- the requested outcome and concrete acceptance behavior;
- relevant inputs, outputs, errors, constraints, and settled decisions;
- owned files or a read-only assignment, plus the workspace;
- necessary checks and the limits of its authority.

Include the engineering expectations directly: prefer reuse and ordinary code,
make effects and failures visible, preserve contracts and protections, and verify
behavior with independent expectations. A separate philosophy document should
not be needed to understand the assignment.

Keep shared decisions in one place. Concurrent edits need nonconflicting
ownership; coordinate changes to shared tests, generated files, and Git state.
Use isolation where necessary. Workers do not gain authority to expand scope,
spend more, publish, or delegate further merely by receiving an assignment.

## Combine the work

Inspect artifacts as well as reports. Check for:

- incompatible assumptions about shared interfaces;
- missed callers or duplicate implementations of the same rule;
- lost validation, cleanup, compatibility, security, accessibility, or data protection;
- tests that pass separately but omit the integrated path.

Run checks for interactions the individual workers could not establish. Reuse
valid evidence, rerunning affected checks when integration changes the tested
state. Preserve others' work and resolve conflicting assumptions before proceeding.

## Before finishing

Can a handoff, worker, or shared abstraction disappear? Could one clear owner
replace repeated coordination?

Report the combined result, actual checks, and remaining dependencies or failures.
Several success reports do not establish that the assembled result works.
