# Polymorphism

The same interface/method call producing different behavior depending on
the actual runtime type of the object.

```java
List<Shape> shapes = List.of(new Circle(), new Square());
for (Shape s : shapes) s.draw(); // each draws differently — one call, different behavior
```

## Key points
- **Runtime polymorphism** — method overriding, resolved at runtime (this is what "polymorphism" usually means in interviews)
- **Compile-time polymorphism** — method overloading, resolved at compile time (weaker form, still worth naming)
- This is the mechanism that makes the [Strategy](../design-patterns/behavioral/strategy.md) and [Template Method](../design-patterns/behavioral/template-method.md) patterns work

**Remember:** if your design has a chain of `if (type == X) ... else if
(type == Y)`, that's almost always a sign you should be using
polymorphism instead — a strong LLD interview signal either way.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
