# Composition

A "has-a" relationship with **exclusive** ownership — the child's
lifecycle is tied to the parent's. Delete the parent, the child goes too.

```java
class House {
    private final List<Room> rooms = new ArrayList<>(); // rooms don't exist without the house
}
```

![Class relationships compared](../assets/class-relationships-overview.svg)

## Key points
- Represented in UML with a filled/solid diamond on the owner's side
- Strongest of the three "has-a" relationships
- Also the name of the design principle "favor composition over
  inheritance" — related concept, don't conflate the two meanings in an
  interview; clarify which you mean if it's ambiguous

**Remember:** rooms don't survive a demolished house — that's composition.
Professors survive a closed department — that's aggregation.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
