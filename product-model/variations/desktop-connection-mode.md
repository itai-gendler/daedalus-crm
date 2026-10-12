---
{
  "kind": "configuration",
  "of": "capability-scenario",
  "settings": [
    {
      "entity": "desktop-config",
      "fact": "Data mode"
    }
  ],
  "takesEffect": "The shell reads its retained mode for native entry and mode controls; an accepted server address or return-local invocation changes that actual configuration immediately.",
  "stability": "Mode remains retained until the next successful mode change. The local service can remain running behind server mode; returning local uses the account-owned local landing, not the server route. A failed local start can leave mode Local while showing its recovery error.",
  "alternatives": [
    {
      "id": "change-desktop-settings-p01",
      "selectedWhen": "Preexisting Local mode offers entering a chosen server address."
    },
    {
      "id": "change-desktop-settings-p02",
      "selectedWhen": "Preexisting Server mode offers return to local data."
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/main.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/desktop/landing.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/route-memory.js"
    }
  ]
}
---

# Desktop Connection Mode

The existing configuration selects the supported actor input path described by these alternatives.
