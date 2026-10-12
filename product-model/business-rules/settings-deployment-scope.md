---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "change-business-settings"
    },
    {
      "type": "capability",
      "id": "change-ai-settings"
    },
    {
      "type": "capability",
      "id": "edit-profile"
    },
    {
      "type": "capability",
      "id": "change-password"
    },
    {
      "type": "capability",
      "id": "test-ai-connection"
    },
    {
      "type": "entity",
      "id": "ai-config"
    },
    {
      "type": "entity",
      "id": "business-config"
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
      "id": "mcp-connection"
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

# Settings preserve actual shared, native and hosted restrictions

The settings processes keep their actual shared/local/hosted configuration limits and initial-template gates. Native local settings are not assumed to match a chosen remote site. Clearing UI AI configuration can expose effective environment/cloud fallback rather than deleting that fallback.
