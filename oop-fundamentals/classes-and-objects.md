# Classes and Objects

**Class** — a blueprint defining state (fields) and behavior (methods).
**Object** — a runtime instance of a class, with its own copy of state.

```java
class Car {
    private String model;      // state
    Car(String model) { this.model = model; }
    void drive() { /* behavior */ }
}
Car myCar = new Car("Model 3"); // object
```

## Key points
- A class defines *shape*; an object is *memory allocated to that shape*
- Multiple objects of the same class share method code, not state
- In an interview, naming your classes well (nouns from the requirements) is itself a signal of clear thinking

**Remember:** if you're struggling to name a class, it's often a sign the
responsibility itself is unclear — fix the design, not the name.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
