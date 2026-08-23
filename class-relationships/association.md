# Association

The weakest relationship — two classes know about and use each other, but
neither owns the other's lifecycle.

```java
class Teacher {
    void teach(Student s) { /* uses a Student, doesn't own it */ }
}
```

![Class relationships compared](../assets/class-relationships-overview.svg)

## Key points
- Can be one-way (Teacher knows Student) or two-way (both know each other)
- No ownership implied — a `Student` exists whether or not this `Teacher` exists
- This is the loosest coupling of the four relationships — prefer it when you don't need stronger ownership semantics

**Remember:** if you're not sure whether a relationship is association or
aggregation, ask "does one own the other's lifecycle?" No → association.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
