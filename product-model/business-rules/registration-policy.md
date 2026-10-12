---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "register-account"
    },
    {
      "type": "entity",
      "id": "cloud-account"
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

# Registration honors its deployment, verification and consent checks

Registration follows the actual deployment policy, optional email-code verification, consent, input and request limits. It creates a cloud account without promising a workspace. Native registration attempts automatic login after account creation, and that later login can fail independently.
