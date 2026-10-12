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
      "text": "Submit the visible matching customer selected for this lead merge.",
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
      },
      "capability": "merge-lead"
    },
    {
      "text": "The reused matching customer identifier opens its selected record.",
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
          "from": "待跟进",
          "to": "已转化"
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
      },
      "capability": "merge-lead"
    },
    {
      "text": "Inspect the reused customer record opened by the merge result identifier.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customer-record"
        },
        "da": {
          "place": "crm-desktop::crm::customer-record"
        }
      },
      "capability": "browse-customers"
    },
    {
      "text": "The selected matching customer is reused and shown, rather than duplicated. An already occupied direct lead association is retained; the newly merged lead records converted status/time and its explanatory note.",
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
          "place": "crm-web::crm::customer-record"
        },
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
      "target": "src/app/(app)/leads/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/leads/LeadsView.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/page.tsx"
    }
  ]
}
---

# Lead Merge Then Review

## Trigger

The reused matching customer identifier opens its selected record.

## Outcome

The selected matching customer is reused and shown, rather than duplicated. An already occupied direct lead association is retained; the newly merged lead records converted status/time and its explanatory note.
