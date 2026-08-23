# Reader-Writer Pattern

Allow multiple concurrent **readers** (since reads don't conflict with
each other), but require exclusive access for a **writer** (since writes
conflict with everything).

```java
ReadWriteLock rwLock = new ReentrantReadWriteLock();
void read() { rwLock.readLock().lock(); try { /* many readers OK */ } finally { rwLock.readLock().unlock(); } }
void write() { rwLock.writeLock().lock(); try { /* exclusive */ } finally { rwLock.writeLock().unlock(); } }
```

## When to use
Read-heavy workloads where a plain mutex would unnecessarily serialize
reads that don't actually conflict — caches, config objects, in-memory
lookup tables that are read constantly and written rarely.

## Key trade-off to mention
Writer starvation is a real risk if reads are continuous — a steady
stream of readers can keep a writer waiting indefinitely. Fair
implementations (like Java's `ReentrantReadWriteLock` in fair mode)
address this at some throughput cost.

**Remember:** "many readers, one writer, readers don't block each other"
— name this pattern explicitly any time a design has a read-heavy,
write-rare shared resource.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
