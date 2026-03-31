# M365 + wiki implementation tasks

Ordered checklist for standing up SharePoint/M365 alongside this wiki. Mark items as you complete them in your runbook or PM tool.

**Current focus:** [Task 4 — Teams alignment](/company/resources/m365-wiki-implementation-tasks#task-4--teams-alignment) (project folder layout in the wiki is **frozen** — no further changes unless the business changes the template).

| # | Task | Status |
|---|------|--------|
| 1 | [Project folder convention](/company/resources/m365-wiki-implementation-tasks#task-1--project-folder-convention-git--wiki) | Done |
| 2 | [SharePoint sites + URLs](/company/resources/m365-wiki-implementation-tasks#task-2--sharepoint-sites--urls) | Done |
| 3 | [Libraries + metadata](/company/resources/m365-wiki-implementation-tasks#task-3--libraries--metadata) | Done |
| 4 | [Teams alignment](/company/resources/m365-wiki-implementation-tasks#task-4--teams-alignment) | In progress |
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

**As built:** **Projects** (job roots), **Bids**, **Standards**, **Templates**, **Forms** — see §3.5 for URLs.

---

### 3.1 — Choose project storage pattern

Pick **one** approach (both are valid):

| Pattern | What you create | Best when |
|---------|-----------------|-----------|
| **A — Two libraries** | **PRJ-Active** + **PRJ-Archive** | Clear mental split; move whole job folders when closing |
| **B — One library** | e.g. **Projects** + column **Lifecycle** = `Active` / `Closeout` / `Archive` | Fewer URLs; rely on views and metadata |

Job **folder names** inside the library follow the wiki: `/<ProjectID>-<ClientShort>/` with the numbered + commercial subfolders (see [Project home template](/projects/template-project/project-home)).

---

### 3.2 — Create document libraries (runbook)

**Who:** Site owner on **WSM Projects**.

1. Open [WSM Projects](https://westatesmechanical.sharepoint.com/sites/WSMProjects).
2. **Gear** → **Site contents** (or **+ New** → **Document library** from the nav, depending on layout).
3. **+ New** → **Document library** → name it exactly (examples):
   - `PRJ-Active` and `PRJ-Archive` **or** a single **`Projects`** library (if using pattern B).
   - `Bids` — estimating / bid files, addenda, **not** the same as live job folders.
   - *(Optional)* `Standards` — controlled NFPA / company criteria PDFs (versioning on).
   - *(Optional)* `Templates` — approved blank forms (versioning on; most users read-only).

4. **Default “Documents”** library: **rename** to **Projects** (or **PRJ-Active**) for job files, or **leave** a separate scratch library — avoid mixing unrelated content with job folders.

5. **Bids:** keep **separate** from PRJ so retention and guest access (if any) stay simpler.

Microsoft: [Create a document library](https://learn.microsoft.com/en-us/sharepoint/create-doc-library) · [Create a column in a list or library](https://support.microsoft.com/office/create-a-column-in-a-list-or-library-b7d7cad1-2824-4949-926f-f4e88cba5228)

---

### 3.3 — Metadata columns (recommended)

Add columns via **Library settings** → **Create column** (or **Add column** in grid view). Use **consistent internal names** (no spaces in API/Power Automate).

**On PRJ-Active / PRJ-Archive / Projects** (apply to both if two libraries):

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

### 3.5 — Record library links (WSM Projects)

Tenant: **westatesmechanical.sharepoint.com** · Site: **WSMProjects**. Paths below use the default **All items** view (`…/Forms/AllItems.aspx`). A library named **Forms** shows `…/Forms/Forms/AllItems.aspx` (folder name repeats).

| Library | URL |
|---------|-----|
| **Projects** *(primary project / job files)* | https://westatesmechanical.sharepoint.com/sites/WSMProjects/Projects/Forms/AllItems.aspx |
| **PRJ-Archive** *(if split later)* | `—` *(single **Projects** library for now)* |
| **Bids** | https://westatesmechanical.sharepoint.com/sites/WSMProjects/Bids/Forms/AllItems.aspx |
| **Standards** | https://westatesmechanical.sharepoint.com/sites/WSMProjects/Standards/Forms/AllItems.aspx |
| **Templates** | https://westatesmechanical.sharepoint.com/sites/WSMProjects/Templates/Forms/AllItems.aspx |
| **Forms** | https://westatesmechanical.sharepoint.com/sites/WSMProjects/Forms/Forms/AllItems.aspx |

**Done when:** Libraries exist, metadata columns applied as in §3.3, and job folders can be created under **Projects**. Then move to **Task 4**.

**Reference:** [SharePoint / M365 architecture guidelines — metadata](/company/resources/sharepoint-m365-architecture-guidelines#metadata-alignment-wiki-mental-model)

---

## Task 4 — Teams alignment

**Goal:** One **Microsoft Team** (or a small number) tied to **WSM Projects** and the **wiki**, so people open **Teams** and reach **files + procedures** without hunting. **Avoid** a new Team per job unless a contract forces it.

**Sites (reference):** [WSM Hub](https://westatesmechanical.sharepoint.com/sites/WSMHub) · [WSM Projects](https://westatesmechanical.sharepoint.com/sites/WSMProjects)

---

### 4.1 — Principles

| Do | Don’t |
|----|--------|
| Tie **one** Team to **[WSM Projects](https://westatesmechanical.sharepoint.com/sites/WSMProjects)** (SharePoint is already the file home) | Create **dozens** of project Teams for every job ID |
| Pin **wiki** + **Projects** + **Bids** as tabs or pinned posts | Duplicate every wiki page inside Teams |
| Use **channels** for workstreams (e.g. Bids, Field) only if traffic justifies it | Require everyone to use Teams for **all** chat — email still exists |

---

### 4.2 — Create or connect the Team

**If your SharePoint site is already a Microsoft 365 Group / Team site:**  
Open **Microsoft Teams** → **Teams** → **Join or create a team** → **Create a team** → **From a group or team** → select the group that backs **WSM Projects** (if listed). If a Team already exists for that group, **use it**.

**If no Team exists yet:**  
**Teams** → **Create a team** → **From scratch** → **Private** → name e.g. **WSM Projects** → add owners/members → in the final step, **link** to the existing SharePoint site if the wizard offers **“Add Microsoft SharePoint site”** or associate the default channel Files tab to [WSM Projects](https://westatesmechanical.sharepoint.com/sites/WSMProjects).

**Optional second Team for company-wide:**  
A small **WSM Hub** or **WSM General** Team linked to [WSM Hub](https://westatesmechanical.sharepoint.com/sites/WSMHub) — only if leadership wants announcements/chat separate from project noise.

Use **Teams** → **Help** (*?*) → search *create team from group* or *SharePoint site* to match your tenant’s UI. Microsoft often changes the exact menu names.

---

### 4.3 — Channels (keep it small)

| Channel | Purpose |
|---------|---------|
| **General** | Announcements, links to wiki **Start here** and **Projects dashboard** |
| *(Optional)* **Bids** | Estimating / pursuit chatter; pin **Bids** library |
| *(Optional)* **Field / PM** | Only if volume is high; otherwise **General** + wiki |

---

### 4.4 — Tabs to add (WSM Projects Team)

In each channel you use, **+** next to the tabs → add:

| Tab type | What to point at |
|----------|------------------|
| **SharePoint** | [Projects](https://westatesmechanical.sharepoint.com/sites/WSMProjects/Projects/Forms/AllItems.aspx) (or site root and browse) |
| **SharePoint** *(second tab)* | [Bids](https://westatesmechanical.sharepoint.com/sites/WSMProjects/Bids/Forms/AllItems.aspx) |
| **Website** | Wiki **Start here** — `REPLACE_WIKI_BASE/company/start-here` |
| **Website** *(optional)* | Wiki **Projects dashboard** — `REPLACE_WIKI_BASE/projects/dashboard` |
| **Planner** | Your portfolio or job plan (when embed IDs exist) |

Rename tabs clearly: **“Project files”**, **“Bids”**, **“Wiki — Start here”**.

---

### 4.5 — Pinned post (General channel)

Pin one message with bullet links:

- [Start here](REPLACE_WIKI_BASE/company/start-here) · [Site map](REPLACE_WIKI_BASE/company/site-map) · [Projects dashboard](REPLACE_WIKI_BASE/projects/dashboard)
- [WSM Projects — Projects](https://westatesmechanical.sharepoint.com/sites/WSMProjects/Projects/Forms/AllItems.aspx) · [Bids](https://westatesmechanical.sharepoint.com/sites/WSMProjects/Bids/Forms/AllItems.aspx)

Replace `REPLACE_WIKI_BASE` with your live Wiki.js root (no trailing slash).

---

### 4.6 — Record (fill when done)

| Item | Value |
|------|--------|
| Team display name | `REPLACE_TEAMS_PROJECTS_TEAM_NAME` |
| Link to open Team in Teams / web | `REPLACE_TEAMS_DEEP_LINK_OR_URL` |
| Notes | e.g. linked to M365 group for WSM Projects |

**Done when:** Team exists, **General** has pinned links + at least **Project files** and **Wiki** access via tabs or posts, and owners know who adds members. Then move to **Task 5**.

**Reference:** [SharePoint / M365 architecture guidelines — Teams](/company/resources/sharepoint-m365-architecture-guidelines#teams-alignment-lightweight)

---

## Task 5 — Wiki deep links

Add “Files live in: …” (SharePoint URL) on high-traffic department and project pages.

---

## Task 6 — Invoices and receipts

Align with [Document retention](/departments/accounting/document-retention-and-audit-readiness) and ERP ownership; restrict **Invoices-Receipts** libraries.

---

*Owner: IT / Operations (update as tasks complete).*
