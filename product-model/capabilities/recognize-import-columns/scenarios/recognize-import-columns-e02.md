---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes recognize import columns for the case “Late result preserves preview”.",
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
      "text": "Failure retains manual choices; a late result does not replace the preview or mappings the human has already changed.",
      "kind": "product",
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

# Late result preserves preview

## Trigger

A CRM member invokes recognize import columns for the case “Late result preserves preview”.

## Outcome

Failure retains manual choices; a late result does not replace the preview or mappings the human has already changed.
