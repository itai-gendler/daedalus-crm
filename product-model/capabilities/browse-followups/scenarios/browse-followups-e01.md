---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse followups for the case “Empty/bounded history”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::follow-ups"
        },
        "da": {
          "place": "crm-desktop::crm::follow-ups"
        }
      }
    },
    {
      "text": "The global filtered history fetches up to 300 communications while keeping its separately counted total. Customer history retains its own bounded fetch. Empty history is not a failed save or deletion.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::follow-ups"
        },
        "da": {
          "place": "crm-desktop::crm::follow-ups"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/follow-ups/page.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/page.tsx"
    }
  ]
}
---

# Empty/bounded history

## Trigger

A CRM member invokes browse followups for the case “Empty/bounded history”.

## Outcome

The global filtered history fetches up to 300 communications while keeping its separately counted total. Customer history retains its own bounded fetch. Empty history is not a failed save or deletion.
