---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "prisma/schema.prisma"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/tables.ts"
    }
  ],
  "domain": "ai-access"
}
---

# AI设置

The current provider/model/credential and recognition configuration. Disclosed hints and configuration source are distinct from the private retained key. Native keys are not team-shared business settings.

## Information kept

- **Provider address** — The configured outbound provider endpoint.
- **Model** — The configured AI model or the actual model attributed to a usage call.
- **Choices** — The configured model choices offered in AI settings.
- **Credential** — The actual private configured key or current MCP bearer credential, distinct from a disclosed hint.
- **Credential hint** — The disclosed indication of a configured key, never the raw retained key.
- **Configuration source** — Whether effective AI access comes from UI settings or the applicable environment/cloud source.
- **Recognition enabled** — The opt-in setting for explicit import-column judgment, not a computed availability flag.
