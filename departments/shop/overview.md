# Shop Operations — Fabrication & Staging

The shop converts **approved submittals** and **cut lists** into **tagged assemblies** ready for **just-in-time** delivery to field crews. This page is the **front door** for standards, KPIs, and links to detailed procedures.

---

## Live visibility — shop load & productivity (Power BI)

<div class="wiki-embed wiki-embed--powerbi">

<iframe
  title="Power BI — Shop throughput & backlog"
  src="https://app.powerbi.com/reportEmbed?reportId=REPLACE_SHOP_REPORT_ID&groupId=REPLACE_WORKSPACE_ID"
  width="100%"
  height="560"
  style="border:0;border-radius:8px;"
  loading="lazy"
  allowfullscreen>
</iframe>

</div>

---

## Shop mission metrics

| KPI | Target | Notes |
|-----|--------|-------|
| On-time release to field | ≥ 95% | Against committed fab dates |
| Rework % of fab hours | ≤ 3% | Coded reason required |
| Material accuracy (pick errors) | ≤ 0.5% | Per 1,000 picks |
| Safety TRIR | 0 | Near-miss reporting encouraged |

---

## Value stream (simplified)

```mermaid
flowchart LR
  I[Released for fab] --> P[Pick & cut]
  P --> T[Thread / groove / weld-outsource]
  T --> A[Assemble & tag]
  A --> Q[QC hold point]
  Q --> S[Stage / load]
  S --> F[Field receipt]
```

---

## Roles

| Role | Responsibility |
|------|----------------|
| Shop manager | Capacity planning, safety, quality |
| Lead fabricator | Standard work adherence, training |
| Material handler | Kitting, FIFO, heat numbers where required |
| QC inspector | Hold / release documentation |

---

## Critical documents

| Document | Location |
|----------|----------|
| **Shop fabrication procedures** (master SOP) | [Fabrication procedures](/departments/shop/fabrication-procedures) |
| Threader / groover PM logs | Shop drive — `EQUIPMENT/` |
| Weld / braze procedures (if applicable) | QC manual |

---

## Planner — fab backlog & PM tasks

<div class="wiki-embed wiki-embed--planner">

<iframe
  title="Planner — Shop fabrication backlog"
  src="https://tasks.office.com/Home/PlanViews/REPLACE_PLANNER_PLAN_ID/Embed"
  width="100%"
  height="560"
  style="border:0;border-radius:8px;"
  loading="lazy"
  allowfullscreen>
</iframe>

</div>

---

*Cross-links: [Field](/departments/field/overview) · [Design](/departments/design/overview) · [Lean — 5S](/lean-tools/5s-and-visual-workplace)*
