# Performance and Concurrency

Do not pay complexity costs without a reason.

## Measure First

Optimize when:

- profiling shows a bottleneck
- scale requirements clearly demand it
- algorithmic complexity is obviously unsuitable
- performance is the explicit task

Prefer measurement over intuition.

## Optimization Order

Consider, roughly:

1. Better algorithm.
2. Avoid unnecessary work.
3. Avoid unnecessary I/O.
4. Avoid unnecessary materialization.
5. Batch operations.
6. Improve data representation.
7. Use optimized libraries.
8. Parallelize where appropriate.
9. Micro-optimize only when measurement justifies it.

## Streaming

Prefer iterators and streaming when datasets are large and random access is
unnecessary.

## Concurrency

Concurrency multiplies complexity.

Use it when benefit is concrete.

## Async

Use async for meaningfully asynchronous I/O architectures.

Do not create async wrappers around synchronous work merely for appearance.

## Threads

Threads can be appropriate for I/O-bound work or libraries releasing the GIL.

Do not assume threads accelerate CPU-bound Python.

## Multiprocessing

Use multiprocessing when process-level parallelism solves a real CPU-bound
problem and serialization/process overhead is acceptable.

## Batching

Batch when fixed per-operation overhead dominates.

Keep batch size configurable only when a real tuning need exists.

## Clarity

When performance requires non-obvious code, document why the complexity is
necessary.
