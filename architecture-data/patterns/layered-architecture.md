# Layered Architecture (Controller-Service-Repository)

Organize code into horizontal layers, each depending only on the layer
below it: **Controller** (handles input) → **Service** (business logic) →
**Repository** (data access).

```java
class OrderController { OrderService service; /* handles HTTP request */ }
class OrderService { OrderRepository repo; /* business logic */ }
class OrderRepository { /* talks to the database */ }
```

![Layered vs Hexagonal architecture](../../assets/layered-vs-hexagonal-architecture.svg)

## When to use
The default, sensible choice for most LLD problems — it's what
interviewers expect unless the problem specifically calls for something
more decoupled (see Hexagonal).

## When NOT to use
Business logic can leak into controllers or repositories if discipline
slips — the layering only helps if you actually enforce "controller never
talks to repository directly."

**Remember:** naming your layers explicitly (even briefly, "I'd put
business rules in a service layer, keep the controller thin") signals
organized thinking beyond just class relationships.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
