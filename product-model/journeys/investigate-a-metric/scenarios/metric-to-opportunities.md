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
      "text": "Activate the home metric for ongoing opportunities.",
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
      "text": "The activated opportunity metric carries its period/stage filter into the opportunity list.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "reads",
          "facts": [
            "Status",
            "Amount",
            "Currency"
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
      "text": "Inspect the carried OPEN opportunity list.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::opportunities"
        },
        "da": {
          "place": "crm-desktop::crm::opportunities"
        }
      },
      "capability": "browse-opportunities"
    },
    {
      "text": "The opportunity list retains the selected status filter and shows its own results and per-currency totals.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "reads",
          "facts": [
            "Name",
            "Amount",
            "Currency",
            "Stage",
            "Probability",
            "Status",
            "Owner",
            "Expected date",
            "Notes",
            "Closed time",
            "Created time",
            "Last change"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::opportunities"
        },
        "da": {
          "place": "crm-desktop::crm::opportunities"
        }
      },
      "capability": "browse-opportunities"
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
      "target": "src/app/(app)/opportunities/page.tsx"
    }
  ]
}
---

# Metric To Opportunities

## Trigger

The activated opportunity metric carries its period/stage filter into the opportunity list.

## Outcome

The opportunity list retains the selected status filter and shows its own results and per-currency totals.
