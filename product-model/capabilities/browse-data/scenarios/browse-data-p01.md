---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse data for the case “Personal home/empty start”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::home"
        },
        "da": {
          "place": "crm-desktop::crm::home"
        }
      }
    },
    {
      "text": "Personal home/empty start. Shows personal home/empty start, current funnel, month or year metrics; keeps unlike currencies separate and uses bounded detail. Metric activation carries its actual filter/subject.",
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
          "place": "crm-web::crm::home"
        },
        "da": {
          "place": "crm-desktop::crm::home"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/dashboard/page.tsx#DashboardPage"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/dashboard/Board.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/dashboard/HomeChat.tsx"
    }
  ]
}
---

# Personal home/empty start

## Trigger

A CRM member invokes browse data for the case “Personal home/empty start”.

## Outcome

Personal home/empty start. Shows personal home/empty start, current funnel, month or year metrics; keeps unlike currencies separate and uses bounded detail. Metric activation carries its actual filter/subject.

## Edge cases

- An empty business database shows the start card. With AI configured, home shows current personal signals and explicit conversation entry; without AI it shows the current board.
- Loading these views does not itself ask the model or accept a proposed CRM write.
