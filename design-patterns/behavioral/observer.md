# Observer

**Intent:** define a one-to-many dependency so that when one object
(subject) changes state, all dependents (observers) are notified
automatically.

```java
interface Observer { void update(Event e); }
class Subject {
    List<Observer> observers;
    void notifyAll(Event e) { observers.forEach(o -> o.update(e)); }
}
```

## When to use
Extremely high-frequency interview pattern — Pub/Sub systems, notification
systems, stock price tickers, event-driven UI updates.

**Gotcha to mention:** naive Observer with synchronous notification can
block the subject if an observer is slow — mention async notification
(queue/event bus) as a production-grade improvement if the interviewer
pushes on scale.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
