# NFPA Design QA Checklist (Sprinkler Systems)

Peer-review checklist for **calc books**, **drawings**, and **submittals** prior to **GC submission**. Not a substitute for **AHJ** or **PE** responsibility.

---

## Live defect Pareto (Power BI)

<div class="wiki-embed wiki-embed--powerbi">

<iframe
  title="Power BI — Design QA findings"
  src="https://app.powerbi.com/reportEmbed?reportId=REPLACE_QA_REPORT_ID&groupId=REPLACE_WORKSPACE_ID"
  width="100%"
  height="460"
  style="border:0;border-radius:8px;"
  loading="lazy"
  allowfullscreen>
</iframe>

</div>

---

## A. Design basis & documents

| # | Check | Pass / fail / N/A |
|---|-------|-------------------|
| A1 | Occupancy classification matches architect life safety | |
| A2 | Design density / area of operation match **NFPA 13** hazard classification | |
| A3 | Water supply data (flow / pressure) is **dated** and **signed** | |
| A4 | Pipe schedule / C-factor matches **calc input** | |

---

## B. Hydraulic calculations

| # | Check | Pass / fail / N/A |
|---|-------|-------------------|
| B1 | Most remote area layout matches drawing | |
| B2 | Node numbering consistent drawing ↔ calc | |
| B3 | **Elevation** differences included where material | |
| B4 | Pump / PRV / backflow curves modeled correctly | |
| B5 | Hose allowance per code / AHJ | |

---

## C. Sprinklers

| # | Check | Pass / fail / N/A |
|---|-------|-------------------|
| C1 | K-factor, RTI, temp rating match spec | |
| C2 | Spacing / obstructions per **Ch 8–10** rules checked | |
| C3 | Concealed / flush / upright orientation correct per ceiling type | |

---

## D. Seismic / structural

| # | Check | Pass / fail / N/A |
|---|-------|-------------------|
| D1 | Bracing spacing / loads per **Ch 18** | |
| D2 | **Subcontractor** structural review log if required | |

---

## E. Shop / field constructability

| # | Check | Pass / fail / N/A |
|---|-------|-------------------|
| E1 | Main sizes stepped economically | |
| E2 | **Hanger spacing** matches pipe size & seismic factors | |
| E3 | **Victaulic / fitting** mix matches shop capability | |

---

## Review workflow

```mermaid
flowchart LR
  S[Self-check by designer] --> P[Peer review]
  P --> E[PE seal]
  E --> U[Upload to PM / GC]
```

---

## Planner — open QA punches

<div class="wiki-embed wiki-embed--planner">

<iframe
  title="Planner — Design QA punches"
  src="https://tasks.office.com/Home/PlanViews/REPLACE_PLANNER_PLAN_ID/Embed"
  width="100%"
  height="500"
  style="border:0;border-radius:8px;"
  loading="lazy"
  allowfullscreen>
</iframe>

</div>

---

*Return to [Standards overview](/standards/overview)*
