---
{
  "kind": "edge",
  "routes": {
    "intake": "Demo intake"
  },
  "steps": [
    {
      "text": "The website client invokes request demo for the case “Honeypot apparent success without send”.",
      "kind": "actor",
      "entities": [],
      "actor": "website-caller",
      "contexts": {
        "intake": {
          "place": "demo-intake"
        }
      }
    },
    {
      "text": "SMTP error is returned without claiming delivery. Honeypot input returns apparent success without sending email or creating a CRM lead.",
      "kind": "product",
      "entities": [],
      "actor": "website-caller",
      "contexts": {
        "intake": {
          "place": "demo-intake"
        }
      }
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

# Honeypot apparent success without send

## Trigger

The website client invokes request demo for the case “Honeypot apparent success without send”.

## Outcome

SMTP error is returned without claiming delivery. Honeypot input returns apparent success without sending email or creating a CRM lead.

## Edge cases

- A filled/nontext honeypot returns apparent HTTP 200 success without sending or creating CRM data; origin/channel/rate gates still precede body validation.
