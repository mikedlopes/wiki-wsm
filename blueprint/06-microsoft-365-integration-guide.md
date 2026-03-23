## Microsoft 365 Integration Guide

### Azure AD SSO (Entra ID)

1. Register an app in Entra ID for Wiki.js.
2. Configure redirect URI from Wiki.js auth settings.
3. Generate client secret.
4. Configure Wiki.js auth provider with:
   - Tenant ID
   - Client ID
   - Client Secret
5. Map claims:
   - email -> Wiki user email
   - name -> display name
   - groups -> Wiki groups/roles
6. Test with pilot users from PM + field + accounting.

### Embedding Planner / Power BI / SharePoint / Excel

Use iframe embeds in trusted-editor pages.

```html
<!-- Planner -->
<iframe src="https://tasks.office.com/Home/PlanViews/REPLACE_PLAN_ID/Embed" width="100%" height="560"></iframe>

<!-- Power BI -->
<iframe src="https://app.powerbi.com/reportEmbed?reportId=REPLACE_REPORT_ID&groupId=REPLACE_WORKSPACE_ID" width="100%" height="680"></iframe>

<!-- SharePoint list -->
<iframe src="https://YOURTENANT.sharepoint.com/sites/FireOps/Lists/Submittals/AllItems.aspx" width="100%" height="680"></iframe>

<!-- Excel web -->
<iframe src="https://YOURTENANT.sharepoint.com/:x:/r/sites/FireOps/Shared%20Documents/Tracker.xlsx?web=1" width="100%" height="680"></iframe>
```

Security warning:
- Restrict HTML/script editing rights to trusted content owners.
- Use only approved domains.
- Validate embed access in mobile and field networks.

### Deep links per project

Standardize `project-id` across systems:

- Wiki path: `/projects/TI-2026-045/...`
- SharePoint list key: `TI-2026-045`
- Planner labels/buckets include `TI-2026-045`
- Power BI filters by `JobId`

### Recommended Power Automate flows

1. **New RFI -> Teams alert**
   - Trigger: SharePoint `RFIs` item created or status changed to Open
   - Action: post adaptive card to project Teams channel
2. **Submittal aging > X days**
   - Trigger: scheduled daily check
   - Action: notify PM + Designer
3. **CO approval -> Accounting + PM**
   - Trigger: `COs` list status = Approved
   - Action: notify billing + update PM board
4. **Weekly PPC digest**
   - Trigger: every Friday afternoon
   - Action: send planned vs completed summary

### Source references

- [NFPA](https://www.nfpa.org/)
- [NFSA](https://nfsa.org/)
- [MeyerFire Blog](https://www.meyerfire.com/blog)
- [QRFS](https://www.qrfs.com/)
