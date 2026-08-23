# Introduction to Concurrency

Concurrency = multiple tasks making progress during overlapping time
periods — they don't have to run at the exact same instant, just be
*in progress* together, potentially interleaved on a single core.

## Key points
- The reason concurrency is hard: shared mutable state accessed from
  multiple threads without coordination produces unpredictable results
- Concurrency is a *design* concern (how do tasks interleave correctly);
  [Parallelism](./concurrency-vs-parallelism.md) is an *execution* concern
  (are they literally simultaneous on multiple cores)

**Remember:** if a concurrency question comes up and you're not sure
where to start, say this out loud: "the core question is always — what
shared state exists, and what happens if two threads touch it at the same
time?"

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
