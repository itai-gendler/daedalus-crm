---
{
  "availability": [
    {
      "place": "crm-web::crm"
    },
    {
      "place": "crm-desktop::crm"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/leads/actions.ts"
    }
  ],
  "domain": "leads"
}
---

# Edit Lead

Edits validated lead facts using the version guard. Changing converted status alone creates no customer and does not substitute for the conversion link.
