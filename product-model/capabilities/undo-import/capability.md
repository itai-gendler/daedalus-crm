---
{
  "availability": [
    {
      "place": "crm-web::crm"
    },
    {
      "place": "crm-desktop::crm"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/import-actions.ts"
    }
  ],
  "domain": "import-history"
}
---

# Undo Import

Consumes one eligible batch undo and restores only creations/fills still matching their snapshots. Later changes and dependencies are skipped; results can be partial.
