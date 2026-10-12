---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "submit-payment-reference"
    },
    {
      "type": "capability",
      "id": "activate-workspace"
    },
    {
      "type": "entity",
      "id": "workspace"
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

# A pending payment reference does not activate a subscription

Submission appends a pending-check payment reference. Actual activation or renewal is a separate operations action after verification; no shipped automatic payment callback is established by this submission.
