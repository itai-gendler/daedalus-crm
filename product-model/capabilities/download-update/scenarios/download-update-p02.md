---
{
  "kind": "primary",
  "routes": {
    "dp": "Native public",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The scheduled or page-triggered qualified automatic delta download condition is reached.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "dp": {
          "place": "crm-desktop::public"
        },
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "unattended": true
    },
    {
      "text": "Qualified automatic delta download. An initial whole-package plan is human initiated; eligible delta download can be automatic, with whole-package fallback continuing the same invocation. Managed plan and SHA256 validation are required; failures can fall back or require external manual download.",
      "kind": "product",
      "entities": [
        {
          "entity": "desktop-config",
          "effect": "changes",
          "facts": [
            "Update state",
            "Update version/method"
          ]
        }
      ],
      "contexts": {
        "dp": {
          "place": "crm-desktop::public"
        },
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      }
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
      "target": "desktop/backup.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/auto-backup.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/updater.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/reminders.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/desktop/landing.ts"
    }
  ]
}
---

# Qualified automatic delta download

## Trigger

The scheduled or page-triggered qualified automatic delta download condition is reached.

## Outcome

Qualified automatic delta download. An initial whole-package plan is human initiated; eligible delta download can be automatic, with whole-package fallback continuing the same invocation. Managed plan and SHA256 validation are required; failures can fall back or require external manual download.


## Edge cases

- Automatic preparation requires a qualifying managed delta plan and source digest checks. An unavailable/error state with no retained plan rechecks; other ineligible states do not start a download.
- Network failure can retry the alternate source. Failed delta assembly removes its staged package and changes the retained plan to whole-package preparation within the same invocation; this fallback can therefore download the whole package without another human action.
- A failing whole-package transfer or SHA256 comparison leaves error state rather than Ready. A resumed/retried transfer retains the actual partial-file behavior; external manual plans do not gain managed readiness.
