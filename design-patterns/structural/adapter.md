# Adapter

**Intent:** convert one interface into another that a client expects —
lets incompatible interfaces work together.

```java
class LegacyPrinter { void printOldFormat(String s) {} }
class PrinterAdapter implements ModernPrinter {
    LegacyPrinter legacy;
    public void print(String s) { legacy.printOldFormat(s); } // adapts the call
}
```

## When to use
Integrating a third-party/legacy API with an interface your system
expects — extremely common in real systems, and a favorite "have you
actually worked with legacy code" interview probe.

**Gotcha to mention:** Adapter changes an interface to match what's
expected; it doesn't add new behavior — that distinction is what separates
it from Decorator.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
