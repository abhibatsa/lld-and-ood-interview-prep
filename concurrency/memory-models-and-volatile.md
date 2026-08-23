# Memory Models and the Volatile Keyword

Modern CPUs and compilers reorder instructions and cache values per-core
for performance — a **memory model** defines the rules for when a write by
one thread becomes visible to another.

```java
class Flag {
    volatile boolean stop = false; // guarantees visibility across threads
}
```

## Key points
- Without `volatile` (Java) or equivalent memory barriers, a thread may
  keep reading a stale, cached value of a variable another thread already
  changed — not a hypothetical, a real production bug class
- `volatile` guarantees **visibility**, not **atomicity** — `volatile int
  count; count++;` is still a race condition, because increment isn't
  atomic even if reads/writes are visible

**Remember:** the distinction to have ready — "volatile makes writes
visible across threads; it does NOT make compound operations like
increment atomic." Confusing these two is a very common interview
mistake, catching it is a real signal.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
