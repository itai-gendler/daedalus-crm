---
{
  "kind": "edge",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes mark test account for the case “Configured operator remains inherently test”.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::account-record"
        }
      }
    },
    {
      "text": "Setting a manual test marker retains its test-history entry. A configured operations identity already has inherent test/unlimited treatment, independent of whether this manual marker was previously set.",
      "kind": "product",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::account-record"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/admin/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/admin/data.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/admin/guard.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/ops-auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/ops-notices.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/feedback-reply.ts"
    }
  ]
}
---

# Configured operator remains inherently test

## Trigger

The operator invokes mark test account for the case “Configured operator remains inherently test”.

## Outcome

Setting a manual test marker retains its test-history entry. A configured operations identity already has inherent test/unlimited treatment, independent of whether this manual marker was previously set.
