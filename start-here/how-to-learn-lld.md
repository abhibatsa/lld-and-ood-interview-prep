# How to Learn LLD

**Night-before refresher — read this first, it's the map for everything else.**

LLD interviews test one thing: **can you turn a fuzzy requirement into a
class design that's correct, extensible, and doesn't fall over the moment
someone asks "what if we added X?"**

## The order that actually works (cramming tonight)

1. **OOP Fundamentals** (30 min) — if these aren't automatic, nothing else lands
2. **Class Relationships** (10 min) — association/aggregation/composition, the vocabulary you'll use out loud
3. **SOLID + core principles** (20 min) — the "why" behind every good answer
4. **Design Patterns** (skim all, deep on Strategy/Observer/Factory/Singleton/Decorator — these five cover 80% of real interviews)
5. **Concurrency basics** (if the role is backend-heavy) — mutex, race conditions, deadlock, producer-consumer
6. **Pick 3 problems and actually solve them on paper** — reading solutions ≠ being able to produce one under pressure

## The interview flow, in one line

**Requirements → identify nouns (classes) and verbs (methods) → relationships → apply a pattern only if it earns its complexity → code the skeleton → talk trade-offs.**

## The single biggest mistake

Jumping straight to a design pattern before nailing down requirements.
Patterns are a *response* to a specific flexibility need — if you can't
say which future change you're protecting against, you're pattern-matching
from memory, not designing.

---
*Part of [LLD & OOD Interview Prep](../README.md)*
