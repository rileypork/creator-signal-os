# Creator Signal OS

Creator Signal OS is a personal intelligence layer that turns creator posts, saved links, audience comments, and recommendation history into a living taste graph and weekly content/product recommendations.

## Wedge
Creators, curators, and cultural tastemakers are overwhelmed by scattered signals across platforms. The product captures those signals in one private, explainable system.

## Moat
Longitudinal taste data, semantic embeddings, a graph of concepts and relationships, and iterative human feedback loops compound over time.

## MVP
Ingest one source (Instagram export, RSS, or saved links), extract and cluster taste signals, render a living taste graph, and deliver a daily/weekly recommendation digest.

## Architecture
Next.js 15 App Router, React 19, strict TypeScript, Tailwind CSS with Neo-Swiss 1px borders, Supabase PostgreSQL/Auth/RLS/Storage with pgvector, OpenAI or Anthropic through Vercel AI SDK for structured semantic extraction, source connectors, graph-based scoring, and agent-written briefings. Every boundary uses Zod; zero `any`; tests use Vitest and Playwright.

## Documents
- [.devin/instructions.md](.devin/instructions.md) — autonomous Devin master prompt
- [docs/APP_CONCEPT.md](docs/APP_CONCEPT.md) — concept and user experience
- [docs/PRD.md](docs/PRD.md) — product requirements
- [docs/MVP_ROADMAP.md](docs/MVP_ROADMAP.md) — roadmap
- [docs/PR_BUILD_PLAN.md](docs/PR_BUILD_PLAN.md) — five serialized PRs
- [docs/DATABASE_SCHEMA.sql](docs/DATABASE_SCHEMA.sql) — pgvector schema and RLS
- [docs/EVAL_HARNESS_SPEC.md](docs/EVAL_HARNESS_SPEC.md) — clustering/recommendation evaluation

## Quality contract
One branch/PR at a time; strict typecheck; no `any`; Zod everywhere; deterministic unit/integration tests before PR; RLS and privacy by default; no autonomous publishing or external actions without user approval.