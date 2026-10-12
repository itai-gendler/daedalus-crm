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

# 待办事项

A distinct member-owned task with title, optional due time and retained completion time.

## Information kept

- **Title** — The retained title used for this account, conversation, communication or task.
- **Due time** — The task deadline or communication due time, where supplied.
- **Owner** — The member responsible for this work or channel.
- **Done** — Whether the arrangement is currently completed.
- **Completion time** — The retained task completion timestamp; reopening clears it.
- **Created time** — When this subject was created.
- **Last change** — The kept last modification time used by the applicable version/snapshot guard.

## States

### Unfinished

The arrangement has not been marked done and remains future work.

### Done

The arrangement is marked done; tasks retain completion time while plans use their last change.
