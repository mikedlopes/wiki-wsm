# Bidding — Strategy, Bonds & Handoff

Turns **estimates** into **submitted proposals** with correct **bonds**, **exclusions**, and **clean handoff** to **project management**.

---

## Live visibility — pipeline & hit rate (Power BI)

<div class="wiki-embed wiki-embed--powerbi">

<iframe
  title="Power BI — Bid pipeline"
  src="https://app.powerbi.com/reportEmbed?reportId=REPLACE_BID_REPORT_ID&groupId=REPLACE_WORKSPACE_ID"
  width="100%"
  height="520"
  style="border:0;border-radius:8px;"
  loading="lazy"
  allowfullscreen>
</iframe>

</div>

---

## Bid control process

```mermaid
sequenceDiagram
  participant ES as Estimator
  participant BD as BD / Exec
  participant SU as Surety
  participant PM as PMO
  ES->>BD: Bid review packet
  BD->>SU: Bond request (if needed)
  SU-->>BD: Bond authorization
  BD->>ES: Go / no-go
  ES->>PM: Award handoff (if won)
```

---

## Go / no-go criteria

| Factor | Weight |
|--------|--------|
| GC payment history | High |
| Capacity vs backlog | High |
| Risk profile | High |
| Margin | Medium |
| Strategic relationship | Medium |

---

## Standard exclusions (review each job)

| Topic | Example language |
|-------|------------------|
| Fire alarm | Monitor-only vs full FA |
| Concrete / coring | By others unless noted |
| Firestopping | By others unless noted |
| Demo | Quantities per drawing only |

---

## Planner — bid week war room

<div class="wiki-embed wiki-embed--planner">

<iframe
  title="Planner — Bid week tasks"
  src="https://tasks.office.com/Home/PlanViews/REPLACE_PLANNER_PLAN_ID/Embed"
  width="100%"
  height="520"
  style="border:0;border-radius:8px;"
  loading="lazy"
  allowfullscreen>
</iframe>

</div>

---

*Cross-links: [Insurance & bonds](/departments/accounting/insurance-bonds-and-coi-tracking) · [Project management](/departments/project-management/overview)*
