## Project Management & Lean Kanban Dashboards

### Standard project page structure (`/projects/[project-id]`)

```text
/projects/[project-id]/
├─ project-home.md
├─ kickoff-and-baseline.md
├─ submittals-board.md
├─ rfi-log.md
├─ co-log.md
├─ procurement-status.md
├─ field-lookahead.md
├─ testing-inspection.md
├─ financial-snapshot.md
└─ closeout.md
```

### Build a central Projects Dashboard (Planner + Markdown + Power BI)

1. Create a Microsoft Planner plan for portfolio-level tracking.
2. Add buckets for Kanban-like flow:
   - `ToSubmit`, `InReview`, `ReviseResubmit`, `Approved`, `Blocked`
3. Create SharePoint lists per project:
   - `Submittals`, `RFIs`, `ChangeOrders`, `MaterialStatus`
4. Create a Power BI report from those lists for aging/cycle-time/PPC.
5. Embed Planner and Power BI in `/projects/dashboard`.
6. Add a field-friendly Markdown summary table under embeds.
7. During weekly PM meeting, update Planner + lists first, then dashboard.

### Sample dashboard Markdown page (copy-paste)

```markdown
# Projects Dashboard

## Portfolio KPIs
| KPI | Current | Target |
|---|---:|---:|
| Active Projects | 12 | - |
| Submittals >14 days | 6 | <= 4 |
| RFIs >10 days | 5 | <= 3 |
| Open CO Exposure | $145,000 | <= $100,000 |
| PPC (weekly) | 81% | >= 85% |

---

## Planner - Submittals and RFIs
<div class="wiki-embed wiki-embed--planner">
<iframe
  title="Planner - Fire Sprinkler Portfolio"
  src="https://tasks.office.com/Home/PlanViews/REPLACE_PLAN_ID/Embed"
  width="100%"
  height="620"
  style="border:0;border-radius:8px;"
  loading="lazy"
  allowfullscreen>
</iframe>
</div>

---

## Power BI - Portfolio Health
<div class="wiki-embed wiki-embed--powerbi">
<iframe
  title="Power BI - Portfolio"
  src="https://app.powerbi.com/reportEmbed?reportId=REPLACE_REPORT_ID&groupId=REPLACE_WORKSPACE_ID"
  width="100%"
  height="680"
  style="border:0;border-radius:8px;"
  loading="lazy"
  allowfullscreen>
</iframe>
</div>

---

## Quick Kanban Snapshot (Field-Friendly)
| Lane | Count | Action |
|---|---:|---|
| ToSubmit | 9 | Complete package docs |
| InReview | 15 | Follow-up by due date |
| ReviseResubmit | 4 | Assign redesign owners |
| Approved | 28 | Release purchasing/fab |
| Blocked | 3 | Escalate constraints |

## Lean Commitments (This Week)
| Commitment | Owner | Due | Status |
|---|---|---|---|
| Close 3 aged RFIs | PM Team | Fri | In Progress |
| Release Zone B fab | Design/Shop | Thu | Planned |
| Resolve valve substitution | Purchasing | Wed | Blocked |
```

Security note:
- Keep embed editing to trusted groups only.
- If custom script is used, only allow vetted code and Microsoft domains.
