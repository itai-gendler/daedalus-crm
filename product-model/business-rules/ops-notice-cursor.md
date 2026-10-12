---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "receive-ops-notices"
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
      "target": "prisma/schema.prisma"
    }
  ]
}
---

# Native operations notices retain their cursor and bounded catch-up

First start skips old notice history. Polling is two-minute, catch-up is bounded to twenty-four hours, and deduplication covers two days. Offline state retains the cursor. Notices group their actual subjects and use supported destinations; delivery is best effort rather than exactly once.
