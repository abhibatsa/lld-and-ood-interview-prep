# Proxy

**Intent:** provide a stand-in/placeholder for another object to control
access to it — lazy loading, access control, logging, or remote access.

```java
interface Image { void display(); }
class RealImage implements Image { RealImage(String path) { loadFromDisk(path); } }
class ProxyImage implements Image {
    RealImage real; String path;
    public void display() {
        if (real == null) real = new RealImage(path); // lazy load
        real.display();
    }
}
```

## When to use
Lazy initialization (expensive object, load on first use), access control
(check permissions before delegating), or remote proxies (hide network
calls behind a local-looking interface).

**Gotcha to mention:** structurally near-identical to Decorator (both
wrap an object behind the same interface) — the difference is *intent*:
Proxy controls *access*, Decorator adds *behavior*. Say this distinction
out loud if asked to compare them.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
