# Enums

A fixed, type-safe set of named constants. Underused in interviews —
reach for an enum instead of a `String status` or magic `int` every time.

```java
enum OrderStatus { PLACED, CONFIRMED, SHIPPED, DELIVERED, CANCELLED }
```

## Key points
- Enums can have fields, constructors, and methods in Java — not just labels
- Great for **state machines** (order status, traffic light state) — pairs directly with the [State pattern](../design-patterns/behavioral/state.md)
- Prevents invalid values at compile time — `"Shiped"` (typo) can't happen with an enum, it can with a string

**Remember:** if an interviewer sees you use `String` for a fixed set of
states, that's a small but real signal — use an enum instead.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
