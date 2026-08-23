# Compare-and-Swap (CAS)

An atomic CPU-level operation: "update this value to X, but only if it
currently equals the expected old value." If another thread changed it in
between, the operation fails and can be retried — no lock needed.

```java
AtomicInteger counter = new AtomicInteger(0);
counter.incrementAndGet(); // implemented internally via CAS, no mutex
```

## Key points
- The foundation of **lock-free** programming — avoids the overhead of
  blocking/context-switching that mutexes incur
- The typical pattern: read current value → compute new value → CAS it in
  → if it fails (someone else changed it first), retry the whole loop

**Remember:** "CAS gives you atomic updates without blocking — it's why
`AtomicInteger`/`AtomicReference` don't need a mutex internally." A strong
answer for the [Concurrent ID Generator](../concurrency-problems/concurrent-id-generator.md)
problem specifically.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
