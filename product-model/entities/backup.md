---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/backup.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/auto-backup.js"
    }
  ],
  "domain": "desktop"
}
---

# 备份

An independently selected immutable local snapshot artifact with time, class, location and size.

## Information kept

- **Time** — When the visible log event occurred.
- **Class** — The backup's manual, automatic or upgrade category.
- **Location** — The backup's file location.
- **Size** — The backup's reported file size.
- **Snapshot** — The selected immutable backup contents; restoring retains saved states and creates a separate pre-restore copy.
