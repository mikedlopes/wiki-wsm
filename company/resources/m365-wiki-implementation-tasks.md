# M365 + wiki implementation tasks

Ordered checklist for standing up SharePoint/M365 alongside this wiki. Mark items as you complete them in your runbook or PM tool.

**Current focus:** [Task 2 — SharePoint sites](/company/resources/m365-wiki-implementation-tasks#task-2--sharepoint-sites--urls) (project folder layout in the wiki is **frozen** — no further changes unless the business changes the template).

| # | Task | Status |
|---|------|--------|
| 1 | [Project folder convention](/company/resources/m365-wiki-implementation-tasks#task-1--project-folder-convention-git--wiki) | Done |
| 2 | [SharePoint sites + URLs](/company/resources/m365-wiki-implementation-tasks#task-2--sharepoint-sites--urls) | Not started |
| 3 | Create libraries + metadata columns (`ProjectID`, `WikiArea`, `Lifecycle`, `DocType`) | Not started |
| 4 | Align Teams channels with libraries; pin wiki + SharePoint links | Not started |
| 5 | Backfill deep links on department pages (real SharePoint URLs) | Not started |
| 6 | Confirm invoice/receipt attachment pattern (ERP vs ERP + SharePoint) with accounting | Not started |

**Reference:** [SharePoint / M365 architecture guidelines](/company/resources/sharepoint-m365-architecture-guidelines)

---

## Task 1 — Project folder convention (Git + wiki)

**Convention (canonical):**

| Item | Rule |
|------|------|
| **Real jobs** | One folder per job: `projects/<ProjectID>/` (e.g. `projects/TI-2026-045/`). `<ProjectID>` matches ERP / portfolio naming. |
| **No placeholder folder names** | Do not use a literal `[project-id]` directory in Git—brackets are documentation shorthand only. |
| **Blank starter** | Duplicate from `projects/template-project/` (starter page: [Project home template](/projects/template-project/project-home)). |
| **Worked example** | [TI-2026-045 — Downtown Office Renovation](/projects/TI-2026-045/downtown-office-renovation) shows a filled-in page using the same layout. |
| **Document library root** | `/<ProjectID>-<ClientShort>/` with **`00_`–`07_`** (permits, inspections, submittals, RFIs, calcs, etc.) **plus** Bid … Template Forms **plus** **Invoices**, **Material Listing**, **Purchase Orders**, and optional `_QuickLinks/` (see [template](/projects/template-project/project-home)). `<ClientShort>` is an agreed abbreviation; it **extends** the wiki folder name, does not replace it. |

**New job checklist:**

1. Copy `projects/template-project/` → `projects/<ProjectID>/`.
2. Rename `project-home.md` if you prefer one main file per job (e.g. `downtown-office-renovation.md`); update links.
3. Replace `{{PROJECT_ID}}`, `{{CLIENT_SHORT}}`, `{{PROJECT_TITLE}}`, and all `REPLACE_*` embed placeholders.
4. In **SharePoint** (or file share), create `/<ProjectID>-<ClientShort>/` and the full folder tree per the template (numbered + alphabetical + Invoices / Material Listing / Purchase Orders).
5. Add a row on [Projects dashboard](/projects/dashboard) and link from PM/field pages as needed.

**SharePoint:** Use the same `<ProjectID>` in library metadata; file tree root uses `<ProjectID>-<ClientShort>` (see architecture guidelines).

---

## Task 2 — SharePoint sites + URLs

**Goal:** Stand up the **minimum** footprint, paste **canonical URLs** here, then Task 3–5 can link to real locations.

**Agreed model (reduce sprawl):**

| Priority | Site function | What lives here |
|----------|----------------|-----------------|
| **Ship first** | **Organization / intranet hub** | Company links, news, optional HR/IT entry points |
| **Ship first** | **Operations & projects** | **Everything delivery + preconstruction:** **PRJ-Active** / **PRJ-Archive**, project roots `/<ProjectID>-<ClientShort>/`, **Bids** library (and optional bid list) — **no separate Estimating site** |
| **Placeholder** | **Accounting / finance** | Reserved for restricted AP/AR supporting docs later; **not required to launch** hub + operations. Use `REPLACE_ACCOUNTING_SITE_URL` or `TBD` until ready |

**Record your tenant (replace placeholders when sites exist):**

| Site display name | SharePoint site URL | Notes |
|-------------------|---------------------|--------|
| *(e.g. WSM Intranet)* | `REPLACE_HUB_SITE_URL` | |
| *(e.g. WSM Operations)* | `REPLACE_OPERATIONS_SITE_URL` | Jobs + **Bids** live here |
| *(Accounting — future)* | `REPLACE_ACCOUNTING_SITE_URL` | Placeholder until accounting site/libraries are stood up |

**Done when:** Hub and Operations URLs are filled in (Accounting can stay placeholder). Then move to **Task 3**.

**Reference:** [SharePoint / M365 architecture guidelines](/company/resources/sharepoint-m365-architecture-guidelines)

---

## Task 3 — Libraries + metadata

On the **Operations** site: **PRJ-Active** / **PRJ-Archive** (or one library + **Lifecycle**), **Bids** (estimating merged here — no separate site), optional **Standards** / **Templates**. **Accounting** libraries only when the placeholder site is real. Agreed columns: `ProjectID`, `WikiArea`, `Lifecycle`, `DocType`, etc.

---

## Task 4 — Teams alignment

Map Teams to workstreams; pin libraries and wiki anchors (Start here, dashboard, department overviews).

---

## Task 5 — Wiki deep links

Add “Files live in: …” (SharePoint URL) on high-traffic department and project pages.

---

## Task 6 — Invoices and receipts

Align with [Document retention](/departments/accounting/document-retention-and-audit-readiness) and ERP ownership; restrict **Invoices-Receipts** libraries.

---

*Owner: IT / Operations (update as tasks complete).*
