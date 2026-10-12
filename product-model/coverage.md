---
{
  "scope": "Inspected identity, CRM, AI confirmation, enabled financial/order, native, sync, hosted operations, demo, MCP and gateway code at afa1d1d0060e32965110adcb2bb90dbd249c0ecf.",
  "method": "Static source tracing from user entry points through persistence, authorization and observable results.",
  "covered": [
    {
      "description": "Identity actions and account-owned native landing branches.",
      "paths": [
        "src/app/login/",
        "src/app/signup/",
        "src/app/forgot/",
        "src/app/login/after-login.ts",
        "src/lib/desktop/",
        "desktop/route-memory.js"
      ]
    },
    {
      "description": "Lead and customer actions, ownership, pool and scope implementations traced in the catalogue.",
      "paths": [
        "src/app/(app)/leads/",
        "src/app/(app)/customers/",
        "src/lib/team-scope.ts",
        "src/lib/pool-db.ts",
        "src/lib/check-then-write.ts",
        "src/lib/pool.ts",
        "src/lib/carry-over-db.ts",
        "src/lib/auth.ts"
      ]
    },
    {
      "description": "Enabled contact, opportunity, communication, plan and lightweight order branches.",
      "paths": [
        "src/app/(app)/contacts/",
        "src/app/(app)/opportunities/",
        "src/app/(app)/follow-ups/",
        "src/app/(app)/follow-ups/plans/",
        "src/app/(app)/orders/",
        "src/lib/order-contract.ts",
        "src/lib/order-db.ts"
      ]
    },
    {
      "description": "Import preview, fill, undo, export and AI preparation paths.",
      "paths": [
        "src/lib/import/",
        "src/app/(app)/customers/import-actions.ts",
        "src/app/(app)/customers/ai.ts"
      ]
    },
    {
      "description": "AI conversation, proposal card, explicit apply, dismissal, limited undo and history code.",
      "paths": [
        "src/app/(app)/dashboard/",
        "src/components/ProposalCard.tsx",
        "src/lib/ai-jobs.ts",
        "src/lib/thread-history.ts"
      ]
    },
    {
      "description": "Member, profile, business, AI, device and audit settings branches.",
      "paths": [
        "src/app/(app)/settings/",
        "src/lib/tenant/members.ts",
        "src/lib/business-config.ts",
        "src/lib/ai-usage.ts",
        "src/lib/constants.ts"
      ]
    },
    {
      "description": "Traced native maintenance, connection, update and notification entry branches.",
      "paths": [
        "desktop/main.js",
        "desktop/backup.js",
        "desktop/auto-backup.js",
        "desktop/updater.js",
        "desktop/reminders.js",
        "desktop/ops-notices.js"
      ]
    },
    {
      "description": "Team membership, mapped table, push/pull and key-management branches.",
      "paths": [
        "src/lib/sync/",
        "src/lib/tenant/sync-relay.ts",
        "src/app/api/sync/",
        "src/lib/tenant/sync-auth.ts",
        "src/lib/tenant/device-token.ts",
        "src/app/api/desktop/sync/route.ts",
        "desktop/sync.js",
        "src/lib/team-scope.ts"
      ]
    },
    {
      "description": "Operations guard, account, workspace, usage, sync-team and feedback implementations.",
      "paths": [
        "src/app/admin/",
        "src/lib/ops-auth.ts",
        "src/lib/ops-notices.ts",
        "src/lib/feedback-reply.ts",
        "prisma/control.prisma"
      ]
    },
    {
      "description": "Billing, feedback, demo-intake, demo-data and read-only MCP contracts.",
      "paths": [
        "src/app/(app)/billing/",
        "src/app/api/feedback/",
        "src/app/api/lead/",
        "src/lib/lead.ts",
        "src/app/(app)/demo-data.ts",
        "src/app/api/mcp/",
        "src/lib/mcp/tools.ts"
      ]
    },
    {
      "description": "Supported gateway authentication, model, credits, completion, charging and refund branches.",
      "paths": [
        "src/lib/tenant/gateway-auth.ts",
        "src/lib/tenant/credits.ts",
        "src/app/api/gateway/v1/models/",
        "src/app/api/gateway/v1/credits/",
        "src/app/api/gateway/v1/chat/completions/"
      ]
    },
    {
      "description": "Persisted CRM and control facts used in the described behavior.",
      "paths": [
        "prisma/schema.prisma",
        "prisma/control.prisma"
      ]
    },
    {
      "description": "MCP tool projections and whitelisted record-query validation inspected for the incoming contract.",
      "paths": [
        "src/lib/agent/tools.ts",
        "src/lib/agent/query.ts",
        "src/lib/mcp/"
      ]
    },
    {
      "description": "Workspace provisioning, selected-tenant resolution/cache and proxy-versus-callback expiry guard branches.",
      "paths": [
        "src/lib/tenant/workspaces.ts",
        "src/lib/tenant/guard.ts",
        "src/lib/prisma.ts",
        "src/lib/tenant/resolve.ts",
        "src/lib/tenant/context.ts"
      ]
    },
    {
      "description": "Personal start, current board and monthly/yearly data projection code traced to its existing result links.",
      "paths": [
        "src/app/(app)/dashboard/Board.tsx",
        "src/app/(app)/dashboard/DashboardView.tsx",
        "src/app/(app)/overview/",
        "src/app/(app)/reports/"
      ]
    },
    {
      "description": "Explicit import column-recognition configuration, direct-provider/native relay selection and relay validation/fallback boundaries.",
      "paths": [
        "src/lib/jev/",
        "src/app/api/gateway/v1/systemone/",
        "src/app/(app)/customers/ai.ts"
      ]
    }
  ],
  "exclusions": [
    {
      "description": "Disabled supplier profiles, quotations and full node/document management branches.",
      "paths": [
        "src/app/(app)/suppliers/",
        "src/lib/features.ts"
      ]
    },
    {
      "description": "Visual appearance settings and presentation assets.",
      "paths": [
        "src/app/(app)/settings/AppearanceTab.tsx",
        "public/"
      ]
    },
    {
      "description": "Development, packaging and release support definitions.",
      "paths": [
        "package.json",
        "scripts/"
      ]
    }
  ],
  "unmapped": [
    {
      "description": "Deep native platform installation, delta, crash/recovery and identity-notification combinations beyond the traced branches.",
      "paths": [
        "desktop/"
      ]
    },
    {
      "description": "Exhaustive cross-version synchronization, crypto, merge, deduplication and referral-repair combinations.",
      "paths": [
        "src/lib/sync/",
        "src/lib/tenant/sync-relay.ts"
      ]
    },
    {
      "description": "Remaining provider/protocol response-shape combinations and private judgment branches.",
      "paths": [
        "src/lib/gateway.ts",
        "src/app/api/gateway/v1/systemone/",
        "src/app/(app)/dashboard/ai.ts"
      ]
    },
    {
      "description": "Unread test and end-to-end assertions.",
      "paths": [
        "tests/",
        "e2e/",
        "e2e-desktop/"
      ]
    },
    {
      "description": "Dormant project, pinned and archive conversation lifecycle fields.",
      "paths": [
        "prisma/schema.prisma",
        "src/lib/thread-history.ts"
      ]
    },
    {
      "description": "Complete cloud-account inactive lifecycle beyond inspected flags and session checks.",
      "paths": [
        "src/lib/tenant/",
        "prisma/control.prisma"
      ]
    },
    {
      "description": "Uncorroborated tutorial and older registration descriptions.",
      "paths": [
        "docs/"
      ]
    }
  ],
  "limitations": [
    {
      "description": "Import auxiliary trade fingerprints do not fully establish later-change detection for undo.",
      "paths": [
        "src/lib/import/"
      ]
    },
    {
      "description": "Raw callback transactions and wrapper-scoped mutations implement different tenant/sales guard coverage.",
      "paths": [
        "src/lib/team-scope.ts",
        "src/lib/tenant/",
        "src/app/(app)/customers/pool-actions.ts"
      ]
    },
    {
      "description": "Draft decision and undo maps do not establish durable issued-proposal provenance or refresh restoration.",
      "paths": [
        "src/components/ProposalCard.tsx",
        "src/app/(app)/dashboard/apply.ts"
      ]
    },
    {
      "description": "Provider, SMTP and operating-system integration success is conditional on external delivery.",
      "paths": [
        "src/lib/gateway.ts",
        "src/lib/feedback-reply.ts",
        "desktop/reminders.js",
        "desktop/ops-notices.js"
      ]
    },
    {
      "description": "Native sales scope uses the running book’s cached local identity, whereas MCP own-member query filters use the token generator; cache freshness and raw-query/callback boundaries prevent a uniform scope guarantee.",
      "paths": [
        "src/lib/team-scope.ts",
        "src/lib/mcp/token.ts",
        "src/lib/agent/tools.ts",
        "src/lib/agent/query.ts"
      ]
    }
  ]
}
---

# Coverage
