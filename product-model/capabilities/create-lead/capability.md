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

# Create Lead

Validates required name, a closed status vocabulary, a free-text source of at most 30 characters (blank defaults to 其他), and masked-phone round-trip values, then saves the responsible member and source facts. A lead has no kept Channel field.
