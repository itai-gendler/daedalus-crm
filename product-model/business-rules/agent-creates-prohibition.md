---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "lead",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "customer",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "assigned-contact",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "unassigned-contact",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "opportunity",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "signing",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "order",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "follow-up",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "plan",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "task",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "channel",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "supplier",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "crm-account",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-agent"
        }
      ]
    },
    {
      "type": "entity",
      "id": "audit-log",
      "effect": "creates",
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

# No MCP client may create 线索, 客户, 客户联系人, 未关联联系人, 商机, 签约, 订单, 跟进记录, 跟进计划, 待办事项, 渠道, 供应商, Crm Account and 操作记录

This Rule governs create operations on 线索 at crm-agent.

This Rule governs create operations on 客户 at crm-agent.

This Rule governs create operations on 客户联系人 at crm-agent.

This Rule governs create operations on 未关联联系人 at crm-agent.

This Rule governs create operations on 商机 at crm-agent.

This Rule governs create operations on 签约 at crm-agent.

This Rule governs create operations on 订单 at crm-agent.

This Rule governs create operations on 跟进记录 at crm-agent.

This Rule governs create operations on 跟进计划 at crm-agent.

This Rule governs create operations on 待办事项 at crm-agent.

This Rule governs create operations on 渠道 at crm-agent.

This Rule governs create operations on 供应商 at crm-agent.

This Rule governs create operations on Crm Account at crm-agent.

This Rule governs create operations on 操作记录 at crm-agent.

Incoming MCP provides reads only; these operations are forbidden.
