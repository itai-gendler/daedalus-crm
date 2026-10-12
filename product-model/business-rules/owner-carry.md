---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "assign-owner"
    },
    {
      "type": "capability",
      "id": "undo-owner-assignment"
    },
    {
      "type": "capability",
      "id": "deactivate-member"
    },
    {
      "type": "capability",
      "id": "claim-customer"
    },
    {
      "type": "capability",
      "id": "register-signing"
    },
    {
      "type": "entity",
      "id": "crm-account"
    },
    {
      "type": "entity",
      "id": "customer"
    },
    {
      "type": "entity",
      "id": "opportunity"
    },
    {
      "type": "entity",
      "id": "order"
    },
    {
      "type": "entity",
      "id": "plan"
    },
    {
      "type": "entity",
      "id": "signing"
    },
    {
      "type": "entity",
      "id": "supplier"
    },
    {
      "type": "entity",
      "id": "task"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "prisma/schema.prisma"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/pool-actions.ts"
    }
  ]
}
---

# Ownership transfer carries specified unfinished work and preserves history

Transfer, claim and deactivation move the specified unfinished plans/tasks and OPEN opportunities from their previous owner under the actual carry-over path. Signing attribution is frozen before applicable ownership changes. Undo considers submitted carried-work IDs still attached to the customer and eligible by current owner/completion/status; those arrays are not authenticated against issued receipts. It does not restore every item the recipient currently owns.
