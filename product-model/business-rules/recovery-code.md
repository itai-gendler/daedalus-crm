---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "reset-password"
    },
    {
      "type": "capability",
      "id": "change-password"
    },
    {
      "type": "entity",
      "id": "cloud-account"
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

# Password recovery uses bounded expiring one-use codes

Recovery and the desktop email-code password path enforce their actual bounded, expiring, one-use verification checks. Code sending uses a uniform response where implemented. Successful cloud password reset invalidates older sessions/devices under the identity path.
