# Try-Lock and Timed Locking

Instead of blocking indefinitely to acquire a lock, `tryLock()` returns
immediately (success/failure), and a timed version waits up to a bounded
duration before giving up.

```java
if (lock.tryLock(500, TimeUnit.MILLISECONDS)) {
    try { /* got it */ } finally { lock.unlock(); }
} else {
    // couldn't acquire in time — fail fast, retry, or fall back
}
```

## When to use
Avoiding indefinite blocking in latency-sensitive systems — better to
fail fast or fall back than hang a request thread forever waiting on a
contended lock. Also useful for deadlock avoidance strategies (give up
and retry rather than wait forever).

**Remember:** "graceful degradation under lock contention" is the phrase
to use — tryLock is what makes that possible instead of a thread hanging
indefinitely.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
