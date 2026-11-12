# Lab 3 — Software Architecture & UML Component Modelling

**Scenario:** Freelance Content Creator Escrow Platform (Problem Statement #53)

## Architecture selection

**Selected style: Layered Architecture with modular business components.**

The submission compares all three styles named in the Lab 3 handout:

- **Layered:** separates presentation, business rules, and data/integration concerns. It supports clear responsibility boundaries and straightforward transaction coordination; cross-layer calls can add overhead.
- **Microservices:** enables independent deployment and scaling, but introduces operational complexity, network latency, and distributed consistency concerns that are disproportionate to this academic-scale workflow.
- **Client-Server:** centralizes logic and data and is simple to reason about, but can create a server bottleneck and concentrates availability risk.

Layered Architecture is selected because the milestone contract, review, approval, escrow, and dispute workflows are closely coordinated and benefit from clear separation without requiring independently deployed services.

## Components represented

1. User Interface
2. Application/API Facade
3. Milestone Contract
4. Deliverable & Watermark
5. Review & Revision
6. Escrow & Payment
7. Dispute Resolution
8. Platform Data Store
9. Append-only Audit Log
10. External Payment Gateway

The diagram maps components to the Lab 1 requirement baseline. It is a logical component view within the selected layered architecture; it does not imply that each component is a separately deployed microservice.

## Deliverables

- [UML Component Diagram (PDF)](Lab3_UML_Component_Diagram.pdf)
- [One-page Architecture Justification (PDF)](Lab3_Architecture_Justification_One_Page.pdf)
- [Editable Graphviz DOT source](source/Lab3_Component_Diagram_Source.dot)

## Handout alignment checklist

- [x] Compare Layered, Microservices, and Client-Server.
- [x] Select and justify one of the required architecture styles.
- [x] Include at least five components.
- [x] Identify provided and required interface concepts in the diagram legend.
- [x] Provide a one-page architecture justification.

**Final visual check:** Before submission, inspect the PDF at normal zoom and confirm the UML provided-interface (lollipop) and required-interface (socket) notation is unambiguous and attached to the relevant component interfaces. If the instructor expects exact port-level ball/socket connectors, refine the diagram in a UML-capable editor before submitting.
