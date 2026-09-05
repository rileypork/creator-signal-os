# RosterOps / Creator Signal OS

RosterOps is an AI talent-management operating system: a digital talent agency workforce for creator managers and agencies. Managers are human middleware between creators, brands, agencies, inboxes, contracts, deliverables, calendars, invoices, travel, and reporting. RosterOps turns one messy deal into an executable campaign workspace and coordinates specialized AI agents.

## Wedge: Send one messy deal
Drop in a messy deal thread or PDF. RosterOps extracts the brief, creates the campaign, proposes creator kickoff tasks, drafts brand communication in the manager's voice, schedules invoice timelines and deadlines, tracks approvals, and creates the reporting checklist. Every action is explainable, auditable, and manager-approved.

## AI workforce
Inbox/Comms, Deal, Campaign, Sales/Outreach, Creator, Finance, Career/Strategy, and Logistics agents share scoped tools, memory, and an event/audit trail. The Manager Workspace serves a manager running 5–20 creators; the Agency Command Center gives leadership roster, manager, pipeline, revenue, workload, and cross-agency memory views.

## Architecture
Next.js 15 App Router, strict TypeScript, Tailwind Neo-Swiss 1px-border UI, Supabase PostgreSQL/Auth/Storage/RLS/pgvector, Anthropic/OpenAI via Vercel AI SDK, Gmail/Outlook and Resend/Postmark adapters, calendar/email/CRM/finance provider boundaries, Vitest and Playwright. Zod validates every boundary; AI never sends or commits consequential actions without approval.

## Vision
AI-native talent-agency infrastructure: Creator <-> AI Representation Layer <-> Brand/Castlane. Start with post-sale ops and inbound triage; compound through structured deal history, creator preferences, relationships, and agency memory.