# Builder

**Intent:** construct a complex object step by step, separating
construction from representation — avoids telescoping constructors.

```java
Pizza pizza = new Pizza.Builder()
    .size(Size.LARGE)
    .addTopping("cheese")
    .addTopping("mushroom")
    .build();
```

## When to use
Objects with many optional parameters, or objects that need to be
immutable once built. Classic interview fits: "design a meal ordering
system," "design an HTTP request builder."

## When NOT to use
Simple objects with 2-3 fields don't need it — a constructor is clearer.
Overusing Builder for trivial objects is a common over-engineering signal.

**Gotcha to mention:** Builder vs telescoping constructors vs a big
setter-based object — Builder's advantage is enforcing valid construction
while staying readable, especially for immutable objects.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
