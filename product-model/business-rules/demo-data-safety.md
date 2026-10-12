---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "load-demo-data"
    },
    {
      "type": "capability",
      "id": "clear-demo-data"
    },
    {
      "type": "entity",
      "id": "customer"
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

# Demo seeding and cleanup preserve their deployment and data guards

Seeding is offered only in its supported selfhost web management context and checks that Customer/Lead/Channel/Opportunity work is empty. Cleanup requires its marker and explicit destructive confirmation; it can also clear real business work added after seeding. Native cannot seed but supports eligible older-marker cleanup. Cloud identity and nondeleted sets remain; both processes can fail nonatomically.
