# Freelance Content Creator Escrow Platform

**Software Engineering Labs 1–3 | Problem Statement #53**

This repository contains the academic analysis and design deliverables for a freelance platform in which creators and sponsors agree milestone terms, review protected draft deliverables, and release escrowed payments only after sponsor approval.

> **Academic scope:** These are Software Engineering coursework deliverables. Jira sprint statuses document a classroom workflow simulation; they are not evidence that the platform has been implemented, tested, or deployed.

## Project scenario

The platform supports:
- Joint definition of milestone deliverables, due dates, and escrow amounts.
- Creator draft submission and automatic watermarking before sponsor preview.
- Sponsor approval or rejection with written revision comments.
- Payment release only after sponsor approval/sign-off.
- Dispute escalation after two rejections to a neutral Escrow Moderator.
- Encrypted escrow wallet data and append-only financial audit events.

## Requirements baseline

| ID | Requirement |
|---|---|
| FR-001 | Submit drafts for review; release locked milestone funds only after sponsor approval/sign-off. |
| FR-002 | Creator and sponsor jointly define deliverable description, due date, and escrow amount. |
| FR-003 | Automatically watermark every uploaded image/video draft before sponsor review. |
| FR-004 | Sponsor rejection requires written comments; milestone becomes Pending Revision, funds remain locked, and creator is notified. |
| FR-005 | Either party may raise a dispute after two rejections; freeze funds and route to neutral moderator for recorded resolution. |
| NFR-001 | Watermark image/video previews within five seconds under a defined test workload. |
| NFR-002 | Encrypt escrow wallet data and maintain append-only lock/release/refund events with timestamp, actor ID, milestone ID, and transaction reference. |

## Lab deliverables

### Lab 1 — Requirements Engineering & UML Use-Case Modelling

- [Original Problem Statement #53](problem-statement/53_SE_Lab1_SE_Problem_Statements.pdf)
- [Requirements Table](requirements/Requirements_Table.pdf)
- [UML Use-Case Diagram](diagrams/UseCase_Diagram.pdf)
- [Use-Case Flow Specification](use-case-flow/UseCase_Flow.pdf)

Use cases: UC-01 Define Milestone Contract; UC-02 Submit Draft Deliverable; UC-03 Apply Watermark; UC-04 Review & Approve Draft; UC-05 Request Revision; UC-06 Release Milestone Payment; UC-07 Process Payment Transaction; UC-08 Raise Dispute.

### Lab 2 — Jira Hands-on: Agile Backlog Creation & Sprint Simulation

See [Lab 2 README](lab-2-agile/README.md), the backlog CSV, simulation report, and evidence folder.

[Jira project backlog](https://vario-pes.atlassian.net/jira/software/c/projects/FEP/boards/34/backlog) · [Sprint board](https://vario-pes.atlassian.net/jira/software/c/projects/FEP/boards/34)

The recorded academic simulation covers 9 stories and 57 story points across three closed sprints: Sprint 1 (18), Sprint 2 (23), Sprint 3 (16). Sprint 2 and Sprint 3 reports identify their stories as completed outside the sprint because the simulation completion timestamps precede their planned start dates. This reporting discrepancy is disclosed in the Lab 2 notes.

**Lab 2 handout limitation:** The official Lab 2 handout was not available when this work was prepared. The deliverable follows the lab title and the supplied peer example's visible Jira activities; confirm any additional instructor-specific criteria.

### Lab 3 — Software Architecture & UML Component Modelling

See [Lab 3 README](lab-3-architecture/README.md).

The selected style is **Layered Architecture with modular business components**, after comparing Layered, Microservices, and Client-Server architectures. The component diagram is a logical component view; components are not claimed to be separately deployed services.

## Repository structure

```
problem-statement/       Original Problem Statement #53
requirements/            Lab 1 requirements baseline
diagrams/                Lab 1 use-case diagram
use-case-flow/           Lab 1 use-case flow
lab-2-agile/             Jira backlog, sprint simulation, evidence
lab-3-architecture/      Architecture justification and component diagram
```

## Traceability and submission notes

- Labs 2 and 3 retain the Lab 1 requirement identifiers FR-001–FR-005 and NFR-001–NFR-002.
- Story-point values are planning estimates, not measured implementation effort.
- Jira issue status is workflow evidence only; do not interpret it as feature-completion evidence.
- The five-second watermark target needs a defined asset size, hardware, concurrency, and timing method before it can be treated as a reproducible performance test.
- Capture genuine Jira UI screenshots for the evidence folder; do not substitute recreated diagrams or mock screenshots for Jira evidence.

## License

See [LICENSE](LICENSE).
