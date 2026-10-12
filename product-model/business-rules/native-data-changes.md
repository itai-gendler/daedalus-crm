---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "crm-account",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "lead",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "customer",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "assigned-contact",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "unassigned-contact",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "opportunity",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "signing",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "order",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "follow-up",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "plan",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "task",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "channel",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "supplier",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "import-batch",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "conversation",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "audit-log",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "business-config",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "ai-config",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "mcp-connection",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
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
    },
    {
      "unattended": true
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
      "target": "src/lib/sync/tables.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/gateway-auth.ts"
    }
  ]
}
---

# Only CRM administrators, sales managers and salespeople and the Product's scheduled process may change Crm Account, 线索, 客户, 客户联系人, 未关联联系人, 商机, 签约, 订单, 跟进记录, 跟进计划, 待办事项, 渠道, 供应商, 导入批次, 对话, 操作记录, 业务设置, AI设置 and Mcp Connection

This Rule governs change operations on Crm Account at crm-desktop::crm::desktop-settings.

This Rule governs change operations on 线索 at crm-desktop::crm::desktop-settings.

This Rule governs change operations on 客户 at crm-desktop::crm::desktop-settings.

This Rule governs change operations on 客户联系人 at crm-desktop::crm::desktop-settings.

This Rule governs change operations on 未关联联系人 at crm-desktop::crm::desktop-settings.

This Rule governs change operations on 商机 at crm-desktop::crm::desktop-settings.

This Rule governs change operations on 签约 at crm-desktop::crm::desktop-settings.

This Rule governs change operations on 订单 at crm-desktop::crm::desktop-settings.

This Rule governs change operations on 跟进记录 at crm-desktop::crm::desktop-settings.

This Rule governs change operations on 跟进计划 at crm-desktop::crm::desktop-settings.

This Rule governs change operations on 待办事项 at crm-desktop::crm::desktop-settings.

This Rule governs change operations on 渠道 at crm-desktop::crm::desktop-settings.

This Rule governs change operations on 供应商 at crm-desktop::crm::desktop-settings.

This Rule governs change operations on 导入批次 at crm-desktop::crm::desktop-settings.

This Rule governs change operations on 对话 at crm-desktop::crm::desktop-settings.

This Rule governs change operations on 操作记录 at crm-desktop::crm::desktop-settings.

This Rule governs change operations on 业务设置 at crm-desktop::crm::desktop-settings.

This Rule governs change operations on AI设置 at crm-desktop::crm::desktop-settings.

This Rule governs change operations on Mcp Connection at crm-desktop::crm::desktop-settings.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
- The Product's scheduled process.
