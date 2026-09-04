# Five-PR Build Plan

## PR 1 — Foundation, types, schemas, migrations, DB harness
Deliver strict app/tooling, env schema, domain types, Zod schemas, Supabase client/server boundary, complete migrations, seed fixtures, repository functions, and RLS tests. Acceptance: clean install/build; no any; migrations apply from empty DB; all tables/constraints/indexes exist; two-tenant isolation tests pass; schema tests reject malformed data; CI runs lint/typecheck/unit/integration.

## PR 2 — LLM extraction, gold evaluation, regression suite
Deliver normalized email model, provider abstraction, structured output prompt, Zod validation, evidence/confidence, safe retries, model metadata, fixtures and evaluator. Acceptance: valid fixture extraction persists; malformed output is rejected and retried/fails safely; unknowns stay null; gold dataset has representative offers, ambiguity, missing terms, currency, usage, exclusivity, and adversarial text; required-field accuracy threshold is enforced; no raw secrets/log leakage.

## PR 3 — Matching, conflicts, redline analyzer
Deliver normalized rate units, creator/rate-card matching, category taxonomy, conflict windows, configurable redline rules, severity and explanations. Acceptance: exact and fallback matches are deterministic; currency/unit edge cases tested; active exclusivity conflict is flagged; usage/term/payment risks cite rule and evidence; no rule silently mutates canonical terms; unit/integration coverage is comprehensive.

## PR 4 — Inbound webhook, parser, notification layer
Deliver Postmark/Resend/SendGrid adapter, signature verification, idempotency, replay protection, email normalization, attachment policy, async processing/status, and notifications. Acceptance: valid webhook creates one deal; duplicate event is harmless; invalid signature is 401; oversized/malicious payload is rejected; provider failures retry safely; notification never leaks cross-tenant data; integration tests cover all branches.

## PR 5 — Triage dashboard, realtime feed, counter-drafts, polish
Deliver responsive dashboard, filters, states, detail/evidence view, realtime updates, editable counter-draft, copy/export, audit timeline, accessibility and visual system. Acceptance: manager can triage fixture end-to-end; realtime insert/update appears; draft reflects selected risks and is editable; no automatic send; keyboard and screen-reader checks pass; Playwright covers happy/error/empty/loading flows; production build green.

## Serialization rule
Never open the next PR until the current PR is merged or explicitly closed. Each PR must include scope, migration notes, test evidence, screenshots where UI changes, and rollback notes.
