---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "lead",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "customer",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "assigned-contact",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "unassigned-contact",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "opportunity",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "signing",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "order",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "follow-up",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "plan",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "task",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "channel",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "supplier",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "crm-account",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "audit-log",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    }
  ],
  "permits": [],
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

# No MCP client may change 线索, 客户, 客户联系人, 未关联联系人, 商机, 签约, 订单, 跟进记录, 跟进计划, 待办事项, 渠道, 供应商, Crm Account and 操作记录

This Rule governs change operations on 线索 at crm-agent.

This Rule governs change operations on 客户 at crm-agent.

This Rule governs change operations on 客户联系人 at crm-agent.

This Rule governs change operations on 未关联联系人 at crm-agent.

This Rule governs change operations on 商机 at crm-agent.

This Rule governs change operations on 签约 at crm-agent.

This Rule governs change operations on 订单 at crm-agent.

This Rule governs change operations on 跟进记录 at crm-agent.

This Rule governs change operations on 跟进计划 at crm-agent.

This Rule governs change operations on 待办事项 at crm-agent.

This Rule governs change operations on 渠道 at crm-agent.

This Rule governs change operations on 供应商 at crm-agent.

This Rule governs change operations on Crm Account at crm-agent.

This Rule governs change operations on 操作记录 at crm-agent.

Incoming MCP provides reads only; these operations are forbidden.
