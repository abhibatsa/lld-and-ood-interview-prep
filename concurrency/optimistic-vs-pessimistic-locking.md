# Optimistic vs Pessimistic Locking

**Pessimistic locking:** acquire a lock *before* touching the data,
assuming conflicts are likely — blocks other threads/transactions until
released.

**Optimistic locking:** don't lock upfront; read data, do work, then check
(usually via a version number) if it changed before committing — if it
did, retry.

```sql
-- Optimistic: version-checked update
UPDATE seats SET status='booked', version=version+1
WHERE seat_id=42 AND version=3;  -- fails silently (0 rows) if someone else booked first
```

## When to use which
- **Pessimistic** — high contention expected, conflicts are common and
  costly to retry (e.g., booking the *last* seat at a popular concert)
- **Optimistic** — low contention expected, most operations don't
  actually conflict (e.g., editing different fields of a large document)

## The critical LLD application
This is **the** concurrency answer for Concert/Movie Ticket Booking
problems — how do you prevent double-booking the same seat? Pessimistic
locking (`SELECT ... FOR UPDATE`) or optimistic locking (version-checked
update, retry on conflict) are the two legitimate answers — pick one and
justify it based on expected contention.

**Remember:** if the interviewer asks "what happens if two users click
'book' on the same seat at the same instant," this doc is the answer —
don't skip naming a concrete mechanism.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
