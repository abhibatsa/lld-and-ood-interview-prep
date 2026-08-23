# Processes vs Threads

**Process:** an independent program with its own memory space — isolated,
heavier to create, communication requires IPC (pipes, sockets, shared
memory).

**Thread:** a unit of execution *within* a process, sharing that
process's memory space — lighter to create, communication is just shared
variables (which is exactly why race conditions happen).

## Key points
- Threads sharing memory is both the point (fast, easy data sharing) and
  the danger (uncoordinated access = race conditions)
- Context switching between threads is cheaper than between processes,
  since the OS doesn't need to swap the whole memory space

**Remember:** "threads share memory, processes don't" is the one-line
answer that unlocks the rest of concurrency — race conditions literally
can't happen across processes without explicit shared memory, but they're
the default risk across threads.

---
*Part of [LLD & OOD Interview Prep](../../README.md)*
