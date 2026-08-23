# Mediator

**Intent:** define an object that encapsulates how a set of objects
interact, avoiding direct references between them (reduces many-to-many
coupling to many-to-one).

```java
class ChatRoomMediator {
    void sendMessage(String msg, User from) { /* routes to all other users */ }
}
class User { ChatRoomMediator mediator; void send(String msg) { mediator.sendMessage(msg, this); } }
```

## When to use
Complex many-to-many communication between objects — chat rooms, air
traffic control, UI form validation with many interdependent fields.

**Gotcha to mention:** without Mediator, N objects that all need to talk
to each other create O(N²) direct relationships; Mediator collapses that
to O(N) — that's the concrete complexity argument to make.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
