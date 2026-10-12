---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes convert lead for the case “Phone conversion”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::leads"
        },
        "da": {
          "place": "crm-desktop::crm::leads"
        }
      }
    },
    {
      "text": "Phone conversion. Creates a customer from normalized phone or trade email and atomically records the conversion association/time/status. Repeat or concurrent conversion, hidden-owner hints and duplicate identity have distinct outcomes.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "changes",
          "facts": [
            "Status",
            "Conversion time",
            "Converted customer",
            "Last change"
          ],
          "to": "已转化",
          "from": "待跟进"
        },
        {
          "entity": "customer",
          "effect": "creates",
          "facts": [
            "Name",
            "Phone",
            "WhatsApp",
            "WeChat",
            "Country",
            "Email",
            "School/company",
            "Grade",
            "Major",
            "Follow-up status",
            "Decision status",
            "Expected signing date",
            "Sales owner",
            "Direct source",
            "Direct channel",
            "Referrer",
            "Attributed channel",
            "Attributed customer",
            "Channel owner",
            "Notes",
            "Latest follow-up",
            "Pool state",
            "Pool entry",
            "Released by",
            "Claim time",
            "Claimed by",
            "Created time",
            "Last change"
          ]
        },
        {
          "entity": "assigned-contact",
          "effect": "creates",
          "facts": [
            "Name",
            "Phone",
            "WeChat",
            "Email",
            "Position",
            "Notes",
            "Primary",
            "Created time",
            "Last change"
          ],
          "with": "customer"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::leads"
        },
        "da": {
          "place": "crm-desktop::crm::leads"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/leads/actions.ts#convertLead"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/lead-convert.ts#线索转档案"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/check-then-write.ts"
    }
  ]
}
---

# Phone conversion

## Trigger

A CRM member invokes convert lead for the case “Phone conversion”.

## Outcome

Phone conversion. Creates a customer from normalized phone or trade email and atomically records the conversion association/time/status. Repeat or concurrent conversion, hidden-owner hints and duplicate identity have distinct outcomes.

## Decision points

### Lead contact

Does the lead contain a nonblank contact name?

- Yes → create the customer and its dependent primary contact with the retained phone/email; use the configured company/industry mapping.
- No → create the customer without a contact, preserving general-template email in notes or trade-template email in its trade profile.

## Edge cases

- Conversion requires an absent direct customer association. An independently edited status alone, including 已转化 without a direct association, is not the conversion gate; other unlinked lead statuses retain the same checked association outcome.

