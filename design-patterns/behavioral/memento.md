# Memento

**Intent:** capture and externalize an object's internal state so it can
be restored later, without violating encapsulation.

```java
class EditorMemento { private final String content; EditorMemento(String c) { content = c; } }
class Editor {
    String content;
    EditorMemento save() { return new EditorMemento(content); }
    void restore(EditorMemento m) { content = m.getContent(); }
}
```

## When to use
Undo/checkpoint systems where you need to snapshot state (not just
actions, which is what [Command](./command.md) handles) — often used
*together* with Command for a full undo/redo implementation.

**Gotcha to mention:** the memento object should be immutable and only
readable by the originator that created it — that's what "without
violating encapsulation" means in practice.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
