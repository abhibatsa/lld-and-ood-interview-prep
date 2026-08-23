# Translating Class Diagrams to Entity-Relationship (ER) Diagrams

Almost every modern LLD interview expects you to sketch the underlying
schema, not just classes — this is the fast mental translation.

```
Class diagram:              →   ER diagram:
Order 1---* OrderItem           orders(id PK, customer_id FK, status)
Order *---1 Customer            order_items(id PK, order_id FK, sku, qty)
                                 customers(id PK, name, email)
```

## The translation rules
- **Composition/Aggregation → foreign key** on the "many" side, pointing
  back to the "one" side
- **Association → foreign key** on either side, or a join table if
  many-to-many
- **Class attributes → table columns**, with types
- **Inheritance → three options**: single table (one table, nullable
  columns per subtype), class-table (one table per class, joined), or
  concrete-table (one table per concrete subclass) — mention the trade-off
  (simplicity vs normalization) if it comes up

**Remember:** draw this *after* your class diagram, not instead of it —
in interviews, showing you can go from OOP model to relational schema in
under a minute is a strong, fast signal.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
