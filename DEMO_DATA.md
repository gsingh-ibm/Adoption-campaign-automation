# Demo Data Structure

This document explains the demo dataset used for the Adoption Campaign Automation workflow.

## Purpose

The demo dataset exists to simulate a realistic adoption review workflow without requiring live integrations to Amplitude, Salesforce, Gainsight, or email systems.

It is designed to demonstrate:

- account-level usage analysis
- baseline comparison
- health scoring
- trend detection
- suppression logic
- outreach draft generation

## Demo Folder Structure

Each account is stored in its own folder.

Example structure:

```text
Account Name/
├── Active Users/
├── Feature Usage/
├── Account data/
└── Outreach history/
```

## Files Per Account

### 1. Active Users

Contains CSV files with daily unique user counts.

Example files:
- `Active Cloudability Users (Feb - April).csv`
- `Active Cloudability Users - May 2026.csv`

Purpose:
- show engagement trend over time
- support declining, stable, or recovering signals

### 2. Feature Usage

Contains CSV files with monthly active users by feature.

Example files:
- `Feature Adoption - # of Active Users by Feature (Feb - April).csv`
- `Feature Adoption - # of Active Users by Feature - May 2026.csv`

Purpose:
- compare actual feature adoption against baseline targets
- identify which features are under-adopted

### 3. Account Data

Contains account metadata used for the demo.

Example file:
- `account_metadata.txt`

Typical fields:
- account name
- account tier
- industry
- account sentiment
- CSM / owner
- renewal date

Purpose:
- select the correct baseline
- simulate ownership mapping for the demo
- provide context for outreach recommendations

### 4. Outreach History

Contains optional outreach history records.

Example file:
- `outreach_history.csv`

Purpose:
- demonstrate suppression logic
- show recent outreach vs old outreach scenarios

Some demo accounts intentionally have empty outreach folders to show eligible-for-outreach cases.

## Demo Accounts

The demo dataset includes multiple account scenarios.

### LandmarkGroup
Original sample account used to inspect the source data structure.

### TechCorp
Scenario:
- Healthy account
- above baseline
- no recent outreach

Purpose:
- demonstrate no-action-needed outcome

### FinanceFirst
Scenario:
- Watchlist account
- mixed performance
- recent outreach within suppression window

Purpose:
- demonstrate suppression due to recent contact

### RetailMax
Scenario:
- At Risk account
- below baseline
- no recent outreach

Purpose:
- demonstrate outreach eligibility

### HealthcarePlus
Scenario:
- Critical account
- very low usage
- old outreach outside suppression window

Purpose:
- demonstrate critical account eligible for new outreach

### ManufacturingPro
Scenario:
- Declining account
- was healthier in earlier months
- now trending downward
- no recent outreach

Purpose:
- demonstrate trend-aware prioritization

## Demo Feature Set

The demo uses a simplified feature set aligned to the baseline model.

Tracked categories:
- dashboards
- reports
- analytics_overview or insights
- rightsizing or optimization
- truecost_explorer as optional supporting context

These are mapped into standard categories for scoring.

## Demo Baseline Alignment

The demo data is aligned to the baseline reference model.

### Enterprise Examples
Expected monthly usage:
- dashboards = 10
- reports = 4
- insights / analytics = 4
- rightsizing / optimization = 2

### Mid-Market Examples
Expected monthly usage:
- dashboards = 5
- reports = 2
- insights / analytics = 2
- rightsizing / optimization = 1

This allows the demo to show:
- healthy accounts
- watchlist accounts
- at risk accounts
- critical accounts
- declining accounts

## Example Analysis Inputs

For each account, the workflow should use:

- account metadata
- feature usage history
- active user trend
- outreach history if available

These inputs are enough to support:
- baseline selection
- score calculation
- trend detection
- suppression checks
- draft generation

## Why CSV-Based Demo Data Works

CSV-based demo data is useful because it is:

- easy to inspect
- easy to explain
- easy to modify
- independent of live API access
- suitable for stakeholder demos

It also allows the workflow to be validated before production integrations are added.

## Demo Limitations

The demo dataset is intentionally simplified.

Limitations:
- ownership is simulated through metadata files
- no live CRM or Gainsight sync
- no live Amplitude API calls
- no real email sending
- no persistent production-grade database

These limitations are acceptable for a demo but should be replaced in production.

## Recommended Production Replacement

Replace demo data sources with:

- Amplitude or warehouse usage data
- Gainsight or Salesforce ownership mapping
- CRM / CTA outreach history
- centralized baseline configuration
- database-backed flow history

## Related Documents

- [`README.md`](README.md)
- [`ARCHITECTURE.md`](ARCHITECTURE.md)
- [`BASELINE_SCORING.md`](BASELINE_SCORING.md)
- [`ROADMAP.md`](ROADMAP.md)