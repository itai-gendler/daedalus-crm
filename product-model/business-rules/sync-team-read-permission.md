---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "sync-team",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::operations::sync-teams"
        },
        {
          "place": "crm-desktop::crm::team"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "contains",
          "entity": "sync-membership"
        },
        {
          "verb": "identifies",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-admin"
        }
      ],
      "when": [
        {
          "entity": "sync-membership",
          "fact": "Left time",
          "absent": true
        }
      ]
    },
    {
      "related": [
        {
          "verb": "contains",
          "entity": "sync-membership"
        },
        {
          "verb": "identifies",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-manager"
        }
      ],
      "when": [
        {
          "entity": "sync-membership",
          "fact": "Left time",
          "absent": true
        }
      ]
    },
    {
      "related": [
        {
          "verb": "contains",
          "entity": "sync-membership"
        },
        {
          "verb": "identifies",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-sales"
        }
      ],
      "when": [
        {
          "entity": "sync-membership",
          "fact": "Left time",
          "absent": true
        }
      ]
    },
    {
      "actors": [
        "operator"
      ]
    },
    {
      "unattended": true,
      "configuredBy": "desktop-config"
    },
    {
      "actors": [
        "crm-admin",
        "crm-manager",
        "crm-sales"
      ],
      "configuredBy": "desktop-config"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/client.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/desktop/sync/route.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/sync-relay.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/settings/team-actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/admin/actions.ts"
    }
  ]
}
---

# Only related CRM administrators, related sales managers, related salespeople, operations staff and the Product's scheduled process may read 同步团队

This Rule governs read operations on 同步团队 at crm-web::operations::sync-teams and crm-desktop::crm::team.

The selected operation can pass through any one of these grants:

- The CRM administrators reached through Sync Membership (contains) → Crm Account (identifies) → 系统管理员 / 老板 (holds), when Sync Membership.Left time is absent.
- The sales managers reached through Sync Membership (contains) → Crm Account (identifies) → 销售主管 (holds), when Sync Membership.Left time is absent.
- The salespeople reached through Sync Membership (contains) → Crm Account (identifies) → 销售 (holds), when Sync Membership.Left time is absent.
- Operations staff.
- The Product's scheduled process, as configured by the currently running native book's desktop settings.

The unattended configuration is the running native service's actual `CRM_DATA_DIR` and current `.team.json` binding. It permits inspection of that bound team's state, local progress/error bookkeeping and continuation of returned exchange work, including reading inactivity and recording refusal. It never grants service activation, invite rotation or arbitrary team mutation. The operator activation and creator secret-control Rules remain conjunctive. No other book's configuration supplies this grant.

The initiating CRM role has the same book-bound configuration alternative for local state inspection and progress/error bookkeeping only, including an unsuccessful relay round. Remote roster disclosure still uses the request's exact cloud membership checks. This alternative confers neither operator activation nor creator secret control.
