---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/feedback/route.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/feedback-reply.ts"
    }
  ]
}
---

# 反馈

Submitted feedback and its context, handled state and contained replies. Successful mail sending precedes retention of a reply.

## Information kept

- **Body** — The submitted feedback text.
- **Page** — The page context supplied with the feedback.
- **Version** — The application version supplied with the feedback.
- **System** — The operating-system details supplied with the feedback.
- **Account/contact** — The submitting account identity and contact available for a reply.
- **Submitted time** — When the feedback was submitted.
- **Handled** — The retained handled/unhandled feedback state.
- **Replies** — Contained recorded mail replies; sending precedes successful persistence.

## States

### Unhandled

Operations has not marked this feedback handled.

### Handled

Operations has marked this feedback handled, including after a successfully saved reply.
