# Prototype

**Intent:** create new objects by cloning an existing instance, instead of
instantiating from scratch — useful when construction is expensive.

```java
interface Shape extends Cloneable { Shape clone(); }
Shape original = new Circle(radius: 10);
Shape copy = original.clone(); // cheaper than rebuilding from scratch
```

## When to use
When object creation is expensive (deep config, DB lookups) and you need
many similar-but-slightly-different instances — game object spawning,
document templates.

## When NOT to use
Rarely the first pattern reached for in interviews — it's real but less
commonly the "expected" answer compared to Factory/Builder/Singleton.
Mention it if the problem genuinely involves expensive object creation.

**Gotcha to mention:** shallow vs deep clone — if your object has nested
mutable objects, a shallow clone shares references and can cause subtle
bugs. Say which one your design needs and why.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
