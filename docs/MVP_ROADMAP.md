# MVP Roadmap

Phase 0 — repository and design contract: establish strict Next.js app, environment validation, CI, Supabase project, design tokens, and docs.

Phase 1 — trusted data foundation: migrations, organization membership, creators, rate cards, contacts, rules, deals, terms, drafts, audit events, RLS, typed repository layer, and test database harness.

Phase 2 — extraction intelligence: canonical email normalization, Zod extraction contracts, provider adapter, structured Claude/OpenAI calls, evidence and confidence, gold dataset, evaluator, fixtures, retries, and regression thresholds.

Phase 3 — commercial intelligence: rate-card matching, normalized units, currency handling, category conflict engine, redline rules, severity/explanation model, and review tests.

Phase 4 — operational intake: inbound provider signature validation, idempotency/replay defense, attachment policy, queue/background processing, notification preferences, and observability.

Phase 5 — manager workspace: triage feed, realtime updates, detail panel, source evidence, filters, keyboard actions, editable counter-draft, copy/export, audit history, responsive polish, accessibility, and production readiness.

Release gates: all PR acceptance criteria pass; no open critical security issue; RLS and webhook tests pass; gold evaluation meets threshold; build and E2E green; secrets and deployment runbook documented.
