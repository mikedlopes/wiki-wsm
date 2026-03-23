# Change Order Workflow (Enterprise Standard)

Single workflow for identifying, pricing, approving, and booking change orders across all projects.

---

## CO workflow

```mermaid
flowchart LR
  I[Issue / scope change identified] --> T[Triage + entitlement]
  T --> P[Pricing package]
  P --> A[Internal approval]
  A --> S[Submit to GC/Owner]
  S --> X[Execute change order]
  X --> B[Budget / forecast update]
```

---

## Required package

| Component | Required |
|----------|----------|
| Narrative with scope boundary | Yes |
| Labor/material backup | Yes |
| Schedule impact statement | Yes |
| Exclusions/assumptions | Yes |

---

## Governance thresholds

| Value | Approval |
|------|----------|
| <= $25k | PM + estimator |
| $25k-$100k | PM + ops manager |
| > $100k | Executive signoff |

---

*Cross-links: [CO template](/templates/template-change-order-summary) · [PM](/departments/project-management/overview)*