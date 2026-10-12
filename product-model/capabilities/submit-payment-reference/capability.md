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
      "target": "src/app/(app)/billing/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/billing/page.tsx"
    }
  ],
  "domain": "subscription"
}
---

# Submit Payment Reference

Appends a pending reference for the workspace owner. Duplicate references can append; no automatic activation or payment callback follows.
