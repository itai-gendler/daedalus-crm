---
{
  "availability": [
    {
      "place": "crm-web::public"
    },
    {
      "place": "crm-desktop::public"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/login/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/signup/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/forgot/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/desktop/landing.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/route-memory.js"
    }
  ]
}
---

# Sign In

Credentials are checked in the deployment identity store. Hosted membership selects the workspace; native cloud login selects only the account-owned local directory. Rejected or unavailable identity never adopts another account’s files.
