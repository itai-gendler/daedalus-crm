---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes assign owner for the case “Transfer customer and unfinished work”.",
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
      "text": "Transfer customer and unfinished work. Transfers selected customer ownership to an active member and carries only specified unfinished work still owned by the previous owner. Existing signings retain their frozen owner.",
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

# Transfer customer and unfinished work

## Trigger

A CRM member invokes assign owner for the case “Transfer customer and unfinished work”.

## Outcome

Transfer customer and unfinished work. Transfers selected customer ownership to an active member and carries only specified unfinished work still owned by the previous owner. Existing signings retain their frozen owner.
