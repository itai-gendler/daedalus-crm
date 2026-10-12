---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "task",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::team"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "crm-admin",
        "crm-manager",
        "crm-sales"
      ],
      "configuredBy": "sync-team"
    },
    {
      "unattended": true,
      "configuredBy": "sync-team"
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

# Only the bound team's configured human or unattended exchange may create task

This Rule governs creates on task at crm-desktop::crm::team.

The configuration-bearing team is the team identified by the running local book's retained `.team.json.teamId` in its actual `CRM_DATA_DIR`. The governed records belong to that same book and exchange. A record owner, another joined member or another active team cannot select this configuration. The human alternative is the initiating CRM role whose account this explicit `立即同步` invocation resolves through `requireUser()`. The unattended alternative has no initiating CRM actor: it uses the running native service and its retained cloud credential, not a CRM browser cookie or a fabricated scheduled member.

Each push/pull relay request uses the account returned by `认同步` for the presented device bearer and membership for that exact account and requested team ID. Missing team or absent/left membership refuses with 403; an inactive selected Team refuses with 402. Team Active is read from the actual relay record on each request, not a kept flag on a customer or local settings. Device recognition verifies the retained token and revocation; this path does not additionally check Cloud Account Active. Eligibility never substitutes for caller authority.

Local preparation and failure bookkeeping remain permitted for the currently bound book even when exchange will be refused. Trigger installation, pending-change inspection and local error/progress updates can precede or follow a relay denial. Successful membership/activation validation is not a prerequisite for every local read. The exchange is push before pull: push checks nonempty packet data up to 8 MiB, device format, safe team identity, device/account conflicts, packet format and the exact current key epoch. Old epoch invokes key refresh and one retry; future epoch is rejected. Pull retains the same team, nonnegative floored sequence bound and 200-batch limit. A missing file younger than one minute stops before it for later retry; an older missing file is skipped.

Newer keys require the actual device envelope and private key. DT2 verifies the retained signing public key and team/epoch/device purpose binding; legacy DT1 has no added signature requirement. Local replay applies the successfully returned supported-table batches with field clocks, tombstones and actual merge/conflict handling. It does not requery relay membership or activation before every replayed row: removal or suspension after a response does not retroactively bar applying that response. Full exchange uses `看全部` and `在同步里`, including records outside ordinary native SALES views, without granting unrestricted direct editing.

The native timer first runs after ten seconds, then schedules eight seconds foreground or thirty seconds background after the preceding round finishes; focus refresh invokes a round. Local writes debounce for 1.5 seconds; replay writes do not recursively push, while writes during a round can queue another. Concurrent rounds share the in-progress promise; team exit waits for it and prevents a new round. The shell endpoint requires local mode and its actual startup token: wrong mode or missing expected token yields 404, mismatched token 403, and missing cloud/team configuration or detected directory-owner mismatch yields a skipped result. The direct change-triggered path does not repeat every shell preflight.

Missing team configuration refuses the round. Credential, network, key and relay failures preserve the implemented error/progress information. SQLite schema-change failure gets one immediate retry. Missing decryption keys do not count as corrupt packets; other repeated decryption failures skip after three attempts. Progress is written only if rereading `.team.json` still finds this same team ID, preventing obsolete binding restoration without promising continuous cancellation. These two configuration-dependent alternatives are exhaustive; neither a bare human nor a bare unattended grant bypasses this decision.
