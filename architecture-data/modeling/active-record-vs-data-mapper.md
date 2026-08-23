# Data Mapping Patterns (Active Record vs Data Mapper)

Two ways to connect your domain objects to the database.

**Active Record:** the domain object knows how to save/load itself.
```java
class User { void save() { /* INSERT/UPDATE directly */ } }
user.save();
```

**Data Mapper:** a separate object handles all persistence; the domain
object knows nothing about the database.
```java
class UserRepository { void save(User u) { /* INSERT/UPDATE */ } }
userRepository.save(user);
```

## Key points
- Active Record is simpler, faster to write, but couples your domain
  model to persistence — harder to unit test without a database, and it
  violates [Single Responsibility](../../design-principles/solid-with-code.md)
  (the object now has two reasons to change: business rules AND storage)
- Data Mapper is what [Layered Architecture](../patterns/layered-architecture.md)'s
  Repository layer is doing — cleaner separation, more boilerplate

**Remember:** if asked "how does your `Order` class get saved," saying
"through a separate `OrderRepository`, not a `save()` method on `Order`
itself" is the Data Mapper answer — the one most interviewers expect at
a senior level.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
