---
{
  "kind": "validation",
  "routes": {
    "intake": "Demo intake"
  },
  "steps": [
    {
      "text": "The website client invokes request demo for the case “Origin/field/rate rejection”.",
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
      "text": "The submitted request reaches this validation boundary: Origin/field/rate rejection.",
      "kind": "condition",
      "entities": [],
      "actor": "website-caller",
      "contexts": {
        "intake": {
          "place": "demo-intake"
        }
      }
    },
    {
      "text": "A rejected Origin returns 403; unavailable SMTP returns 503; the five-per-IP/fifty-global daily cap returns 429; malformed JSON, missing name/phone/company/email or invalid/overlong text/email returns 400. No demo email or CRM Lead is produced by these refusals.",
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

# Origin/field/rate rejection

## Trigger

The website client invokes request demo for the case “Origin/field/rate rejection”.

## Outcome

A rejected Origin returns 403; unavailable SMTP returns 503; the five-per-IP/fifty-global daily cap returns 429; malformed JSON, missing name/phone/company/email or invalid/overlong text/email returns 400. No demo email or CRM Lead is produced by these refusals.

## Edge cases

- An unallowed origin returns 403; allowed origins include the two shipped ai-daedalus.com origins and configured additions.
- An unconfigured SMTP channel returns 503; invalid JSON/text/required fields return 400.
- Five successful requests per source IP per day or 50 total per day produce 429. Unknown IP still uses the total cap.
