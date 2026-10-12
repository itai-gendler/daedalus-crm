---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "parse-followup-note"
    },
    {
      "type": "capability",
      "id": "record-followup"
    },
    {
      "type": "entity",
      "id": "customer"
    },
    {
      "type": "entity",
      "id": "follow-up"
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

# Reviewed communication saves before its selected extra work

Parsing produces reviewable communication and optional plan/task suggestions. Human recording saves the communication first, then tries the selected extra writes; individual extra failures can leave the communication successfully retained.
