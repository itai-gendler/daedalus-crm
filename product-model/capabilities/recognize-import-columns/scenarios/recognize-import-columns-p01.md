---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes recognize import columns for the case “Explicit unresolved-column judgment”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customer-import"
        },
        "da": {
          "place": "crm-desktop::crm::customer-import"
        }
      }
    },
    {
      "text": "Explicit unresolved-column judgment. Opt-in unresolved-column judgment sends headers and first three rows to the judgment model. It consumes no generative credit; late/failing results preserve manual mappings and preview.",
      "kind": "product",
      "entities": [
        {
          "entity": "ai-config",
          "effect": "reads",
          "facts": [
            "Recognition enabled"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customer-import"
        },
        "da": {
          "place": "crm-desktop::crm::customer-import"
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

# Explicit unresolved-column judgment

## Trigger

A CRM member invokes recognize import columns for the case “Explicit unresolved-column judgment”.

## Outcome

Explicit unresolved-column judgment. Opt-in unresolved-column judgment sends headers and first three rows to the judgment model. It consumes no generative credit; late/failing results preserve manual mappings and preview.
