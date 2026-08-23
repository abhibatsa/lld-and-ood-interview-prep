# Immutability in Data Models (Event Sourcing & Audit Logs)

Instead of storing and overwriting current state, store the sequence of
**events** that led to that state — current state becomes a derived view,
never the source of truth.

```
Traditional: accounts.balance = 500  (overwritten on every transaction)
Event-sourced: [Deposited(300), Deposited(300), Withdrew(100)] → balance derived = 500
```

## When to use
Audit-heavy domains (banking, Splitwise-style expense tracking, order
history) where "what happened and when" matters as much as "what's true
now." Directly relevant to fintech-flavored LLD problems.

## When NOT to use
Adds real complexity (replaying events to get current state, event schema
versioning) — don't reach for it unless the problem genuinely needs a full
audit trail or point-in-time reconstruction.

**Remember:** even without full event sourcing, storing **immutable
value objects** (see [Entities vs Value Objects](../ddd/entities-vs-value-objects.md))
for things like `Transaction` records gets you most of the audit-safety
benefit with far less complexity — mention this middle ground if the
problem doesn't justify full event sourcing.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
