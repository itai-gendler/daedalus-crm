---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes undo import for the case “Restore eligible creations/fills”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::import-history"
        },
        "da": {
          "place": "crm-desktop::crm::import-history"
        }
      }
    },
    {
      "text": "Restore eligible creations/fills. Consumes one eligible batch undo and restores only creations/fills still matching their snapshots. Later changes and dependencies are skipped; results can be partial.",
      "kind": "product",
      "entities": [
        {
          "entity": "import-batch",
          "effect": "changes",
          "facts": [
            "Undo result",
            "Undone time"
          ],
          "from": "Recorded",
          "to": "Undone"
        },
        {
          "entity": "customer",
          "effect": "changes",
          "facts": [
            "Name",
            "Phone",
            "Email",
            "Notes",
            "Last change"
          ],
          "as": "filled-customer"
        },
        {
          "entity": "customer",
          "effect": "removes",
          "as": "created-customer"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::import-history"
        },
        "da": {
          "place": "crm-desktop::crm::import-history"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/import-actions.ts"
    }
  ]
}
---

# Restore eligible creations/fills

## Trigger

A CRM member invokes undo import for the case “Restore eligible creations/fills”.

## Outcome

Restore eligible creations/fills. Consumes one eligible batch undo and restores only creations/fills still matching their snapshots. Later changes and dependencies are skipped; results can be partial.
