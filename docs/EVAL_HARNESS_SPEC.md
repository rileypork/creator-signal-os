# RosterOps Multi-Agent Evaluation Harness

## Purpose
Evaluate the wedge and workforce: messy thread/PDF extraction, campaign generation, rate/redline correctness, manager-voice drafts, action plans, and safe orchestration.

## Gold dataset
Each redacted case contains thread/PDF, message ordering, creator/rate card, brand/contact facts, expected brief fields and evidence, deliverables/deadlines, kickoff tasks, approval/reporting checklist, invoice schedule, expected redlines, counter-offer constraints, manager-voice examples, and policy/permission labels. Include changed terms, attachments, whitelisting, exclusivity, Net 30/60, travel, missing dates, contradictory messages, prompt injection, and malicious files.

## Agent evals
Inbox/Comms: summary, action extraction, factual draft and voice match. Deal: field accuracy, rate variance, usage/exclusivity/redline precision and negotiation history. Campaign: checklist completeness, date consistency, approval dependencies, invoice/reporting plans. Finance: arithmetic, due dates, splits, no invented payment state. Logistics: conflict-free scheduling proposals. Sales/Brand: provenance-backed enrichment and warmth scoring. Creator/Strategy: preference and fit grounding. Orchestrator: correct delegation, tool authorization, retries, trace completeness, budget, and approval gates.

## Metrics and gates
>=95% required extraction accuracy, >=95% schema validity, >=90% redline recall, >=95% campaign checklist completeness, >=95% draft factual accuracy, >=99% invoice arithmetic, zero unauthorized side effects, zero cross-tenant reads, and zero invented source facts. Measure precision/recall, evidence validity, deadline normalization, voice similarity by human rubric, calibration, latency, cost, and recovery.

## Test layers
Deterministic unit tests for money/dates/permissions; Zod contracts; mocked model/tool tests; golden snapshots; property tests for malformed input; replay/idempotency; RLS; approval-boundary; prompt-injection; agent trace/retry; and Playwright manager wedge flow. Persist model, prompt, tool, schema, fixture, and evaluator versions. Never commit secrets or unredacted personal data.