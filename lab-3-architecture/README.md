# Lab 3 — Architecture Selection and UML Component Modelling

**System:** Freelance Content Creator Escrow Platform  
**Problem statement:** #53

## Deliverables

- [Architecture justification (one-page PDF)](Lab3_Architecture_Justification_One_Page.pdf)
- [UML component diagram (PDF)](Lab3_UML_Component_Diagram.pdf)
- [Editable Graphviz source](Lab3_Component_Diagram_Source.dot)
- [Architecture justification source](Lab3_Architecture_Justification.md)

Regenerate and visually inspect the PDF exports after source changes. The source files are authoritative.

## Selected architecture

**Layered Architecture with modular business components.** Presentation, application/business, and data/external-integration responsibilities are separated. Business capabilities remain logical modules in one application; this is not a claim that they are independently deployed microservices.

## Comparison

| Architecture | Advantages | Limitations for this system |
|---|---|---|
| Layered | Clear separation of concerns; supports testing, maintainability, and coordinated escrow transactions. | Cross-layer calls can add overhead; scaling is less granular. |
| Microservices | Independent deployment and scaling of capabilities. | Adds service discovery, network latency, distributed consistency/transactions, observability, and deployment overhead. |
| Client-Server | Centralized business logic and data; simple interaction model. | Can concentrate availability and load; internal responsibilities may become tightly coupled without modular structure. |

## Component model and interface notation

The diagram contains ten logical components: User Interface, Application/API Facade, Milestone Contract, Deliverable & Watermark, Review & Revision, Escrow & Payment, Dispute Resolution, Platform Data Store, Append-only Audit Log, and External Payment Gateway.

The revised DOT source depicts provided interfaces as lollipop (ball) symbols and required interfaces as socket symbols, joined as named interface pairs. Seven interface pairs are shown:

| Interface | Provider | Consumer |
|---|---|---|
| IApplicationAPI | User Interface | Application/API Facade |
| IMilestoneContract | Milestone Contract | Application/API Facade |
| IWatermarkProcessing | Deliverable & Watermark | Application/API Facade |
| IReviewWorkflow | Review & Revision | Application/API Facade |
| IEscrowOperations | Escrow & Payment | Application/API Facade |
| IPaymentGateway | External Payment Gateway | Escrow & Payment |
| IAuditEvents | Append-only Audit Log | Escrow & Payment and Review & Revision |

The DOT socket is represented by a half-circle glyph. Inspect the rendered PDF at normal viewing size; if the selected font does not render the glyph clearly, replace it with the native required-interface symbol in a UML editor.

## Requirement traceability

- FR-001: Review & Revision and Escrow & Payment; release is gated by sponsor approval/sign-off.
- FR-002: Milestone Contract.
- FR-003 and NFR-001: Deliverable & Watermark.
- FR-004: Review & Revision.
- FR-005: Dispute Resolution, including fund freeze after two rejections.
- NFR-002: Escrow & Payment, Platform Data Store, and Append-only Audit Log.

## Limitations and validation

The five-second watermark target (NFR-001) is a requirement, not a measured result. A performance claim requires a defined image/video workload, hardware, concurrency, and timing method. The diagram is a design artifact; it does not prove implementation or deployment.

See the repository [LICENSE](../LICENSE).
