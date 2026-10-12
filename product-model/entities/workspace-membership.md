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
      "target": "src/lib/tenant/members.ts"
    }
  ],
  "relations": [
    {
      "entity": "crm-account",
      "verb": "identifies",
      "cardinality": "one-to-one"
    }
  ]
}
---

# Workspace Membership

One cloud account’s role and participation in one hosted workspace, linked to its CRM identity.

## Information kept

- **Role** — The membership vocabulary within the containing workspace or synchronization team.
- **Joined time** — When the account joined the containing workspace or team.
