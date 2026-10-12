---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "crm-account",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "lead",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "customer",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "assigned-contact",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "unassigned-contact",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "opportunity",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "signing",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "order",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "follow-up",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "plan",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "task",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "channel",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "supplier",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "import-batch",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "conversation",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "audit-log",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "business-config",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "ai-config",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::desktop-settings"
        }
      ]
    },
    {
      "type": "entity",
      "id": "mcp-connection",
      "effect": "creates",
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

# Only CRM administrators, sales managers and salespeople and the Product's scheduled process may create Crm Account, 线索, 客户, 客户联系人, 未关联联系人, 商机, 签约, 订单, 跟进记录, 跟进计划, 待办事项, 渠道, 供应商, 导入批次, 对话, 操作记录, 业务设置, AI设置 and Mcp Connection

This Rule governs create operations on Crm Account at crm-desktop::crm::desktop-settings.

This Rule governs create operations on 线索 at crm-desktop::crm::desktop-settings.

This Rule governs create operations on 客户 at crm-desktop::crm::desktop-settings.

This Rule governs create operations on 客户联系人 at crm-desktop::crm::desktop-settings.

This Rule governs create operations on 未关联联系人 at crm-desktop::crm::desktop-settings.

This Rule governs create operations on 商机 at crm-desktop::crm::desktop-settings.

This Rule governs create operations on 签约 at crm-desktop::crm::desktop-settings.

This Rule governs create operations on 订单 at crm-desktop::crm::desktop-settings.

This Rule governs create operations on 跟进记录 at crm-desktop::crm::desktop-settings.

This Rule governs create operations on 跟进计划 at crm-desktop::crm::desktop-settings.

This Rule governs create operations on 待办事项 at crm-desktop::crm::desktop-settings.

This Rule governs create operations on 渠道 at crm-desktop::crm::desktop-settings.

This Rule governs create operations on 供应商 at crm-desktop::crm::desktop-settings.

This Rule governs create operations on 导入批次 at crm-desktop::crm::desktop-settings.

This Rule governs create operations on 对话 at crm-desktop::crm::desktop-settings.

This Rule governs create operations on 操作记录 at crm-desktop::crm::desktop-settings.

This Rule governs create operations on 业务设置 at crm-desktop::crm::desktop-settings.

This Rule governs create operations on AI设置 at crm-desktop::crm::desktop-settings.

This Rule governs create operations on Mcp Connection at crm-desktop::crm::desktop-settings.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
- The Product's scheduled process.
