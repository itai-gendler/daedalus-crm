---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "customer",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::conversation"
        },
        {
          "place": "crm-desktop::crm::customer-record"
        },
        {
          "place": "crm-desktop::crm::customers"
        },
        {
          "place": "crm-desktop::crm::follow-ups"
        },
        {
          "place": "crm-desktop::crm::import-history"
        },
        {
          "place": "crm-desktop::crm::signing"
        },
        {
          "place": "crm-web::crm::conversation"
        },
        {
          "place": "crm-web::crm::customer-record"
        },
        {
          "place": "crm-web::crm::customers"
        },
        {
          "place": "crm-web::crm::follow-ups"
        },
        {
          "place": "crm-web::crm::import-history"
        },
        {
          "place": "crm-web::crm::signing"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "crm-admin",
        "crm-manager"
      ]
    },
    {
      "actors": [
        "crm-sales"
      ],
      "when": [
        {
          "entity": "service-config",
          "fact": "Hosting/native mode",
          "is-not": "desktop-local"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "sales-owns",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-sales"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "channel-owns",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-sales"
        }
      ]
    },
    {
      "actors": [
        "crm-sales"
      ],
      "when": [
        {
          "fact": "Pool state",
          "is": "in"
        }
      ]
    },
    {
      "unattended": true
    },
    {
      "when": [
        {
          "entity": "desktop-config",
          "fact": "Current team binding",
          "absent": true
        }
      ],
      "related": [
        {
          "verb": "keeps",
          "entity": "desktop-config"
        },
        {
          "verb": "uses",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-sales"
        }
      ]
    },
    {
      "actors": [
        "crm-admin",
        "crm-manager",
        "crm-sales"
      ],
      "configuredBy": "crm-account"
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
      "target": "src/app/(app)/customers/pool-actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/carry-over-db.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/actions.ts"
    }
  ]
}
---

# Ordinary scoped members or the configured pool caller may change customer

This Rule governs change operations on 客户 at crm-desktop::crm::conversation, crm-desktop::crm::customer-record, crm-desktop::crm::customers, crm-desktop::crm::follow-ups, crm-desktop::crm::import-history, crm-desktop::crm::signing, crm-web::crm::conversation, crm-web::crm::customer-record, crm-web::crm::customers, crm-web::crm::follow-ups, crm-web::crm::import-history and crm-web::crm::signing.

The selected operation can pass through any one of these grants:

- CRM administrators and sales managers.
- Salespeople, when Service Config.Hosting/native mode is not desktop-local.
- The salespeople reached through Crm Account (sales-owns) → 销售 (holds).
- The salespeople reached through Crm Account (channel-owns) → 销售 (holds).
- Salespeople, when 客户.Pool state is in.
- The Product's scheduled process.
- The salespeople reached through 桌面设置 (keeps) → Crm Account (uses) → 销售 (holds), when 桌面设置.Current team binding is absent.

An additional CRM-role alternative is configured by the exact current account returned by the actual pool invocation's requireUser(). It applies only to its implemented pool callback consequences: Customer claim/undo-claim, or carried-work ownership transfer/restoration. Claim is gated by deleting the surviving pool row; undo-claim uses the preselected current caller-owned/out-of-pool customer and active submitted restoration account. Carried work must belong to that customer and the relevant old/caller owner, and remain unfinished (plans/tasks) or OPEN (opportunities); undo uses submitted work IDs without an authenticated issued receipt. These effects inherit the initiating operation's checks and do not acquire another direct-edit owner filter inside the callback. For actual undo-assignment dispatch, the exact current account may restore submitted customer/owner pairs only when the customer still has the specified new owner, the submitted restoration owner is active, and the row was ordinarily visible to this caller or returns to the caller itself. The full-scope callback rechecks the specified new owner on update and skips a changed row. Submitted provenance is not authenticated against an issued receipt. For other dispatch this additional alternative refuses, leaving the ordinary grants operative. It grants no arbitrary account configuration or general direct-edit authority.
