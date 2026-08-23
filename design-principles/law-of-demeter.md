# Law of Demeter (Principle of Least Knowledge)

Only talk to your immediate friends — a method should only call methods
on: itself, its own fields, its parameters, or objects it directly
creates. Not on objects returned by those.

```java
// Violation: reaching through multiple objects ("train wreck")
order.getCustomer().getAddress().getCity();

// Better: ask the order directly, let it delegate internally
order.getCustomerCity();
```

## Key points
- The giveaway is a chain of dots (`a.getB().getC().getD()`) — each link
  is a hidden dependency on that object's internal structure
- Violating this creates fragile code: if `Customer`'s internal structure
  changes, every caller reaching through it breaks
- Directly supports low coupling — one of the most-repeated LLD interview
  phrases ("low coupling, high cohesion") has this principle as one of
  its concrete enforcement mechanisms

**Remember:** if your code has more than one dot chained past the object
you were originally given, that's usually a Law of Demeter violation
worth calling out.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
