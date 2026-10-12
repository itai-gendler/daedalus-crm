---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "plan",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::conversation"
        },
        {
          "place": "crm-desktop::crm::schedules"
        },
        {
          "place": "crm-web::crm::conversation"
        },
        {
          "place": "crm-web::crm::schedules"
        },
        {
          "place": "crm-web::crm::follow-ups"
        },
        {
          "place": "crm-desktop::crm::follow-ups"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "crm-admin",
        "crm-manager",
        "crm-sales"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/team-scope.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/settings/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/mcp/tools.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts"
    }
  ]
}
---

# Only CRM administrators, sales managers and salespeople may create 跟进计划

This Rule governs create operations on 跟进计划 at crm-desktop::crm::conversation, crm-desktop::crm::schedules, crm-web::crm::conversation, crm-web::crm::schedules, crm-web::crm::follow-ups and crm-desktop::crm::follow-ups.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
