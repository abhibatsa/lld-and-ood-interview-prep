# Encapsulation

Bundling data and the methods that operate on it, while hiding internal
state from the outside world. The "protect your object's invariants" principle.

```java
class BankAccount {
    private double balance;   // hidden
    void withdraw(double amt) {
        if (amt > balance) throw new IllegalStateException("Insufficient funds");
        balance -= amt;
    }
}
```

## Key points
- Private fields + public methods = the classic implementation
- The point isn't hiding for its own sake — it's **protecting invariants** (balance can never go negative here)
- Getters/setters that just expose the raw field defeat the purpose — ask "what rule should this method enforce?"

**Remember:** in an interview, if you're adding a public setter with no
validation, say out loud why — often you shouldn't need one at all.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
