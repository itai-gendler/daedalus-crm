---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes edit customer for the case “Whole-record/nonoverlap merge”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customer-record"
        },
        "da": {
          "place": "crm-desktop::crm::customer-record"
        }
      }
    },
    {
      "text": "Whole-record/nonoverlap merge. Whole-record edits merge nonoverlapping changes with bounded retries and refuse overlapping conflicts. Inline and bulk status paths retain their own validation and do not promise whole-record merge parity.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "changes",
          "facts": [
            "Name",
            "Phone",
            "WhatsApp",
            "WeChat",
            "Country",
            "Email",
            "School/company",
            "Grade",
            "Major",
            "Follow-up status",
            "Decision status",
            "Expected signing date",
            "Sales owner",
            "Direct source",
            "Direct channel",
            "Referrer",
            "Attributed channel",
            "Attributed customer",
            "Channel owner",
            "Notes",
            "Last change"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customer-record"
        },
        "da": {
          "place": "crm-desktop::crm::customer-record"
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

# Whole-record/nonoverlap merge

## Trigger

A CRM member invokes edit customer for the case “Whole-record/nonoverlap merge”.

## Outcome

Whole-record/nonoverlap merge. Whole-record edits merge nonoverlapping changes with bounded retries and refuse overlapping conflicts. Inline and bulk status paths retain their own validation and do not promise whole-record merge parity.
