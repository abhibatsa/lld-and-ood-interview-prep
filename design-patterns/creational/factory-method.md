# Factory Method

**Intent:** let a superclass defer object creation to subclasses, without
the caller knowing the concrete class being created.

```java
interface NotificationFactory { Notification create(); }
class EmailFactory implements NotificationFactory {
    public Notification create() { return new EmailNotification(); }
}
```

## When to use
When object creation logic varies by type and you want callers decoupled
from concrete classes — classic case: "design a notification system"
(Email/SMS/Push) or "design a parking lot" (different vehicle/spot types).

## When NOT to use
If there's only one implementation and no near-term signal of more,
skip it — plain `new` is fine (YAGNI applies here directly).

**Gotcha to mention:** distinguish this from Abstract Factory — Factory
Method creates *one* product via inheritance; Abstract Factory creates
*families* of related products via composition.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
