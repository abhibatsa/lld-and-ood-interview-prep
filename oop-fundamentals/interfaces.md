# Interfaces

A pure contract — method signatures with no implementation (default
methods aside) and no state. Defines *what* a class can do, not *how*.

```java
interface PaymentMethod {
    void pay(double amount);
}
class CreditCard implements PaymentMethod {
    public void pay(double amount) { /* ... */ }
}
```

## Key points
- "Program to an interface, not an implementation" — depend on `PaymentMethod`, not `CreditCard`, wherever you can
- A class can implement multiple interfaces (unlike single inheritance of classes)
- Interfaces are how you enable the [Strategy](../design-patterns/behavioral/strategy.md) and [Dependency Inversion](../design-principles/solid-with-code.md) patterns

**Remember:** if your method signature takes a concrete class instead of an
interface, ask yourself if that's really necessary — it's the #1 place
LLD interviews probe for coupling.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
