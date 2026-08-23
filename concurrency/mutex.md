# Mutex

**Mut**ual **ex**clusion — a lock that allows exactly one thread into a
critical section at a time. The most basic synchronization primitive.

```java
private final Object lock = new Object();
void increment() {
    synchronized (lock) { count++; } // only one thread at a time
}
```

## Key points
- Whoever locks it must unlock it — forgetting to release (or an
  exception skipping the unlock) causes every other thread to block
  forever. Always release in a `finally` block if not using `synchronized`
- A mutex is binary — locked or unlocked. Compare with
  [Semaphores](./semaphores.md), which allow N concurrent holders

**Remember:** the fastest way to say this correctly in an interview:
"a mutex ensures only one thread executes the critical section at a time
— it's the primitive that turns a race condition into safe sequential
access."

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
