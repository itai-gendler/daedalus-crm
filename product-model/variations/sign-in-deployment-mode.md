---
{
  "kind": "configuration",
  "of": "capability-scenario",
  "settings": [
    {
      "entity": "service-config",
      "fact": "Hosting/native mode"
    }
  ],
  "takesEffect": "The login page and sign-in action read the runtime's deployment mode on each request.",
  "stability": "The mode is fixed for a running deployment and changes only when the runtime is restarted in another mode; sign-in then uses that mode's form.",
  "alternatives": [
    {
      "id": "sign-in-p01",
      "selectedWhen": "Neither hosted nor desktop-local mode is set: a self-hosted deployment checks its own CRM accounts. This is the default."
    },
    {
      "id": "sign-in-p02",
      "selectedWhen": "Hosted mode is set (MULTI_TENANT is 1): a cloud account signs in and enters its workspace."
    },
    {
      "id": "sign-in-p03",
      "selectedWhen": "Desktop-local mode is set (DESKTOP_LOCAL is 1): the native client exchanges cloud credentials for a device token."
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/login/page.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/login/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/context.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/desktop/cloud.ts"
    }
  ]
}
---

# Sign-in Deployment Mode

A self-hosted team signs in with accounts kept on its own server, a hosted customer signs in with a cloud account that opens their workspace, and a desktop user signs in with a cloud account that opens their own local data. All three deployments are supported, so all three sign-in forms coexist.
