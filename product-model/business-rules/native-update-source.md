---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "check-updates"
    },
    {
      "type": "capability",
      "id": "download-update"
    },
    {
      "type": "entity",
      "id": "desktop-config"
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

# Managed update readiness requires a verified plan and digest

Update checking prefers the managed feed and uses its implemented GitHub fallback. A managed download follows its plan and SHA256 verification. Without the required digest, the working path is an external manual download rather than a verified ready package.
