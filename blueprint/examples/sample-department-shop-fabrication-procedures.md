# Shop Fabrication Procedures (Sample Department Page)

**Owner:** Shop Manager  
**Applies To:** Shop fabrication, purchasing interface, field handoff  
**References:** NFPA 13, approved project submittals, internal QA gates

## Purpose
Produce code-compliant, correctly tagged, field-ready sprinkler assemblies with minimal rework and reliable release dates.

## Inputs Required
- Approved-for-fabrication drawings
- Approved submittals (heads, couplings, valves, backflow accessories)
- Cut lists with project-zone identifiers
- Delivery windows from PM/superintendent

## Fabrication Workflow
```mermaid
flowchart LR
  releasedForFab[ReleasedForFab] --> pickMaterial[PickMaterial]
  pickMaterial --> cutThreadGroove[CutThreadGroove]
  cutThreadGroove --> qcHoldPoint[QCHoldPoint]
  qcHoldPoint --> tagBundle[TagAndBundle]
  tagBundle --> stageLoad[StageAndLoad]
  stageLoad --> fieldReceipt[FieldReceipt]
```

## Standard Work
| Step | Action | Owner | Evidence |
|---|---|---|---|
| 1 | Verify drawing revision and submittal approvals | Shop Lead | Revision check log |
| 2 | Pick material by project/zone | Material Handler | Pick list |
| 3 | Cut/thread/groove per setup charts | Fabricator | Traveler |
| 4 | Perform QC hold-point checks | QC Inspector | QC checklist |
| 5 | Tag and bundle with line identifiers | Shop Team | Tag photos |
| 6 | Issue BOL and release to field | Shop Admin | Signed BOL |

## Quality Hold Points
| Hold Point | Requirement | Fail Action |
|---|---|---|
| HP-1 | First article dimensions/thread quality | Stop and reset machine |
| HP-2 | Random spool verification per batch | Quarantine and recheck |
| HP-3 | Tag accuracy vs drawing line numbers | Re-tag and re-verify |

## Daily Shop Metrics
| Metric | Today | Target |
|---|---:|---:|
| Releases due | 6 | - |
| Releases on-time | 5 | 100% |
| Rework items | 2 | <= 1 |
| Safety observations | 3 | >= 2 |

## Escalation
- Missing approved submittal: escalate to PM + Design immediately.
- Material shortage risk >24h: escalate to Purchasing + PM.
- QA defect affecting release date: escalate to Shop Manager + Superintendent.
