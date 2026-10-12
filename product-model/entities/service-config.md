---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/gateway-auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/context.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/signup-policy.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/ops-auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/gateway.ts"
    }
  ],
  "relations": [
    {
      "entity": "cloud-account",
      "verb": "governs",
      "cardinality": "one-to-many"
    },
    {
      "entity": "workspace",
      "verb": "governs",
      "cardinality": "one-to-many"
    },
    {
      "entity": "sync-team",
      "verb": "governs",
      "cardinality": "one-to-many"
    }
  ],
  "singleton": true
}
---

# Service Config

The actual current runtime’s retained deployment and service configuration, including signup policies, operator identities and private outbound credentials.

## Information kept

- **Hosting/native mode** — The actual runtime deployment mode distinguishing local native and hosted/selfhost behavior.
- **Shared workspace address** — The runtime address identifying its configured shared workspace.
- **Registration policy/redirect** — The runtime's registration availability and supported post-registration destination.
- **Verification policy** — The runtime's actual registration/recovery verification configuration.
- **Operator identities** — The configured cloud identities that can enter product operations.
- **Console credential** — The configured operations-console credential used to validate entry.
- **Generation provider address** — The runtime's outbound model-provider destination.
- **Generation credential** — The retained gateway provider key used outbound by the product, not disclosed to the incoming client.
- **Generation model choices** — The configured models supplied by the runtime's model gateway.
- **Judgment credential** — The retained judgment-provider credential used for explicit column recognition, without generative-credit charging.
