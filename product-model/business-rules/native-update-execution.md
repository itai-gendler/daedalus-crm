---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "download-update"
    },
    {
      "type": "capability",
      "id": "install-update"
    },
    {
      "type": "entity",
      "id": "desktop-config"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/main.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/updater.js"
    }
  ]
}
---

# Only a qualified ready delta follows automatic installation on normal quit

A qualifying managed delta may download automatically and install on normal quit once Ready. An initial whole-package plan waits for explicit download, but failure of an already started automatic delta can switch to whole-package downloading within that same invocation without a second human action. Managed package/manifest validation is preserved. Normal quit automatically installs only a Ready delta, not a Ready whole package. Human installation follows its actual restart path. Windows quit-time handoff failure cancels quit and leaves the old version usable; Mac swap failure is logged. A ready or handed-off package is not proof that installation succeeded.
