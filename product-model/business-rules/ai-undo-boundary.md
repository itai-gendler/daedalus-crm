---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "undo-ai-change"
    },
    {
      "type": "entity",
      "id": "customer"
    },
    {
      "type": "entity",
      "id": "follow-up"
    },
    {
      "type": "entity",
      "id": "followup-draft"
    },
    {
      "type": "entity",
      "id": "status-draft"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/dashboard/apply.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/team-scope.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/credits.ts"
    }
  ]
}
---

# AI undo restores only supported still-matching changes

Undo supports an added communication and a still-matching status change, not arbitrary accepted drafts. Missing communication or subsequently changed status retains the later state. The process-memory receipt map does not authenticate arbitrary undo input.
