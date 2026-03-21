# Projects Hub — Active Portfolio Dashboard

Central landing for **job health**, **financial snapshot**, and **deep links** to each Git-backed project folder (`projects/[project-id]/`).

---

## Live portfolio — Power BI

<div class="wiki-embed wiki-embed--powerbi">

<iframe
  title="Power BI — Active projects portfolio"
  src="https://app.powerbi.com/reportEmbed?reportId=REPLACE_PORTFOLIO_REPORT_ID&groupId=REPLACE_WORKSPACE_ID"
  width="100%"
  height="620"
  style="border:0;border-radius:8px;"
  loading="lazy"
  allowfullscreen>
</iframe>

</div>

---

## Active projects (sample table — sync from ERP)

| Job ID | Name | PM | Phase | Billing type | Health |
|--------|------|-----|-------|--------------|--------|
| TI-2026-045 | Downtown Office Renovation | A. Rivera | Field / test | Progress | Green |
| HC-2025-112 | Data Hall — Building C | J. Kim | Fab release | GMP | Yellow |
| SV-2026-008 | County Courthouse retrofit | M. Patel | Design | Lump sum | Green |

---

## Stage definitions

```mermaid
flowchart LR
  D[Design] --> P[Procure]
  P --> F[Fab]
  F --> I[Install]
  I --> T[Test & inspect]
  T --> O[Owner turnover]
```

---

## Planner — portfolio actions

<div class="wiki-embed wiki-embed--planner">

<iframe
  title="Planner — Cross-project actions"
  src="https://tasks.office.com/Home/PlanViews/REPLACE_PORTFOLIO_PLAN_ID/Embed"
  width="100%"
  height="540"
  style="border:0;border-radius:8px;"
  loading="lazy"
  allowfullscreen>
</iframe>

</div>

---

## Gold-standard project page

Use **[TI-2026-045 — Downtown Office Renovation](/projects/TI-2026-045/downtown-office-renovation)** as the **clone target** when creating a new `[project-id]` folder in Git Storage.

### New project Git checklist

| Step | Action |
|------|--------|
| 1 | Copy `TI-2026-045` folder → rename to new job ID |
| 2 | Replace all placeholders (`{{JOB_ID}}`, etc.) |
| 3 | Update Planner / Power BI embed URLs for the job |
| 4 | Link from this dashboard table |

---

*Navigation: [Home](/home) · [PMO](/departments/project-management/overview)*
