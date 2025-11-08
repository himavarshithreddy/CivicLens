# CivicLens Project Brief

## Vision

A world where every public infrastructure project is transparent, verifiable, and accountable—from planning to completion—so citizens can trust how public funds are used.

## Problem

- Project information is fragmented across agencies and portals.
- Claims about progress are difficult to verify against reality.
- Critical records can be altered or go missing over time.
- Citizens and watchdogs lack timely, actionable visibility.

## Solution

CivicLens provides a unified view of public works projects with:
- Canonical data model for projects, contracts, milestones, and payments
- Evidence and verification workflows to compare planned vs. actual progress
- Public, auditable anchors of critical records on a blockchain for tamper-evidence
- Open data APIs for journalism, research, and civic tech reuse

## Objectives (MVP)

1. Aggregate and normalize project data from official sources
2. Provide searchable project directory and detailed project pages
3. Capture milestones, payments, and evidence (photos/docs) with provenance
4. Anchor hashes of critical records on-chain to make tampering detectable
5. Offer a simple public API for programmatic access

## Users & Personas

- Citizens: Track local projects, report issues, verify progress
- Journalists/NGOs: Investigate delays, overruns, inconsistencies
- Officials/Oversight: Monitor portfolios, identify risks, respond to concerns
- Developers/Researchers: Consume open data and build analyses/tools

## Core Features

- Project Directory: Filter by location, sector, agency, contractor, budget, status
- Project Profile: Overview, budget, parties, contract docs, milestones, payments
- Evidence: Upload and link photos/docs; record source, hash, and moderation state
- Verification: Compare planned vs. actual timelines; flag discrepancies
- Chain Anchors: Store content-addressed hashes with tx id and timestamp
- Alerts: Overdue milestones, cost overruns, data gaps (post-MVP)

## Data Architecture (Conceptual)

- Sources: Open data portals, procurement systems, contract registries, manual uploads
- Ingest: ETL pipelines to fetch, deduplicate, normalize
- Store: Relational DB for entities; object storage for artifacts
- Anchor: Hashes of critical artifacts recorded on a public chain
- Serve: REST/GraphQL API and web UI; public exports

## Blockchain Strategy (Initial)

- Use blockchain as an integrity layer (tamper evidence), not full storage
- Store only content hashes and minimal metadata on-chain
- Preserve privacy and comply with local regulations
- Chain choice: evaluate low-fee, high-availability public networks

## Canonical Data Model (Draft)

- Project(id, title, description, sector, location, budget, start_date, end_date, agency_id)
- Party(id, type[agency|contractor|oversight], name, contact)
- Contract(id, project_id, amount, currency, tender_id, documents[], amendments[])
- Milestone(id, project_id, name, planned_date, actual_date, status, evidence[])
- Payment(id, project_id, payee_id, amount, currency, date, reference)
- Evidence(id, owner_id, type[photo|pdf|url], storage_uri, content_hash, source, verifier, moderation_state)
- ChainAnchor(id, record_type, record_id, content_hash, chain, tx_id, anchored_at)

## Lifecycle

1. Data Ingest -> Normalize -> Link to projects
2. Evidence added -> Hash computed -> Anchor recorded
3. Milestones updated -> Status recalculated -> Alerts emitted
4. Public UI/API -> Discovery, monitoring, export

## Governance & Roles

- Admin: system configuration, source management, moderation oversight
- Moderator: review evidence, handle reports, approve/deny
- Contributor: submit evidence and corrections
- Viewer: read-only access via UI/API

## Security & Privacy

- Content hashing for integrity; on-chain anchoring for immutability
- PII minimization; do not anchor personal data
- Access controls for moderation/administration

## Success Metrics

- % of projects with complete milestone and payment coverage
- Time-to-detect discrepancies (claimed vs. actual)
- Evidence submissions approved per month
- Data reuse via API (requests, unique consumers)

## Risks & Mitigations

- Data quality variance -> rigorous normalization and source labeling
- Legal/compliance constraints -> PII minimization, clear terms, safe defaults
- Chain availability/fees -> multi-chain support or delayed batch anchoring

## Glossary

- Anchor: Record a hash of off-chain content on-chain for tamper-evidence
- Evidence: Artifact supporting verification (photo, PDF, URL)
- Provenance: Who/when/where of data creation and transformation

## Next Steps (MVP)

- Finalize data model and API contracts
- Select chain and anchoring strategy
- Implement ingest for priority sources
- Build project directory and profile UI
- Ship public read-only API


