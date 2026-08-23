# Bridge

**Intent:** decouple an abstraction from its implementation so both can
vary independently — avoids a combinatorial explosion of subclasses.

```java
interface Renderer { void renderCircle(); }          // implementation hierarchy
abstract class Shape { protected Renderer renderer; } // abstraction hierarchy
class Circle extends Shape { void draw() { renderer.renderCircle(); } }
```

## When to use
When you have two dimensions of variation (e.g., Shape × Renderer, Remote
× Device) that would otherwise multiply into N×M subclasses.

**Gotcha to mention:** Bridge is often confused with Strategy — Bridge is
a *structural* pattern splitting abstraction from implementation at
design time; Strategy is *behavioral*, swapping an algorithm at runtime.
Similar shape, different intent.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
