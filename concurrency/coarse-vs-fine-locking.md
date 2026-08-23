# Coarse-grained vs Fine-grained Locking

**Coarse-grained:** one lock protects a large chunk of state (e.g., one
lock for an entire `Bank` object). Simple, but limits concurrency —
threads touching *unrelated* accounts still block each other.

**Fine-grained:** separate locks per smaller unit (e.g., one lock per
`Account`). More concurrency, but more complexity and new risk: multiple
locks can deadlock if acquired in inconsistent order.

```java
class Bank { Object lock; /* coarse: one lock for all accounts */ }
class Account { Object lock; /* fine: lock per account */ }
```

## Key points
- The trade-off is always **simplicity/safety vs throughput** — start
  coarse, only go fine-grained if profiling shows real lock contention
- Fine-grained locking reintroduces [deadlock](./deadlock.md) risk if
  locks aren't acquired in a consistent global order across all code paths

**Remember:** "coarse-grained is safer and simpler, fine-grained is faster
but reintroduces deadlock risk if you're not careful with lock ordering"
— have this trade-off ready, it comes up in Bank/ATM-style problems constantly.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
