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
      "target": "src/lib/tenant/device-token.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/gateway-auth.ts"
    }
  ]
}
---

# 登录设备

A named cloud-login device identified by its bearer credential, with retained client descriptors and revocation state.

## Information kept

- **Name** — The displayed identity of this subject.
- **Platform** — The operating-system platform reported by the logged device.
- **Architecture** — The architecture reported by the logged desktop client.
- **Client version** — The native application version reported for this client or device.
- **Login time** — When this desktop device authenticated to its cloud account.
- **Last use** — When the logged device most recently used the supported cloud service.
- **Revocation** — The retained device-revocation status/time that invalidates later service use.

## States

### Active

The logged device has not been revoked and remains subject to cloud-account/session checks.

### Revoked

The device can no longer authenticate later service requests; revocation does not delete its local files.
