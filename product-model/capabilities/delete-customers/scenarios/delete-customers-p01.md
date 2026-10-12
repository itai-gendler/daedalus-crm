---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes delete customers for the case “Delete while preserving contacts and reopening direct lead”.",
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
      "text": "Delete while preserving contacts and reopening direct lead. Referring customers can block removal. Contacts survive as unassigned, their former context is retained, and the direct converted lead reopens. Selected targets can produce partial batch results.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "removes"
        },
        {
          "entity": "assigned-contact",
          "effect": "removes",
          "with": "customer"
        },
        {
          "entity": "unassigned-contact",
          "effect": "creates",
          "facts": [
            "Name",
            "Phone",
            "WeChat",
            "Email",
            "Position",
            "Notes",
            "Former customer",
            "Former customer name",
            "Recoverable follow-up links",
            "Detach time",
            "Created time",
            "Last change"
          ],
          "to": "Unassigned"
        },
        {
          "entity": "lead",
          "effect": "changes",
          "facts": [
            "Status",
            "Conversion time",
            "Converted customer",
            "Last change"
          ],
          "from": "已转化",
          "to": "待跟进"
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

# Delete while preserving contacts and reopening direct lead

## Trigger

A CRM member invokes delete customers for the case “Delete while preserving contacts and reopening direct lead”.

## Outcome

Delete while preserving contacts and reopening direct lead. Referring customers can block removal. Contacts survive as unassigned, their former context is retained, and the direct converted lead reopens. Selected targets can produce partial batch results.
