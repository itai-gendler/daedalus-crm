---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "da": "DA"
  },
  "steps": [
    {
      "text": "A CRM member invokes restore local data for the case “Select, preserve current copy, replace and reopen”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "The restore operation uses the selected copy.",
      "kind": "product",
      "entities": [
        {
          "entity": "backup",
          "effect": "reads",
          "facts": [
            "Time",
            "Class",
            "Location",
            "Snapshot"
          ],
          "as": "selected-copy"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "The restore operation preserves the current copy.",
      "kind": "product",
      "entities": [
        {
          "entity": "backup",
          "effect": "creates",
          "facts": [
            "Time",
            "Class",
            "Location",
            "Size",
            "Snapshot"
          ],
          "as": "pre-restore-copy"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "The restore operation replaces the customer snapshot set.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "removes",
          "as": "old-customer"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "The restore operation replaces the customer snapshot set.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "creates",
          "facts": [
            "Name",
            "Phone",
            "WhatsApp",
            "WeChat",
            "Country",
            "Email",
            "School/company",
            "Grade",
            "Major",
            "Follow-up status",
            "Decision status",
            "Expected signing date",
            "Sales owner",
            "Direct source",
            "Direct channel",
            "Referrer",
            "Attributed channel",
            "Attributed customer",
            "Channel owner",
            "Notes",
            "Latest follow-up",
            "Pool state",
            "Pool entry",
            "Released by",
            "Claim time",
            "Claimed by",
            "Created time",
            "Last change"
          ],
          "as": "restored-customer"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the 待跟进 snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "removes",
          "as": "old-lead-1",
          "from": "待跟进"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the 跟进中 snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "removes",
          "as": "old-lead-2",
          "from": "跟进中"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the 已转化 snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "removes",
          "as": "old-lead-3",
          "from": "已转化"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the 已放弃 snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "removes",
          "as": "old-lead-4",
          "from": "已放弃"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the 待跟进 snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "creates",
          "facts": [
            "Name",
            "Contact",
            "Industry",
            "Phone",
            "Email",
            "Status",
            "Source",
            "Responsible member",
            "Notes",
            "Conversion time",
            "Converted customer",
            "Created time",
            "Last change"
          ],
          "as": "restored-lead-1",
          "to": "待跟进"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the 跟进中 snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "creates",
          "facts": [
            "Name",
            "Contact",
            "Industry",
            "Phone",
            "Email",
            "Status",
            "Source",
            "Responsible member",
            "Notes",
            "Conversion time",
            "Converted customer",
            "Created time",
            "Last change"
          ],
          "as": "restored-lead-2",
          "to": "跟进中"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the 已转化 snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "creates",
          "facts": [
            "Name",
            "Contact",
            "Industry",
            "Phone",
            "Email",
            "Status",
            "Source",
            "Responsible member",
            "Notes",
            "Conversion time",
            "Converted customer",
            "Created time",
            "Last change"
          ],
          "as": "restored-lead-3",
          "to": "已转化"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the 已放弃 snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "creates",
          "facts": [
            "Name",
            "Contact",
            "Industry",
            "Phone",
            "Email",
            "Status",
            "Source",
            "Responsible member",
            "Notes",
            "Conversion time",
            "Converted customer",
            "Created time",
            "Last change"
          ],
          "as": "restored-lead-4",
          "to": "已放弃"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "The restore operation replaces the assigned contact snapshot set.",
      "kind": "product",
      "entities": [
        {
          "entity": "assigned-contact",
          "effect": "removes",
          "as": "old-assigned-contact"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "The restore operation replaces the assigned contact snapshot set.",
      "kind": "product",
      "entities": [
        {
          "entity": "assigned-contact",
          "effect": "creates",
          "facts": [
            "Name",
            "Phone",
            "WeChat",
            "Email",
            "Position",
            "Notes",
            "Primary",
            "Created time",
            "Last change"
          ],
          "as": "restored-assigned-contact"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Unassigned snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "unassigned-contact",
          "effect": "removes",
          "as": "old-unassigned-contact-1",
          "from": "Unassigned"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Unassigned snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "unassigned-contact",
          "effect": "creates",
          "facts": [
            "Name",
            "Phone",
            "WeChat",
            "Email",
            "Position",
            "Notes",
            "Former customer",
            "Former customer name",
            "Recoverable follow-up links",
            "Detach time",
            "Created time",
            "Last change"
          ],
          "as": "restored-unassigned-contact-1",
          "to": "Unassigned"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the OPEN snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "removes",
          "as": "old-opportunity-1",
          "from": "OPEN"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the WON snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "removes",
          "as": "old-opportunity-2",
          "from": "WON"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the LOST snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "removes",
          "as": "old-opportunity-3",
          "from": "LOST"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the OPEN snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "creates",
          "facts": [
            "Name",
            "Amount",
            "Currency",
            "Stage",
            "Probability",
            "Status",
            "Owner",
            "Expected date",
            "Notes",
            "Closed time",
            "Created time",
            "Last change"
          ],
          "as": "restored-opportunity-1",
          "to": "OPEN"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the WON snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "creates",
          "facts": [
            "Name",
            "Amount",
            "Currency",
            "Stage",
            "Probability",
            "Status",
            "Owner",
            "Expected date",
            "Notes",
            "Closed time",
            "Created time",
            "Last change"
          ],
          "as": "restored-opportunity-2",
          "to": "WON"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the LOST snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "creates",
          "facts": [
            "Name",
            "Amount",
            "Currency",
            "Stage",
            "Probability",
            "Status",
            "Owner",
            "Expected date",
            "Notes",
            "Closed time",
            "Created time",
            "Last change"
          ],
          "as": "restored-opportunity-3",
          "to": "LOST"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Recorded snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "signing",
          "effect": "removes",
          "as": "old-signing-1",
          "from": "Recorded"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Recorded snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "signing",
          "effect": "creates",
          "facts": [
            "Amount",
            "Precise amount",
            "Currency",
            "Signing date",
            "Notes",
            "Frozen sales owner",
            "Frozen channel owner",
            "Prior linked opportunity stage/probability",
            "Created time",
            "Last change"
          ],
          "as": "restored-signing-1",
          "to": "Recorded"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Recorded snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "order",
          "effect": "removes",
          "as": "old-order-1",
          "from": "Recorded"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Recorded snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "order",
          "effect": "creates",
          "facts": [
            "Number",
            "Amount",
            "Currency",
            "Payment information",
            "Supplier information",
            "Trade terms",
            "Legacy deposits",
            "Confirmation time",
            "Notes",
            "Owner",
            "Created time",
            "Last change"
          ],
          "as": "restored-order-1",
          "to": "Recorded"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Recorded snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "follow-up",
          "effect": "removes",
          "as": "old-follow-up-1",
          "from": "Recorded"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Recorded snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "follow-up",
          "effect": "creates",
          "facts": [
            "Type",
            "Title",
            "Status",
            "Participants",
            "Content",
            "Occurred time",
            "Duration",
            "Due time",
            "Original text",
            "Recording member",
            "Created time",
            "Last change",
            "Customer",
            "Contact",
            "Opportunity",
            "Order"
          ],
          "as": "restored-follow-up-1",
          "to": "Recorded"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Unfinished snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "removes",
          "as": "old-plan-1",
          "from": "Unfinished"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Done snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "removes",
          "as": "old-plan-2",
          "from": "Done"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Unfinished snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "creates",
          "facts": [
            "Subject",
            "Planned time",
            "Method",
            "Owner",
            "Done",
            "Created time",
            "Last change"
          ],
          "as": "restored-plan-1",
          "to": "Unfinished"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Done snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "creates",
          "facts": [
            "Subject",
            "Planned time",
            "Method",
            "Owner",
            "Done",
            "Created time",
            "Last change"
          ],
          "as": "restored-plan-2",
          "to": "Done"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Unfinished snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "task",
          "effect": "removes",
          "as": "old-task-1",
          "from": "Unfinished"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Done snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "task",
          "effect": "removes",
          "as": "old-task-2",
          "from": "Done"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Unfinished snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "task",
          "effect": "creates",
          "facts": [
            "Title",
            "Due time",
            "Owner",
            "Done",
            "Completion time",
            "Created time",
            "Last change"
          ],
          "as": "restored-task-1",
          "to": "Unfinished"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Done snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "task",
          "effect": "creates",
          "facts": [
            "Title",
            "Due time",
            "Owner",
            "Done",
            "Completion time",
            "Created time",
            "Last change"
          ],
          "as": "restored-task-2",
          "to": "Done"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Active snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "channel",
          "effect": "removes",
          "as": "old-channel-1",
          "from": "Active"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Inactive snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "channel",
          "effect": "removes",
          "as": "old-channel-2",
          "from": "Inactive"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Active snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "channel",
          "effect": "creates",
          "facts": [
            "Name",
            "Phone",
            "Notes",
            "Owner",
            "Active",
            "Created time",
            "Last change"
          ],
          "as": "restored-channel-1",
          "to": "Active"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Inactive snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "channel",
          "effect": "creates",
          "facts": [
            "Name",
            "Phone",
            "Notes",
            "Owner",
            "Active",
            "Created time",
            "Last change"
          ],
          "as": "restored-channel-2",
          "to": "Inactive"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "The restore operation replaces the supplier snapshot set.",
      "kind": "product",
      "entities": [
        {
          "entity": "supplier",
          "effect": "removes",
          "as": "old-supplier"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "The restore operation replaces the supplier snapshot set.",
      "kind": "product",
      "entities": [
        {
          "entity": "supplier",
          "effect": "creates",
          "facts": [
            "Name"
          ],
          "as": "restored-supplier"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "The restore operation replaces the conversation snapshot set.",
      "kind": "product",
      "entities": [
        {
          "entity": "conversation",
          "effect": "removes",
          "as": "old-conversation"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "The restore operation replaces the conversation snapshot set.",
      "kind": "product",
      "entities": [
        {
          "entity": "conversation",
          "effect": "creates",
          "facts": [
            "Title",
            "Page scope",
            "Messages",
            "Created time",
            "Last activity"
          ],
          "as": "restored-conversation"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Recorded snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "import-batch",
          "effect": "removes",
          "as": "old-import-batch-1",
          "from": "Recorded"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Undone snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "import-batch",
          "effect": "removes",
          "as": "old-import-batch-2",
          "from": "Undone"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Recorded snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "import-batch",
          "effect": "creates",
          "facts": [
            "File name",
            "Importer",
            "Import time",
            "Results",
            "Creation snapshots",
            "Fill snapshots",
            "Undo result",
            "Undone time"
          ],
          "as": "restored-import-batch-1",
          "to": "Recorded"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Undone snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "import-batch",
          "effect": "creates",
          "facts": [
            "File name",
            "Importer",
            "Import time",
            "Results",
            "Creation snapshots",
            "Fill snapshots",
            "Undo result",
            "Undone time"
          ],
          "as": "restored-import-batch-2",
          "to": "Undone"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "The restore operation replaces the audit log snapshot set.",
      "kind": "product",
      "entities": [
        {
          "entity": "audit-log",
          "effect": "removes",
          "as": "old-audit-log"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "The restore operation replaces the audit log snapshot set.",
      "kind": "product",
      "entities": [
        {
          "entity": "audit-log",
          "effect": "creates",
          "facts": [
            "Time",
            "Acting member",
            "Operation",
            "Subject",
            "Summary",
            "Details"
          ],
          "as": "restored-audit-log"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "The restore operation replaces the business config snapshot set.",
      "kind": "product",
      "entities": [
        {
          "entity": "business-config",
          "effect": "removes",
          "as": "old-business-config"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "The restore operation replaces the business config snapshot set.",
      "kind": "product",
      "entities": [
        {
          "entity": "business-config",
          "effect": "creates",
          "facts": [
            "Template",
            "Terms",
            "Field labels",
            "Source/grade/industry options",
            "Status display labels",
            "Currency",
            "Pool threshold",
            "Initial-template choice",
            "Demo marker"
          ],
          "as": "restored-business-config"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "The restore operation replaces the ai config snapshot set.",
      "kind": "product",
      "entities": [
        {
          "entity": "ai-config",
          "effect": "removes",
          "as": "old-ai-config"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "The restore operation replaces the ai config snapshot set.",
      "kind": "product",
      "entities": [
        {
          "entity": "ai-config",
          "effect": "creates",
          "facts": [
            "Provider address",
            "Model",
            "Choices",
            "Credential",
            "Credential hint",
            "Configuration source",
            "Recognition enabled"
          ],
          "as": "restored-ai-config"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Enabled snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "mcp-connection",
          "effect": "removes",
          "as": "old-mcp-connection-1",
          "from": "Enabled"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Disabled snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "mcp-connection",
          "effect": "removes",
          "as": "old-mcp-connection-2",
          "from": "Disabled"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Enabled snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "mcp-connection",
          "effect": "creates",
          "facts": [
            "Enabled",
            "Address",
            "Credential",
            "Generating member",
            "Generation time"
          ],
          "as": "restored-mcp-connection-1",
          "to": "Enabled"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Disabled snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "mcp-connection",
          "effect": "creates",
          "facts": [
            "Enabled",
            "Address",
            "Credential",
            "Generating member",
            "Generation time"
          ],
          "as": "restored-mcp-connection-2",
          "to": "Disabled"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Active snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "crm-account",
          "effect": "removes",
          "as": "old-crm-account-1",
          "from": "Active"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Inactive snapshot group, the restore operation replaces the prior records. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "crm-account",
          "effect": "removes",
          "as": "old-crm-account-2",
          "from": "Inactive"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Active snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
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
          "as": "restored-crm-account-1",
          "to": "Active"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "For the Inactive snapshot group, the restore operation retains the restored records in their saved state. Empty groups contribute no records.",
      "kind": "product",
      "entities": [
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
          "as": "restored-crm-account-2",
          "to": "Inactive"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "Restart/session landing uses the default home when no remembered route is valid.",
      "kind": "product",
      "entities": [
        {
          "entity": "backup",
          "effect": "reads",
          "facts": [
            "Location",
            "Snapshot"
          ],
          "as": "selected-copy"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "capability": "restore-local-data"
    },
    {
      "text": "Read the default home reached by the restored book landing.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::home"
        }
      },
      "capability": "browse-data"
    },
    {
      "text": "The restored account-owned book reopens at the default home when no acceptable remembered route applies. Restoration and restart failure remain separate outcomes; successful landing does not prove every referenced subject exists.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "reads",
          "facts": [
            "Name",
            "Phone",
            "WhatsApp",
            "WeChat",
            "Country",
            "Email",
            "School/company",
            "Grade",
            "Major",
            "Follow-up status",
            "Decision status",
            "Expected signing date",
            "Sales owner",
            "Direct source",
            "Direct channel",
            "Referrer",
            "Attributed channel",
            "Attributed customer",
            "Channel owner",
            "Notes",
            "Latest follow-up",
            "Pool state",
            "Pool entry",
            "Released by",
            "Claim time",
            "Claimed by",
            "Created time",
            "Last change"
          ],
          "as": "restored-customer"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::home"
        }
      },
      "capability": "browse-data"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/backup.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/main.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/route-memory.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/desktop/landing.ts"
    }
  ]
}
---

# Restore To Default Home

## Trigger

Restart/session landing uses the default home when no remembered route is valid.

## Outcome

The restored account-owned book reopens at the default home when no acceptable remembered route applies. Restoration and restart failure remain separate outcomes; successful landing does not prove every referenced subject exists.
