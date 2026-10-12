---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "prisma/control.prisma"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/admin/data.ts"
    }
  ]
}
---

# Model Usage Log

The operator-visible collective provider-call usage history. Missing stream/provider usage or failed logging does not become zero usage.

## Information kept

- **Time** — When the visible log event occurred.
- **Owner attribution** — The account or workspace to which the provider call is attributed.
- **Feature** — The provider call's available feature attribution, where the caller supplies it.
- **Model** — The configured AI model or the actual model attributed to a usage call.
- **Input usage** — The provider-reported input token usage, when available.
- **Output usage** — The provider-reported output token usage, when available.
