# Freelance Content Creator Escrow Platform

**Software Engineering Labs 1–3 | Problem Statement #53**

This repository contains requirements analysis, Agile workflow simulation, and architecture design for a freelance platform in which creators and sponsors agree milestone terms, review protected drafts, and release escrowed payments only after sponsor approval.

> **Academic scope:** Jira statuses document a classroom workflow simulation. They are not evidence that the platform has been implemented, tested, or deployed.

## Problem scope and requirements baseline

- Jointly define milestone deliverables, due dates, and escrow amounts.
- Submit creator drafts and automatically watermark image/video previews before sponsor access.
- Record sponsor approval or rejection with written revision comments.
- Release milestone payment only after sponsor approval/sign-off.
- After two rejections, allow either party to raise a dispute; freeze escrow and route it to a neutral Escrow Moderator.
- Encrypt escrow wallet data and maintain append-only financial audit events.

| ID | Requirement |
|---|---|
| FR-001 | Submit drafts for review; release locked milestone funds only after sponsor approval/sign-off. |
| FR-002 | Creator and sponsor jointly define deliverable description, due date, and escrow amount. |
| FR-003 | Automatically watermark every uploaded image/video draft before sponsor review. |
| FR-004 | Sponsor rejection requires written comments; milestone becomes Pending Revision, funds remain locked, and creator is notified. |
| FR-005 | Either party may raise a dispute after two rejections; freeze funds and route to a neutral moderator for recorded resolution. |
| NFR-001 | Watermark image/video previews within five seconds under a defined test workload. |
| NFR-002 | Encrypt escrow wallet data and maintain append-only lock/release/refund events with timestamp, actor ID, milestone ID, and transaction reference. |

## Lab 1 — Requirements Engineering & UML Use-Case Modelling

- [Original Problem Statement #53](problem-statement/53_SE_Lab1_SE_Problem_Statements.pdf)
- [Requirements Table](requirements/Requirements_Table.pdf)
- [UML Use-Case Diagram](diagrams/UseCase_Diagram.pdf)
- [Use-Case Flow Specification](use-case-flow/UseCase_Flow.pdf)

Use cases: UC-01 Define Milestone Contract; UC-02 Submit Draft Deliverable; UC-03 Apply Watermark; UC-04 Review & Approve Draft; UC-05 Request Revision; UC-06 Release Milestone Payment; UC-07 Process Payment Transaction; UC-08 Raise Dispute.

## Lab 2 — Agile Backlog Creation & Sprint Simulation

- [Lab 2 report (Markdown source)](lab-2-agile/Lab2_Agile_Backlog_and_Sprint_Simulation.md)
- [Lab 2 report (PDF)](lab-2-agile/Lab2_Agile_Backlog_and_Sprint_Simulation.pdf)
- [Jira backlog CSV](lab-2-agile/Lab2_Jira_Backlog_Import.csv)
- [Evidence capture instructions](lab-2-agile/evidence/README.md)
- [Jira backlog](https://vario-pes.atlassian.net/jira/software/c/projects/FEP/boards/34/backlog) · [Sprint board](https://vario-pes.atlassian.net/jira/software/c/projects/FEP/boards/34)

The simulation contains 9 stories and 57 story points across three closed sprints: Sprint 1 (18), Sprint 2 (23), Sprint 3 (16). Sprint 2 and Sprint 3 reports classify their stories as completed outside the sprint because completion timestamps precede their planned start dates. This discrepancy is disclosed rather than hidden.

## Lab 3 — Architecture Selection & UML Component Modelling

- [Lab 3 overview](lab-3-architecture/README.md)
- [Architecture justification (source)](lab-3-architecture/Lab3_Architecture_Justification.md)
- [Architecture justification (one-page PDF)](lab-3-architecture/Lab3_Architecture_Justification_One_Page.pdf)
- [UML component diagram (PDF)](lab-3-architecture/Lab3_UML_Component_Diagram.pdf)
- [Editable Graphviz source](lab-3-architecture/Lab3_Component_Diagram_Source.dot)

**Selected architecture:** Layered Architecture with modular business components, chosen after comparing Layered, Microservices, and Client-Server architectures. Components are logical modules, not separately deployed microservices.

## Final submission checklist

- [x] Lab 1 source PDFs present.
- [x] Lab 2 Jira backlog and sprint simulation report source present.
- [x] Lab 3 architecture justification and editable diagram source present.
- [ ] Regenerate and visually inspect the Lab 2 and Lab 3 PDFs from the latest sources.
- [ ] Add five genuine Jira screenshots listed in the evidence README.
- [ ] Confirm instructor-specific criteria against the official Lab 2 handout (not supplied during preparation).

## Important limitations

- Jira Done statuses are workflow-simulation evidence only; they do not prove feature implementation, testing, or deployment.
- The 57 story points are planning estimates, not measured effort or velocity.
- NFR-001 is a target, not a verified performance result. Validation requires defined asset sizes, hardware, concurrency, and timing method.
- The official Lab 2 handout was not available during preparation. Check for any additional instructor-specific criteria.

## License

See [LICENSE](LICENSE).
