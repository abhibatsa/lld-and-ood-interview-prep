# Concurrency vs Parallelism

**Concurrency:** dealing with multiple tasks *in progress* at once —
possible even on a single core, via interleaving/context switching.

**Parallelism:** multiple tasks *literally executing at the same instant*
— requires multiple cores.

```
Concurrency (1 core): Task A -- Task B -- Task A -- Task B  (interleaved)
Parallelism (2 cores): Task A ========
                        Task B ========  (simultaneous)
```

## Key points
- You can have concurrency without parallelism (single-core multitasking
  OS), and parallelism without much concurrency design (embarrassingly
  parallel batch jobs with no shared state)
- This distinction is a favorite quick interview question precisely
  because most people use the words interchangeably — having the crisp
  answer ready is free credibility

**Remember:** concurrency is about *structure* (how you design for
overlapping tasks); parallelism is about *hardware* (whether they
literally run at once).

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
