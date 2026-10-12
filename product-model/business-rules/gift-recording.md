---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "register-account"
    },
    {
      "type": "capability",
      "id": "grant-ai-credits"
    },
    {
      "type": "capability",
      "id": "read-gateway-info"
    },
    {
      "type": "capability",
      "id": "complete-model"
    },
    {
      "type": "entity",
      "id": "cloud-account"
    },
    {
      "type": "entity",
      "id": "gift-log"
    },
    {
      "type": "entity",
      "id": "logged-device"
    },
    {
      "type": "entity",
      "id": "service-config"
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

# Visible credit history records its actual account grant details

Initial gifts and manual account grants retain the actual account, amount, reason, note and time in the visible gift log. Manual test history belongs to the cloud account. An unseen workspace accounting receipt is not claimed as another visible gift history.
