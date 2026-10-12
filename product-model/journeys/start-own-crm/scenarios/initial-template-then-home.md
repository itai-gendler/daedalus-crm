---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "wa": "WA",
    "da": "DA"
  },
  "steps": [
    {
      "text": "Choose the shipped General or Trade preset in the required initial template process.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-admin",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::business-settings"
        },
        "da": {
          "place": "crm-desktop::crm::initial-template"
        }
      },
      "capability": "change-business-settings"
    },
    {
      "text": "After the required initial choice the product sends this same person to /dashboard.",
      "kind": "product",
      "entities": [
        {
          "entity": "business-config",
          "effect": "changes",
          "facts": [
            "Template",
            "Terms",
            "Field labels",
            "Source/grade/industry options",
            "Status display labels",
            "Currency",
            "Pool threshold",
            "Initial-template choice"
          ]
        }
      ],
      "actor": "crm-admin",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::business-settings"
        },
        "da": {
          "place": "crm-desktop::crm::initial-template"
        }
      },
      "capability": "change-business-settings"
    },
    {
      "text": "Read the home context reached after the successful template choice.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-admin",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::home"
        },
        "da": {
          "place": "crm-desktop::crm::home"
        }
      },
      "capability": "browse-data"
    },
    {
      "text": "The chosen business preset and initial-choice time are retained, and the required continuation reaches the home context, including its empty starting state for a new book.",
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
      "actor": "crm-admin",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::home"
        },
        "da": {
          "place": "crm-desktop::crm::home"
        }
      },
      "capability": "browse-data"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/start/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/start/TemplatePicker.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/dashboard/DashboardView.tsx"
    }
  ]
}
---

# Initial Template Then Home

## Trigger

After the required initial choice the product sends this same person to /dashboard.

## Outcome

The chosen business preset and initial-choice time are retained, and the required continuation reaches the home context, including its empty starting state for a new book.
