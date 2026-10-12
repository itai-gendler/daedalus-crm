---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "plan",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::customers"
        },
        {
          "place": "crm-desktop::crm::schedules"
        },
        {
          "place": "crm-web::crm::customers"
        },
        {
          "place": "crm-web::crm::schedules"
        },
        {
          "place": "crm-web::crm::follow-ups"
        },
        {
          "place": "crm-desktop::crm::follow-ups"
        },
        {
          "place": "crm-web::crm::signing"
        },
        {
          "place": "crm-desktop::crm::signing"
        },
        {
          "place": "crm-web::crm::conversation"
        },
        {
          "place": "crm-desktop::crm::conversation"
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
          "verb": "owns",
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
          "verb": "has",
          "entity": "customer"
        },
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
          "verb": "has",
          "entity": "customer"
        },
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
          "entity": "customer",
          "fact": "Pool state",
          "is": "in"
        }
      ]
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
      "target": "src/app/(app)/customers/[id]/actions.ts"
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

# Ordinary scoped members or the configured consequential caller may change plan

This Rule governs change operations on 跟进计划 at crm-desktop::crm::customers, crm-desktop::crm::schedules, crm-web::crm::customers, crm-web::crm::schedules, crm-web::crm::follow-ups, crm-desktop::crm::follow-ups, crm-web::crm::signing and crm-desktop::crm::signing.

The selected operation can pass through any one of these grants:

- CRM administrators and sales managers.
- Salespeople, when Service Config.Hosting/native mode is not desktop-local.
- The salespeople reached through Crm Account (owns) → 销售 (holds).
- The salespeople reached through 客户 (has) → Crm Account (sales-owns) → 销售 (holds).
- The salespeople reached through 客户 (has) → Crm Account (channel-owns) → 销售 (holds).
- Salespeople, when 客户.Pool state is in.
- The salespeople reached through 桌面设置 (keeps) → Crm Account (uses) → 销售 (holds), when 桌面设置.Current team binding is absent.

An additional CRM-role alternative is configured by the exact current account returned by the actual pool invocation's requireUser(). It applies only to its implemented pool callback consequences: Customer claim/undo-claim, or carried-work ownership transfer/restoration. Claim is gated by deleting the surviving pool row; undo-claim uses the preselected current caller-owned/out-of-pool customer and active submitted restoration account. Carried work must belong to that customer and the relevant old/caller owner, and remain unfinished (plans/tasks) or OPEN (opportunities); undo uses submitted work IDs without an authenticated issued receipt. These effects inherit the initiating operation's checks and do not acquire another direct-edit owner filter inside the callback. The same exact initiating account may carry unfinished old-owner work through the actual full-scope helper after a successful scoped customer ownership edit/assignment, including accepted profile fields; it is not independently reauthorized as a direct edit after the customer has changed owner. Undo assignment uses its actual visible-or-return-to-caller eligibility, active submitted owner, currently specified new owner and callback ownership recheck; only submitted attached work still unfinished/OPEN and owned by the specified recipient restores. Submitted work arrays are not authenticated issued receipts. For other dispatch this additional alternative refuses, leaving the ordinary grants operative. It grants no arbitrary account configuration or general direct-edit authority.
