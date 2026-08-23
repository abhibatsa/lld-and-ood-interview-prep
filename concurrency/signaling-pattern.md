# Signaling Pattern

One thread explicitly signals another that a condition has changed,
instead of the second thread repeatedly checking (polling/busy-waiting).

```java
synchronized (lock) {
    while (!ready) lock.wait();  // sleeps until signaled — no CPU wasted polling
}
// elsewhere:
synchronized (lock) { ready = true; lock.notifyAll(); }
```

## Key points
- The alternative — busy-waiting (`while (!ready) {}`) — wastes CPU
  spinning and is a real anti-pattern interviewers watch for
- `notify()` wakes one waiting thread (unspecified which); `notifyAll()`
  wakes all of them — use `notifyAll()` unless you're certain only one
  waiter should ever proceed, to avoid missed-wakeup bugs

**Remember:** if your design has any thread looping and checking a
condition repeatedly, replace it with wait/notify (or a
[Condition Variable](./condition-variables.md)) — polling is a concrete,
callable-out inefficiency.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
