# Tell, Don't Ask Principle

Tell an object what to do — don't ask for its internal state and then
make decisions about it from the outside. Keep behavior next to the data
it operates on.

```java
// Ask (breaks encapsulation): caller decides the logic
if (account.getBalance() >= amount) {
    account.setBalance(account.getBalance() - amount);
}

// Tell: object enforces its own rule
account.withdraw(amount); // throws internally if insufficient funds
```

## Key points
- Directly reinforces [encapsulation](../oop-fundamentals/encapsulation.md) — if you're calling three getters to make
  a decision, that logic probably belongs *inside* the object being asked
- Reduces the chance of two callers implementing the same business rule
  slightly differently (a DRY violation in disguise)
- Not absolute — sometimes you genuinely need to read state (e.g., for
  display). The principle is about avoiding *externalized decision logic*
  that should be internal

**Remember:** if you write `if (obj.getX() ...) obj.setY(...)`, ask
whether that logic belongs inside `obj` instead.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
