# Race Conditions and Critical Sections

**Race condition:** the correctness of a result depends on the
unpredictable timing/interleaving of multiple threads.

**Critical section:** the part of code that accesses shared state and
must not be executed by more than one thread at a time.

```java
// Classic race condition
count++; // actually 3 steps: read, increment, write — another thread can interleave
```

## Key points
- The fix is always the same shape: protect the critical section with a
  synchronization primitive ([Mutex](./mutex.md), etc.) so only one thread
  executes it at a time
- Race conditions are notoriously hard to catch in testing — they may not
  manifest under low load and only appear in production under real
  concurrent traffic

**Remember:** `count++` looking like "one operation" is the classic trap —
say out loud that it's actually read-modify-write, three steps, any of
which can be interleaved by another thread.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
