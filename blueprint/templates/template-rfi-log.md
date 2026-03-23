# Template - RFI Template & Log

## New RFI Template
| Field | Value |
|---|---|
| RFI No. | {{RFI-###}} |
| Date | {{YYYY-MM-DD}} |
| From | {{PM/Design}} |
| To | {{GC/AOR/AHJ}} |
| Subject | {{Short title}} |
| Drawing/Spec Ref | {{Ref}} |
| Question | {{Clear question}} |
| Proposed Resolution | {{Option}} |
| Cost Impact | {{Yes/No/TBD}} |
| Schedule Impact | {{Yes/No/TBD}} |
| Required By | {{Date}} |

## Open RFI Log
| RFI | Subject | Submitted | Ball-in-Court | Aging | Impact | Status |
|---|---|---|---|---:|---|---|
| RFI-001 | {{Question}} | {{DATE}} | {{Party}} | 0 | {{Cost/Schedule/None}} | Open |

## Optional Teams Notification
- Power Automate trigger: SharePoint `RFIs` item created/updated where `Status=Open`.
- Action: post adaptive card in project Teams channel.
