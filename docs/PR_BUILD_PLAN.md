# Five-PR Build Plan — Taste Graph & Recommendation OS

## PR 1 — Foundation, domain types, pgvector schema, RLS, harness
Implement Next.js/tooling, strict env and domain schemas, Supabase clients, migrations for profiles/sources/source_items/ingestion_runs/taste_nodes/signal_edges/embeddings/feedback/briefings, pgvector indexes, tenant RLS, seed fixtures, and test harness. Acceptance: empty DB migration succeeds; pgvector enabled; all external/persisted shapes use Zod; two-user isolation tests pass; lint/typecheck/Vitest/build are green; no any.

## PR 2 — One-source ingestion and semantic extraction
Implement one connector selected by the product owner, normalized source records, idempotency, provenance, retry state, structured OpenAI/Anthropic extraction through Vercel AI SDK, evidence spans, confidence, and embedding jobs. Acceptance: fixture import is repeatable without duplicates; malformed/provider failures are safe; deletion removes derived data; outputs validate; connector contract and failure tests pass; source terms are respected.

## PR 3 — Taste graph and feedback loop
Implement clustering, taste node lifecycle, embeddings persistence, signal edge creation/weighting, graph queries, user correction/merge/mute/pin, and save/dismiss/rate feedback. Acceptance: deterministic fixtures form expected clusters; edges are explainable and scoped; feedback changes weights; node edits preserve provenance; vector similarity is tested; RLS tests cover every graph table; no silent inference.

## PR 4 — Recommendation and briefing engine
Implement candidate retrieval, graph-based scoring using similarity, proximity, recency, novelty, diversity, and feedback; evidence-backed daily/weekly briefings; model adapter; persisted scoring snapshots. Acceptance: ranking is deterministic for fixed inputs; diversity prevents near duplicates; every result cites source items/nodes and confidence; briefing schema validates; evaluator thresholds and prompt-injection tests pass; generation failure does not corrupt graph data.

## PR 5 — Living graph UI, digest, realtime, polish
Implement Neo-Swiss dashboard, graph/list/timeline views, node and source detail, digest cards, explanations, feedback actions, realtime ingestion/job updates, accessibility, responsive states, and observability. Acceptance: Playwright covers import -> graph -> digest -> feedback; loading/empty/error/deletion states work; keyboard/screen-reader checks pass; no external action is automatic; production build and all tests pass.

## Serialization
One branch and one PR at a time. Each PR includes scope, migrations, rollback notes, tests, screenshots for UI, security review, and exact commands/results. Do not begin the next PR until the current PR is merged or explicitly closed.