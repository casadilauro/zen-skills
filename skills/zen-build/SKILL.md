---
name: zen-build
description: Use when implementing an understood software behavior or refactoring code to resolve a specific maintenance difficulty.
---

# Zen Build

Write ordinary code that makes its purpose and behavior easy to see.

Optimize for correctness, clarity, simplicity, explicitness, maintainability, then appropriate performance. Minimize unnecessary complexity, not line count.

## Repository first

Read the implementation, callers, tests, types, and project configuration.
Follow the user's scope, existing tools, and reasonable repository conventions.
Check existing helpers and platform facilities before adding code or dependencies.

## Functions and flow

- Give each function one coherent operation at a useful conceptual level.
- Extract a helper for a meaningful operation, algorithm, domain concept, or effect boundary.
- Do not split functions merely to reduce line count or add wrappers that only forward calls.
- Prefer flat control flow and guard clauses when they improve readability.
- Use intermediate variables when they explain intent. Dense expressions are not inherently simpler.

Use domain names consistently: nouns for values and verbs for operations.
Prefer calculate_total to process_data when that is the actual responsibility.
Do not alternate get, fetch, and load unless they mean different operations.

## Data and interfaces

Start with functions and ordinary data. Add classes for meaningful state,
invariants, identity, or lifecycle. Add interfaces for useful boundaries or
real variation, not hypothetical implementations.

- Share rules that must agree; allow independent policies to retain similar code.
- Keep one obvious public path for an operation, preserving required compatibility.
- Question boolean arguments that select unrelated operations: render_html and render_text may be clearer than render with an html flag. Boolean data is fine.
- Use meaningful constants, without naming every literal.
- Add configuration only for a real use case. Every option creates more states to understand and test.
- Use dependencies when their benefit justifies their maintenance cost; purity alone is not a reason to reject one.

## Effects and failures

Mutation is acceptable; surprising mutation is not. A function named as a
calculation should not unexpectedly modify its inputs.

- Make inputs, outputs, ownership, and external effects apparent.
- Separate loading, transformation, and saving when that makes the flow clearer.
- Validate untrusted data at entry boundaries; avoid redundant internal validation of established invariants.
- Preserve error context. Expected absence and failed operations need distinguishable behavior.
- Keep cleanup deterministic and multi-step writes recoverable where required.
- Preserve security, accessibility, compatibility, and protection against data loss.

Comments explain constraints or decisions the code cannot show. Record a
known limitation and when to revisit it; remove dead commented-out code.

## Complete and check

Finish affected callers, exports, configuration, fixtures, migrations, and docs.
For refactoring, establish baseline behavior and simplify in understandable
steps. Keep intentional behavior changes distinguishable from restructuring.

For bugs, reproduce the failure, trace callers, and correct the supported cause.
Retain a meaningful test or repeatable check for nontrivial behavior. Prefer
test-first when useful; derive expectations independently and cover relevant
failure cases and integration. Trivial edits need an appropriate direct check.

Run affected and required project checks. Measure performance claims. Inspect
the final diff for missing integration and accidental changes. Can a layer,
option, or dependency disappear? Can names, effects, or errors become clearer?
Report what ran and any failures or limits.
