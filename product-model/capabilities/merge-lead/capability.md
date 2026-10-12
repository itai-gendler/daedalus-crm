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

# Merge Lead

Reuses the matching visible customer and records conversion. If that customer already has a direct lead association it is retained; a hidden match does not authorize a duplicate.
