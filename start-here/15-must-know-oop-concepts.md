# 15 Must-Know OOP Concepts

**The fastest possible refresher — one line each, in the order they usually
come up.**

1. **Class** — the blueprint; **Object** — the instance
2. **Encapsulation** — hide internal state, expose behavior through methods
3. **Abstraction** — expose *what* an object does, hide *how*
4. **Inheritance** — "is-a" relationship; reuse + override behavior
5. **Polymorphism** — same interface, different behavior at runtime (or compile time, for overloading)
6. **Interface vs Abstract Class** — interface = pure contract, no state; abstract class = partial implementation + state
7. **Composition over Inheritance** — favor "has-a" over "is-a" for flexibility (see [dedicated doc](../design-principles/composition-over-inheritance.md))
8. **Association / Aggregation / Composition** — increasing strength of ownership between objects
9. **Coupling** — how much one class depends on another's internals; keep it low
10. **Cohesion** — how focused a class's responsibilities are; keep it high
11. **Immutability** — an object whose state can't change after construction; thread-safe by default
12. **SOLID** — the five principles that keep a design maintainable as it grows
13. **Design Pattern** — a named, reusable solution to a recurring design problem
14. **Method Overloading vs Overriding** — overloading = same name, different params, compile-time; overriding = subclass replaces parent behavior, runtime
15. **Enum** — a fixed, type-safe set of constants — underused for state machines and strategy selection

## Say this out loud once before you go in

> "Low coupling, high cohesion, program to an interface not an
> implementation, favor composition over inheritance."

That sentence alone signals you know what actually matters, not just
vocabulary.

---
*Part of [LLD & OOD Interview Prep](../README.md)*
