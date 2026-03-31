# SharePoint navigation — 1:1 with Wiki.js (WSM Projects)

Use this to **edit site navigation** on **WSM Projects** (gear → **Change the look** → **Navigation**, or **Site settings** → **Navigation** depending on experience).

**Convention**

- **Wiki URL** = `REPLACE_WIKI_BASE` + path from the table (set `REPLACE_WIKI_BASE` to your Wiki.js public root, no trailing slash — e.g. `https://wiki.yourdomain.com`).
- **SharePoint types:** **Link** = wiki or external URL; **Document library** = files you create on the site; **List** = structured rows; **Notebook** = OneNote team notebook (optional).

---

## Top level (matches [Site map](/company/site-map) + [home](/home) “Browse by library”)

| # | Nav label | Wiki path | SharePoint nav type | What to create on WSM Projects |
|---|-----------|-----------|---------------------|--------------------------------|
| 1 | **Wiki home** | `/home` | **Link** | Nothing — URL only |
| 2 | **Start here** | `/company/start-here` | **Link** | Nothing |
| 3 | **Site map** | `/company/site-map` | **Link** | Nothing |
| — | **Company** | *(heading, no URL)* | **Heading** | Nothing |
| 3a | Company hub | `/company/overview` | **Link** | Nothing |
| 3b | About | `/company/about` | **Link** | Nothing |
| 3c | Mission and values | `/company/mission-and-values` | **Link** | Nothing |
| 3d | Team directory | `/company/people/team-directory` | **Link** | Nothing |
| 3e | Org chart | `/company/people/org-chart-and-roles` | **Link** | Nothing |
| 3f | Onboarding | `/company/onboarding/overview` | **Link** | Nothing |
| 3g | Operating cadence | `/company/operations/operating-cadence` | **Link** | Nothing |
| 3h | Office handbook | `/company/operations/office-handbook` | **Link** | Nothing |
| 3i | Systems and tools | `/company/resources/systems-and-tools` | **Link** | Nothing |
| 3j | M365 architecture | `/company/resources/sharepoint-m365-architecture-guidelines` | **Link** | Nothing |
| 3k | Implementation tasks | `/company/resources/m365-wiki-implementation-tasks` | **Link** | Nothing |
| 3l | Industry resources | `/company/resources/industry-resources` | **Link** | Nothing |
| — | **Departments** | *(heading)* | **Heading** | Nothing |
| 4 | Accounting | `/departments/accounting/accounts-payable-and-vendor-management` | **Link** | Nothing |
| 5 | Purchasing | `/departments/purchasing/overview` | **Link** | Nothing |
| 6 | Shop | `/departments/shop/overview` | **Link** | Nothing |
| 7 | Field | `/departments/field/overview` | **Link** | Nothing |
| 8 | Design | `/departments/design/overview` | **Link** | Nothing |
| 9 | Estimating | `/departments/estimating/overview` | **Link** | Nothing |
| 10 | Bidding | `/departments/bidding/overview` | **Link** | Nothing |
| 11 | Project management | `/departments/project-management/overview` | **Link** | Nothing |
| 12 | Service | `/departments/service/overview` | **Link** | Nothing |
| 13 | Safety | `/departments/safety/overview` | **Link** | Nothing |
| 14 | HR | `/departments/hr/overview` | **Link** | Nothing |
| 15 | IT | `/departments/it/overview` | **Link** | Nothing |
| 16 | Business development | `/departments/business-development/overview` | **Link** | Nothing |
| 17 | Executive office | `/departments/executive/overview` | **Link** | Nothing |
| — | **Process + technical** | *(heading)* | **Heading** | Nothing |
| 18 | Processes | `/processes/overview` | **Link** | Nothing |
| 19 | Standards | `/standards/overview` | **Link** | Nothing |
| 20 | Lean tools | `/lean-tools/overview` | **Link** | Nothing |
| 21 | Templates | `/templates/template-meeting-notes` | **Link** | Nothing |
| — | **Project workspace** | *(heading)* | **Heading** | Nothing |
| 22 | Projects dashboard | `/projects/dashboard` | **Link** | Nothing |
| 23 | New project starter | `/projects/template-project/project-home` | **Link** | Nothing |
| 24 | Sample project (TI-2026-045) | `/projects/TI-2026-045/downtown-office-renovation` | **Link** | Nothing |

**Full URL pattern:** `REPLACE_WIKI_BASE` + path (e.g. `REPLACE_WIKI_BASE/company/overview`).

---

## File storage on WSM Projects (Hero + libraries — not every wiki page)

Narrative lives in **Wiki.js**. On **SharePoint**, create **document libraries** only where **official files** live. Align Hero tiles + left nav to these **libraries** (add as nav items **below** or **instead** of duplicate wiki links if you want less clutter).

| Nav / Hero label | SharePoint type | Purpose (matches wiki + Task 3) |
|------------------|-----------------|----------------------------------|
| **Projects** | **Document library** `PRJ-Active` (and optional `PRJ-Archive`) *or* one `Project Documents` + **Lifecycle** column | Job roots `/<ProjectID>-<ClientShort>/` — see [Project home template](/projects/template-project/project-home) |
| **Bids** | **Document library** `Bids` | Estimating / bid files ([Estimating](/departments/estimating/overview), [Bidding](/departments/bidding/overview)) |
| **Standards** | **Document library** `Standards` *(optional)* | Controlled PDFs that mirror [Standards](/standards/overview); wiki stays narrative |
| **Templates** | **Document library** `Templates` *(optional)* | Controlled blanks that mirror [Templates](/templates/template-meeting-notes) |
| **Forms** | **Document library** `Forms` *or* merge into **Templates** with a **Forms** view | If you keep a separate Hero tile; avoid three places for the same file |

**Optional lists** (already on your site — keep or rename to match wiki language):

| Wiki concept | SharePoint type | Notes |
|--------------|-----------------|-------|
| Project tracking | **List** (e.g. “Project tracker”) | Portfolio rows — pairs with [Projects dashboard](/projects/dashboard) |
| Issues / punch | **List** (e.g. “Issue tracker”) | Optional; can link wiki [PM](/departments/project-management/overview) |

**Do not** duplicate the entire wiki as SharePoint pages unless you want two sources of truth — use **Links** for 1:1 parity with Wiki.js.

---

## Minimal nav (if the full list is too long)

Keep **headings** + **Wiki home**, **Start here**, **Site map**, **Projects dashboard**, **Departments** (link to [PM overview](/departments/project-management/overview) only), **Standards**, **Templates**, **Processes**, then add **Projects** / **Bids** / **Standards** / **Templates** **libraries** as the SharePoint-native entries. Expand the rest when needed.

---

## WSM Hub vs WSM Projects

| Site | Typical nav |
|------|-------------|
| **[WSM Hub](https://westatesmechanical.sharepoint.com/sites/WSMHub)** | Company news, links to **Wiki.js** company/start-here, HR, IT, link to **WSM Projects** |
| **[WSM Projects](https://westatesmechanical.sharepoint.com/sites/WSMProjects)** | Full wiki parity table above + **document libraries** for job files and bids |

---

*Update `REPLACE_WIKI_BASE` when Wiki.js URL is final. Reorder nav to match team preference; structure above matches [Site map](/company/site-map).*
