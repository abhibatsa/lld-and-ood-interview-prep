# Inheritance

An "is-a" relationship — a subclass inherits fields/methods from a parent
and can override behavior.

```java
class Vehicle { void move() { /* generic */ } }
class Car extends Vehicle { @Override void move() { /* car-specific */ } }
```

## Key points
- Only use it for genuine "is-a" relationships — a `Car` truly *is a*
  `Vehicle`. If it's really "has-a" or "behaves-like", use
  [composition](../class-relationships/composition.md) instead
- Deep inheritance hierarchies are a common LLD anti-pattern — 2-3 levels
  max is a reasonable rule of thumb
- Inheritance creates tight coupling to the parent's implementation — a
  parent class change can silently break every subclass

**Remember:** if you're inheriting just to reuse a method (not because of
a real "is-a" relationship), that's a signal to use composition instead —
see [Composition Over Inheritance](../design-principles/composition-over-inheritance.md).

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
