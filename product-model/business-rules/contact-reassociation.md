---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "detach-contact"
    },
    {
      "type": "capability",
      "id": "attach-contact"
    },
    {
      "type": "capability",
      "id": "delete-contact"
    },
    {
      "type": "capability",
      "id": "restore-contact"
    },
    {
      "type": "entity",
      "id": "assigned-contact"
    },
    {
      "type": "entity",
      "id": "follow-up"
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

# Reassociation restores only eligible former communication links

Detaching retains the former customer and recoverable links. Reattaching to that same customer restores only surviving still-null links; attaching elsewhere does not carry the former customer's links. Communication history survives contact deletion.
