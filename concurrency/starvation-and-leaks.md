# Thread Starvation and Resource Leaks

**Starvation:** a thread never gets the CPU time or lock access it needs
— technically not blocked forever like deadlock, but effectively never
makes progress because other threads keep getting priority.

**Thread leak:** threads are created but never properly terminated/
returned to a pool — they accumulate, eventually exhausting memory or
hitting OS thread limits.

```java
// Common leak: forgetting to shut down an ExecutorService
ExecutorService pool = Executors.newFixedThreadPool(10);
// ... if pool.shutdown() is never called, threads never terminate
```

## Key points
- Starvation often comes from unfair locks or naive priority scheduling —
  a fair lock (`ReentrantLock(true)` in Java) trades some throughput for
  guaranteeing FIFO-ish access
- Thread leaks are one of the most common real production bugs — always
  use a bounded thread pool with proper shutdown, not raw unmanaged
  thread creation

**Remember:** starvation and deadlock get confused — "deadlock: stuck
forever, provably. Starvation: technically could progress, but keeps
losing out in practice." Different root causes, different fixes.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
