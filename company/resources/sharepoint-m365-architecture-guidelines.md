# SharePoint & Microsoft 365 architecture (guidelines)

This document is the **reference map** for how we intend to use **SharePoint sites**, **libraries**, **lists**, and **Teams** alongside **Wiki.js**. It is a guideline—not a rigid org chart of URLs—so names can match your tenant while the **roles** stay consistent.

---

## How this ties together

| Layer | Role |
|--------|------|
| **Wiki** | Narrative SOPs, onboarding, standards, “how we work,” links out to live systems. |
| **SharePoint** | Files, controlled libraries, metadata, retention, and **official document storage**. |
| **Lists / Planner** | Structured tracking (RFIs, punch, training, simple registers). |
| **Teams** | Conversations, meetings, and **shortcuts** to the right library/list. |
| **ERP / accounting system** | **Financial truth** for invoices, payments, and job costing. |

**Rule of thumb:** If it is a **procedure or explanation**, it lives in the wiki (or is linked from it). If it is a **file or row of record data** we must produce in an audit, it lives in SharePoint or the ERP with clear ownership.

---

## Site architecture (reference table)

Use this table to decide **where something belongs** and **what to link from the wiki**. Site *names* are examples; keep the **function** even if you consolidate into fewer URLs.

| Site (function) | What it’s for | Primary users | Wiki tie-in | Typical M365 pieces | Notes |
|------------------|---------------|---------------|-------------|----------------------|-------|
| **Organization / intranet hub** | Company news, policies, org-wide links, “start here” for employees | Everyone | Links from [Start here](/company/start-here), [Systems and tools](/company/resources/systems-and-tools), onboarding | Communication site, highlighted links, maybe org asset library for branded templates | Avoid duplicating long SOPs here—**link to the wiki** for narrative content. |
| **Operations & projects** | Project folders, submittals packages, closeout, field turnover, shop packages by job | PM, field, shop, design | [Projects](/projects/dashboard), [Project template](/projects/[project-id]), department hubs | Document libraries **PRJ-Active** / **PRJ-Archive** (or one library + **Lifecycle** column), metadata (project ID, phase, discipline) | Align metadata with wiki areas (e.g. `WikiArea: projects`) **without** mirroring every wiki path as folders. |
| **Estimating & bids** | Bid files, addenda, pricing workpapers, **bid decision log** | Estimating, BD, exec as needed | Processes for bid/no-bid; link to bid library from wiki bid pages when created | Library **Bids** (or similar), optional **Bids** list for status/owner/due dates | Keeps bid clutter off the main project libraries; retention can differ from active jobs. |
| **Company templates & standards** | Controlled blank forms, spec excerpts we’re allowed to redistribute, **approved** company letterhead | All who publish | [Standards](/standards/home), [Templates](/templates/home) | Library with versioning; read-only for most roles | Wiki describes *when* to use a template; SharePoint holds the **file version** employees must use. |
| **Accounting / finance workspace** | **Supporting documents** for AP/AR, month-end packs, audit binders—not a second general ledger | Accounting, admin, approvers | [Accounting](/departments/accounting/overview), [Document retention](/departments/accounting/document-retention-and-audit-readiness) | Restricted library or libraries (e.g. **Invoices-Receipts**, **Month-end**, **Audit**), optional Lists for approval queues if not in ERP | See **Invoices and receipts** below. |
| **People & HR (optional site or hub area)** | Offer letters, I-9 storage policy, training attestations **if** stored outside HRIS | HR, managers | [Onboarding](/company/onboarding/overview), HR department pages | Restricted libraries; avoid PII in open Teams | Often merged with hub for small orgs; **separate permissions** matter more than separate URL. |
| **IT & records (optional)** | IT runbooks, license proof, export of wiki backup policy | IT | [IT overview](/departments/it/overview) | Small team site or hub library | Keeps technical artifacts out of project noise. |

---

## Invoices and receipts (small but important note)

**Financial transactions remain authoritative in the ERP/accounting system.** SharePoint is for **documentation that supports** those transactions—not a parallel bookkeeping system.

| Need | Typical approach |
|------|------------------|
| Vendor **invoices** (AP) | ERP holds amount, vendor, GL; SharePoint stores **PDF/image** and routing/approval trail if not fully in ERP. |
| Customer **invoices** (AR) | Same: ERP for numbers; SharePoint for **signed PDFs**, lien releases, or backup the customer requested. |
| **Receipts** (expenses, small purchases) | Policy + retention per [Document retention](/departments/accounting/document-retention-and-audit-readiness); attach scans to expense workflow or file in a **Receipts** library with metadata (date, employee, job optional). |

Naming libraries clearly (e.g. **Invoices-Receipts-Supporting**) avoids mixing them with **project** submittal folders. Restrict access to accounting roles.

---

## Metadata alignment (wiki mental model)

Optional columns on libraries help navigation without exploding folder trees:

| Column (example) | Use |
|--------------------|-----|
| `ProjectID` | TI-2026-045 style IDs; ties to wiki project pages. |
| `WikiArea` | `company` · `departments` · `processes` · `projects` · `standards` · `templates` · `lean` · `blueprint` — for reporting, not for duplicating wiki URLs. |
| `Lifecycle` | Active · Closeout · Archive — pairs with PRJ-Active / PRJ-Archive pattern. |
| `DocType` | Submittal · RFI · Drawing · Invoice-Receipt · Bid · etc. |

---

## Teams alignment (lightweight)

For a ~30-person internal shop, prefer **Teams mapped to workstreams** (e.g. Operations, Estimating, Accounting) with **pinned** links to the right SharePoint libraries and wiki pages—**not** a new Team per project unless isolation or volume demands it.

---

## Related wiki pages

- [Systems and tools](/company/resources/systems-and-tools)
- [Site map](/company/site-map)
- [Document retention and audit readiness](/departments/accounting/document-retention-and-audit-readiness)

---

*This page is maintained with IT/Operations leadership. Update when tenant structure or ERP boundaries change.*
