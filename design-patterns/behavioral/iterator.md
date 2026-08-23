# Iterator

**Intent:** provide a way to access elements of a collection sequentially
without exposing its underlying representation.

```java
Iterator<Order> it = orderList.iterator();
while (it.hasNext()) { Order o = it.next(); }
```

## When to use
Basically always available for free in modern languages (`for-each`,
`Iterable`) — worth naming explicitly when designing a *custom* collection
type (e.g., a tree structure, a paginated result set) that needs its own
traversal logic.

**Gotcha to mention:** the win is decoupling traversal logic from the
collection's internal structure — callers don't need to know if it's an
array, linked list, or tree underneath.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
