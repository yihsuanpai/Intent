# Intent — Product Requirements Document

**Product:** Intent
**Owner:** Head of Product, Intent
**Status:** Draft
**Date:** 2026-06-07
**Authors:** Product, Design & Engineering

> *Your intent becomes the outcome.*

---

## 1. Vision & Mission

Money management has always been backwards. People are asked to learn the tool — to categorize, reconcile, budget, tap through screens — when what they actually have is an *intent*: "pay rent," "see where my money went this month," "split this dinner," "don't let me overspend on takeout again." The gap between that intent and the outcome is where every personal finance product loses people.

**Intent closes that gap.** A user (or an agent acting for them) expresses what they want — in natural language or a single action — and Intent does the rest: understands the intent, executes the payment, unifies the full financial picture across in-app payments and linked receipts, and surfaces a clear, honest outcome. No spreadsheets, no taxonomy homework, no anxiety.

**Mission:** Make the distance between *what you want with your money* and *what actually happens* as close to zero as possible — for humans and for the agents they trust.

**Why now.** Two shifts make this the right moment. First, open financial data (receipts, invoices, bank and card feeds) is finally accessible enough to assemble a genuinely *complete* spending picture, not a partial one. Second, and more profoundly, we are entering the agentic era: people will increasingly delegate routine financial work to AI agents — comparing, querying, paying, optimizing. Today's finance apps were built for a human thumb on a screen. The winning product of this decade must be legible and operable by *both* a human and an agent, sharing the same surfaces, the same guardrails, and the same source of truth. Intent is designed for that world from first principles, not retrofitted into it.

---

## 2. Market & Context

Personal finance management has historically split into two camps: passive *trackers* (dashboards that tell you what happened) and active *payment apps* (wallets that move money but forget context). Users carry both and stitch them together in their heads. Intent collapses the two: every payment is context, and every piece of context can lead to an action.

The market is now bending toward **agentic commerce**. Assistants and autonomous agents are beginning to research purchases, manage subscriptions, and initiate transactions on a person's behalf. This creates a new class of user — the agent — and a new requirement: financial products must expose clean, permissioned, auditable interfaces that an agent can read and act on, while keeping the human firmly in control of consequential decisions.

Intent treats **humans and agents as first-class, co-equal users of the same product.** A human taps; an agent calls an intent. Both flow through identical understanding, confirmation, and guardrail logic. This is our durable differentiation: most incumbents will bolt a chatbot onto a legacy app. We are building the substrate — a unified financial picture plus an intent-execution layer — that is natively operable by either kind of user.

---

## 3. Goals & Non-Goals

**Goals**

- Deliver a single, trustworthy view of a user's money by unifying in-app payments with linked receipts and invoices.
- Let users *express intent* — pay, analyze, organize, optimize — and reliably turn it into the correct outcome with minimal friction.
- Make spending genuinely understandable through automatic categorization, a clean monthly summary, and witty, personalized insights.
- Establish the **agent layer**: a permissioned, auditable interface so trusted agents can query and transact on the user's behalf, always within human-set guardrails.
- Earn daily trust through beautiful, simple, outcome-oriented design and rewards (**Intent Points**) that reinforce healthy engagement.

**Non-Goals (v1)**

- We are **not** building a bank, a lending product, or an investment/brokerage platform.
- We are **not** building a fully autonomous money agent that moves significant funds without human confirmation. The human stays in the loop for consequential actions.
- We are **not** building a general-purpose chatbot. The Intent assistant is assistive and scoped to finance — subtle, not a takeover.
- We are **not** targeting business accounting, multi-entity bookkeeping, or tax filing in v1.

---

## 4. Personas

**Maya — the primary human user (28, salaried).** Wants to feel on top of her money without effort. She pays in-app, links her receipts, and checks Intent a few times a week. She values clarity over control and is delighted by insights that feel personal. Her core ask: *"Just show me what's true and make paying effortless."*

**Devin — the power user (35, freelancer with variable income).** Tracks everything, creates custom categories, watches trends month-over-month, and shares his monthly story card. He wants precision, fast period navigation, and the ability to correct categorization. His core ask: *"Give me control and depth without slowing me down."*

**Aria — the AI agent persona (acts on the user's behalf).** A trusted assistant the user has authorized. Aria queries Intent for spending summaries ("how much did Maya spend on food this month?"), prepares and proposes payments ("the electricity invoice is due Friday — pay it from the usual account?"), and surfaces optimizations. Aria operates only within explicit, user-defined scopes and spend limits, never finalizes a consequential payment without the human's confirmation, and leaves a full audit trail. Aria's core constraint: *"I do the legwork and propose the outcome; the human owns the decision."*

---

## 5. Jobs To Be Done

- *When I pay for something,* I want it to be instant and to automatically carry context, so I never have to reconcile it later.
- *When I want to understand my spending,* I want one honest, unified view across payments and receipts, so I don't second-guess whether it's complete.
- *When the month ends,* I want a clear summary and a few sharp insights, so I learn something without doing analysis myself.
- *When a bill is due or a routine purchase is needed,* I want my agent to handle the legwork and propose the action, so I just approve.
- *When I delegate to an agent,* I want hard guardrails and a clear record, so delegation never means losing control.

---

## 6. Core User Journeys

**Journey A — Onboarding and the first unified picture (Maya).** Maya installs Intent and is greeted with the thesis, not a feature tour. To make her picture complete, she enters the receipt/invoice sync flow: a clear **consent** screen explains exactly what will be read and why, she **chooses a source**, watches a calm **sync** progress state, and lands on a **success** screen that reveals her unified Spending view for the first time — in-app payments and synced receipts already merged and auto-categorized. The payoff is immediate: she sees a real, complete month without lifting a finger.

**Journey B — Pay, with context (Maya).** At a counter, Maya pays in-app in two taps. The transaction lands instantly in her ledger, auto-categorized as Food, and folds into her monthly total. There is no separate "go track this" step — the payment *is* the record. Later, the Monthly Highlights notices a pattern and tells her, in a warm, witty line, that her weekend coffee habit quietly became her third-largest category.

**Journey C — The agent-assisted bill (Aria + Maya).** Maya has authorized Aria with a scope ("recurring household bills, up to a monthly limit, from my primary account"). An electricity invoice syncs in. Aria reads it, matches it to the recurring "Bills" pattern, and — because it's within scope — prepares a payment and sends Maya a single confirmation: *"Electricity, due Friday — pay from primary account? "* Maya taps **Confirm**; Intent executes and logs the action with Aria attributed as the initiator. Had the amount exceeded the limit, or the merchant been new, Aria would have escalated with a clearer prompt and refused to proceed unilaterally. The entire exchange is visible in an audit timeline.

**Journey D — Month-end story and depth (Devin).** At month close, Devin opens his **monthly spending story** card — a beautiful, Instagram-story-style summary of expense, income, net, top categories, and a standout highlight — and shares it. He then dives into the ledger, re-categorizes two ambiguous transactions into a custom "Gear" category he created, and flips the period navigation back three months to confirm a downward trend in his sparkline. Intent remembers his correction and improves future categorization.

---

## 7. Functional Requirements

### 7.1 Home
The Home surface answers "what do I need to know and do right now?" It presents the monthly summary hero (expense / income / net), a trend sparkline, period navigation, and entry points to pay and to the Intent assistant. It also surfaces timely items: a pending agent proposal, a bill due soon, or a fresh Monthly Highlight.
*Acceptance:* Home renders the current period's expense, income, and net within 1s of a warm launch; period navigation moves between months without a full reload; any pending agent proposal is clearly surfaced with a single confirm/decline affordance.

### 7.2 Payments
Users pay in-app in no more than two deliberate actions. Each payment writes an immutable transaction with amount, merchant, timestamp, source account/card, and an auto-assigned category.
*Acceptance:* a completed payment appears in the ledger and updates the monthly summary within 2s; failed payments produce a clear, recoverable error and never silently double-charge.

### 7.3 Unified Spending Analysis
The Spending surface merges in-app payments and linked receipts/invoices into one ledger and one set of totals — explicitly de-duplicating where a synced receipt corresponds to an in-app payment.
*Acceptance:* a receipt that matches an existing in-app payment is merged, not double-counted; the user can see the constituent sources behind any merged item; totals reconcile (sum of categories equals the period expense).

### 7.4 Transaction Ledger & Categorization
Every transaction is auto-categorized into one of: Food, Shopping, Bills, Transport, Entertainment, Education, Transfer, Income, Other — and users may create **custom categories**. Users can recategorize any item.
*Acceptance:* new transactions receive a category automatically; a manual recategorization persists and measurably biases future auto-categorization for similar items; custom categories appear everywhere standard categories do (filters, summaries, story card).

### 7.5 Monthly Summary & Trend
The hero shows expense, income, and net for the selected period; the sparkline shows the trend across recent periods; period navigation lets users move backward/forward.
*Acceptance:* values are consistent with the underlying ledger to the cent; the sparkline reflects at least the trailing several months when data exists; empty/early states are handled gracefully.

### 7.6 Monthly Highlights
Witty, personalized, data-driven insights ("Your weekend coffees added up to more than your phone bill") generated from the user's own data.
*Acceptance:* every highlight is grounded in a verifiable figure from the user's ledger (no hallucinated numbers); tone is warm and never shaming; users can dismiss or mute a highlight type.

### 7.7 Intent Points (Rewards)
Engagement and healthy behaviors earn **Intent Points**, visible and redeemable via Partners.
*Acceptance:* point accrual rules are transparent; balance is always reconcilable; redemption never blocks core finance functions.

### 7.8 Partners
A surface for redemption and partner offers, reframed around outcomes ("turn points into…").
*Acceptance:* offers are clearly labeled; redemptions confirm explicitly and reflect in the points balance immediately.

### 7.9 Receipt/Invoice Sync Onboarding
A four-step flow: **consent → choose source → sync → success**, written in plain language with explicit data-use disclosure.
*Acceptance:* sync cannot begin without affirmative consent; progress is visible; failure is recoverable; success lands the user directly in their newly unified picture.

### 7.10 Monthly Spending Story Card
A shareable, beautiful, story-format summary of the month.
*Acceptance:* generates from real data; excludes sensitive identifiers by default; renders cleanly at standard story dimensions; sharing is opt-in per card.

### 7.11 Intent Assistant
A subtle, finance-scoped assistant available across screens that interprets natural-language intents and routes them to the right surface or action. (Detailed in §8.)
*Acceptance:* assistant is reachable from any primary surface; intents are interpreted by the Claude API (per §8.1); it proposes actions and never executes a consequential payment without explicit confirmation; it always cites the data behind any number it states.

### 7.12 Navigation
Bottom navigation: **Home, Partners, Spending, My Page.**
*Acceptance:* state is preserved per tab; the active tab is unambiguous and meets accessibility contrast and target-size requirements.

---

## 8. The Agent Layer

The agent layer is the heart of Intent's bet: **humans and agents operate the same product through the same intent-execution pipeline.** Whether the actor is Maya's thumb or Aria's API call, the request becomes a structured *intent* (e.g., `analyze_spending(period, category)`, `propose_payment(payee, amount, source)`), passes through the same interpretation and validation, and is subject to the same guardrails.

**Intents, not commands.** An intent describes a desired outcome, not a brittle sequence of taps. Intent resolves it — disambiguating where needed ("which dinner did you mean to split?") rather than failing.

**Confirmation and human-in-the-loop.** Read-only intents (summaries, queries, insights) can be served directly. **Consequential intents — anything that moves money or changes a payment commitment — require explicit human confirmation by default.** Agents *propose*; humans *dispose*. An agent never completes a consequential payment unilaterally in v1.

**Guardrails.** Each authorized agent operates within an explicit grant: allowed intent types, eligible accounts, category and per-transaction/per-period spend limits, and allowed payees. Anything outside the grant — a new payee, an over-limit amount, an unusual pattern — triggers escalation to the human and refusal to proceed. Limits are user-owned and revocable instantly.

**Auditability.** Every agent action — query or proposal — is recorded in an audit timeline attributing the initiator (human vs. specific agent), the intent, the data accessed, and the outcome. Delegation is never opaque.

### 8.1 Assistant inference — Claude API & model routing

**Powered by the Claude API.** The Intent assistant's natural-language understanding and response generation run on the **Claude API** (Anthropic). Every user or agent utterance is interpreted by Claude, which maps it to a structured intent (e.g., `analyze_spending`, `propose_payment`) and produces either a read-only response or a *proposed* action. This does not alter the human-in-the-loop contract above: the model proposes, it never auto-executes. Consequential intents still require explicit human confirmation per §8, and the model's output is treated as a candidate that the guardrail and validation layers may reject before anything is shown or acted upon.

**A token-efficient model router.** Because the assistant sits on high-volume, latency-sensitive surfaces, the system does not call one large model for everything. A **model router** selects the smallest sufficient model per request, biasing hard toward the cheapest tier and escalating only when a turn genuinely demands it. The policy is explicit and bounded at both ends.

The **default is Claude Haiku 4.5**, which handles the large majority of traffic: intent classification and routing, short read-only answers (spending summaries, balance and points lookups), category labeling, output formatting, and disambiguation prompts — in short, any high-volume or low-complexity turn. The system **escalates to Claude Sonnet 4.6, and only at a "medium" reasoning budget**, for genuinely hard turns: multi-step financial reasoning, ambiguous multi-entity disambiguation, nuanced insight generation, and reasoning about consequential payment proposals. This is a strict **hard cap**: the router must never select a model above Sonnet 4.6 and never a reasoning effort above "medium" — there is no Opus tier and no extended or high-thinking mode in this product. **Claude Sonnet 4.6 at medium is the absolute top of the ladder.**

**How the router decides.** A cheap, fast first stage — itself Claude Haiku 4.5, or a rules-plus-score classifier — assigns each request a complexity tier from a small set of signals: the resolved intent type, whether the action is consequential, input length and ambiguity, and expected tool-call depth. The tier maps to a model. The router is biased toward Haiku and escalates to Sonnet-4.6-medium only when a confidence or complexity threshold is crossed. As a backstop, if Haiku's output fails a validation check (malformed structure, low confidence, or a guardrail-relevant ambiguity), the router may perform a single one-step escalation to Sonnet-4.6-medium rather than degrade the answer.

**Token-efficiency requirements.** Inference must be lean by construction. The static instruction and intent schema are delivered via a **concise, cached system prompt** (prompt caching), and outputs are **structured/JSON-constrained** so the model emits only the fields the pipeline consumes. Each task class carries a **tight `max_tokens` cap**, and context is **minimal and windowed** — only the data needed for the intent, never the full ledger. The assistant reasons over **summary and rollup context rather than raw transactions**, and tool inputs and results are kept to **short payloads**. Together these techniques directly support the §9 latency target (read-only intents feeling sub-second to low-seconds) and hold token cost flat as volume scales.

| Task class | Model | Reasoning effort | Why |
| --- | --- | --- | --- |
| Intent classification / routing | Claude Haiku 4.5 | minimal | Cheapest, highest-volume turn; sets the routing decision itself |
| Read-only summary / lookup | Claude Haiku 4.5 | minimal | Bounded data, deterministic shape; speed matters most |
| Category labeling / formatting | Claude Haiku 4.5 | minimal | Pattern-level work over short inputs |
| Disambiguation question | Claude Haiku 4.5 | low | Light reasoning to frame one clarifying prompt |
| Complex multi-step insight | Claude Sonnet 4.6 | medium | Ceiling tier; multi-step reasoning over aggregated data |
| Consequential payment-proposal reasoning | Claude Sonnet 4.6 | medium | Ceiling tier; highest-stakes reasoning — still human-confirmed |

**Design principle.** The assistant and agents remain *subtle and assistive*. The product's center of gravity stays with the human; agents reduce legwork and surface options, they do not seize the wheel.

---

## 9. Non-Functional Requirements

**Privacy.** Data access (especially receipt/invoice sync) is consent-first, purpose-limited, and clearly disclosed. Users can view what is connected, what each agent can access, and revoke any of it at any time. Sensitive data is minimized in shareable artifacts by default.

**Security.** Strong authentication, encryption in transit and at rest, biometric gating for payments and confirmations, and least-privilege scoping for agents. Agent grants are signed, scoped, time- and limit-bounded, and revocable. All consequential actions are logged immutably.

**Latency.** Warm-launch Home and Spending render core figures within ~1s; payment confirmation reflects in the ledger within ~2s; assistant responses to read-only intents feel conversational (sub-second to low-seconds).

**Accessibility.** Conform to **WCAG 2.1 AA**: sufficient color contrast, scalable text, adequate touch-target sizes, full screen-reader labeling across all surfaces and the story card, and no reliance on color alone to convey category or status.

**Agent-readiness / API surface.** Expose a clean, versioned, permissioned intent API mirroring the human surfaces (query spending, fetch summaries, propose payment, read audit log). The API enforces the same guardrails as the UI — there is no privileged backdoor that bypasses confirmation or limits. Assistant and intent interpretation run on the Claude API under the token-routed model policy defined in §8.1 (Haiku-default, Sonnet-4.6-medium ceiling), and the same guardrails and audit apply to model-mediated actions as to any other initiator.

**Offline.** Recently viewed summaries, ledger, and the current period remain readable offline; payments and agent confirmations require connectivity and queue/fail gracefully with clear messaging rather than ambiguous states.

---

## 10. Success Metrics & North Star

**North Star: Confirmed Intents per Active User per Week** — the count of expressed intents (human or agent-initiated) that resolve into a correct, user-accepted outcome (a payment, a successful query that drove a decision, an accepted proposal). It captures our entire thesis in one number: are we turning intent into outcome, repeatedly and trustfully?

Supporting metrics:
- **Picture completeness:** share of active users with at least one receipt/invoice source synced (proxy for a trustworthy unified view).
- **Categorization accuracy:** rate of transactions left uncorrected by users.
- **Insight resonance:** Monthly Highlight save/share rate and inverse of mute rate.
- **Agent trust:** agent-proposed actions confirmed vs. declined; zero out-of-scope agent executions (a hard guardrail KPI, target = 0).
- **Story card shares** as a top-of-funnel growth signal.
- Retention (W4/W12) and weekly active payment usage as durability signals.

---

## 11. MVP Scope — Now / Next / Later

**Now (MVP).** Unified Spending analysis (payments + receipts, de-duplicated); transaction ledger with auto-categorization and custom categories; monthly summary hero with sparkline and period navigation; Monthly Highlights; receipt/invoice sync onboarding (consent → source → sync → success); in-app payments; bottom nav (Home, Partners, Spending, My Page); Intent Points basics; monthly spending story card; the Intent assistant for **read-only** intents and surface routing.

**Next.** Agent layer for *consequential* intents with proposal-and-confirm, scoped grants, spend limits, and the audit timeline; the permissioned agent API surface; smarter, learning categorization; richer Partners redemption.

**Later.** Multi-agent delegation and inter-agent handoffs; predictive/proactive optimization ("you'll likely overspend on dining — adjust?"); deeper goal-based budgeting; broader payment rails and partner ecosystem.

---

## 12. Risks & Mitigations

**Over-automation erodes trust.** If agents act too freely, a single bad payment poisons confidence. *Mitigation:* human-in-the-loop by default for all consequential actions; hard, user-owned limits; instant revocation; out-of-scope executions treated as a zero-tolerance KPI.

**Incomplete or duplicated picture.** A unified view that double-counts or misses sources is worse than none. *Mitigation:* explicit receipt-to-payment de-duplication with visible provenance; totals that always reconcile.

**Insight tone backfires.** "Witty" can slip into shaming. *Mitigation:* warm, non-judgmental copy standards; user mute controls; figures always grounded in real data.

**Privacy perception.** Reading receipts/invoices is sensitive. *Mitigation:* consent-first onboarding, plain-language disclosure, granular and revocable permissions, data minimization in shareable artifacts.

**Agent API as attack surface.** A programmatic interface invites abuse. *Mitigation:* least-privilege signed grants, the same guardrails as the UI, immutable audit logs, anomaly escalation.

**Scope creep into banking/lending.** *Mitigation:* explicit v1 non-goals; stay an intent-and-insight layer, not a regulated institution, until deliberately chosen.

---

## 13. Open Questions

- What is the precise default boundary between "read-only" (no confirmation) and "consequential" (confirmation required) intents — and is per-user customization safe?
- How do we let users set agent spend limits and scopes in a way that is both expressive and effortless?
- What is the trust model for *third-party* agents versus a first-party Intent agent — and how do we verify and certify them?
- How aggressive should proactive insights and proposals be before they feel intrusive rather than helpful?
- What is the canonical de-duplication confidence threshold for matching receipts to in-app payments, and how do we expose uncertainty to the user?
- For the story card and shared artifacts, what is the right default privacy posture across regions?

---

*End of document.*
