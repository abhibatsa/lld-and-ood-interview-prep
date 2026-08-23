# Flyweight

**Intent:** minimize memory use by sharing as much data as possible
between similar objects, separating intrinsic (shared) from extrinsic
(per-instance) state.

```java
class CharacterGlyph { char symbol; Font font; } // intrinsic — shared across all uses
// extrinsic state (position on screen) is passed in at render time, not stored per glyph
```

## When to use
Massive numbers of similar objects where per-object memory matters — text
rendering (millions of character glyphs), game particle systems, map tile
rendering.

**Gotcha to mention:** this is a real interview pattern for "design a text
editor" or similar high-volume-object problems — the key insight to
verbalize is separating what's *shared* (font, glyph shape) from what's
*per-instance* (position), and only storing the per-instance part
separately.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
