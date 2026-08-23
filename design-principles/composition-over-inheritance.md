# Composition Over Inheritance

Prefer building behavior by composing small objects together ("has-a")
over deep inheritance hierarchies ("is-a") — because composition is more
flexible and doesn't lock you into a rigid class tree.

```java
// Inheritance-heavy (rigid): what about a robot duck that can't fly but can swim?
class Duck { void fly() {} void swim() {} }

// Composition (flexible): swap behaviors independently
class Duck {
    FlyBehavior flyBehavior;
    SwimBehavior swimBehavior;
    Duck(FlyBehavior f, SwimBehavior s) { flyBehavior = f; swimBehavior = s; }
}
```

## Key points
- This is literally the mechanism behind the [Strategy pattern](../design-patterns/behavioral/strategy.md) — composing in a behavior object instead of inheriting it
- Inheritance couples you to the parent's implementation *and* forces
  every subclass down the same rigid tree; composition lets you mix and
  match at runtime
- Classic interview tell: if you're inheriting from a class just to reuse
  one method, that's a composition candidate, not an inheritance one

**Remember:** "favor composition over inheritance" is one of the most
quoted OOP principles for a reason — bring it up explicitly when you
choose composition, it signals deliberate design, not default habit.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
