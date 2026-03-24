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

**Goal:** Decide how many SharePoint **sites** you will maintain (not per job—per *function*), name them, and paste **canonical URLs** here so Task 3–5 can link to real locations.

**Recommended default for a ~30-person internal shop (adjust names to your tenant):**

| # | Site function | Typical contents | Owner (who decides access) |
|---|----------------|------------------|----------------------------|
| 1 | **Organization / intranet hub** | Company links, news, optional HR/IT entry points | Admin / IT |
| 2 | **Operations & projects** | **PRJ-Active** / **PRJ-Archive** (or one library + Lifecycle); project roots `/<ProjectID>-<ClientShort>/` | Operations / PM |
| 3 | **Estimating & bids** (can merge with #2 if same owners) | Bids library, bid status list | Estimating / BD |
| 4 | **Accounting / finance** (restricted) | Invoices–receipts supporting docs, month-end, audit binders | Accounting |

**Merge options:** Combine **Estimating & bids** into **Operations** if you want fewer URLs; keep **Accounting** separate for permissions.

**Record your tenant (replace placeholders after sites exist):**

| Site display name | SharePoint site URL | Notes |
|-------------------|---------------------|--------|
| *(e.g. WSM Intranet)* | `REPLACE_HUB_SITE_URL` | |
| *(e.g. WSM Operations)* | `REPLACE_OPERATIONS_SITE_URL` | Job document libraries live here |
| *(e.g. WSM Estimating)* | `REPLACE_ESTIMATING_SITE_URL` | Or `—` if merged with Operations |
| *(e.g. WSM Accounting)* | `REPLACE_ACCOUNTING_SITE_URL` | Restricted membership |

**Done when:** Leadership agrees on the row count (3 vs 4 sites), sites are created in Microsoft 365, and URLs are filled in above. Then move to **Task 3**.

**Reference:** [SharePoint / M365 architecture guidelines](/company/resources/sharepoint-m365-architecture-guidelines)

---

## Task 3 — Libraries + metadata

Implement **PRJ-Active** / **PRJ-Archive** (or one library + **Lifecycle**), **Bids**, **Standards**, **Templates**, accounting supporting libraries, and agreed columns.

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
