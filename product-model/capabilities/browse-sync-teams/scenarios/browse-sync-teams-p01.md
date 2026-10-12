---
{
  "kind": "primary",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes browse sync teams for the case “Team/member/push-pull/activation summaries”.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::sync-teams"
        }
      }
    },
    {
      "text": "Team/member/push-pull/activation summaries. Inspects team/member push-pull and activation summaries; empty results and read failure are distinct.",
      "kind": "product",
      "entities": [
        {
          "entity": "sync-team",
          "effect": "reads",
          "facts": [
            "Name",
            "Active",
            "Activation time",
            "Invite/key generation",
            "Creator",
            "Sync state"
          ]
        }
      ],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::sync-teams"
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

# Team/member/push-pull/activation summaries

## Trigger

The operator invokes browse sync teams for the case “Team/member/push-pull/activation summaries”.

## Outcome

Team/member/push-pull/activation summaries. Inspects team/member push-pull and activation summaries; empty results and read failure are distinct.
