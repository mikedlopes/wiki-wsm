# Projects (wiki repo)

## Folder convention

| Type | Path | Purpose |
|------|------|---------|
| Portfolio hub | `dashboard.md` | One page: `/projects/dashboard` |
| **Starter (copy this)** | `template-project/` | Duplicate folder for each new job; edit [project-home](/projects/template-project/project-home) |
| **Live job** | `<ProjectID>/` | Example: `TI-2026-045/` — matches ERP job ID and SharePoint `ProjectID` metadata |

## Document library / file-share root (not the wiki path)

For SharePoint **PRJ-Active** (or file server), each job uses the **same eight folders** as the current project template, under a root named with a client short code:

```text
/<ProjectID>-<ClientShort>/
  Bid/
  Billing/
  Change Estimates/
  Contract/
  Drawings/
  Job Setup/
  Prelien Info/
  Template Forms/
  _QuickLinks/    ← optional shortcut files (wiki, Planner, Teams)
```

Full detail and a “what goes where” table: [Project home template](/projects/template-project/project-home).

Do **not** commit a folder literally named `[project-id]`; that name is docs-only shorthand.

See [implementation tasks — Task 1](/company/resources/m365-wiki-implementation-tasks#task-1--project-folder-convention-git--wiki).
