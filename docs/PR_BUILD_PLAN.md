# Serialized RosterOps PR Plan

PR1 — Trusted foundation: Next.js, Supabase organizations/managers/creators, roles/RLS, typed agent contracts, jobs/events/memory, CI, fixtures. Acceptance: empty migration, two-tenant RLS, strict typecheck, audit trace, no any.

PR2 — Wedge ingestion and Deal Agent: Resend/Postmark/Gmail/Outlook boundary, signature/replay/idempotency, thread/PDF normalization, structured brief extraction, rate-card match, redlines, evidence/confidence. Acceptance: messy fixture creates one deal, missing terms stay unknown, risks cite evidence, duplicate is harmless, gold gates pass.

PR3 — Campaign execution and Manager Workspace: campaign/deliverables, kickoff, deadlines, approvals, brand drafts, invoice/reporting plans, Inbox/Comms and Campaign agents, minimal Swiss UI. Acceptance: one messy deal produces complete workspace; all external effects have approval; Playwright and accessibility pass.

PR4 — Workforce expansion: Creator, Finance, Logistics, Career/Strategy, and Sales agents; memory scopes; manager voice; payment and calendar adapters; observability and agent health. Acceptance: tools are authorized/idempotent; money/calendar actions are gated; traces and failure recovery are visible; pilot SLA tests pass.

PR5 — Agency Command Center and network: leadership rollups, workload/revenue/pipeline, cross-agency memory, brand/contact intelligence, org charts, warmth/intent, and network permissions. Acceptance: aggregate correctness, row-level privacy, provenance for enrichment, performant dashboards, export/deletion, security review, production build.

No PR starts until the previous is merged/closed. Every PR includes migration/rollback notes, tests, screenshots, security analysis, and exact command results.