# Choosing Storage: SQL vs NoSQL at the Component Level

Don't pick one database for the whole system — pick per component, based
on that component's actual access pattern. (Full depth on this trade-off
lives in the [System Design repo](https://github.com/abhibatsa/architecting-software/blob/main/01-system-design-and-architecture/01-core-concepts/data-modeling-relational-vs-nosql.md) — this is the fast LLD-interview version.)

## The 10-second decision rule
- **Need joins, transactions, evolving query needs** (orders, payments,
  inventory) → relational
- **Need to store exactly the shape you'll read, fixed access pattern**
  (user profile cache, product catalog page, session data) → NoSQL/document

## Key points
- In an LLD interview, this usually comes up as a quick aside during
  schema design, not a deep dive — one sentence with reasoning beats
  silence or an unjustified default
- A hybrid answer ("relational for the order system, a cache/document
  store for the read-heavy catalog view") is often the strongest answer

**Remember:** justify your choice with the *access pattern*, not
familiarity — "I'd use Postgres here because orders need transactional
consistency across items and payment status" beats "I always use Postgres."

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
