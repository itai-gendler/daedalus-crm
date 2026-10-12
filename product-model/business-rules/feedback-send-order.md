---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "send-feedback"
    },
    {
      "type": "capability",
      "id": "reply-feedback"
    },
    {
      "type": "capability",
      "id": "handle-feedback"
    },
    {
      "type": "entity",
      "id": "feedback"
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

# Feedback replies send mail before retaining the reply

Submitted feedback and replies retain their bounded input checks. Reply sends mail before saving reply/handled state. SMTP failure saves nothing; a persistence failure after sending can leave delivered mail without a retained reply.
