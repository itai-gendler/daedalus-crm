---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-contact"
    },
    {
      "type": "capability",
      "id": "edit-contact"
    },
    {
      "type": "entity",
      "id": "assigned-contact"
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

# A customer has at most one primary contact

Creating or editing an assigned contact updates primary selection and contact values transactionally so that the customer's current primary contact is unique.
