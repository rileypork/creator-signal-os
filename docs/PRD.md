# Product Requirements Document

## Vision
An autonomous deal-flow and inbound email triage OS that gives talent managers a structured, explainable answer to: what is the brand asking, which creator fits, is the price right, what is risky, and what should we counter?

## Functional requirements
FR1: authenticated organization membership and strict RLS. FR2: CRUD creators, contacts, rate cards, and configurable redline rules. FR3: Resend/Postmark signed inbound webhooks accept full threads, normalize headers/body/attachments safely, deduplicate by provider event and content hash, and queue processing. FR4: Anthropic/OpenAI via Vercel AI SDK returns a Zod-validated structured brief with evidence, confidence, model version, and explicit unknowns. FR5: match creator and active rate card by deliverable/platform/usage/duration/currency. FR6: compute fee and term mismatch with transparent formulas. FR7: detect whitelisting, paid amplification, exclusivity, perpetual usage, category, cancellation, payment, and approval redlines with severity and evidence. FR8: dashboard supports queue, filters, status, detail, source thread, missing fields, risk cards, audit log, and realtime processing state. FR9: one-click counter-offer generator creates an editable draft; it never sends automatically.

## Non-functional requirements
Strict TypeScript, Zod boundaries, Supabase Postgres/Auth/RLS, idempotent jobs, signature verification, replay protection, privacy-minimized retention, redacted structured logs, accessible responsive UI, provider adapters, deterministic tests, and safe retries.

## MVP success metrics
>=95% required-field accuracy on gold briefs; >=95% schema-valid outputs; >=90% correct risk detection; zero invented missing terms; zero cross-org reads; duplicate webhook creates one deal; a manager reviews and drafts a deal in under five minutes.
