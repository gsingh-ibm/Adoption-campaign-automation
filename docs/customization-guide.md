# Customization Guide

This guide explains how to adapt the Adoption Campaign Automation workflow for different teams, products, and operating models.

## What Can Be Customized

The workflow is intentionally modular. The following areas can be adapted:

- baseline definitions
- feature mappings
- suppression rules
- ownership mapping source
- outreach templates
- approval workflow
- deployment model

## 1. Baseline Definitions

Baselines should reflect expected adoption for your business.

You can customize by:
- account tier
- industry
- customer maturity
- product edition
- region
- lifecycle stage

Examples:
- enterprise accounts may require higher dashboard and report usage
- newer customers may have lower initial expectations
- mature FinOps customers may have stronger optimization expectations

See [`../BASELINE_SCORING.md`](../BASELINE_SCORING.md) for the default demo model.

## 2. Feature Mappings

Raw product usage labels often vary across exports and systems.

You should define a mapping from raw labels to standard categories.

Example:
- `dashboards`, `dashboard views` → Dashboards
- `reports`, `saved reports` → Reports
- `analytics_overview`, `insights` → Insights / Analytics
- `rightsizing`, `optimize`, `optimization` → Rightsizing / Optimization

This keeps scoring consistent even when source labels differ.

## 3. Suppression Rules

Suppression rules should reflect your outreach governance model.

Common rules:
- suppress if recent email exists
- suppress if recent manual outreach exists
- suppress if open CTA exists
- suppress if flow already ran recently
- suppress if account is already healthy

You can customize:
- suppression window length
- which channels count as outreach
- whether CTA state blocks new drafts
- whether healthy accounts are excluded automatically

## 4. Ownership Mapping Source

The demo uses local metadata for simplicity, but production should use a real ownership source.

Possible sources:
- Gainsight
- Salesforce
- Monday
- internal ownership table
- synced warehouse table

Recommended production pattern:
- use one primary source of truth
- sync ownership into a lightweight lookup table
- avoid live multi-system lookups on every request unless necessary

## 5. Outreach Templates

Draft generation can be customized by:

- account segment
- health status
- feature gap type
- renewal proximity
- industry
- communication channel

Examples:
- watchlist accounts may receive lighter educational messaging
- critical accounts may receive stronger intervention messaging
- declining accounts may receive urgency-focused messaging

## 6. Approval Workflow

Human approval can happen in different places.

Options:
- Slack
- BOB chat
- CRM task queue
- internal review dashboard

Possible actions:
- approve
- edit
- suppress
- save for later
- escalate

## 7. Deployment Model

You can adapt the deployment model based on maturity.

### Demo
- local files
- CSV exports
- manual or scripted orchestration

### Prototype
- local or hosted runtime
- reusable scoring logic
- sample trigger and outputs

### Production
- serverless orchestration
- synced ownership mapping
- database-backed flow history
- live integrations

See [`deployment-guide.md`](deployment-guide.md) for deployment guidance.

## 8. Reporting Output

You can customize the output format for different audiences.

Examples:
- Slack summary card
- markdown report
- CRM note
- CTA recommendation
- executive dashboard summary

Typical output fields:
- account name
- health score
- status
- top feature gaps
- trend label
- suppression result
- recommendation

## 9. Governance Controls

As the workflow matures, define clear governance rules for:

- who can trigger reviews
- who can approve outbound drafts
- what gets logged
- how long suppression lasts
- how exceptions are handled

## 10. Recommended Customization Sequence

If adapting this workflow for a new team, use this order:

1. define ownership source
2. define baseline model
3. define feature mappings
4. define suppression rules
5. define approval workflow
6. define output format
7. choose deployment model

## Related Documents

- [`../README.md`](../README.md)
- [`../ARCHITECTURE.md`](../ARCHITECTURE.md)
- [`../BASELINE_SCORING.md`](../BASELINE_SCORING.md)
- [`deployment-guide.md`](deployment-guide.md)