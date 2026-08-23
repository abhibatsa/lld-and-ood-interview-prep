# Semaphores

A counter-based lock that allows up to **N** threads into a section
concurrently — a generalization of the mutex (a mutex is a semaphore with
N=1, sometimes called a binary semaphore).

```java
Semaphore pool = new Semaphore(3); // max 3 concurrent connections
void useConnection() {
    pool.acquire();
    try { /* use one of 3 connections */ } finally { pool.release(); }
}
```

## When to use
Limiting concurrent access to a resource with fixed capacity —
connection pools, rate-limited API callers, bounded worker pools.

**Remember:** the interview-ready one-liner — "a semaphore generalizes a
mutex from 'one at a time' to 'N at a time'" — plus naming a concrete N-
capacity resource (connection pool) as the use case.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
