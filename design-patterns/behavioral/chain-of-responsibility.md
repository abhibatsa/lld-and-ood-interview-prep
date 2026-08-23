# Chain of Responsibility

**Intent:** pass a request along a chain of handlers until one handles it
— decouples sender from the specific receiver.

```java
abstract class Handler {
    Handler next;
    void handle(Request r) {
        if (canHandle(r)) process(r); else if (next != null) next.handle(r);
    }
}
```

## When to use
Middleware/filter chains (auth → logging → rate limiting → business
logic), approval workflows (manager → director → VP based on amount),
support ticket escalation.

**Gotcha to mention:** every handler needs a clear "can I handle this or
pass it on" rule — an ambiguous chain (multiple handlers could both claim
a request) is a design smell worth flagging if it comes up.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
