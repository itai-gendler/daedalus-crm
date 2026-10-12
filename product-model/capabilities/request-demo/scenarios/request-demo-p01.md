---
{
  "kind": "primary",
  "routes": {
    "intake": "Demo intake"
  },
  "steps": [
    {
      "text": "The website client invokes request demo for the case “Valid request sent by email”.",
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
      "text": "Valid request sent by email. Valid allowed-origin demo input is mailed, subject to success-count rate limits. Honeypot requests appear successful without sending; SMTP failure is exposed and no CRM lead is created.",
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

# Valid request sent by email

## Trigger

The website client invokes request demo for the case “Valid request sent by email”.

## Outcome

Valid request sent by email. Valid allowed-origin demo input is mailed, subject to success-count rate limits. Honeypot requests appear successful without sending; SMTP failure is exposed and no CRM lead is created.

## Edge cases

- Name, phone, company and valid email are required; optional title/team size are single-line text up to 200 characters and scenario text up to 2,000.
- lang=en selects the English email; other values select Chinese. Reply-To identifies the submitter’s name/email. Successful send returns HTTP 200 and increments success counters; no CRM record is created.
