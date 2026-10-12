---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "merge-lead"
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
      "target": "prisma/schema.prisma"
    }
  ]
}
---

# Merging reuses a matching customer without stealing its direct lead link

Merge checks the visible matching customer using normalized phone or supported Trade email. If another lead already holds that customer's direct association, that link remains and this lead records converted status/time and a merge note instead. Hidden duplicate information does not permit a second customer.
