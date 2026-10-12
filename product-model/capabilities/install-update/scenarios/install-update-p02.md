---
{
  "kind": "primary",
  "routes": {
    "dp": "Native public",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The scheduled or page-triggered ready delta installed on normal quit condition is reached.",
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
      "text": "Ready delta installed on normal quit. A human can restart with a ready package; a ready delta can install on normal quit. Installation hand-off can fail while the old version continues.",
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

# Ready delta installed on normal quit

## Trigger

The scheduled or page-triggered ready delta installed on normal quit condition is reached.

## Outcome

Ready delta installed on normal quit. A human can restart with a ready package; a ready delta can install on normal quit. Installation hand-off can fail while the old version continues.


## Edge cases

- Normal quit performs automatic installation only with a retained Ready delta. No ready delta or a ready whole package leaves that automatic installation branch unentered; a whole package requires its restart/install action.
- Windows handoff failure cancels that quit, sets error and permits the old version to continue. The Mac quit-time synchronous swap failure is logged; readiness does not guarantee a successful swap.
- Installation-in-progress guards prevent duplicate Windows handoffs. The actual packaged/platform checks remain in the update plan and swap helpers; startup/public observation creates no additional manual installation control.
