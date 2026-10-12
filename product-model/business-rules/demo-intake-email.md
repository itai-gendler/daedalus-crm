---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "request-demo"
    },
    {
      "type": "entity",
      "id": "website-caller"
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

# Demo intake validates its Origin, fields and daily success limits

Demo intake accepts the configured exact Origins, validates its supported text fields and email, and counts only successfully sent requests against five per known IP and fifty global requests per day. Honeypot input returns apparent success without sending. SMTP failure is exposed. This contract sends an email and never creates a CRM Lead.
