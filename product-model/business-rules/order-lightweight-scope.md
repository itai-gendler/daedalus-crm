---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "browse-orders"
    },
    {
      "type": "capability",
      "id": "register-signing"
    },
    {
      "type": "capability",
      "id": "edit-signing"
    },
    {
      "type": "entity",
      "id": "customer"
    },
    {
      "type": "entity",
      "id": "order"
    },
    {
      "type": "entity",
      "id": "signing"
    },
    {
      "type": "entity",
      "id": "supplier"
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

# Enabled order work stays within its lightweight contract

The enabled order/signing process keeps order number, supplier lookup, payment and supported lightweight Trade fields. Disabled supplier profiles, quotations and full node/document management are outside that process.
