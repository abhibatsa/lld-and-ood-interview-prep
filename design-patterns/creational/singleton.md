# Singleton

**Intent:** ensure a class has exactly one instance, with a global access point.

```java
class ConfigManager {
    private static final ConfigManager INSTANCE = new ConfigManager();
    private ConfigManager() {}
    static ConfigManager getInstance() { return INSTANCE; }
}
```

## When to use
Shared resources where multiple instances would cause bugs or waste —
connection pools, config managers, logging.

## When NOT to use
It's the most overused pattern in interviews. If you don't have a real
"exactly one, globally" requirement, don't reach for it — it also makes
unit testing harder (global mutable state) and hides dependencies.

**Gotcha to mention out loud:** naive singletons aren't thread-safe under
lazy initialization — mention double-checked locking or eager
initialization (as above) if concurrency comes up.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
