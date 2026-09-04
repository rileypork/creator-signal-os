# Product Requirements Document

## Goals
Make every inbound creator deal reviewable in minutes; make AI output explainable; prevent tenant leakage; establish a regression-tested extraction foundation.

## Functional requirements
FR1 authenticated users belong to organizations and may access only permitted tenant data. FR2 managers CRUD creators, rate cards, contacts, category conflicts, and redline rules. FR3 inbound messages are signature-verified, idempotent, stored with minimal source data, and parsed. FR4 extraction returns typed terms, confidence, evidence spans, model metadata, and explicit unknowns. FR5 matching selects applicable creator/rate card and explains price differences. FR6 analyzer flags exclusivity, usage, term, whitelisting, licensing, cancellation, payment, and category risks. FR7 dashboard supports filters, states, sorting, detail review, and audit timeline. FR8 draft generator creates an editable counter-draft but never sends automatically.

## Non-functional requirements
Strict typing; RLS; encrypted secrets; predictable latency with asynchronous processing where needed; accessible WCAG-oriented UI; observable errors without sensitive logs; deterministic tests; migration safety; provider adapters; idempotency and retries.

## Success metrics
Extraction field accuracy on gold set >= 95% for required fields; zero cross-tenant reads in RLS tests; webhook duplicate processing creates one deal; manager can review and draft a deal in under five minutes; CI green on every PR.
