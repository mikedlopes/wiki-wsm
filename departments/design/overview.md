# Design & VDC — Hydraulics, BIM & Submittals

**Design engineering** translates **contract documents** into **code-compliant**, **constructible** systems with **hydraulic calculations**, **BIM coordination**, and **submittal** packages.

---

## Live visibility — submittal & model health (Power BI)

<div class="wiki-embed wiki-embed--powerbi">

<iframe
  title="Power BI — Design queue & SLAs"
  src="https://app.powerbi.com/reportEmbed?reportId=REPLACE_DESIGN_REPORT_ID&groupId=REPLACE_WORKSPACE_ID"
  width="100%"
  height="560"
  style="border:0;border-radius:8px;"
  loading="lazy"
  allowfullscreen>
</iframe>

</div>

---

## Design workflow

```mermaid
flowchart LR
  K[Kickoff] --> H[Hydraulics]
  H --> C[Coordination clash]
  C --> S[Submittal]
  S --> R[Resubmit loop]
  R --> F[Fab release]
```

---

## Deliverable matrix

| Deliverable | Typical lead | Owner |
|-------------|--------------|-------|
| Calc book + summary | Per contract | PE |
| Shop / field drawings | Per contract | Designer / VDC |
| Head schedule | With calcs | PE |
| Seismic bracing | Per NFPA 13 | Designer |

---

## BIM / clash priorities

| Trade clash | Action |
|-------------|--------|
| Structural embeds | RFI early |
| Duct / cable tray | Route negotiation |
| Architect ceiling zones | Head layout confirmation |

---

## Planner — submittal due dates

<div class="wiki-embed wiki-embed--planner">

<iframe
  title="Planner — Submittal & RFI deadlines"
  src="https://tasks.office.com/Home/PlanViews/REPLACE_PLANNER_PLAN_ID/Embed"
  width="100%"
  height="560"
  style="border:0;border-radius:8px;"
  loading="lazy"
  allowfullscreen>
</iframe>

</div>

---

*Cross-links: [Standards — NFPA QA](/standards/nfpa-design-qa-checklist) · [Estimating](/departments/estimating/overview) · [Shop](/departments/shop/overview)*
