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
      "text": "Activate a customer metric result carrying its existing time or owner filter.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::data"
        },
        "da": {
          "place": "crm-desktop::crm::data"
        }
      },
      "capability": "browse-data"
    },
    {
      "text": "The activated customer metric carries its filter into the customer list.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "reads",
          "facts": [
            "Created time",
            "Sales owner"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::data"
        },
        "da": {
          "place": "crm-desktop::crm::data"
        }
      },
      "capability": "browse-data"
    },
    {
      "text": "Inspect the customer list under that carried filter.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customers"
        },
        "da": {
          "place": "crm-desktop::crm::customers"
        }
      },
      "capability": "browse-customers"
    },
    {
      "text": "The destination list uses the selected metric filter; its actual scoped matching customers and empty/bounded results remain visible.",
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
        "wa": {
          "place": "crm-web::crm::customers"
        },
        "da": {
          "place": "crm-desktop::crm::customers"
        }
      },
      "capability": "browse-customers"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/dashboard/DashboardView.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/reports/ReportsView.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/page.tsx"
    }
  ]
}
---

# Metric To Customers

## Trigger

The activated customer metric carries its filter into the customer list.

## Outcome

The destination list uses the selected metric filter; its actual scoped matching customers and empty/bounded results remain visible.
