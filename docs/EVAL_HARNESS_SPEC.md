# Taste Clustering and Recommendation Evaluation Harness

## Goal
Measure whether Creator Signal OS extracts stable taste signals, forms useful clusters, updates from feedback, and recommends novel relevant content/products with defensible evidence.

## Fixture format
Each fixture includes source records, timestamps, author/context, expected entities/concepts/styles, expected cluster memberships, acceptable alternatives, provenance spans, user profile state, candidate set, gold ranking, rationale, and feedback events. Fixtures must be synthetic or redacted; never commit private raw exports.

## Gold cases
1. Repeated signals across three posts converge on one concept with stable embedding neighborhood.
2. A polysemous word is disambiguated using surrounding context.
3. Two adjacent but distinct styles remain separate until evidence supports merging.
4. A user dismisses a recommendation and its near-duplicates lose score.
5. A save increases related-node weight without overpowering all other signals.
6. A new concept receives a novelty bonus but is not recommended without relevance evidence.
7. Temporal drift makes recent feedback more influential than stale feedback.
8. Diversity prevents five recommendations from the same creator/category.
9. Deleted source data removes derived embeddings/evidence from user views.
10. Prompt injection inside a source record cannot alter extraction schema or scoring policy.

## Metrics and gates
Track schema-valid output rate, concept precision/recall, cluster purity, normalized mutual information, duplicate/near-duplicate rate, recommendation precision@k, nDCG@k, novelty, diversity, evidence coverage, calibration, feedback sensitivity, and deletion/privacy assertions. MVP gates: >=95% valid structured outputs, >=0.85 human usefulness, >=90% evidence coverage, no critical gold-case failure, and zero cross-user reads.

## Test layers
Pure deterministic graph/scoring tests; Zod contract tests; mocked provider/embedding tests; golden extraction and clustering snapshots; property tests for malformed records; ranking invariants; RLS tests; deletion cascade tests; prompt-injection tests; and Playwright tests for import, graph inspection, digest feedback, and error states. Persist model, prompt, schema, embedding model, fixture, and scoring versions for reproducibility. Provider calls are separately marked integration tests and never required for offline CI.