---
{
  "kind": "primary",
  "routes": {
    "dp": "Native public",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The scheduled or page-triggered background check condition is reached.",
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
      "text": "Background check. Checks feed priority and GitHub fallback for a managed update plan. An unavailable source can present no newer release; explicit errors remain visible.",
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

# Background check

## Trigger

The scheduled or page-triggered background check condition is reached.

## Outcome

Background check. Checks feed priority and GitHub fallback for a managed update plan. An unavailable source can present no newer release; explicit errors remain visible.


## Edge cases

- The background check coalesces while already checking and leaves available/downloading/ready/installing work undisturbed; it does not start a second package preparation.
- Unavailable sources can yield no candidate and idle state; an exception in the check sets error state. Neither outcome proves that the running version is the newest.
- Missing valid SHA256, unsupported package/runtime or an unsuitable destination selects external manual download rather than an unverified managed installation. Whole-package preparation waits for an explicit action except when a started automatic delta falls back during the same invocation.
