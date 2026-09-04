# Creator Signal OS — App Concept

## Problem
Boutique talent managers and creator coordinators receive fragmented brand opportunities through email. Important terms are buried in prose, rate cards live in spreadsheets, conflicts are remembered informally, and drafting a response requires repetitive comparison and negotiation. Missed deadlines, underpriced work, category conflicts, and inconsistent redlines create revenue and relationship risk.

## Solution
Creator Signal OS is a focused operating layer over inbound deal flow. It extracts deal facts with provenance, highlights uncertainty, compares terms to creator-specific rate cards and rules, flags conflicts and risk, and gives the manager an editable counter-draft. Humans retain final authority.

## Persona
Primary users are boutique talent managers, creator managers, and creator coordinators handling multiple creators and brand relationships. They are commercially sophisticated, time-constrained, email-centric, and need fast trustable recommendations rather than an opaque autonomous agent.

## Core flows
1. Configure organization, members, creators, rate cards, category restrictions, and redline rules.
2. Forward or receive an inbound brand email through a signed inbound webhook.
3. System normalizes the message, deduplicates it, extracts structured terms, and shows source snippets and confidence.
4. System matches creators and rate cards, computes pricing deltas, detects conflicts, and explains risks.
5. Manager triages the deal, edits terms, generates a counter-draft, and copies or sends it only after explicit approval.
6. Accepted edits and outcomes become auditable feedback for future rules and evaluation.

## UX philosophy
Neo-Swiss / clean utilitarian: 1px borders, crisp typography, visible hierarchy, compact information density, strong whitespace, monochrome foundation with restrained semantic accents, Lucide icons, keyboard-first interactions, responsive layouts, and clear tables. Avoid gradients, ornamental cards, heavy shadows, modal overload, and large component libraries. Every screen has loading, empty, error, and permission states.

## Value proposition
Managers convert noisy inboxes into a prioritized, explainable deal queue; protect creator economics and exclusivity; reduce time to reply; standardize negotiation quality; and preserve human judgment with auditable AI assistance.

## MVP boundaries
In scope: one organization workspace, creator/rate-card configuration, inbound email ingestion, structured extraction, matching, conflict/redline alerts, triage dashboard, realtime updates, draft generation, auditability. Out of scope: autonomous sending, payment processing, CRM replacement, generalized contract management, training custom models, and multi-provider complexity beyond a clean adapter.
