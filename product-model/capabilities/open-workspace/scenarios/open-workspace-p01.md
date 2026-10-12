---
{
  "kind": "primary",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes open workspace for the case “New account/seven-day trial and one-time password reveal”.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::workspaces"
        }
      }
    },
    {
      "text": "New account/seven-day trial and one-time password reveal. Provisions a new account and seven-day trial workspace, showing the generated password once. Failed creation cleanup may leave metadata.",
      "kind": "product",
      "entities": [
        {
          "entity": "cloud-account",
          "effect": "creates",
          "facts": [
            "Name",
            "Contact",
            "Active",
            "Credentials",
            "Session cutoff",
            "AI allowance",
            "Test marker",
            "Test history",
            "Registration time",
            "Initial gift received"
          ]
        },
        {
          "entity": "workspace",
          "effect": "creates",
          "facts": [
            "Name",
            "Address/slug",
            "Status",
            "Trial expiry",
            "Paid expiry",
            "Plan",
            "AI allowance",
            "Notes",
            "Payment references"
          ],
          "to": "TRIAL",
          "with": "cloud-account"
        },
        {
          "entity": "workspace-membership",
          "effect": "creates",
          "facts": [
            "Role",
            "Joined time"
          ],
          "with": "workspace"
        },
        {
          "entity": "crm-account",
          "effect": "creates",
          "facts": [
            "Name",
            "Login",
            "Title",
            "Role assignment",
            "Active",
            "Credentials",
            "Favorites",
            "Created time",
            "Last change"
          ],
          "to": "Active",
          "with": "workspace"
        }
      ],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::workspaces"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/admin/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/workspaces.ts#createWorkspace"
    }
  ]
}
---

# New account/seven-day trial and one-time password reveal

## Trigger

The operator invokes open workspace for the case “New account/seven-day trial and one-time password reveal”.

## Outcome

New account/seven-day trial and one-time password reveal. Provisions a new account and seven-day trial workspace, showing the generated password once. Failed creation cleanup may leave metadata.

## Edge cases

- The copied workspace book receives its first ADMIN CRM account and cloud-to-CRM mapping; its CRM password is an unusable managed password.
- File cleanup on failure does not guarantee already-created control metadata was removed.
