# M365 + wiki implementation tasks

Ordered checklist for standing up SharePoint/M365 alongside this wiki. Mark items as you complete them in your runbook or PM tool.

**Current focus:** [Task 3 — Libraries + metadata](/company/resources/m365-wiki-implementation-tasks#task-3--libraries--metadata) (project folder layout in the wiki is **frozen** — no further changes unless the business changes the template).

| # | Task | Status |
|---|------|--------|
| 1 | [Project folder convention](/company/resources/m365-wiki-implementation-tasks#task-1--project-folder-convention-git--wiki) | Done |
| 2 | [SharePoint sites + URLs](/company/resources/m365-wiki-implementation-tasks#task-2--sharepoint-sites--urls) | Done |
| 3 | [Libraries + metadata](/company/resources/m365-wiki-implementation-tasks#task-3--libraries--metadata) | In progress |
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
| **Placeholder** | **Accounting / finance** | Reserved for restricted AP/AR supporting docs later; **not required to launch** hub + operations. URL `TBD` in table below until ready |

**Record your tenant (replace placeholders when sites exist):**

| Site display name | SharePoint site URL | Notes |
|-------------------|---------------------|--------|
| **WSM Hub** | https://westatesmechanical.sharepoint.com/sites/WSMHub | Organization / intranet hub |
| **WSM Projects** | https://westatesmechanical.sharepoint.com/sites/WSMProjects | Operations — job libraries + **Bids** (Task 3) |
| *(Accounting — future)* | `TBD` | Create site when ready; paste URL here |

---

### Task 2 runbook — create Hub + Operations (do this in Microsoft 365)

**Who:** Someone with permission to **create SharePoint sites** (often SharePoint admin, or allowed by your org’s site-creation policy).

**Prerequisites:** Decide **URL slugs** first (they are hard to change later), e.g. `WSM-Hub` and `WSM-Operations` → URLs like `https://*yourtenant*.sharepoint.com/sites/WSM-Operations`.

#### A. Organization hub (intranet)

1. Open **SharePoint** from the Microsoft 365 app launcher (or [SharePoint admin center](https://admin.microsoft.com/) → **Sites** → **Active sites** → **Create**).
2. Choose **Communication site** (read-friendly landing; good for links and news).
3. Set **site name** and **URL**; finish the wizard.
4. Open the site → copy the **root URL** from the address bar (ends at `/sites/YourSiteName` or similar). That is your **hub** URL.
5. *(Optional)* **Register as hub:** **Settings** (gear) → **Site information** → **Hub site** settings (or SharePoint admin → Active sites → select site → Hub → Register as hub). Use this if you want **Operations** (and later Accounting) to **associate** with the hub for shared navigation.

#### B. Operations & projects (jobs + bids)

1. **Create site** again.
2. Choose **Team site** (strong default for **document libraries**, lists, and future **Teams** linkage). If your org restricts team sites, use another site type your admin allows—libraries work the same.
3. Set **name** and **URL** (e.g. `WSM-Operations`). Avoid spaces in the URL slug.
4. Add **site owners** (IT + operations lead) and **members** (broader staff who need project files) per least privilege.
5. Copy the **root site URL** → record in the table above (live tenant: **WSM Projects**).

#### C. Accounting (placeholder)

- Leave **`TBD`** in the table until Task 6 / accounting is ready, **or** create a **restricted** team site now with **no** broad membership and paste the URL into the table.

#### D. Verify before Task 3

| Check | Pass? |
|-------|--------|
| Hub URL opens and you can edit the home page | ☐ |
| Operations URL opens; default **Documents** library is visible | ☐ |
| You know who **Site owners** are for each site | ☐ |
| *(If using hub)* Operations is **associated** with the hub, or you skipped hub on purpose | ☐ |

**Done when:** Hub and Operations URLs are filled in the table (Accounting can stay `TBD`). Then move to **Task 3**.

**Reference:** [SharePoint / M365 architecture guidelines](/company/resources/sharepoint-m365-architecture-guidelines) · Microsoft: [Create a site](https://learn.microsoft.com/en-us/sharepoint/create-site)

---

## Task 3 — Libraries + metadata

**Where:** **[WSM Projects](https://westatesmechanical.sharepoint.com/sites/WSMProjects)** (all libraries below live on this site unless noted). **Hub:** [WSM Hub](https://westatesmechanical.sharepoint.com/sites/WSMHub).

**Goal:** Libraries for **active jobs**, **archive**, **bids**, and (optional) **standards/templates** — plus **metadata columns** so views and Power Automate stay usable without deep folder paths.

---

### 3.1 — Choose project storage pattern

Pick **one** approach (both are valid):

| Pattern | What you create | Best when |
|---------|-----------------|-----------|
| **A — Two libraries** | **PRJ-Active** + **PRJ-Archive** | Clear mental split; move whole job folders when closing |
| **B — One library** | e.g. **Project Documents** + column **Lifecycle** = `Active` / `Closeout` / `Archive` | Fewer URLs; rely on views and metadata |

Job **folder names** inside the library follow the wiki: `/<ProjectID>-<ClientShort>/` with the numbered + commercial subfolders (see [Project home template](/projects/template-project/project-home)).

---

### 3.2 — Create document libraries (runbook)

**Who:** Site owner on **WSM Projects**.

1. Open [WSM Projects](https://westatesmechanical.sharepoint.com/sites/WSMProjects).
2. **Gear** → **Site contents** (or **+ New** → **Document library** from the nav, depending on layout).
3. **+ New** → **Document library** → name it exactly (examples):
   - `PRJ-Active` and `PRJ-Archive` **or** a single `Project Documents` (if using pattern B).
   - `Bids` — estimating / bid files, addenda, **not** the same as live job folders.
   - *(Optional)* `Standards` — controlled NFPA / company criteria PDFs (versioning on).
   - *(Optional)* `Templates` — approved blank forms (versioning on; most users read-only).

4. **Default “Documents”** library: either **rename** to fit your pattern or **leave** as general scratch — avoid mixing unrelated content with **PRJ-*** if you want clean permissions later.

5. **Bids:** keep **separate** from PRJ so retention and guest access (if any) stay simpler.

Microsoft: [Create a document library](https://learn.microsoft.com/en-us/sharepoint/create-doc-library) · [Create a column in a list or library](https://support.microsoft.com/office/create-a-column-in-a-list-or-library-b7d7cad1-2824-4949-926f-f4e88cba5228)

---

### 3.3 — Metadata columns (recommended)

Add columns via **Library settings** → **Create column** (or **Add column** in grid view). Use **consistent internal names** (no spaces in API/Power Automate).

**On PRJ-Active / PRJ-Archive / Project Documents** (apply to both if two libraries):

| Column | Type | Values / notes |
|--------|------|----------------|
| **ProjectID** | Single line of text | e.g. `TI-2026-045`; matches ERP and wiki |
| **ClientShort** | Single line of text | Matches folder suffix `ProjectID-ClientShort` |
| **Lifecycle** | Choice | `Active`, `Closeout`, `Archive` — *required if using one library (pattern B)* |
| **WikiArea** | Choice | `projects` (default for job files); other values if you tag non-project uploads |
| **DocType** | Choice | e.g. `Submittal`, `RFI`, `Drawing`, `Contract`, `Bid`, `Other` — extend as needed |

**On Bids** (simpler set):

| Column | Type | Notes |
|--------|------|--------|
| **BidID** or **Opportunity** | Single line of text | Your bid / opportunity key |
| **BidStatus** | Choice | e.g. `Pursuing`, `Submitted`, `Won`, `Lost`, `No-bid` |
| **DueDate** | Date | Bid due date |

**Standards / Templates** libraries: versioning **on**; minimal columns (e.g. **Category**, **EffectiveDate**) if useful.

---

### 3.4 — Views (quick win)

On each PRJ library, create a **view** grouped or filtered by **ProjectID** or **Lifecycle** so PMs are not scrolling one flat list.

---

### 3.5 — Record library links (fill after creation)

Paste each library’s **root URL** (open the library → copy address bar up to the library path, before `/Forms/` if present).

| Library | URL |
|---------|-----|
| PRJ-Active *(or primary project library)* | `REPLACE_PRJ_ACTIVE_LIBRARY_URL` |
| PRJ-Archive *(if used)* | `REPLACE_PRJ_ARCHIVE_LIBRARY_URL` |
| Bids | `REPLACE_BIDS_LIBRARY_URL` |
| Standards *(optional)* | `REPLACE_STANDARDS_LIBRARY_URL` or `—` |
| Templates *(optional)* | `REPLACE_TEMPLATES_LIBRARY_URL` or `—` |

**Done when:** At least **one** project library + **Bids** exist, core columns are on the project library, URLs are filled above, and a test folder `TEST-0000-TEST` can be created. Then move to **Task 4**.

**Reference:** [SharePoint / M365 architecture guidelines — metadata](/company/resources/sharepoint-m365-architecture-guidelines#metadata-alignment-wiki-mental-model)

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
