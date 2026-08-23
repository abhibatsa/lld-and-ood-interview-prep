# State

**Intent:** let an object alter its behavior when its internal state
changes — looks like the object changed class.

```java
interface OrderState { void next(Order o); }
class PlacedState implements OrderState { public void next(Order o) { o.setState(new ConfirmedState()); } }
```

## When to use
State machines — order lifecycle, traffic light, media player
(playing/paused/stopped), connection states. Directly pairs with
[Enums](../../oop-fundamentals/enums.md) for the state identifiers.

**Gotcha to mention:** without this pattern, state logic tends to become a
sprawling `if/else` or `switch` on a status field scattered across the
codebase — State pattern localizes each state's behavior into its own
class, which is the concrete win to name.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
