# Facade

**Intent:** provide a simplified, unified interface to a complex subsystem
of classes.

```java
class OrderFacade {
    InventoryService inventory; PaymentService payment; ShippingService shipping;
    void placeOrder(Order o) { // hides the orchestration complexity
        inventory.reserve(o); payment.charge(o); shipping.schedule(o);
    }
}
```

## When to use
Whenever a client would otherwise need to coordinate many subsystem
classes directly — Facade doesn't add new capability, it hides complexity
behind one clean entry point.

**Gotcha to mention:** Facade doesn't prevent direct access to the
subsystem if needed — it's a convenience layer, not a hard boundary
(that's closer to what Hexagonal Architecture does at a bigger scale).

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
