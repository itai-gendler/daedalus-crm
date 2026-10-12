---
{
  "type": "api",
  "actors": [
    "website-caller"
  ],
  "languages": [
    "zh-CN",
    "en"
  ],
  "entryPoints": [
    {
      "api": "/api/lead"
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
    }
  ]
}
---

# Demo Intake

Website demo intake delivered by email; no CRM Lead is created.
