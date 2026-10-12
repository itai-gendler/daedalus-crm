---
{
  "availability": [
    {
      "place": "crm-web::crm"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/lead/route.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/lead.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/demo-data.ts"
    }
  ]
}
---

# Load Demo Data

Loads only the selfhost empty database under the demo gate; hosted and native loading are unavailable. Writes have no universal atomic guarantee.
