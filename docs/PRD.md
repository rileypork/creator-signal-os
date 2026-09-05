# RosterOps PRD

## Goals
Turn a messy deal into a campaign within minutes; reduce manager coordination load; improve creator economics and deadline reliability; give agencies aggregate operating leverage without leaking private data.

## Manager Workspace requirements
Authenticate organizations and roles; manage creators, contacts, preferences, rate cards, campaigns, deals, deliverables, approvals, invoices, and tasks. Ingest Gmail/Outlook threads and Resend/Postmark webhooks plus PDFs. Extract structured briefs with Anthropic/OpenAI and Zod: brand, campaign, creator, deliverables, rates, currency, usage, whitelisting, exclusivity, dates, approvals, payment, travel, reporting, missing terms, and evidence. Match rate cards and flag redlines. Generate drafts, kickoff, timelines, invoice plans, and reporting checklists. Human approval gates every external side effect.

## Agency Command Center requirements
Leadership sees authorized rollups of managers, rosters, active campaigns, pipeline, revenue, outstanding invoices, workload, SLA/deadline risk, and agent health. Cross-agency memory is permissioned, provenance-backed, and never exposes private creator or negotiation data by default.

## Brand intelligence
Brand accounts and contacts support enrichment, org charts, verified emails, relationship history, warmth/intent, interaction recency, and source provenance. No fabricated contact facts; provider terms, consent, and deletion controls apply.

## Agent runtime
Durable event-driven orchestration; typed tools; scoped memory; trace/log; retries and budgets; deterministic rules for money/deadlines/permissions; parallel read-only research only; approval checkpoints for drafts, sends, financial actions, calendar changes, and writes.

## Success metrics
>=95% required deal-field extraction, >=90% redline recall, >=90% campaign checklist completeness, >=95% draft factual accuracy, duplicate webhook rate zero, 30% faster triage, zero cross-tenant reads, and manager review under five minutes.