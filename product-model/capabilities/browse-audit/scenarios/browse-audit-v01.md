---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse audit for the case “Session/local-scope rejection”.",
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
      "text": "The submitted request reaches this validation boundary: Session/local-scope rejection.",
      "kind": "condition",
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
      "text": "Failed session validation or native history-author scope prevents the requested audit history from being disclosed through this refused request.",
      "kind": "product",
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

# Session/local-scope rejection

## Trigger

A CRM member invokes browse audit for the case “Session/local-scope rejection”.

## Outcome

Failed session validation or native history-author scope prevents the requested audit history from being disclosed through this refused request.
