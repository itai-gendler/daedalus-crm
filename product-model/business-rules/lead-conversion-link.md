---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "convert-lead"
    },
    {
      "type": "capability",
      "id": "merge-lead"
    },
    {
      "type": "capability",
      "id": "edit-lead"
    },
    {
      "type": "entity",
      "id": "customer"
    },
    {
      "type": "entity",
      "id": "lead"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/leads/actions.ts#convertLead"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/lead-convert.ts#线索转档案"
    }
  ]
}
---

# Lead conversion marks and links once while merge preserves occupied links

Conversion atomically marks the lead, records conversion time and creates its new customer association, guarding repeat/concurrent conversion. Status editing alone creates no customer. Merge can mark converted without taking another lead's occupied direct association. Company/contact/industry/source/email mapping follows the actual General or Trade configuration.

## Rationale

When the configured first profile field names a company and the contact is nonblank, lead name becomes company and contact becomes customer name. Recognized industry labels receive industry; unrelated labels remain empty. General source and an otherwise unplaced email are preserved in notes. Trade source/email use the supported trade profile, with invalid normalized values omitted while original lead text remains.
