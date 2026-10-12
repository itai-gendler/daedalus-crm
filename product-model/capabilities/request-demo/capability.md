---
{
  "availability": [
    {
      "place": "demo-intake"
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

# Request Demo

Valid allowed-origin demo input is mailed, subject to success-count rate limits. Honeypot requests appear successful without sending; SMTP failure is exposed and no CRM lead is created.
