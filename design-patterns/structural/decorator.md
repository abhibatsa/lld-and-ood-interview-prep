# Decorator

**Intent:** attach new behavior to an object dynamically, by wrapping it,
without modifying its class or affecting other instances.

```java
interface Coffee { double cost(); }
class SimpleCoffee implements Coffee { public double cost() { return 2.0; } }
class MilkDecorator implements Coffee {
    Coffee inner;
    public double cost() { return inner.cost() + 0.5; } // wraps and adds
}
```

## When to use
When you need to add responsibilities to individual objects (not the
whole class) at runtime, and subclassing for every combination would
explode (coffee with milk, sugar, milk+sugar, milk+sugar+cream...).

**Gotcha to mention:** contrast with inheritance — inheritance adds
behavior to *every* instance of a subclass at compile time; Decorator adds
it to *specific* instances at runtime. That flexibility is the whole
value proposition.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
