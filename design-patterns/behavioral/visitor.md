# Visitor

**Intent:** separate an algorithm from the object structure it operates
on, by letting you add new operations without modifying the classes.

```java
interface ShapeVisitor { void visit(Circle c); void visit(Square s); }
interface Shape { void accept(ShapeVisitor v); }
class Circle implements Shape { public void accept(ShapeVisitor v) { v.visit(this); } }
```

## When to use
When you need to perform many unrelated operations (export, render,
validate) across a fixed set of classes, and don't want to keep editing
every class each time you add an operation.

**Gotcha to mention:** the least commonly *expected* pattern in a typical
LLD round — mention it only if the problem genuinely has "many operations,
stable class hierarchy" shape (e.g., an AST/compiler-style problem);
forcing it elsewhere reads as pattern-name-dropping.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
