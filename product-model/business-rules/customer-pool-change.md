---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "customer",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-web::crm"
        },
        {
          "place": "crm-desktop::crm"
        }
      ],
      "facts": [
        "Pool state",
        "Pool entry",
        "Released by",
        "Sales owner",
        "Claim time",
        "Claimed by"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/pool-actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/pool-db.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/pool.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/carry-over-db.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/page.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/dashboard/page.tsx"
    }
  ],
  "permits": [
    {
      "actors": [
        "crm-admin",
        "crm-manager",
        "crm-sales"
      ],
      "configuredBy": "crm-account"
    },
    {
      "unattended": true,
      "configuredBy": "business-config"
    }
  ]
}
---

# Pool changes require the current account's dispatched human checks or the book's automatic-scan configuration

This Rule selects Customer changes to Pool state, Pool entry, Released by, Sales owner, Claim time or Claimed by in web and native CRM. The human configuration-bearing account is the exact `me` returned by this invocation's `requireUser()`; its retained Role assignment supplies the ADMIN branch. Target owner, releasing member and submitted restoration identities are distinct from that caller. The decision follows the invoked function and submitted undo action, not just the resulting pool state.

Manual `放进公海` resolves submitted customers through the ordinary query scope. Already-pooled rows are unchanged. Each remaining found row can be released only by ADMIN or its current sales owner; MANAGER has no administrator bypass. Unauthorized rows are skipped and counted; no releasable row with unauthorized rows remaining returns the implemented refusal. Release retains the sales owner and Customer last change, and records a manual pool entry attributed to `me`.

`领取` can be attempted by any account passing `requireUser()`, without an original-releaser or sales-owner prerequisite. Inside each full-scope callback transaction, deletion of the customer's surviving pool row gates success; zero deleted rows are unchanged. A missing customer rolls that deletion back. Success conditionally assigns `me` and upserts Claim time/Claimed by. Unfinished old-owner work follows afterward through `带走并记下`; that helper can fail after the customer claim committed.

Undo action `放进` removes only surviving pool rows whose submitted customer IDs match and whose retained releasing `userId` is `me.id`. ADMIN has no bypass. No match is unchanged. No original-action receipt or release timestamp is authenticated. Sales ownership and Claim facts are untouched.

Undo action `领取` preselects submitted customers currently sales-owned by `me` and outside the pool, and requires each submitted restoration account to be active. Each selected row restores the submitted owner, creates a manual pool entry attributed to `me`, and removes a Claim row only if that row's `userId` equals `me.id`. A kept Claim record is not required to prove that `me` originally claimed the customer. Submitted old-owner and carried-work arrays are not authenticated against an issued receipt. Eligibility is preselected before the transaction loop; the loop does not recheck all ownership/active-owner predicates against intervening reassignment.

Submitted carried plans/tasks restore only where their IDs still belong to this customer, remain owned by `me` and unfinished; submitted opportunities restore only where similarly owned and OPEN. Those consequences inherit the initiating undo decision, without another direct-edit authorization check inside the callback. Other Customer changes overlapping these facts—assignment, import repair, signing effects and restoration—meet a neutral additional pool policy unless actual dispatch invokes a pool branch; their own Rules still govern them. Neutrality grants no new mutation.

The unattended grant applies only to the actual automatic scan, using this book's Business Config and its triggering page's resolved member identity. Customers and Dashboard call it after `requireUser()`; Dashboard's initial-template redirect precedes it. It is not a cron job. Read the current normalized Pool threshold; zero disables scanning. This book's `poolSweptOn` receipt skips a matching local-calendar day and is not team-synchronized.

The cutoff is `startOf("day").subtract(poolDays - 1, "day")`. Select customers outside the pool, excluding 已签约 and 已流失, whose latest follow-up—or creation when absent—is strictly before that cutoff, with absent Claim or Claim time strictly before it. A retained `读团队()` configuration adds `salesOwnerId === triggeringMember.id` for every role; otherwise no extra owner predicate is added, though the ordinary wrapper still applies. Automatic entries retain sales ownership and Customer last change, record reason/time without a releasing member, and preserve concurrent-create fallback to per-row upsert, best-effort audit and daily receipt update after scanning. The receipt is not an atomic reservation. This unattended alternative grants no claim or undo.
