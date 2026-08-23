# Condition Variables

Lets a thread **wait** until a specific condition becomes true, releasing
the lock while waiting (so other threads can make progress) and
re-acquiring it when woken.

```java
synchronized (queue) {
    while (queue.isEmpty()) { queue.wait(); }  // releases lock, sleeps
    // ... process item
}
// producer: queue.notify(); after adding an item
```

## Key points
- The direct mechanism behind [Producer-Consumer](./producer-consumer-pattern.md)
  — a consumer waits on "queue not empty," a producer signals it
- Always wait in a `while` loop, not an `if` — spurious wakeups are real,
  and re-checking the condition after waking is required for correctness

**Remember:** "wait releases the lock, notify wakes a waiter, but the
woken thread must re-check the condition" — this exact sequence is a
common interview follow-up question.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
