# Freelance Content Creator Escrow Platform

**Software Engineering Labs 1–3 | Problem Statement #53**

This repository contains the academic analysis and design deliverables for a freelance platform in which creators and sponsors agree milestone terms, review protected draft deliverables, and release escrowed payments only after sponsor approval.

> **Academic scope:** Jira sprint statuses document a classroom workflow simulation. They are not evidence that the platform has been implemented, tested, or deployed.

## Problem scope

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

## Lab 1 — Requirements Engineering & UML Use-Case Modelling

- [Original Problem Statement #53](problem-statement/53_SE_Lab1_SE_Problem_Statements.pdf)
- [Requirements Table](requirements/Requirements_Table.pdf)
- [UML Use-Case Diagram](diagrams/UseCase_Diagram.pdf)
- [Use-Case Flow Specification](use-case-flow/UseCase_Flow.pdf)

Use cases: UC-01 Define Milestone Contract; UC-02 Submit Draft Deliverable; UC-03 Apply Watermark; UC-04 Review & Approve Draft; UC-05 Request Revision; UC-06 Release Milestone Payment; UC-07 Process Payment Transaction; UC-08 Raise Dispute.

## Lab 2 — Agile Backlog Creation & Sprint Simulation

- [Lab 2 folder](lab-2-agile/)
- [Lab 2 report source](lab-2-agile/Lab2_Agile_Backlog_and_Sprint_Simulation.md)
- [Jira backlog CSV](lab-2-agile/Lab2_Jira_Backlog_Import.csv)
- [Evidence capture notes](lab-2-agile/evidence/README.md)

[Jira backlog](https://vario-pes.atlassian.net/jira/software/c/projects/FEP/boards/34/backlog) · [Sprint board](https://vario-pes.atlassian.net/jira/software/c/projects/FEP/boards/34)

The recorded simulation covers 9 stories and 57 story points across three closed sprints: Sprint 1 (18), Sprint 2 (23), Sprint 3 (16). Sprint 2 and Sprint 3 reports identify their stories as completed outside the sprint because the completion timestamps precede their planned start dates. This discrepancy is disclosed in the Lab 2 report.

**Handout limitation:** The official Lab 2 handout was not available when this work was prepared. The deliverable follows the lab title and the supplied peer example's visible Jira activities; confirm any additional instructor-specific criteria.

## Lab 3 — Software Architecture & UML Component Modelling

- [Lab 3 folder](lab-3-architecture/)
- [Architecture justification source](lab-3-architecture/Lab3_Architecture_Justification.md)
- [Editable component diagram source](lab-3-architecture/source/Lab3_Component_Diagram_Source.dot)

The selected style is **Layered Architecture with modular business components**, after comparing Layered, Microservices, and Client-Server architectures. Components are logical modules, not separately deployed services.

## Submission status

The Lab 1 PDFs already present in this repository are retained. Lab 2 and Lab 3 Markdown sources, the backlog CSV, and editable DOT source have been added. The Lab 2 report PDF and both Lab 3 PDFs still need to be committed as binary files. Genuine Jira screenshots also need to be captured and added; no synthetic screenshots are used.

## Traceability and limitations

- Labs 2 and 3 retain the Lab 1 requirement identifiers FR-001–FR-005 and NFR-001–NFR-002.
- Story-point values are planning estimates, not measured implementation effort.
- Jira issue status is workflow evidence only; it does not establish feature implementation.
- The five-second watermark target needs a defined asset size, hardware, concurrency, and timing method before it can be treated as a reproducible performance result.

## License

See [LICENSE](LICENSE).
