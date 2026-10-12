---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "sign-in"
    },
    {
      "type": "capability",
      "id": "sign-out"
    },
    {
      "type": "capability",
      "id": "revoke-device"
    },
    {
      "type": "entity",
      "id": "cloud-account"
    },
    {
      "type": "entity",
      "id": "crm-account"
    },
    {
      "type": "entity",
      "id": "desktop-config"
    },
    {
      "type": "entity",
      "id": "logged-device"
    },
    {
      "type": "entity",
      "id": "workspace"
    },
    {
      "type": "entity",
      "id": "workspace-membership"
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

# Sessions use the correct active identity and deployment credential store

Login and account work validate the active identity in the actual selfhost or cloud credential store, retaining revocation and cooldown checks. Native local data selection follows the authenticated cloud identity; an authenticated identity does not adopt another account's bound directory.
