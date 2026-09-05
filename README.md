# Creator Signal OS / Inbound Deal Triage

Creator Signal OS is an autonomous deal-flow and inbound email triage OS for talent managers and creator coordinators. It turns messy brand threads into structured briefs, matches terms against creator rate cards, surfaces whitelisting/exclusivity and redline risk, and produces a manager-controlled counter-offer.

## Core loop
Resend/Postmark inbound webhook -> normalize thread -> extract brief with evidence and confidence -> match creator/rate card -> detect risk and mismatches -> triage dashboard -> one-click editable counter-offer. AI recommends; a human approves any outbound action.

## Stack and architecture
Next.js 15 App Router, strict TypeScript, Tailwind CSS, and a minimal Neo-Swiss interface with crisp typography and 1px borders. Supabase PostgreSQL/Auth/Storage/RLS. Anthropic or OpenAI through the Vercel AI SDK for structured extraction and drafting. Zod validates every external boundary. Resend/Postmark adapters are signature-verified, idempotent, and retryable. Vitest and Playwright provide coverage.

## Product documents
Read .devin/instructions.md first. See docs/APP_CONCEPT.md, docs/PRD.md, docs/MVP_ROADMAP.md, docs/PR_BUILD_PLAN.md, docs/DATABASE_SCHEMA.sql, and docs/EVAL_HARNESS_SPEC.md.

## Non-negotiables
No autonomous sending, no invented terms, no unvalidated JSON, no secrets in logs, no cross-organization reads, no `any`, and no PR without acceptance criteria and passing checks.