# Creator Signal OS

Creator Signal OS is an AI-native deal-intelligence workspace for boutique talent managers and creator coordinators. It turns inbound brand emails into structured deals, matches them against creator rate cards, detects category conflicts and redline risks, and produces manager-reviewed counter-drafts.

## Product loop
Inbound email -> verified extraction -> rate-card match -> conflict/risk analysis -> triage feed -> one-click counter-draft -> human approval and outbound communication.

## Stack
Next.js 15 App Router, React 19, strict TypeScript, Tailwind CSS, Lucide, Supabase PostgreSQL/Auth/Storage/RLS, Vercel AI SDK, OpenAI SDK, LangChain, Anthropic Claude 3.5 Sonnet structured outputs, Postmark/Resend/SendGrid inbound parse, Vitest and Playwright.

## Operating contract
One branch and one PR at a time. No `any`; no unchecked parsing; Zod at every external boundary; tests must pass before a PR; small dependency footprint; secrets never committed; all tenant data protected by RLS.

## Build documents
- [.devin/instructions.md](.devin/instructions.md): copy-ready autonomous Devin system prompt
- [docs/APP_CONCEPT.md](docs/APP_CONCEPT.md): problem, persona, flows, UX, value proposition
- [docs/PRD.md](docs/PRD.md): product requirements and non-functional requirements
- [docs/MVP_ROADMAP.md](docs/MVP_ROADMAP.md): complete MVP roadmap
- [docs/PR_BUILD_PLAN.md](docs/PR_BUILD_PLAN.md): five-PR implementation sequence and acceptance criteria
- [docs/DATABASE_SCHEMA.sql](docs/DATABASE_SCHEMA.sql): complete schema and RLS policies
- [docs/EVAL_HARNESS_SPEC.md](docs/EVAL_HARNESS_SPEC.md): extraction gold dataset and regression harness

## Local setup
Create a Supabase project, copy `.env.example` to `.env.local`, install dependencies, run migrations, then `npm run dev`. Required checks: `npm run lint`, `npm run typecheck`, `npm run test`, `npm run test:e2e`, and `npm run build`.
