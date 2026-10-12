---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse contacts for the case “Empty/bounded groups”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::contacts"
        },
        "da": {
          "place": "crm-desktop::crm::contacts"
        }
      }
    },
    {
      "text": "Associated and unassigned searches have independent 300-row fetch bounds. Counts use separate count queries instead of treating fetched rows as the total; no matches produce empty groups.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::contacts"
        },
        "da": {
          "place": "crm-desktop::crm::contacts"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/contacts/page.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/contacts/ContactsView.tsx"
    }
  ]
}
---

# Empty/bounded groups

## Trigger

A CRM member invokes browse contacts for the case “Empty/bounded groups”.

## Outcome

Associated and unassigned searches have independent 300-row fetch bounds. Counts use separate count queries instead of treating fetched rows as the total; no matches produce empty groups.
