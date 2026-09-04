# LLM Extraction Evaluation Harness

## Purpose
Prevent regressions in extracting commercial deal facts from inbound email. The harness must run offline against versioned fixtures and optionally against a provider in a separately marked integration suite.

## Fixture format
Each case contains id, raw_email, expected fields, acceptable alternatives, evidence requirements, adversarial notes, and tags. Required fields: brand, creator if explicit, deliverables, fee, currency, usage, exclusivity, dates, payment terms, cancellation terms, confidence, unknown fields, and evidence spans.

## Gold cases
1. Clear paid Instagram Reel: exact fee, USD, one deliverable, 30-day organic usage.
2. Ambiguous fee: email says budget is flexible; fee must be null and ambiguity flagged.
3. Whitelisting: paid amplification and duration must be captured separately from organic usage.
4. Exclusivity: beauty category and date window must produce structured restriction.
5. Missing deadline: deadline remains null, never inferred from received date.
6. Currency: GBP must remain GBP; no conversion without an explicit rate.
7. Multi-deliverable offer: each deliverable retains quantity and platform.
8. Adversarial prompt injection: email content cannot override system extraction contract.
9. Threaded email: newest relevant offer is selected with source evidence.
10. Contradiction: conflicting fee statements produce an uncertainty flag and both evidence spans.

## Metrics and gates
Compute exact/normalized field accuracy, precision/recall for flags, evidence validity, unknown calibration, schema validity, and tenant/security assertions. Required fields target >=95% exact/normalized accuracy; zero schema-invalid accepted outputs; zero invented values in missing-field cases. Fail CI on threshold regression or any critical-case failure.

## Test layers
Pure evaluator tests; Zod contract tests; mocked provider integration tests; golden snapshot tests with reviewed snapshots; property tests for malformed/truncated input; prompt-injection tests; latency/retry tests. Store model name, prompt version, schema version, fixture version, and timestamp for every run. Do not commit provider secrets or unredacted personal email.
