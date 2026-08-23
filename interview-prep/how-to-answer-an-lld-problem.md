# How to Answer an LLD Interview Problem

**The framework — memorize this sequence, it works for every problem in
this repo.**

## 1. Clarify requirements (2-3 min)
Ask about scope. "Design a parking lot" is ambiguous — multiple floors?
Multiple vehicle types? Payment? Don't assume; ask, then explicitly state
what's out of scope.

## 2. Identify core entities (nouns) and actions (verbs) (3-5 min)
From the requirements, list the classes and their key responsibilities.
Say them out loud as you go — this is where the interviewer starts
forming an opinion of your thinking.

## 3. Define relationships (3-5 min)
Association, aggregation, composition, inheritance — see
[Class Relationships](../class-relationships/association.md). Sketch a
rough class diagram.

## 4. Apply patterns *only where they earn their complexity* (5-10 min)
Don't force a pattern. Ask: "what's the specific future change I'm
protecting against?" If you can't answer that, skip the pattern —
see [YAGNI](../design-principles/yagni.md).

## 5. Handle edge cases and concurrency (5 min)
What happens with concurrent access? (See [Optimistic vs Pessimistic
Locking](../concurrency/optimistic-vs-pessimistic-locking.md) for
booking-style problems.) What are the invalid states? Sketch a
[state machine](../uml/state-machine-diagram.md) if the entity has a
lifecycle.

## 6. Code the skeleton (10-15 min)
Working class signatures and key method bodies — doesn't need to compile
perfectly, needs to demonstrate the design is real, not hand-wavy.

## 7. Talk trade-offs (2-3 min)
State what you'd do differently at 10x scale, or what you simplified and
why. This is the single highest-leverage 2 minutes of the interview —
most candidates run out of time before reaching it. Budget for it.

## The one-sentence version, if you forget everything else

**Requirements → nouns/verbs → relationships → patterns only if justified
→ code the skeleton → talk trade-offs.**

---
*Part of [LLD & OOD Interview Prep](../README.md)*
