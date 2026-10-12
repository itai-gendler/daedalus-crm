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

# Convert Lead

Creates a customer from normalized phone or trade email and atomically records the conversion association/time/status. Repeat or concurrent conversion, hidden-owner hints and duplicate identity have distinct outcomes.
