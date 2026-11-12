# Lab 3 — Software Architecture & UML Component Modelling

**Scenario:** Freelance Content Creator Escrow Platform (Problem Statement #53)

## Deliverables and sources

- [Architecture justification (Markdown source)](Lab3_Architecture_Justification.md)
- [Editable Graphviz DOT component diagram source](source/Lab3_Component_Diagram_Source.dot)

The previously prepared component-diagram PDF and one-page justification PDF are available as local submission assets but their binary files have not yet been committed to this repository. Export the updated justification source to PDF and add both PDFs before final submission.

## Architecture selection

**Layered Architecture with modular business components.**

The justification explicitly compares Layered, Microservices, and Client-Server architectures and selects Layered for the current academic-scale scope and tightly coordinated escrow workflow.

## Components

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

The components are logical modules within one layered architecture, not separately deployed microservices.

## Handout alignment

- [x] Compare Layered, Microservices, and Client-Server.
- [x] Select and justify one of the required styles.
- [x] Model at least five components.
- [x] Describe provided and required interface notation.
- [ ] Confirm that at least four UML provided/required interfaces are clearly drawn and connected in the exported PDF.
- [ ] Add the component diagram PDF and one-page justification PDF to this repository.

Before submission, inspect the diagram at normal zoom. If exact UML lollipop/socket notation on component ports is expected, refine the diagram in a UML-capable editor.
