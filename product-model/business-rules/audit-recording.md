---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-customer"
    },
    {
      "type": "capability",
      "id": "edit-customer"
    },
    {
      "type": "capability",
      "id": "delete-customers"
    },
    {
      "type": "capability",
      "id": "convert-lead"
    },
    {
      "type": "capability",
      "id": "merge-lead"
    },
    {
      "type": "capability",
      "id": "create-lead"
    },
    {
      "type": "capability",
      "id": "edit-lead"
    },
    {
      "type": "capability",
      "id": "record-followup"
    },
    {
      "type": "capability",
      "id": "edit-followup"
    },
    {
      "type": "capability",
      "id": "register-signing"
    },
    {
      "type": "capability",
      "id": "edit-signing"
    },
    {
      "type": "capability",
      "id": "delete-signing"
    },
    {
      "type": "capability",
      "id": "assign-owner"
    },
    {
      "type": "capability",
      "id": "release-to-pool"
    },
    {
      "type": "capability",
      "id": "claim-customer"
    },
    {
      "type": "capability",
      "id": "undo-pool-operation"
    },
    {
      "type": "capability",
      "id": "import-customers"
    },
    {
      "type": "capability",
      "id": "undo-import"
    },
    {
      "type": "capability",
      "id": "change-business-settings"
    },
    {
      "type": "capability",
      "id": "accept-draft"
    },
    {
      "type": "entity",
      "id": "assigned-contact"
    },
    {
      "type": "entity",
      "id": "audit-log"
    },
    {
      "type": "entity",
      "id": "business-config"
    },
    {
      "type": "entity",
      "id": "channel"
    },
    {
      "type": "entity",
      "id": "channel-draft"
    },
    {
      "type": "entity",
      "id": "customer"
    },
    {
      "type": "entity",
      "id": "customer-draft"
    },
    {
      "type": "entity",
      "id": "follow-up"
    },
    {
      "type": "entity",
      "id": "followup-draft"
    },
    {
      "type": "entity",
      "id": "import-batch"
    },
    {
      "type": "entity",
      "id": "lead"
    },
    {
      "type": "entity",
      "id": "lead-draft"
    },
    {
      "type": "entity",
      "id": "opportunity"
    },
    {
      "type": "entity",
      "id": "opportunity-draft"
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
      "id": "plan-draft"
    },
    {
      "type": "entity",
      "id": "signing"
    },
    {
      "type": "entity",
      "id": "signing-draft"
    },
    {
      "type": "entity",
      "id": "status-draft"
    },
    {
      "type": "entity",
      "id": "supplier"
    },
    {
      "type": "entity",
      "id": "task"
    },
    {
      "type": "entity",
      "id": "unassigned-contact"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "prisma/schema.prisma"
    }
  ]
}
---

# Audited operations retain their available actor and subject history

The implemented audited operations retain acting member, action, subject, summary, operation details and time in the visible audit history. Logging is best effort and does not establish complete history for every product operation.
