# Five-PR Serialized Build Plan

## PR 1: Foundation and trusted data
Implement Next.js/tooling, env validation, domain/Zod schemas, Supabase clients, complete migration, seed fixtures, repository layer, auth/org membership, and RLS tests. Acceptance: empty DB migration succeeds; required tables/constraints/indexes exist; two-org isolation passes; strict lint/typecheck/unit CI is green; no any.

## PR 2: Webhook ingestion and brief extraction
Implement Resend/Postmark adapter, signature/replay protection, idempotency, thread normalization, attachment policy, processing states, provider abstraction, structured LLM extraction, evidence/confidence, retries, and gold fixtures. Acceptance: valid event produces one deal; duplicate is harmless; bad signature is rejected; malformed model output never persists; missing terms stay null; gold threshold passes; raw secrets are absent from logs.

## PR 3: Rate-card matching and risk engine
Implement rate-card CRUD, normalization for deliverable/platform/usage/duration/currency, deterministic matching, fee variance, redline rules, severity, explanations, and audit events. Acceptance: active card selection is deterministic; currency/unit cases pass; whitelisting, exclusivity, perpetual usage, category, payment, cancellation, and approval risks are correctly flagged with evidence; no canonical term is silently changed.

## PR 4: Triage dashboard and counter-offer
Implement minimal Neo-Swiss queue, filters, loading/empty/error states, detail split view, source spans, match comparison, risk cards, realtime status, draft generator, editable counter-offer, copy/export, and approval boundary. Acceptance: manager completes fixture flow; each recommendation cites data; draft is editable and never auto-sends; keyboard/screen-reader checks pass; Playwright happy/error/empty flows pass.

## PR 5: Beta hardening and launch
Implement observability, correction/feedback loop, retention/deletion, rate limits, deployment/runbook, performance, security review, accessibility polish, and pilot instrumentation. Acceptance: production build and all tests green; webhook load/replay tests pass; RLS audit passes; gold evaluation meets release threshold; no critical security finding; beta rollback documented.

## Serialization
Only one branch/PR may be active. Every PR includes scope, migration and rollback notes, test commands/results, security considerations, and screenshots for UI changes. Do not begin the next PR until the current PR is merged or explicitly closed.