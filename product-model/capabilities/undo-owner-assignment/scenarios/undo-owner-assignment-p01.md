---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes undo owner assignment for the case “Conditional owner/carried-work restoration”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customers"
        },
        "da": {
          "place": "crm-desktop::crm::customers"
        }
      }
    },
    {
      "text": "Conditional owner/carried-work restoration. Restores only the original eligible owner and originally carried unfinished work. Later reassignment, completed work or an inactive prior owner is retained rather than overwritten.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "changes",
          "facts": [
            "Sales owner",
            "Last change"
          ]
        },
        {
          "entity": "opportunity",
          "effect": "changes",
          "facts": [
            "Owner",
            "Last change"
          ]
        },
        {
          "entity": "plan",
          "effect": "changes",
          "facts": [
            "Owner",
            "Last change"
          ]
        },
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Owner",
            "Last change"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customers"
        },
        "da": {
          "place": "crm-desktop::crm::customers"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/pool-actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/pool-db.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/team-scope.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/check-then-write.ts"
    }
  ]
}
---

# Conditional owner/carried-work restoration

## Trigger

A CRM member invokes undo owner assignment for the case “Conditional owner/carried-work restoration”.

## Outcome

Conditional owner/carried-work restoration. Restores only the original eligible owner and originally carried unfinished work. Later reassignment, completed work or an inactive prior owner is retained rather than overwritten.
