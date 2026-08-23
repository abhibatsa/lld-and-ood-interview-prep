# DRY Principle

**D**on't **R**epeat **Y**ourself — every piece of knowledge should have a
single, unambiguous representation in the system.

```java
// Bad: tax calculation duplicated in two places
double checkoutTax = price * 0.18;
double invoiceTax = price * 0.18;

// Good: single source of truth
double tax = TaxCalculator.calculate(price);
```

## Key points
- DRY is about **knowledge duplication**, not just code duplication — two
  similar-looking code blocks that represent *different* business rules
  are not a DRY violation, even if they look alike
- Over-applying DRY (forcing unrelated things to share code because they
  look similar today) creates brittle, wrongly-coupled abstractions — this
  is a real anti-pattern interviewers watch for

**Remember:** if you're about to copy-paste business logic, stop. If
you're about to force two unrelated concepts to share an abstraction just
because the code looks similar, also stop.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
