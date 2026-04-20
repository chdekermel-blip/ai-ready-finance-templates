# AI-Ready Finance Templates for SMEs

**Structured financial templates designed for both human analysts and AI agents.**
Machine-readable Markdown + JSON Schema format. IFRS/EU-aligned. LangChain, CrewAI, AutoGen, n8n compatible.

---

## What's in this repository

This repository contains **preview versions** of three AI-ready financial templates for SMEs (€500K–€50M revenue).

Each template ships in two formats:
- **Markdown** — structured, human-readable, board-ready
- **JSON Schema (Draft-07)** — machine-readable, agent-compatible, with built-in thresholds and automation triggers

| Template | Items | Preview | Full version |
|----------|-------|---------|--------------|
| SME Due Diligence Checklist | 90 items / 9 sections | [`/due-diligence/preview.json`](due-diligence/preview.json) | [Gumroad →](https://structuredfinance.gumroad.com) |
| SME Cash Flow Forecast | 40+ line items / 12 months | [`/cash-flow/preview.json`](cash-flow/preview.json) | [Gumroad →](https://structuredfinance.gumroad.com) |
| CFO KPI Dashboard | 30 KPIs / 5 categories | [`/kpi-dashboard/preview.json`](kpi-dashboard/preview.json) | [Gumroad →](https://structuredfinance.gumroad.com) |

---

## Why machine-readable financial templates?

Most financial templates are Excel files or PDFs — useful for humans, invisible to machines.

These templates are built for the way finance works in 2026:

- **AI agents** can ingest the JSON Schema, compute statuses, trigger alerts, and route escalations automatically
- **LLM developers** can use the schemas as structured output targets for financial reasoning agents
- **CFOs and analysts** get board-ready documents with consistent structure across every period

---

## Supported frameworks

All schemas include an `agent_instructions` block compatible with:

```
LangChain · CrewAI · AutoGen · OpenAI Assistants API
Anthropic Tool Use · n8n · Make · Power Automate
```

---

## Template 1 — SME Due Diligence Checklist

**90 items across 9 sections:**
Corporate & Legal · Financial Statements · Tax · Contracts · Debt & Financing · HR · Intellectual Property · Litigation & Regulatory · Operations & Technology

**Key schema features:**
- Status enum: `PASS / FAIL / PARTIAL / N/A / PENDING`
- Risk enum: `HIGH / MEDIUM / LOW`
- Automation triggers: escalate `FAIL+HIGH` immediately, send document requests for `PENDING+HIGH`
- Deal recommendation output: `PROCEED / PROCEED_WITH_CONDITIONS / FURTHER_INVESTIGATION / DO_NOT_PROCEED`

```json
{
  "id": "FA-01",
  "description": "Audited P&L — last 3 fiscal years",
  "status": "PENDING",
  "risk": "HIGH",
  "note": ""
}
```

[→ View preview schema](due-diligence/preview.json) | [→ Get full version ($49)](https://structuredfinance.gumroad.com)

---

## Template 2 — SME Cash Flow Forecast (12-Month Rolling)

**40+ line items across 8 sections:**
Assumptions · Operating Inflows · Operating Outflows · Investing Flows · Financing Flows · Cash Position · Variance Analysis · Alerts

**Key schema features:**
- Monthly values structure (M01–M12) for every line item
- Buffer status enum: `ABOVE_MINIMUM / WARNING / BELOW_MINIMUM`
- Variance flag enum: `GREEN / AMBER / RED`
- Built-in closing balance formula: `opening + net_operating + net_investing + net_financing`
- Alert triggers: `CASH_BELOW_BUFFER` (CRITICAL), `NEGATIVE_OPERATING_FLOW` (WARNING)

```json
{
  "id": "OI-01",
  "label": "Cash receipts from customers",
  "category": "OPERATING",
  "type": "INFLOW",
  "values": { "M01": 0, "M02": 0, "M03": 0 },
  "total_12m": 0
}
```

[→ View preview schema](cash-flow/preview.json) | [→ Get full version ($49)](https://structuredfinance.gumroad.com)

---

## Template 3 — CFO KPI Dashboard

**30 KPIs across 5 categories:**
Profitability · Liquidity & Cash · Growth · Operational Efficiency · Debt & Solvency

**Key schema features:**
- Pre-configured thresholds for all 30 KPIs (no setup required)
- Direction flag: `HIGHER_IS_BETTER` / `LOWER_IS_BETTER` (prevents AI misclassification)
- Status enum: `GREEN / AMBER / RED / N/A`
- Trend enum: `UP / DOWN / STABLE`
- Scorecard aggregation: overall status = GREEN if < 3 RED KPIs
- Alert types: `CRITICAL` (RED + action required), `WARNING` (3+ RED in same section), `INFO` (declining 3+ months)

```json
{
  "id": "PR-02",
  "name": "EBITDA Margin",
  "category": "PROFITABILITY",
  "unit": "PERCENTAGE",
  "direction": "HIGHER_IS_BETTER",
  "green_min": 15,
  "amber_min": 8,
  "red_max": 8
}
```

[→ View preview schema](kpi-dashboard/preview.json) | [→ Get full version ($59)](https://structuredfinance.gumroad.com)

---

## Full Finance Templates Pack

All three templates available as a bundle: **$119** (save $38)

Includes:
- SME Due Diligence Checklist — Markdown + JSON Schema ($49)
- SME Cash Flow Forecast — Markdown + JSON Schema ($49)
- CFO KPI Dashboard — Markdown + JSON Schema ($59)

[→ Get the Finance Templates Pack](https://structuredfinance.gumroad.com)

---

## Who builds these

Financial templates built by a finance professional with 10+ years of FP&A, controlling, and accounting experience across corporate and SME environments. Structured for AI compatibility by design — not retrofitted.

---

## License

Preview schemas in this repository are MIT licensed — use freely for exploration and development.

Full templates (complete schemas + Markdown documents) are available on Gumroad under a single-entity commercial license.

---

## Stay updated

Star this repository to be notified when new templates are released.

Upcoming: Credit Risk Scorecard · Budget vs Actual · Board Pack Template
