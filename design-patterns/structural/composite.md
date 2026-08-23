# Composite

**Intent:** compose objects into tree structures, then treat individual
objects and compositions of objects uniformly.

```java
interface FileSystemItem { long size(); }
class File implements FileSystemItem { public long size() { return bytes; } }
class Folder implements FileSystemItem {
    List<FileSystemItem> children;
    public long size() { return children.stream().mapToLong(FileSystemItem::size).sum(); }
}
```

## When to use
Anything tree-shaped where you want uniform treatment of leaf and
container nodes — file systems, org charts, UI component trees. **Design
a File System** is a classic interview problem built directly on this
pattern.

**Gotcha to mention:** the key win is that client code calling `.size()`
doesn't need to know or care if it's holding a `File` or a `Folder` — that
uniformity is the entire point.

---
*Part of [LLD & OOD Interview Prep](../../../README.md)*
