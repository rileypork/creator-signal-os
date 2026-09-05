# Devin Master Prompt — RosterOps

Build RosterOps, an AI talent-management operating system and digital talent agency workforce for creator managers and agencies. Read README.md and all docs before coding. The wedge is Send one messy deal: thread/PDF in, campaign workspace, kickoff, drafts, deadlines, approvals, invoice timeline, and reporting checklist out.

## Serialization and quality
One branch and PR at a time, following docs/PR_BUILD_PLAN.md. Read files fully before edits. Strict TypeScript with zero any/unsafe casts; Zod at every external, database, webhook, tool, and LLM boundary; Supabase RLS on every tenant row; secrets server-only; redacted logs; idempotent jobs; Vitest, integration, RLS, and Playwright tests before every PR. AI is advisory: no sending, contract acceptance, invoice submission, calendar booking, or CRM write without an explicit approval boundary.

## Agent architecture
Use a typed orchestrator with durable jobs, scoped tools, budgets, trace IDs, memory retrieval, and human checkpoints. Agents must emit structured proposals and citations, not arbitrary side effects.

Inbox/Comms Agent: read Gmail/Outlook threads, summarize, extract action items, draft in manager voice. Tools: search_threads, read_thread, extract_actions, draft_reply, create_approval.
Deal Agent: parse opportunities, rates, usage, exclusivity, redlines, negotiation history. Tools: extract_brief, compare_rate_card, detect_redlines, append_deal_event.
Campaign Agent: create campaign, deliverables, deadlines, approvals, posting/reporting checklists. Tools: create_campaign, create_deliverable, schedule_deadline, track_approval.
Sales Agent: brand intelligence, org charts, decision-makers, warmth/intent, outreach drafts. Tools: enrich_brand, find_contact, score_relationship, draft_pitch.
Creator Agent: goals, audience, content pillars, stats, category/whitelisting preferences. Tools: retrieve_creator_profile, propose_fit, update_preference_after_approval.
Finance Agent: invoices, Net 30/60, commission splits, payment tracking, revenue forecast. Tools: create_invoice_plan, reconcile_payment, forecast_revenue.
Career/Strategy Agent: trends, brand fit, growth opportunities. Tools: analyze_fit, generate_strategy_brief.
Logistics Agent: calendar, shoots, travel, itineraries, conflicts. Tools: find_availability, propose_schedule, build_itinerary.

Each tool checks authorization, tenant, idempotency, input schema, and approval requirements. Memory is separated into source facts, derived facts, preferences, and agent traces; provenance and expiry are mandatory. Prefer deterministic rules for money, deadlines, permissions, and conflicts; use LLMs for interpretation and drafting.

## Definition of done
Wedge works end-to-end; Manager Workspace is usable for 5–20 creators; Command Center aggregates safely; brand/contact intelligence is provenance-backed; agent traces are inspectable; every consequential action has approval; RLS, deletion, rate limits, retry/replay, accessibility, and CI gates pass.