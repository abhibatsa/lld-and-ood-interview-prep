# Strategy

**Intent:** define a family of interchangeable algorithms, encapsulate
each one, and make them swappable at runtime.

```java
interface DiscountStrategy { double apply(double price); }
class Cart {
    DiscountStrategy strategy;
    double checkout(double price) { return strategy.apply(price); } // swap freely
}
```

## When to use
Any time you have multiple algorithms/behaviors for the same operation
that should be selectable at runtime — payment methods, sorting
strategies, pricing rules, route-finding algorithms. One of the highest-ROI
patterns to know cold — shows up constantly.

**Gotcha to mention:** this is the concrete mechanism behind [Composition
Over Inheritance](../../design-principles/composition-over-inheritance.md) — say that connection out loud, it signals deeper understanding than just naming the pattern.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
