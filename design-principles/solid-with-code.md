# SOLID Principles with Code

Quick code-level refresher for each — the version you actually reproduce
on a whiteboard.

## Single Responsibility Principle
```java
// Bad: Invoice both calculates AND persists AND formats — 3 reasons to change
class Invoice { void calculate() {} void saveToDb() {} void printPdf() {} }
// Good: split by responsibility
class InvoiceCalculator {}
class InvoiceRepository {}
class InvoicePrinter {}
```

## Open/Closed Principle
```java
// Bad: editing this method every time a new shape is added
double area(Object shape) { if (shape instanceof Circle) ... else if (shape instanceof Square) ... }
// Good: extend via polymorphism, don't modify existing code
interface Shape { double area(); }
class Circle implements Shape { public double area() { return Math.PI * r * r; } }
```

## Liskov Substitution Principle
```java
// Bad: Square breaks Rectangle's contract (setWidth shouldn't change height)
class Square extends Rectangle {
    @Override void setWidth(int w) { super.setWidth(w); super.setHeight(w); } // surprising side effect
}
// Fix: Square and Rectangle shouldn't share an inheritance relationship at all
```

## Interface Segregation Principle
```java
// Bad: forces every worker to implement eat(), even robots
interface Worker { void work(); void eat(); }
// Good: split by capability
interface Workable { void work(); }
interface Eatable { void eat(); }
```

## Dependency Inversion Principle
```java
// Bad: high-level class depends on a concrete low-level class
class OrderService { MySqlRepository repo = new MySqlRepository(); }
// Good: depend on an abstraction, inject the implementation
class OrderService { Repository repo; OrderService(Repository repo) { this.repo = repo; } }
```

**Remember:** you don't need to recite the acronym — walking through *one*
violation-and-fix like the ones above, live, is worth more than reciting
all five definitions from memory.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
