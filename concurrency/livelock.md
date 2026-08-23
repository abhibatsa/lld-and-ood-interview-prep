# Livelock

Threads aren't blocked (unlike deadlock) — they're actively responding to
each other, but no actual progress happens. Classic analogy: two people in
a hallway both stepping aside the same direction, repeatedly, forever.

```java
// Both threads politely "back off" on conflict and retry — forever, in lockstep
while (!tryAcquireBoth()) { releaseAll(); sleep(random); retry(); }
```

## Key points
- Often introduced *by* a deadlock-avoidance strategy done poorly (both
  threads back off identically and collide again on retry)
- Fix: introduce randomized backoff (jitter) so retries don't stay in
  lockstep — this is also why exponential backoff with jitter is standard
  in distributed retry logic, not just local concurrency

**Remember:** "deadlock = stuck and blocked; livelock = busy but stuck" —
have that one-line distinction ready, it's a common quick-fire question.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
