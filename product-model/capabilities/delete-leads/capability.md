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

# Delete Leads

Removes selected visible leads and returns the actual deleted count. Customer history is not inferred to disappear with its original lead.
