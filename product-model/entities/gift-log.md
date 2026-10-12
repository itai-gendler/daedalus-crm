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
      "target": "src/lib/tenant/credits.ts"
    }
  ]
}
---

# Gift Log

The operator-visible collective account grant history with amount, reason, note and time.

## Information kept

- **Account** — The cloud account receiving this credit grant.
- **Time** — When the visible log event occurred.
- **Amount** — The retained amount in its currency, with the financial process’s validation.
- **Reason** — The retained explanation supporting this proposed CRM change.
- **Note** — The credit grant's retained explanatory note.
