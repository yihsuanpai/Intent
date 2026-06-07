# Intent — Agentic Wallet Prototype

A high-fidelity, single-file mobile prototype for **Intent**, an AI-era money app and **agentic-commerce wallet** built for humans *and* the AI agents that act on their behalf. *"Your intent becomes the outcome."*

> Self-contained `Intent_Prototype.html` — no build step, no dependencies. Open it in any modern browser and click through a 375×812 phone frame.

## Highlights

- **Three tabs + Intent assistant** — Home, Insights, Wallet, with a centered "Ask Intent" assistant that turns a natural-language intent into a confirmed, reversible outcome with an audit line.
- **Home overview** — a dark-navy balance hero, an *agent activity* feed (a completed autonomous bill payment + a pending action with real Approve / Deny → 10-second Undo), and recent activity.
- **Insights** — navy summary card, a calendar month/year picker, searchable transactions with category filters, a category breakdown, and a redesigned receipt-style transaction-detail view with an "Initiated by" agent-audit row.
- **Wallet (Link-by-Stripe inspired)** — verified identity & one-click checkout, saved instruments, and the core **agentic trust layer**: authorized agents with per-agent spend caps, usage bars, approval modes, machine-readable state, a global **Pause all**, plus full **authorize-new-agent** and **edit-authorization** (cap / approval mode / pause / revoke) flows.
- **Design system** — near-monochrome dark theme, a single electric-blue accent, consistent 1.8px line icons, and tabular, signed money throughout.

## Files

- `Intent_Prototype.html` — the prototype (open this).
- `Intent_PRD.md` — product requirements, incl. the agent layer and the Claude-API assistant inference + token-efficient model-routing policy (Haiku-default, Sonnet-4.6-medium ceiling).
- `Intent_DesignSystem.md` — tokens, components, and behavior.

## Run

Open `Intent_Prototype.html` in a browser. That's it.

---

*Prototype — illustrative data only; not a real financial product.*
