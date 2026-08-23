# Domain Events and Handlers

**Domain Event:** something meaningful that happened in the domain
(`OrderPlaced`, `PaymentFailed`) — modeled as an explicit object, not just
a side effect buried in a method.

```java
class OrderPlacedEvent { String orderId; Instant occurredAt; }
interface EventHandler<T> { void handle(T event); }
class InventoryHandler implements EventHandler<OrderPlacedEvent> {
    public void handle(OrderPlacedEvent e) { /* reserve stock */ }
}
```

## Key points
- This is [Observer](../../design-patterns/behavioral/observer.md) applied
  at the domain-modeling level, with events as first-class named objects
  instead of generic notifications
- Decouples "what happened" from "what should happen as a result" —
  useful when one action (placing an order) triggers multiple unrelated
  downstream effects (inventory, notifications, analytics)

**Remember:** if your design has one method doing five unrelated things
(charge payment AND send email AND update inventory AND log analytics),
that's a signal to extract a domain event and let separate handlers react
— cleaner and easier to extend later.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
