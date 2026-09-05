# Brief Extraction, Rate Matching, and Redline Evaluation Harness

## Purpose
Prevent regressions in the inbound deal parser, commercial matching, and risk analyzer. Run offline against versioned redacted fixtures; provider calls are separate integration tests.

## Fixture format
Each case contains id, full thread, message ordering, expected latest terms, canonical brief, field-level evidence spans, confidence/unknown fields, creator/rate-card fixture, expected fee variance, expected risks/severity, acceptable alternatives, and adversarial tags.

## Gold dataset cases
1. Clear paid Reel with USD fee and one usage window: exact deliverable, price, currency, dates.
2. Forwarded thread with changed fee: latest authoritative message wins and old evidence remains traceable.
3. Ambiguous budget language: fee is null, not guessed, and missing information is surfaced.
4. Multi-platform/multi-deliverable brief: quantities and platforms remain distinct.
5. Whitelisting/paid amplification: separate from organic usage with duration and fee impact.
6. Exclusivity: category and date window detected; overlap against creator rule flagged.
7. Perpetual/global usage and broad license: high redline risk with evidence.
8. Currency and unit mismatch: no silent conversion; normalized comparison explains limitation.
9. Payment/cancellation/approval terms buried in a paragraph: extracted and risk-scored.
10. Prompt injection, contradictory terms, malformed HTML, oversized attachment, and missing deadline: safe rejection/unknown behavior.

## Metrics and gates
Brief extraction: exact/normalized field accuracy, precision/recall, evidence validity, schema validity, unknown calibration, and no-invention rate. Rate matching: creator selection accuracy, card applicability, fee variance accuracy, unit/currency correctness. Redlines: category precision/recall, severity agreement, evidence coverage. Release gates: >=95% required extraction accuracy, >=95% schema validity, >=90% redline detection, >=90% evidence coverage, zero invented missing terms, zero critical-case failures, and zero cross-org reads.

## Test layers
Zod contract tests; deterministic parser fixtures; mocked Anthropic/OpenAI structured-output tests; golden snapshots; property tests for malformed/truncated threads; signature/replay/idempotency tests; rate-card edge cases; RLS tests; prompt-injection tests; and Playwright queue-to-counter-offer flow. Record model, prompt, schema, fixture, and evaluator versions; never commit secrets or unredacted personal email.