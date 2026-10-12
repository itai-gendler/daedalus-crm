---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "da": "DA"
  },
  "steps": [
    {
      "text": "Activate the follow-up notification carrying the customer destination.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm"
        }
      },
      "capability": "receive-followup-reminders"
    },
    {
      "text": "Notification activation carries the work’s customer identifier to the selected record.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "reads",
          "facts": [
            "Subject",
            "Planned time",
            "Owner",
            "Done"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm"
        }
      },
      "capability": "receive-followup-reminders"
    },
    {
      "text": "Inspect that selected customer record.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::customer-record"
        }
      },
      "capability": "browse-customers"
    },
    {
      "text": "Notification activation carries the same customer identifier into record inspection. OS delivery and missing records retain their actual failure/empty outcomes.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "reads",
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
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::customer-record"
        }
      },
      "capability": "browse-customers"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/reminders.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/main.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/desktop/reminders/route.ts"
    }
  ]
}
---

# Reminder To Customer Record

## Trigger

Notification activation carries the work’s customer identifier to the selected record.

## Outcome

Notification activation carries the same customer identifier into record inspection. OS delivery and missing records retain their actual failure/empty outcomes.
