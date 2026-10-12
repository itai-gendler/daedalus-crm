---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes accept draft for the case “Customer-profile apply conflict/duplicate/dependency outcome”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::conversation"
        },
        "da": {
          "place": "crm-desktop::crm::conversation"
        }
      }
    },
    {
      "text": "If the initial save commits before the later dependent step fails, these saved records/fields remain. A pre-save validation or transaction refusal contributes no such committed write.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "changes",
          "facts": [
            "Name",
            "Phone",
            "School/company",
            "Grade",
            "Major",
            "Follow-up status",
            "Decision status",
            "Expected signing date",
            "Sales owner",
            "Direct channel",
            "Referrer",
            "Attributed channel",
            "Attributed customer",
            "Channel owner",
            "Notes",
            "Last change"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::conversation"
        },
        "da": {
          "place": "crm-desktop::crm::conversation"
        }
      }
    },
    {
      "text": "A duplicate phone, invalid referral chain, ambiguous/missing named owner/channel/referrer or supplied stale profile comparison refuses apply and releases the failed reservation. If saveCustomer committed the profile before unfinished-work transfer failed, that saved profile can remain while the card stays Proposed; failure is not a universal rollback.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::conversation"
        },
        "da": {
          "place": "crm-desktop::crm::conversation"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/dashboard/ai.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/dashboard/apply.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/components/ProposalCard.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/ai-jobs.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/thread-history.ts"
    }
  ]
}
---

# Customer-profile apply conflict/duplicate/dependency outcome

## Trigger

A CRM member invokes accept draft for the case “Customer-profile apply conflict/duplicate/dependency outcome”.

## Outcome

A duplicate phone, invalid referral chain, ambiguous/missing named owner/channel/referrer or supplied stale profile comparison refuses apply and releases the failed reservation. If saveCustomer committed the profile before unfinished-work transfer failed, that saved profile can remain while the card stays Proposed; failure is not a universal rollback.
