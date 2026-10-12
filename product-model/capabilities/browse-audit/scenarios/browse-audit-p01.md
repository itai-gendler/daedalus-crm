---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse audit for the case “Bounded history with shared masking”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::audit"
        },
        "da": {
          "place": "crm-desktop::crm::audit"
        }
      }
    },
    {
      "text": "Bounded history with shared masking. Shows bounded actual history with shared masking and implemented native SALES authorship scope; best-effort recording can leave missing entries.",
      "kind": "product",
      "entities": [
        {
          "entity": "audit-log",
          "effect": "reads",
          "facts": [
            "Time",
            "Acting member",
            "Operation",
            "Subject",
            "Summary",
            "Details"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::audit"
        },
        "da": {
          "place": "crm-desktop::crm::audit"
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

# Bounded history with shared masking

## Trigger

A CRM member invokes browse audit for the case “Bounded history with shared masking”.

## Outcome

Bounded history with shared masking. Shows bounded actual history with shared masking and implemented native SALES authorship scope; best-effort recording can leave missing entries.
