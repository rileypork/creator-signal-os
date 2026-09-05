# MVP Roadmap

## Phase 0 — Concierge validation
Manually process a representative inbox sample with a human-in-the-loop extraction template. Define canonical brief fields, rate-card vocabulary, redline taxonomy, privacy/retention policy, gold examples, and interview 3–5 managers. Exit when fields and workflow are stable.

## Phase 1 — Ingestion and extraction
Ship Supabase schema, organization/auth/RLS, creator and rate-card configuration, Resend/Postmark adapters, signed webhook verification, thread normalization, idempotency, queue state, structured Anthropic/OpenAI extraction, evidence/confidence, and evaluation harness. Exit when one real source processes reliably with safe retries.

## Phase 2 — Dashboard and triage
Ship minimal 1px Swiss triage queue, detail view, source evidence, missing-term prompts, creator/rate comparison, redline risk cards, filters/statuses, audit events, and editable one-click counter-offer. Exit when managers can triage end-to-end in under five minutes.

## Phase 3 — Beta launch
Pilot with a small set of talent teams. Add observability, feedback capture, correction workflow, performance tuning, export/copy controls, accessibility hardening, retention/deletion controls, onboarding, runbooks, and production deployment. Exit on gold thresholds, RLS/security review, stable webhook processing, and positive pilot feedback.