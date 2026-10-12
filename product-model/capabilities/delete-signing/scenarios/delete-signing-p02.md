---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes delete signing for the case “Selected status restoration after last signing”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::signing"
        },
        "da": {
          "place": "crm-desktop::crm::signing"
        }
      }
    },
    {
      "text": "Selected status restoration after last signing. Financial removal and dependent order removal are transactional. Eligible linked opportunity values and the user-selected customer status after the last signing may restore; completed work remains.",
      "kind": "product",
      "entities": [
        {
          "entity": "signing",
          "effect": "removes",
          "from": "Recorded"
        },
        {
          "entity": "order",
          "effect": "removes",
          "from": "Recorded",
          "with": "signing"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::signing"
        },
        "da": {
          "place": "crm-desktop::crm::signing"
        }
      }
    },
    {
      "text": "After financial removal, reopen only still-WON opportunities whose surviving signing-win receipt retains their prior stage/probability. Normalize an invalid or previously winning stage to 谈判审核. Completed work is retained.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "changes",
          "from": "WON",
          "to": "OPEN",
          "facts": [
            "Status",
            "Stage",
            "Probability",
            "Closed time",
            "Last change"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::signing"
        },
        "da": {
          "place": "crm-desktop::crm::signing"
        }
      }
    },
    {
      "text": "Apply the explicitly selected follow-up/decision restoration only after the last signing is gone. A remaining signing prevents this customer-status restoration.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "changes",
          "facts": [
            "Follow-up status",
            "Decision status",
            "Last change"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::signing"
        },
        "da": {
          "place": "crm-desktop::crm::signing"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/order-contract.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/order-db.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/orders/page.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/features.ts"
    }
  ]
}
---

# Selected status restoration after last signing

## Trigger

A CRM member invokes delete signing for the case “Selected status restoration after last signing”.

## Outcome

Selected status restoration after last signing. Financial removal and dependent order removal are transactional. Eligible linked opportunity values and the user-selected customer status after the last signing may restore; completed work remains.

## Decision points

### Eligible opportunity restoration

Does the linked opportunity still have this signing-win receipt and WON status?

- Yes → try reopening with the retained prior probability and a valid prior stage.
- No → retain its later independent state.

### Last signing and status choice

Is this the last signing, with an explicit validated restoration choice?

- Yes → restore the selected customer statuses.
- No → retain customer statuses.
