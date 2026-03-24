# Projects (wiki repo)

## Folder convention

| Type | Path | Purpose |
|------|------|---------|
| Portfolio hub | `dashboard.md` | One page: `/projects/dashboard` |
| **Starter (copy this)** | `template-project/` | Duplicate folder for each new job; edit [project-home](/projects/template-project/project-home) |
| **Live job** | `<ProjectID>/` | Example: `TI-2026-045/` — matches ERP job ID and SharePoint `ProjectID` metadata |

## Document library / file-share root (not the wiki path)

For SharePoint **PRJ-Active** (or file server), each job uses a **numbered subfolder tree** under a root named with a client short code:

```text
/<ProjectID>-<ClientShort>/
  00_Admin_Contracts_Insurance/
  01_Design_Calcs_ShopDrawings/
  02_Submittals/
  03_RFIs_ChangeOrders/
  04_Permits_AHJ/
  05_Field_Site/
  06_Testing_Inspection/
  07_Closeout/
  _QuickLinks/    ← optional shortcut files (wiki, Planner, Teams)
```

Full detail and a “what goes where” table: [Project home template](/projects/template-project/project-home).

Do **not** commit a folder literally named `[project-id]`; that name is docs-only shorthand.

See [implementation tasks — Task 1](/company/resources/m365-wiki-implementation-tasks#task-1--project-folder-convention-git--wiki).
