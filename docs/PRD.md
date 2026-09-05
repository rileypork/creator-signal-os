# Creator Signal OS — Product Requirements

## Goal
Build a private, explainable taste graph that converts one source of personal cultural signals into useful daily/weekly content and product recommendations.

## MVP requirements
FR1: authenticate users and isolate their data with RLS. FR2: support one source adapter at launch: Instagram export, RSS, or saved links. FR3: ingest idempotently with provenance and deletion support. FR4: extract structured entities, concepts, themes, style attributes, sentiment, novelty, and preference evidence. FR5: generate and store pgvector embeddings. FR6: create weighted edges between source items, taste nodes, creators, products, and concepts. FR7: let users inspect, rename, merge, pin, mute, and correct nodes. FR8: rank recommendation candidates using semantic similarity plus graph proximity, recency, novelty, diversity, and feedback. FR9: generate evidence-linked daily/weekly briefings. FR10: capture save, dismiss, rating, and annotation feedback. FR11: provide graph and chronological/list views with loading, empty, error, and privacy states.

## Non-goals
No autonomous publishing, purchasing, messaging, scraping that violates provider terms, public social graph, ads, custom model training, or multi-source complexity before the one-source loop is trustworthy.

## Success metrics
At least 95% schema-valid extraction; >=85% human-judged useful recommendations on the gold set; >=90% of recommendations have valid evidence; duplicate ingestion rate effectively zero; user can inspect why a recommendation appeared; RLS cross-tenant reads equal zero; feedback changes subsequent ranking in deterministic tests.

## Architecture requirements
Next.js 15 App Router, TypeScript strict, Tailwind Neo-Swiss UI, Supabase PostgreSQL/Auth/Storage/RLS/pgvector, OpenAI/Anthropic through Vercel AI SDK structured outputs, connector abstraction, graph scoring service, briefing generator, Vitest, and Playwright. Zod validates every boundary. Jobs are retryable and idempotent. Secrets and raw sensitive content are not logged.
