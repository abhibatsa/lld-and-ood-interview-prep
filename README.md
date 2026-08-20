# Low Level Design (LLD) / Object-Oriented Design Interview Prep

Resources to learn Low Level Design / Object-Oriented Design and prepare
for interviews — OOP fundamentals, design patterns, UML, concurrency, and
commonly asked interview questions. Production-grounded where it matters
(concurrency, real system case studies), standard-taxonomy where standard
taxonomy is genuinely the right taxonomy (design patterns aren't
reinvented here — GoF categorization is correct and worth keeping).

## 🏁 Start Here
- [How to Learn LLD](./start-here/how-to-learn-lld.md)
- [15 Must-Know OOP Concepts](./start-here/15-must-know-oop-concepts.md)

## 🧱 OOP Fundamentals
- [Classes and Objects](./oop-fundamentals/classes-and-objects.md)
- [Enums](./oop-fundamentals/enums.md)
- [Interfaces](./oop-fundamentals/interfaces.md)
- [Encapsulation](./oop-fundamentals/encapsulation.md)
- [Abstraction](./oop-fundamentals/abstraction.md)
- [Inheritance](./oop-fundamentals/inheritance.md)
- [Polymorphism](./oop-fundamentals/polymorphism.md)

## 🔗 Class Relationships
- [Association](./class-relationships/association.md)
- [Aggregation](./class-relationships/aggregation.md)
- [Composition](./class-relationships/composition.md)
- [Dependency](./class-relationships/dependency.md)

## 🧭 Design Principles
- [DRY Principle](./design-principles/dry.md)
- [YAGNI Principle](./design-principles/yagni.md)
- [KISS Principle](./design-principles/kiss.md)
- [SOLID Principles with Pictures](./design-principles/solid-with-pictures.md)
- [SOLID Principles with Code](./design-principles/solid-with-code.md)

## 🧩 Design Patterns

| Creational | Structural | Behavioral |
|---|---|---|
| [Singleton](./design-patterns/creational/singleton.md) | [Adapter](./design-patterns/structural/adapter.md) | [Iterator](./design-patterns/behavioral/iterator.md) |
| [Factory Method](./design-patterns/creational/factory-method.md) | [Bridge](./design-patterns/structural/bridge.md) | [Observer](./design-patterns/behavioral/observer.md) |
| [Abstract Factory](./design-patterns/creational/abstract-factory.md) | [Composite](./design-patterns/structural/composite.md) | [Strategy](./design-patterns/behavioral/strategy.md) |
| [Builder](./design-patterns/creational/builder.md) | [Decorator](./design-patterns/structural/decorator.md) | [Command](./design-patterns/behavioral/command.md) |
| [Prototype](./design-patterns/creational/prototype.md) | [Facade](./design-patterns/structural/facade.md) | [State](./design-patterns/behavioral/state.md) |
| | [Flyweight](./design-patterns/structural/flyweight.md) | [Template Method](./design-patterns/behavioral/template-method.md) |
| | [Proxy](./design-patterns/structural/proxy.md) | [Visitor](./design-patterns/behavioral/visitor.md) |
| | | [Mediator](./design-patterns/behavioral/mediator.md) |
| | | [Memento](./design-patterns/behavioral/memento.md) |
| | | [Chain of Responsibility](./design-patterns/behavioral/chain-of-responsibility.md) |

## 🗂️ UML
- [Class Diagram](./uml/class-diagram.md)
- [Use Case Diagram](./uml/use-case-diagram.md)
- [Sequence Diagram](./uml/sequence-diagram.md)
- [Activity Diagram](./uml/activity-diagram.md)
- [State Machine Diagram](./uml/state-machine-diagram.md)

## ⏱️ Concurrency & Multi-threading Concepts

**Concurrency 101**
- [Introduction to Concurrency](./concurrency/intro-to-concurrency.md)
- [Concurrency vs Parallelism](./concurrency/concurrency-vs-parallelism.md)
- [Processes vs Threads](./concurrency/processes-vs-threads.md)
- [Thread Lifecycle and States](./concurrency/thread-lifecycle.md)
- [Race Conditions and Critical Sections](./concurrency/race-conditions.md)

**Synchronization Primitives**
- [Mutex](./concurrency/mutex.md)
- [Semaphores](./concurrency/semaphores.md)
- [Condition Variables](./concurrency/condition-variables.md)
- [Coarse-grained vs Fine-grained Locking](./concurrency/coarse-vs-fine-locking.md)
- [Reentrant Locks](./concurrency/reentrant-locks.md)
- [Try-Lock and Timed Locking](./concurrency/try-lock-and-timed-locking.md)
- [Compare-and-Swap (CAS)](./concurrency/compare-and-swap.md)

**Concurrency Challenges**
- [Deadlock](./concurrency/deadlock.md)
- [Livelock](./concurrency/livelock.md)

**Concurrency Patterns**
- [Signaling Pattern](./concurrency/signaling-pattern.md)
- [Thread Pool Pattern](./concurrency/thread-pool-pattern.md)
- [Producer-Consumer Pattern](./concurrency/producer-consumer-pattern.md)
- [Reader-Writer Pattern](./concurrency/reader-writer-pattern.md)

## ✅ [How to Answer an LLD Interview Problem](./interview-prep/how-to-answer-an-lld-problem.md)

## 💻 Low Level Design Interview Problems

**Easy**
- [Design Parking Lot](./problems/easy/parking-lot.md)
- [Design Stack Overflow](./problems/easy/stack-overflow.md)
- [Design a Vending Machine](./problems/easy/vending-machine.md)
- [Design Logging Framework](./problems/easy/logging-framework.md)
- [Design Traffic Signal Control System](./problems/easy/traffic-signal-control.md)
- [Design a Task Management System](./problems/easy/task-management-system.md)

**Medium**
- [Design ATM](./problems/medium/atm.md)
- [Design LinkedIn](./problems/medium/linkedin.md)
- [Design LRU Cache](./problems/medium/lru-cache.md)
- [Design Tic Tac Toe Game](./problems/medium/tic-tac-toe.md)
- [Design Pub Sub System](./problems/medium/pub-sub-system.md)
- [Design an Elevator System](./problems/medium/elevator-system.md)
- [Design Car Rental System](./problems/medium/car-rental-system.md)
- [Design Hotel Management System](./problems/medium/hotel-management-system.md)
- [Design a Digital Wallet Service](./problems/medium/digital-wallet-service.md) — real depth here, fintech background
- [Design a Library Management System](./problems/medium/library-management-system.md)
- [Design a Concert Ticket Booking System](./problems/medium/concert-ticket-booking.md)

**Hard**
- [Design Splitwise](./problems/hard/splitwise.md)
- [Design Chess Game](./problems/hard/chess-game.md)
- [Design a Ride-Sharing Service like Uber](./problems/hard/ride-sharing-service.md)
- [Design Movie Ticket Booking System](./problems/hard/movie-ticket-booking.md)
- [Design an Online Stock Brokerage System](./problems/hard/online-stock-brokerage.md) — real depth here, fintech background

## ⏱️ Concurrency & Multi-threading Problems
- [Print FooBar Alternately](./concurrency-problems/print-foobar-alternately.md)
- [Print Zero Even Odd](./concurrency-problems/print-zero-even-odd.md)
- [Design Thread-Safe Cache with TTL](./concurrency-problems/thread-safe-cache-with-ttl.md)
- [Design Concurrent HashMap](./concurrency-problems/concurrent-hashmap.md)
- [Design Thread-Safe Blocking Queue](./concurrency-problems/thread-safe-blocking-queue.md)
- [Producer-Consumer with Bounded Buffer](./concurrency-problems/producer-consumer-bounded-buffer.md)

## 📇 Related repos in this family
- [System Design & Architecture](https://github.com/abhibatsa/architecting-software) — high-level design, this repo's natural pairing
- [SDE Career Prep](https://github.com/abhibatsa/sde-career-prep) — cross-links here for the LLD-round portion of SDE interviews

## 📚 Books
- *Head First Design Patterns*
- *Clean Code* — Robert C. Martin
- *Refactoring: Improving the Design of Existing Code* — Martin Fowler

## 🤝 Contributing
See [CONTRIBUTING.md](./CONTRIBUTING.md). Fork, branch, commit, PR — same
flow as every repo in this family. If this helped, a star helps others
find it too.

## 📄 License
MIT
