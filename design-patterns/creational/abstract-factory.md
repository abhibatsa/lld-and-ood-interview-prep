# Abstract Factory

**Intent:** create families of related objects without specifying their
concrete classes.

```java
interface UIFactory { Button createButton(); Checkbox createCheckbox(); }
class DarkThemeFactory implements UIFactory {
    public Button createButton() { return new DarkButton(); }
    public Checkbox createCheckbox() { return new DarkCheckbox(); }
}
```

## When to use
When you need to guarantee a *consistent family* of objects are used
together — e.g., all UI components matching one theme, or all payment
components matching one region's regulatory rules.

## When NOT to use
Adds real complexity (a factory of factories) — don't reach for it unless
you genuinely have multiple related product families, not just multiple
products.

**Gotcha to mention:** this is Factory Method one level up — Factory
Method returns one type; Abstract Factory returns an interface exposing
several related factory methods.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
