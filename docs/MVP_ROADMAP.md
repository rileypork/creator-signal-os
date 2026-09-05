# MVP Roadmap — Taste Graph & Recommendation OS

Phase 0: establish the product contract, Next.js foundation, strict TypeScript, environment validation, design tokens, CI, Supabase, privacy/deletion policy, and source adapter interface.

Phase 1: build the trusted signal foundation: profiles, sources, source items, ingestion runs, taste nodes, signal edges, embeddings, feedback, and RLS/pgvector migrations. Add deterministic fixtures and graph repository tests.

Phase 2: ship one connector end-to-end: import Instagram export, RSS, or saved links; normalize records; deduplicate; preserve provenance; queue extraction and embedding jobs; expose retry/deletion status.

Phase 3: ship semantic intelligence: Zod extraction contracts, embeddings, clustering, node merge/split/correction, edge weighting, graph traversal, feedback updates, and explainable scoring.

Phase 4: ship recommendation intelligence: candidate generation, similarity/graph/novelty/diversity/recency scoring, daily/weekly briefing generation, evidence cards, and evaluation harness.

Phase 5: ship the product surface: Neo-Swiss dashboard, graph explorer, signal detail, digest, feedback controls, realtime job status, accessibility, observability, and production hardening.

Release gates: one source reliably ingests; deletion works; no RLS leak; outputs validate; every recommendation has evidence; gold clustering/recommendation thresholds pass; all tests/build pass; no autonomous external action.