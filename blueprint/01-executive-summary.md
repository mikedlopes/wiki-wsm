## Executive Summary

This blueprint defines a production-ready Wiki.js operations hub for a California C-16 fire sprinkler subcontractor focused on tenant improvements and design-build projects. It establishes a single source of truth across accounting, purchasing, shop fabrication, field operations, design, estimating, bidding, and project management with role-based access, revision history, and auditable workflows. The system uses practical lean controls (lookahead, PPC, constraints, waste reduction) and Kanban-style visibility through embedded Microsoft Planner, Power BI, and SharePoint lists (because Wiki.js has no native Kanban board). Recommended deployment is self-hosted Docker + PostgreSQL with Microsoft Entra ID (Azure AD) SSO for secure, scalable identity and permissions.

### Key benefits

- One operating system for office, shop, and field
- Faster TI execution with standardized submittal/RFI/CO workflows
- Improved compliance traceability for NFPA 13/25 and C-16 documentation
- Reduced handoff errors between estimating, PM, design, purchasing, and field
- Better decision speed through embedded Planner and Power BI dashboards
