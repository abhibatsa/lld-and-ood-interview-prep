# Dependency

The weakest, most transient relationship — one class uses another only
briefly, often just as a method parameter or local variable, with no
stored reference.

```java
class OrderService {
    void process(Order order, Logger logger) { // Logger is a dependency, not a field
        logger.log("Processing " + order.getId());
    }
}
```

![Class relationships compared](../assets/class-relationships-overview.svg)

## Key points
- No persistent link — the moment the method returns, the relationship is gone
- Still worth naming explicitly on a class diagram — dependencies are exactly what [Dependency Injection](../design-principles/solid-with-code.md) manages
- Changing the dependency's interface can still break the dependent class, even though there's no stored reference — that's why it's still a real coupling relationship, just a shallow one

**Remember:** the four relationships in increasing strength: **Dependency
< Association < Aggregation < Composition.**

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
