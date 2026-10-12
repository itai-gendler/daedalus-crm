---
{
  "kind": "edge",
  "routes": {
    "intake": "Demo intake"
  },
  "steps": [
    {
      "text": "The website client invokes request demo for the case “SMTP failure”.",
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

# SMTP failure

## Trigger

The website client invokes request demo for the case “SMTP failure”.

## Outcome

SMTP error is returned without claiming delivery. Honeypot input returns apparent success without sending email or creating a CRM lead.

## Edge cases

- SMTP failure returns 502 and does not consume the successful-send counter; a later retry can still send.
