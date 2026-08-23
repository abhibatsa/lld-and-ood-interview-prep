# Abstraction

Exposing *what* an object does while hiding *how* it does it. Related to
encapsulation but a different axis: encapsulation hides data, abstraction
hides complexity.

```java
interface Notifier { void send(String message); }
// caller doesn't know or care if it's Email, SMS, or Push under the hood
```

## Key points
- Achieved via interfaces and abstract classes
- The caller depends on the abstraction, never the concrete implementation
- This is what lets you swap an implementation later without touching calling code

**Remember:** "abstraction" and "encapsulation" get confused constantly —
encapsulation = hide *data*, abstraction = hide *complexity/detail*. Know
the distinction, interviewers do ask.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
