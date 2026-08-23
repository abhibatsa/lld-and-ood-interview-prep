# Thread Pool Pattern

Maintain a fixed set of reusable worker threads that pull tasks from a
shared queue, instead of creating a new thread per task.

```java
ExecutorService pool = Executors.newFixedThreadPool(10);
pool.submit(() -> processOrder(order));
```

## Key points
- Creating a thread per request is expensive and unbounded — under load,
  this is a fast path to resource exhaustion (the exact
  [thread leak](./starvation-and-leaks.md) failure mode)
- Pool size is a real trade-off: too small underutilizes CPU/blocks
  callers; too large causes excessive context switching — mention this if
  asked to justify a pool size

**Remember:** "bounded thread pool with a task queue" is the answer to
nearly every "how would you handle concurrent requests" LLD follow-up —
know it cold.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
