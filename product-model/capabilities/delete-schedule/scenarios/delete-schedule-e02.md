---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes delete schedule for the case “No general restore”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::schedules"
        },
        "da": {
          "place": "crm-desktop::crm::schedules"
        }
      }
    },
    {
      "text": "Deleting a plan or task removes that arrangement. This working process provides no general snapshot-restore operation after deletion; completed or unrelated arrangements are not substituted as an undo.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::schedules"
        },
        "da": {
          "place": "crm-desktop::crm::schedules"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#deletePlan"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#deleteTask"
    }
  ]
}
---

# No general restore

## Trigger

A CRM member invokes delete schedule for the case “No general restore”.

## Outcome

Deleting a plan or task removes that arrangement. This working process provides no general snapshot-restore operation after deletion; completed or unrelated arrangements are not substituted as an undo.
