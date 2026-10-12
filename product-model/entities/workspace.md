---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "prisma/control.prisma"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/workspaces.ts"
    }
  ],
  "relations": [
    {
      "entity": "workspace-membership",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "customer",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "lead",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "assigned-contact",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "unassigned-contact",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "opportunity",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "signing",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "order",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "follow-up",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "plan",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "task",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "channel",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "supplier",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "conversation",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "import-batch",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "audit-log",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "business-config",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "ai-config",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "mcp-connection",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "crm-account",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ]
}
---

# 工作区

A hosted CRM workspace with its own book, memberships, plan, allowance and subscription dates.

## Information kept

- **Name** — The displayed identity of this subject.
- **Address/slug** — The workspace address used to select its hosted CRM context.
- **Status** — The subject's recorded status vocabulary described in its states or kept vocabulary.
- **Trial expiry** — The workspace's retained trial entitlement expiry.
- **Paid expiry** — The workspace's retained paid entitlement expiry.
- **Plan** — The selected workspace subscription plan.
- **AI allowance** — The retained grant/usage accounting for this owner; compatibility test display 999 does not replace the real balance.
- **Notes** — The subject’s retained notes.
- **Payment references** — The dated pending-check references appended without granting entitlement.

## States

### TRIAL

The workspace is recorded as trial; its entitlement considers future paid expiry first, then trial expiry.

### ACTIVE

The workspace is recorded as active; entitlement requires future paid expiry.

### SUSPENDED

The workspace is suspended with false computed writability; data remains retained and actual guarded writes follow the workspace entitlement Rule.
