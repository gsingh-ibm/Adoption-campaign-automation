# Roadmap

This document outlines a practical evolution path for the Adoption Campaign Automation project.

## Guiding Principle

Build in phases.

Start with:
- clear documentation
- demo-ready data
- explainable scoring
- stakeholder-friendly workflows

Then evolve toward:
- runnable prototype
- hosted or serverless MVP
- production integrations
- advanced intelligence

## Phase 1: Documentation-First Demo

### Goals
- explain the business problem clearly
- document the workflow and architecture
- define baseline and suppression logic
- create realistic demo data
- support stakeholder reviews and GitHub presentation

### Deliverables
- project documentation
- flow charts
- baseline reference
- demo data structure
- sample outputs

### Outcome
A clean, presentation-ready repository that explains the concept end to end.

## Phase 2: Local Runnable Prototype

### Goals
- run the workflow locally
- analyze demo account folders automatically
- calculate scores and statuses
- generate sample outreach drafts
- produce markdown or console outputs

### Deliverables
- local analysis script
- reusable scoring logic
- sample report generation
- sample outreach generation

### Outcome
A working prototype that proves the workflow beyond documentation.

## Phase 3: Hosted or Serverless MVP

### Goals
- trigger the workflow from Slack or BOB
- identify the requesting user
- fetch owned accounts automatically
- check recent flow execution history
- run scoring and suppression logic
- generate drafts through Bob or an LLM
- return results to Slack or BOB

### Recommended Architecture
- Slack App or BOB chat trigger
- hosted orchestrator or serverless flow
- AWS Lambda, Azure Functions, or similar
- synced ownership mapping from Gainsight or Salesforce
- database-backed flow history
- API-based draft generation

### Outcome
A production-style MVP with real orchestration and approval flow.

## Phase 4: Production Integrations

### Goals
- replace demo CSVs with live or synced data
- integrate with Amplitude or warehouse
- integrate with Gainsight or Salesforce
- integrate with CRM / CTA / email systems
- centralize baseline configuration
- add monitoring and alerting

### Deliverables
- production data connectors
- secure credential management
- logging and observability
- retry and failure handling
- admin configuration controls

### Outcome
A scalable operational workflow that can support real CSM teams.

## Phase 5: Advanced Intelligence

### Goals
- improve prioritization quality
- personalize recommendations further
- reduce false positives
- support more nuanced outreach decisions

### Possible Enhancements
- churn-risk signals
- anomaly detection
- account sentiment enrichment
- renewal-aware prioritization
- feature recommendation logic
- multi-channel outreach suggestions
- adaptive baselines by segment or maturity

### Outcome
A smarter and more strategic adoption intelligence system.

## Suggested Near-Term Priorities

Recommended next steps after documentation:

1. publish the GitHub documentation repo
2. add sample outputs and screenshots
3. build a lightweight local prototype
4. define the production data contracts
5. choose the orchestration platform
6. implement a serverless MVP

## Decision Points Ahead

Before moving to production, decide:

- what is the source of truth for ownership mapping
- where flow history should be stored
- what suppression rules are mandatory
- which LLM or Bob integration will generate drafts
- whether approval happens in Slack, BOB, or CRM
- whether the first MVP is batch-based or on-demand

## Long-Term Vision

The long-term vision is not just automated email drafting.

It is a broader adoption intelligence workflow that can:

- continuously monitor account health
- prioritize intervention opportunities
- explain why an account is at risk
- recommend the right next action
- keep humans in control of outbound communication

## Related Documents

- [`README.md`](README.md)
- [`ARCHITECTURE.md`](ARCHITECTURE.md)
- [`BASELINE_SCORING.md`](BASELINE_SCORING.md)
- [`DEMO_DATA.md`](DEMO_DATA.md)