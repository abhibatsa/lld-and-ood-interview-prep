# Command

**Intent:** encapsulate a request as an object, so you can parameterize,
queue, log, or undo operations.

```java
interface Command { void execute(); void undo(); }
class AddTextCommand implements Command {
    public void execute() { doc.append(text); }
    public void undo() { doc.remove(text); }
}
```

## When to use
Undo/redo systems (text editors, drawing apps), task queues/job
scheduling, macro recording. "Design a text editor with undo" is a
classic Command-pattern interview problem.

**Gotcha to mention:** the object-ification of an action is what enables
queueing and undo stacks — a plain method call can't be stored, logged, or
reversed the way a Command object can.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
