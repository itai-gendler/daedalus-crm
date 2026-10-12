---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-member"
    },
    {
      "type": "capability",
      "id": "edit-member"
    },
    {
      "type": "capability",
      "id": "deactivate-member"
    },
    {
      "type": "capability",
      "id": "reactivate-member"
    },
    {
      "type": "entity",
      "id": "crm-account"
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

# Member changes preserve the last active administrator and historical work

The shipped CRM role vocabulary is ADMIN/MANAGER/SALES. Member changes preserve the last active administrator and refuse invalid identity conversion. Hosted provisioning does not silently attach an existing cloud account. Deactivation transfers future work while preserving historical ownership and frozen signing attribution.
