# Template Method

**Intent:** define the skeleton of an algorithm in a base class, letting
subclasses override specific steps without changing the algorithm's
structure.

```java
abstract class DataProcessor {
    final void process() { readData(); transform(); saveData(); } // fixed skeleton
    abstract void transform(); // subclasses customize this step only
    void readData() { /* shared default */ }
    void saveData() { /* shared default */ }
}
```

## When to use
When multiple classes share the same overall algorithm but differ in one
or two specific steps — report generation, data import pipelines with
different transform logic per source.

**Gotcha to mention:** contrast with Strategy — Template Method uses
inheritance to vary *one step* of a fixed algorithm; Strategy uses
composition to swap the *entire* algorithm. Different tools for a similar
sounding problem.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
