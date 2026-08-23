# Reentrant Locks

A lock that the **same thread** can acquire multiple times without
deadlocking itself — each acquisition is counted, and the lock only fully
releases once the count returns to zero.

```java
ReentrantLock lock = new ReentrantLock();
void outer() {
    lock.lock();
    try { inner(); } finally { lock.unlock(); }
}
void inner() {
    lock.lock(); // same thread — this does NOT deadlock, because reentrant
    try { /* ... */ } finally { lock.unlock(); }
}
```

## Key points
- Without reentrancy, a method calling another synchronized method on the
  same object (same thread) would deadlock against itself — reentrant
  locks are the practical default for this reason (Java's `synchronized`
  keyword is reentrant by default)
- Still requires matching `lock()`/`unlock()` calls — an unbalanced
  unlock is a real bug source

**Remember:** know that `synchronized` in Java is already reentrant — a
common quick-fire interview question.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
