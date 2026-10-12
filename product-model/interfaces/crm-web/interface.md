---
{
  "type": "web",
  "actors": [
    "visitor",
    "crm-admin",
    "crm-manager",
    "crm-sales",
    "operator"
  ],
  "languages": [
    "zh-CN"
  ],
  "entryPoints": [
    {
      "web": "/login"
    },
    {
      "web": "/signup"
    },
    {
      "web": "/forgot"
    },
    {
      "web": "/terms"
    },
    {
      "web": "/privacy"
    },
    {
      "web": "/dashboard"
    },
    {
      "web": "/admin"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/settings/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/admin/guard.ts"
    }
  ]
}
---

# Crm Web

Chinese identity/legal, authenticated CRM and restricted operations.
