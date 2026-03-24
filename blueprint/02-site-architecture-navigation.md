## Site Architecture & Navigation

### Full hierarchy tree (key paths)

```text
/
├─ home.md
├─ company/
│  ├─ start-here.md
│  ├─ about.md
│  ├─ mission-and-values.md
│  ├─ people/
│  │  ├─ team-directory.md
│  │  └─ org-chart-and-roles.md
│  ├─ onboarding/
│  │  ├─ overview.md
│  │  ├─ new-hire-checklist.md
│  │  └─ role-onboarding-plans.md
│  ├─ operations/
│  │  ├─ operating-cadence.md
│  │  ├─ communication-protocol.md
│  │  └─ office-handbook.md
│  └─ resources/
│     ├─ systems-and-tools.md
│     └─ industry-resources.md
├─ departments/
│  ├─ accounting/
│  ├─ purchasing/
│  ├─ shop/
│  ├─ field/
│  ├─ design/
│  ├─ estimating/
│  ├─ bidding/
│  └─ project-management/
├─ processes/
├─ projects/
│  ├─ dashboard.md
│  ├─ template-project/
│  └─ <ProjectID>/
├─ standards/
├─ templates/
└─ lean-tools/
```

### Suggested sidebar menu + top nav

- **Top nav:** Home | Start Here | Projects Dashboard | Standards | Templates
- **Sidebar groups:**
  - Company
  - Departments
  - Processes
  - Projects
  - Standards
  - Templates
  - Lean Tools

### Tagging & search strategy

Use controlled tags:

- **Discipline:** `accounting`, `purchasing`, `shop`, `field`, `design`, `estimating`, `bidding`, `pm`
- **Lifecycle:** `kickoff`, `submittal`, `rfi`, `co`, `procurement`, `fabrication`, `inspection`, `closeout`
- **Compliance:** `nfpa13`, `nfpa25`, `cslb-c16`, `ahj`, `california-code`
- **Project:** `project:TI-2026-045`, `status:active`, `client:...`
- **Lean:** `lookahead`, `ppc`, `constraint`

Rules:

- Keep 5-8 tags per page
- Include at least one discipline + one lifecycle tag
- Project pages always include `project:<id>`

### User roles/groups & permissions matrix

| Group | Read | Write | Notes |
|---|---|---|---|
| Executive | All | All | Strategy and governance |
| PM | Projects/processes/departments | Projects and PM/process pages | No HR/payroll admin details |
| Design | Design/standards/projects | Design + technical project pages | Submittals/calcs ownership |
| Field/Super | Field/shop/projects/standards/templates | Field execution pages | Read-only for financial pages |
| Shop | Shop/purchasing/projects | Shop fabrication pages | |
| Accounting | Accounting/projects | Accounting pages | Financial controls |
| Estimating/Bidding | Estimating/bidding/standards | Estimating/bidding pages | |
| Purchasing | Purchasing/shop/projects | Purchasing pages | |
| HR/Admin | Company/onboarding/hr | Company/HR pages | |
| Viewer | Scoped areas | None | Read-only users |
