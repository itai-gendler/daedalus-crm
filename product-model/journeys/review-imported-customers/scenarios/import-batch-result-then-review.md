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
      "text": "Review the mapped rows and execute their customer import.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customer-import"
        },
        "da": {
          "place": "crm-desktop::crm::customer-import"
        }
      },
      "capability": "import-customers"
    },
    {
      "text": "The completed batch result carries its batch identifier into the customer filter.",
      "kind": "product",
      "entities": [
        {
          "entity": "import-batch",
          "effect": "creates",
          "facts": [
            "File name",
            "Importer",
            "Import time",
            "Results",
            "Creation snapshots",
            "Fill snapshots",
            "Undo result",
            "Undone time"
          ],
          "to": "Recorded"
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
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customer-import"
        },
        "da": {
          "place": "crm-desktop::crm::customer-import"
        }
      },
      "capability": "import-customers"
    },
    {
      "text": "Activate the completed-batch result control and inspect its customer filter.",
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
      "text": "The customer list receives the completed batch identifier and presents its matching created/filled records. Batch counts retain created, filled, skipped and failed distinctions.",
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
      "target": "src/app/(app)/customers/ImportDrawer.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/import-actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/CustomersView.tsx"
    }
  ]
}
---

# Import Batch Result Then Review

## Trigger

The completed batch result carries its batch identifier into the customer filter.

## Outcome

The customer list receives the completed batch identifier and presents its matching created/filled records. Batch counts retain created, filled, skipped and failed distinctions.
