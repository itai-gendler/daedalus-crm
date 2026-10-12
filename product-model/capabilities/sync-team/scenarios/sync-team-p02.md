---
{
  "kind": "primary",
  "routes": {
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The native timer/focus refresh or a 1.5-second local-write debounce triggers a round for the running book.",
      "kind": "condition",
      "entities": [
        {
          "entity": "desktop-config",
          "effect": "reads",
          "facts": [
            "Data mode",
            "Data location",
            "Account binding",
            "Current team binding"
          ]
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      },
      "unattended": true
    },
    {
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      },
      "text": "The Product reads the bound team configuration, installs or refreshes local synchronization triggers and inspects pending data before relay exchange checks.",
      "kind": "product",
      "entities": [
        {
          "entity": "sync-team",
          "effect": "reads",
          "facts": [
            "Sync state"
          ]
        },
        {
          "entity": "desktop-config",
          "effect": "reads",
          "facts": [
            "Data mode",
            "Data location",
            "Account binding",
            "Current team binding"
          ]
        }
      ]
    },
    {
      "text": "The mapped crm account reads set is inspected in this bound book before relay exchange; field clocks and tombstones determine the pending delta; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "crm-account",
          "effect": "reads",
          "facts": [
            "Name",
            "Login",
            "Title",
            "Active",
            "Created time",
            "Last change"
          ],
          "as": "crm-account-reads-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped business config reads set is inspected in this bound book before relay exchange; field clocks and tombstones determine the pending delta; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "business-config",
          "effect": "reads",
          "facts": [
            "Template",
            "Terms",
            "Field labels",
            "Source/grade/industry options",
            "Status display labels",
            "Currency",
            "Pool threshold"
          ],
          "as": "business-config-reads-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped channel reads set is inspected in this bound book before relay exchange; field clocks and tombstones determine the pending delta; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "channel",
          "effect": "reads",
          "facts": [
            "Name",
            "Phone",
            "Notes",
            "Owner",
            "Active",
            "Created time",
            "Last change"
          ],
          "as": "channel-reads-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped customer reads set is inspected in this bound book before relay exchange; field clocks and tombstones determine the pending delta; an empty delta set contributes no records.",
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
            "Pool state",
            "Pool entry",
            "Released by",
            "Claim time",
            "Claimed by",
            "Created time",
            "Last change"
          ],
          "as": "customer-reads-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped assigned contact reads set is inspected in this bound book before relay exchange; field clocks and tombstones determine the pending delta; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "assigned-contact",
          "effect": "reads",
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
          "as": "assigned-contact-reads-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped unassigned contact reads set is inspected in this bound book before relay exchange; field clocks and tombstones determine the pending delta; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "unassigned-contact",
          "effect": "reads",
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
          "as": "unassigned-contact-reads-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped lead reads set is inspected in this bound book before relay exchange; field clocks and tombstones determine the pending delta; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "reads",
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
          "as": "lead-reads-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped opportunity reads set is inspected in this bound book before relay exchange; field clocks and tombstones determine the pending delta; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "reads",
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
          "as": "opportunity-reads-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped signing reads set is inspected in this bound book before relay exchange; field clocks and tombstones determine the pending delta; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "signing",
          "effect": "reads",
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
          "as": "signing-reads-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped follow up reads set is inspected in this bound book before relay exchange; field clocks and tombstones determine the pending delta; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "follow-up",
          "effect": "reads",
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
          "as": "follow-up-reads-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped task reads set is inspected in this bound book before relay exchange; field clocks and tombstones determine the pending delta; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "task",
          "effect": "reads",
          "facts": [
            "Title",
            "Due time",
            "Owner",
            "Done",
            "Completion time",
            "Created time",
            "Last change"
          ],
          "as": "task-reads-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped plan reads set is inspected in this bound book before relay exchange; field clocks and tombstones determine the pending delta; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "reads",
          "facts": [
            "Subject",
            "Planned time",
            "Method",
            "Owner",
            "Done",
            "Created time",
            "Last change"
          ],
          "as": "plan-reads-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped audit log reads set is inspected in this bound book before relay exchange; field clocks and tombstones determine the pending delta; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "audit-log",
          "effect": "reads",
          "facts": [
            "Time",
            "Acting member",
            "Operation",
            "Subject",
            "Summary",
            "Details"
          ],
          "as": "audit-log-reads-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped supplier reads set is inspected in this bound book before relay exchange; field clocks and tombstones determine the pending delta; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "supplier",
          "effect": "reads",
          "facts": [
            "Name"
          ],
          "as": "supplier-reads-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped order reads set is inspected in this bound book before relay exchange; field clocks and tombstones determine the pending delta; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "order",
          "effect": "reads",
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
          "as": "order-reads-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      },
      "text": "The push request presents its retained device bearer for this exact team; the relay checks that account’s nonleft membership, actual Team Active, packet/device bounds and exact current key epoch.",
      "kind": "condition",
      "entities": [
        {
          "entity": "sync-membership",
          "effect": "reads",
          "facts": [
            "Left time",
            "Device participation"
          ]
        },
        {
          "entity": "sync-team",
          "effect": "reads",
          "facts": [
            "Active",
            "Invite/key generation"
          ]
        }
      ]
    },
    {
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      },
      "text": "After pushes succeed, pull checks the same requested team and bearer account, then returns selected sequence-bounded batches; newer keys use the actual envelope/private key and applicable DT2 signature binding.",
      "kind": "condition",
      "entities": [
        {
          "entity": "sync-team",
          "effect": "reads",
          "facts": [
            "Active",
            "Invite/key generation"
          ]
        },
        {
          "entity": "sync-membership",
          "effect": "reads",
          "facts": [
            "Left time",
            "Device participation"
          ]
        }
      ]
    },
    {
      "text": "The mapped crm account changes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "crm-account",
          "effect": "changes",
          "facts": [
            "Name",
            "Login",
            "Title",
            "Active",
            "Created time",
            "Last change"
          ],
          "as": "crm-account-changes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped crm account creates set is applied from successfully returned batches according to field clocks and tombstones for saved state Active; an empty delta set contributes no records.",
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
          "to": "Active",
          "as": "crm-account-creates-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped crm account creates set is applied from successfully returned batches according to field clocks and tombstones for saved state Inactive; an empty delta set contributes no records.",
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
          "to": "Inactive",
          "as": "crm-account-creates-2"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped crm account removes set is applied from successfully returned batches according to field clocks and tombstones for saved state Active; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "crm-account",
          "effect": "removes",
          "from": "Active",
          "as": "crm-account-removes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped crm account removes set is applied from successfully returned batches according to field clocks and tombstones for saved state Inactive; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "crm-account",
          "effect": "removes",
          "from": "Inactive",
          "as": "crm-account-removes-2"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped business config changes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "business-config",
          "effect": "changes",
          "facts": [
            "Template",
            "Terms",
            "Field labels",
            "Source/grade/industry options",
            "Status display labels",
            "Currency",
            "Pool threshold"
          ],
          "as": "business-config-changes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped business config creates set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
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
            "Pool threshold"
          ],
          "as": "business-config-creates-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped business config removes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "business-config",
          "effect": "removes",
          "as": "business-config-removes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped channel changes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "channel",
          "effect": "changes",
          "facts": [
            "Name",
            "Phone",
            "Notes",
            "Owner",
            "Active",
            "Created time",
            "Last change"
          ],
          "as": "channel-changes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped channel creates set is applied from successfully returned batches according to field clocks and tombstones for saved state Active; an empty delta set contributes no records.",
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
          "to": "Active",
          "as": "channel-creates-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped channel creates set is applied from successfully returned batches according to field clocks and tombstones for saved state Inactive; an empty delta set contributes no records.",
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
          "to": "Inactive",
          "as": "channel-creates-2"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped channel removes set is applied from successfully returned batches according to field clocks and tombstones for saved state Active; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "channel",
          "effect": "removes",
          "from": "Active",
          "as": "channel-removes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped channel removes set is applied from successfully returned batches according to field clocks and tombstones for saved state Inactive; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "channel",
          "effect": "removes",
          "from": "Inactive",
          "as": "channel-removes-2"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped customer changes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "changes",
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
            "Pool state",
            "Pool entry",
            "Released by",
            "Claim time",
            "Claimed by",
            "Created time",
            "Last change"
          ],
          "as": "customer-changes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped customer creates set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
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
            "Pool state",
            "Pool entry",
            "Released by",
            "Claim time",
            "Claimed by",
            "Created time",
            "Last change"
          ],
          "as": "customer-creates-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped customer removes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "removes",
          "as": "customer-removes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped assigned contact changes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "assigned-contact",
          "effect": "changes",
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
          "as": "assigned-contact-changes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped assigned contact creates set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
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
          "as": "assigned-contact-creates-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped assigned contact removes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "assigned-contact",
          "effect": "removes",
          "as": "assigned-contact-removes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped unassigned contact changes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "unassigned-contact",
          "effect": "changes",
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
          "as": "unassigned-contact-changes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped unassigned contact creates set is applied from successfully returned batches according to field clocks and tombstones for saved state Unassigned; an empty delta set contributes no records.",
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
          "to": "Unassigned",
          "as": "unassigned-contact-creates-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped unassigned contact removes set is applied from successfully returned batches according to field clocks and tombstones for saved state Unassigned; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "unassigned-contact",
          "effect": "removes",
          "from": "Unassigned",
          "as": "unassigned-contact-removes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped lead changes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "changes",
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
          "as": "lead-changes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped lead creates set is applied from successfully returned batches according to field clocks and tombstones for saved state 待跟进; an empty delta set contributes no records.",
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
          "to": "待跟进",
          "as": "lead-creates-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped lead creates set is applied from successfully returned batches according to field clocks and tombstones for saved state 跟进中; an empty delta set contributes no records.",
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
          "to": "跟进中",
          "as": "lead-creates-2"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped lead creates set is applied from successfully returned batches according to field clocks and tombstones for saved state 已转化; an empty delta set contributes no records.",
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
          "to": "已转化",
          "as": "lead-creates-3"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped lead creates set is applied from successfully returned batches according to field clocks and tombstones for saved state 已放弃; an empty delta set contributes no records.",
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
          "to": "已放弃",
          "as": "lead-creates-4"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped lead removes set is applied from successfully returned batches according to field clocks and tombstones for saved state 待跟进; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "removes",
          "from": "待跟进",
          "as": "lead-removes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped lead removes set is applied from successfully returned batches according to field clocks and tombstones for saved state 跟进中; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "removes",
          "from": "跟进中",
          "as": "lead-removes-2"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped lead removes set is applied from successfully returned batches according to field clocks and tombstones for saved state 已转化; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "removes",
          "from": "已转化",
          "as": "lead-removes-3"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped lead removes set is applied from successfully returned batches according to field clocks and tombstones for saved state 已放弃; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "removes",
          "from": "已放弃",
          "as": "lead-removes-4"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped opportunity changes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "changes",
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
          "as": "opportunity-changes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped opportunity creates set is applied from successfully returned batches according to field clocks and tombstones for saved state OPEN; an empty delta set contributes no records.",
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
          "to": "OPEN",
          "as": "opportunity-creates-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped opportunity creates set is applied from successfully returned batches according to field clocks and tombstones for saved state WON; an empty delta set contributes no records.",
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
          "to": "WON",
          "as": "opportunity-creates-2"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped opportunity creates set is applied from successfully returned batches according to field clocks and tombstones for saved state LOST; an empty delta set contributes no records.",
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
          "to": "LOST",
          "as": "opportunity-creates-3"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped opportunity removes set is applied from successfully returned batches according to field clocks and tombstones for saved state OPEN; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "removes",
          "from": "OPEN",
          "as": "opportunity-removes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped opportunity removes set is applied from successfully returned batches according to field clocks and tombstones for saved state WON; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "removes",
          "from": "WON",
          "as": "opportunity-removes-2"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped opportunity removes set is applied from successfully returned batches according to field clocks and tombstones for saved state LOST; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "removes",
          "from": "LOST",
          "as": "opportunity-removes-3"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped signing changes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "signing",
          "effect": "changes",
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
          "as": "signing-changes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped signing creates set is applied from successfully returned batches according to field clocks and tombstones for saved state Recorded; an empty delta set contributes no records.",
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
          "to": "Recorded",
          "as": "signing-creates-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped signing removes set is applied from successfully returned batches according to field clocks and tombstones for saved state Recorded; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "signing",
          "effect": "removes",
          "from": "Recorded",
          "as": "signing-removes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped follow up changes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "follow-up",
          "effect": "changes",
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
          "as": "follow-up-changes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped follow up creates set is applied from successfully returned batches according to field clocks and tombstones for saved state Recorded; an empty delta set contributes no records.",
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
          "to": "Recorded",
          "as": "follow-up-creates-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped follow up removes set is applied from successfully returned batches according to field clocks and tombstones for saved state Recorded; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "follow-up",
          "effect": "removes",
          "from": "Recorded",
          "as": "follow-up-removes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped task changes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Title",
            "Due time",
            "Owner",
            "Done",
            "Completion time",
            "Created time",
            "Last change"
          ],
          "as": "task-changes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped task creates set is applied from successfully returned batches according to field clocks and tombstones for saved state Unfinished; an empty delta set contributes no records.",
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
          "to": "Unfinished",
          "as": "task-creates-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped task creates set is applied from successfully returned batches according to field clocks and tombstones for saved state Done; an empty delta set contributes no records.",
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
          "to": "Done",
          "as": "task-creates-2"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped task removes set is applied from successfully returned batches according to field clocks and tombstones for saved state Unfinished; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "task",
          "effect": "removes",
          "from": "Unfinished",
          "as": "task-removes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped task removes set is applied from successfully returned batches according to field clocks and tombstones for saved state Done; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "task",
          "effect": "removes",
          "from": "Done",
          "as": "task-removes-2"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped plan changes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "changes",
          "facts": [
            "Subject",
            "Planned time",
            "Method",
            "Owner",
            "Done",
            "Created time",
            "Last change"
          ],
          "as": "plan-changes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped plan creates set is applied from successfully returned batches according to field clocks and tombstones for saved state Unfinished; an empty delta set contributes no records.",
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
          "to": "Unfinished",
          "as": "plan-creates-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped plan creates set is applied from successfully returned batches according to field clocks and tombstones for saved state Done; an empty delta set contributes no records.",
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
          "to": "Done",
          "as": "plan-creates-2"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped plan removes set is applied from successfully returned batches according to field clocks and tombstones for saved state Unfinished; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "removes",
          "from": "Unfinished",
          "as": "plan-removes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped plan removes set is applied from successfully returned batches according to field clocks and tombstones for saved state Done; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "removes",
          "from": "Done",
          "as": "plan-removes-2"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped audit log changes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "audit-log",
          "effect": "changes",
          "facts": [
            "Time",
            "Acting member",
            "Operation",
            "Subject",
            "Summary",
            "Details"
          ],
          "as": "audit-log-changes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped audit log creates set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
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
          "as": "audit-log-creates-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped audit log removes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "audit-log",
          "effect": "removes",
          "as": "audit-log-removes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped supplier changes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "supplier",
          "effect": "changes",
          "facts": [
            "Name"
          ],
          "as": "supplier-changes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped supplier creates set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "supplier",
          "effect": "creates",
          "facts": [
            "Name"
          ],
          "as": "supplier-creates-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped supplier removes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "supplier",
          "effect": "removes",
          "as": "supplier-removes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped order changes set is applied from successfully returned batches according to field clocks and tombstones; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "order",
          "effect": "changes",
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
          "as": "order-changes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped order creates set is applied from successfully returned batches according to field clocks and tombstones for saved state Recorded; an empty delta set contributes no records.",
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
          "to": "Recorded",
          "as": "order-creates-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The mapped order removes set is applied from successfully returned batches according to field clocks and tombstones for saved state Recorded; an empty delta set contributes no records.",
      "kind": "product",
      "entities": [
        {
          "entity": "order",
          "effect": "removes",
          "from": "Recorded",
          "as": "order-removes-1"
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      },
      "text": "The Product applies returned batches and records progress/errors only while rereading finds the same retained team ID; replay does not requery relay membership or activation per row.",
      "kind": "product",
      "entities": [
        {
          "entity": "sync-team",
          "effect": "changes",
          "facts": [
            "Sync state"
          ]
        }
      ]
    },
    {
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      },
      "kind": "product",
      "text": "When the implemented roster refresh is due or newly arrived identities require it, the Product derives local CRM account role assignments from that exact team roster without synchronizing passwords or roles.",
      "entities": [
        {
          "entity": "crm-account",
          "effect": "changes",
          "facts": [
            "Role assignment"
          ],
          "as": "crm-account-role-reconciled"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/client.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/sync-relay.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/sync-auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/device-token.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/desktop/sync/route.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/sync.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/team-scope.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/tables.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/local.ts"
    }
  ]
}
---

# Periodic/change-triggered sync

## Trigger

The native timer/focus refresh or a 1.5-second local-write debounce triggers a round for the running book.

## Outcome

Local preparation precedes relay validation; encrypted push precedes pull and returned-batch replay. The full supported dataset is merged with field clocks/tombstones, preserving partial progress and failures without continuous membership revalidation.

## Edge cases

- Only business configuration is shared as a setting; AI credentials, native preferences, conversations and import-undo batches remain outside the synchronized set.
- User passwords and roles do not synchronize; incoming identities receive local placeholders and roles are reconciled from creator/member identity.
- Latest follow-up is recalculated rather than copied. Channel collisions merge by name and redirect references; attribution snapshots do synchronize.

## Timing

The first timer runs after ten seconds. Subsequent intervals are eight seconds foreground and thirty seconds background, scheduled after the previous round finishes; focus invokes a round. Local writes debounce for 1.5 seconds, replay does not recursively schedule pushes, writes during a round can queue another, and simultaneous rounds share one promise. Exit waits and prevents starting another round. The shell path checks local mode/startup token and skips missing cloud/team configuration or detected directory-owner mismatch; direct write-triggered rounds do not repeat every shell preflight.

## Replay boundary

A response returned before removal/suspension can still replay. SQLite schema change retries once immediately; missing keys do not count as corrupt packets, while other repeated decryption failures skip after three attempts. Progress cannot restore an obsolete team binding, but rereading the binding is not continuous cancellation of in-flight work.
