# Entities vs Value Objects

**Entity:** has a distinct identity that persists over time, even if its
attributes change (a `User` with the same `id` is the same user even
after they change their name).

**Value Object:** has no identity — defined entirely by its attributes,
immutable, and interchangeable if attributes match (`Money(100, "USD")`
equals any other `Money(100, "USD")`).

```java
class Money { // value object — immutable, equality by value
    final int amount; final String currency;
    boolean equals(Object o) { /* compares amount + currency */ }
}
```

![DDD building blocks](../../assets/ddd-building-blocks.svg)

## Key points
- Getting this distinction right avoids a common bug class: mutating a
  shared value object accidentally changes it everywhere it's referenced
- `Address`, `Money`, `DateRange` are classic value objects; `User`,
  `Order`, `Account` are classic entities

**Remember:** ask "does this need an `equals()` based on identity (id
field) or based on all its values?" — that answer tells you which one it is.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
