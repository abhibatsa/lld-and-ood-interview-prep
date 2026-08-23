# Bounded Contexts and Ubiquitous Language

**Bounded Context:** a explicit boundary within which a domain model is
defined and consistent — the same word can mean different things in
different contexts, and that's fine.

```
"Customer" in the Sales context: has a sales rep, a discount tier
"Customer" in the Support context: has a ticket history, an SLA tier
```

![DDD building blocks](../../assets/ddd-building-blocks.svg)

## Key points
- **Ubiquitous Language:** the shared vocabulary between engineers and
  domain experts, used consistently *within* one bounded context —
  reduces translation errors between "what the business says" and "what
  the code says"
- Large interview problems (Uber, Splitwise, a marketplace) often
  implicitly span multiple bounded contexts (Booking vs Payments vs
  Ratings) — naming this explicitly is a strong senior-level signal

**Remember:** don't force one giant unified model across a whole system —
say "I'd treat Payments and Booking as separate bounded contexts with
their own Order concept" if the problem is big enough to warrant it.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
