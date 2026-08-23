# CQRS (Command Query Responsibility Segregation)

Split the model used for **writes** (Commands — change state) from the
model used for **reads** (Queries — return data) — they don't have to be
the same shape.

```java
// Command side — optimized for validating and applying changes
class PlaceOrderCommand { void execute() { /* validate, mutate, persist */ } }
// Query side — optimized for fast, denormalized reads
class OrderSummaryQuery { OrderSummaryDto fetch(String orderId) { /* read-optimized */ } }
```

## When to use
When read and write patterns genuinely diverge — high-read systems
(dashboards, feeds) that need denormalized/cached read models distinct
from the normalized write model. Directly relevant for **Pub/Sub** and
**Stock Brokerage** style problems where reads (price feeds, order books)
and writes (placing trades) have very different performance needs.

## When NOT to use
Adds real complexity (often two data models, sometimes two data stores)
— don't reach for it unless the problem has a genuine read/write
asymmetry. Mentioning it without justification reads as pattern-dropping.

**Remember:** CQRS is often paired with event sourcing in real systems,
but the two are independent — you can do CQRS with a normal database on
both sides. Don't conflate them if asked.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
