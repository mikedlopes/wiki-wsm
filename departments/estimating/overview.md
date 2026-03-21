# Estimating — Takeoff, Pricing & Risk

**Estimating** builds **defendable bids** using **historical productivity**, **commodity exposure**, and **risk registers** for fire protection scope.

---

## Live visibility — win rate & margin (Power BI)

<div class="wiki-embed wiki-embed--powerbi">

<iframe
  title="Power BI — Estimating KPIs"
  src="https://app.powerbi.com/reportEmbed?reportId=REPLACE_EST_REPORT_ID&groupId=REPLACE_WORKSPACE_ID"
  width="100%"
  height="560"
  style="border:0;border-radius:8px;"
  loading="lazy"
  allowfullscreen>
</iframe>

</div>

---

## Bid development flow

```mermaid
flowchart TD
  Q[Qualify opportunity] --> P[Plan takeoff]
  P --> L[Labor model]
  L --> M[Material pricing]
  M --> E[Equipment & GS]
  E --> R[Risk / margin]
  R --> B[Bid review]
```

---

## Labor model inputs

| Input | Source |
|-------|--------|
| Crew mix | Norms database |
| Height factors | Drawing review |
| Seismic intensity | Job address |
| Overtime assumption | Schedule narrative |

---

## Risk register (template fields)

| Risk | Cost / schedule impact | Mitigation | Owner |
|------|------------------------|------------|-------|
| Long-lead valve | +$— / — wks | Early release PO | Purchasing |
| Conflicting specs | RFI exposure | Clarification addendum | Estimator |

---

## Planner — bid calendar

<div class="wiki-embed wiki-embed--planner">

<iframe
  title="Planner — Bid deadlines & assignments"
  src="https://tasks.office.com/Home/PlanViews/REPLACE_PLANNER_PLAN_ID/Embed"
  width="100%"
  height="560"
  style="border:0;border-radius:8px;"
  loading="lazy"
  allowfullscreen>
</iframe>

</div>

---

*Cross-links: [Bidding](/departments/bidding/overview) · [Job costing](/departments/accounting/job-costing-and-wip)*
