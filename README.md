# CivicLens

Making public infrastructure transparent, verifiable, and accountable.

## Overview

CivicLens is a platform that makes public infrastructure projects easy for citizens, journalists, and officials to track and verify. It aggregates trusted data about each project—budget, responsible agency, contractors, timeline, milestones, payments, and field status—and anchors critical records on a blockchain to make them tamper-evident. This creates a permanent, auditable trail that strengthens accountability and public trust.

## Why CivicLens

- Lack of transparency and fragmented data on public works
- Difficulty verifying claims vs. on-ground progress
- Limited, delayed, or altered public records
- Weak feedback loops for citizens and watchdogs

By allowing anyone to search for projects in their area and compare claimed progress with actual results, CivicLens helps uncover misuse of funds, highlight delays, and improve governance outcomes.

## Key Features (MVP)

- Project Directory: Search and filter by location, sector, agency, contractor, budget, and status
- Project Profiles: Budget, tender/contract details, responsible officials, milestones, timeline, payments
- Evidence & Verification: Attach photos, documents, and on-site checks; compare planned vs. actual
- Audit Trail: Hash of critical records (tenders, contracts, change orders, milestones, payments) anchored on a public chain
- Alerts: Flag overdue milestones, cost overruns, and data inconsistencies
- Public API: Open data access to project metadata and status

## How It Works (High-Level)

1. Ingest and normalize project data from official sources (open data portals, tender systems, contracts)
2. Structure data into a canonical model (projects, milestones, payments, parties, locations)
3. Anchor hashes of critical records on a blockchain to provide immutability/tamper evidence
4. Serve a public UI and API for discovery, monitoring, and verification
5. Enable crowd verification with evidence submissions and moderation workflows

## Data Model (Conceptual)

- Project: id, title, description, sector, location, budget, start/end dates, agency
- Party: agency, contractor, oversight, contact info
- Contract/Tender: amounts, line items, documents, amendments
- Milestone: planned/actual dates, status, evidence
- Payment: amount, date, payee, reference
- Evidence: photos/docs, source, hash, verifier, moderation state
- Chain Anchors: record type, record id, hash, tx id, timestamp

## Roadmap (Draft)

- MVP: Project directory, profiles, milestones, basic evidence, anchor critical records
- V2: Alerts, change order tracking, cost overrun analysis, map visualizations
- V3: Mobile field verification app, richer analytics, advanced provenance metadata

## Getting Started

This repository currently contains project documentation and scaffolding. Implementation details (API, web app, data pipelines) will be added in subsequent commits.

### Local Setup (placeholder)

1. Clone the repo
2. Install dependencies (to be defined)
3. Run dev server (to be defined)

## Contributing

Contributions are welcome! Please open an issue to discuss proposed features, data sources, or improvements. When submitting changes, include clear descriptions and rationale.

## License

MIT © 2025 Himavarshith Reddy

