# KISS Principle

**K**eep **I**t **S**imple, **S**tupid — prefer the simplest design that
correctly solves the actual problem.

## Key points
- KISS, YAGNI, and DRY overlap but aren't identical: YAGNI is about
  *scope* (don't build unneeded features), KISS is about *design
  complexity* (don't over-architect what you do build), DRY is about
  *duplication*
- A simple design that's easy to extend later usually beats a "clever"
  design that's hard to reason about — simplicity often *is* the
  extensibility strategy
- In interviews, explaining *why* you kept something simple ("I didn't add
  a factory here because there's only one implementation type and no
  signal we'll need more") is stronger than silently being simple

**Remember:** if you can't explain your design to someone in two
sentences, it's probably not simple enough yet.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
