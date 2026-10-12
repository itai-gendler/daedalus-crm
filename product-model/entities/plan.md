---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "prisma/schema.prisma"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/tables.ts"
    }
  ]
}
---

# 跟进计划

A distinct appended follow-up plan owned by a member, with subject, planned time, method and completion flag. Its display approximates completion time from last change.

## Information kept

- **Subject** — The arrangement's subject, or the entity and subject identified by an audit record.
- **Planned time** — The plan's intended follow-up time; existing plans are not replaced by a new plan.
- **Method** — The plan's communication method, such as the selected contact method.
- **Owner** — The member responsible for this work or channel.
- **Done** — Whether the arrangement is currently completed.
- **Created time** — When this subject was created.
- **Last change** — The kept last modification time used by the applicable version/snapshot guard.

## States

### Unfinished

The arrangement has not been marked done and remains future work.

### Done

The arrangement is marked done; tasks retain completion time while plans use their last change.
