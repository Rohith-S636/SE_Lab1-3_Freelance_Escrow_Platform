# Lab 3 — Architecture Selection and Justification

**System:** Freelance Content Creator Escrow Platform  
**Problem statement:** #53

## Selected architecture

**Layered Architecture with modular business components.**

The platform coordinates milestone definition, creator draft submission, watermarking, sponsor review, payment release, and dispute handling. These activities share business state and require controlled transaction boundaries. A layered design provides clear responsibility separation without the operational cost of independently deploying and coordinating many services.

## Comparison of required architectural styles

| Style | Advantages | Limitations for this system |
|---|---|---|
| Layered | Separates presentation, business rules, and persistence/integration; supports maintainability, testability, and transaction coordination. | Cross-layer calls can add overhead; independent scaling is less granular. |
| Microservices | Independent deployment and scaling of contract, watermark, review, payment, and dispute capabilities. | Adds service discovery, network latency, distributed transactions/consistency, observability, and deployment overhead. |
| Client-Server | Centralizes business logic and data; straightforward interaction model and access control. | Central server can become a bottleneck and availability concentration point; internal responsibilities can become tightly coupled without additional modular structure. |

For the current academic-scale scope, Layered Architecture offers the best balance of clarity, coordinated escrow transactions, maintainability, and implementation simplicity.

## Two primary reasons

1. **Workflow cohesion:** Contract definition, review, approval, payment release, and dispute resolution are tightly related steps. Separating presentation, application/business logic, and data/integration responsibilities makes the workflow easier to reason about and test.
2. **Proportionate complexity:** The platform does not currently require independent deployment of each business capability. Modular components within layers preserve separation of concerns without introducing microservice orchestration and distributed consistency problems.

## Security advantage

The application/business layer mediates escrow operations. The user interface cannot directly change wallet balances. The escrow capability checks sponsor approval before release, freezes funds when a qualifying dispute is raised after two rejections, and records lock/release/refund events in an append-only audit log. Escrow wallet data is encrypted, aligning with NFR-002.

## Performance benefit

Watermark processing is isolated as a business capability. Its image/video preview path can be optimized and measured against NFR-001's five-second target without changing contract, review, or payment logic. A valid performance claim still requires a defined workload, hardware, concurrency, and timing method.

## Component view

The accompanying component model identifies the User Interface, Application/API Facade, Milestone Contract, Deliverable & Watermark, Review & Revision, Escrow & Payment, Dispute Resolution, Platform Data Store, Append-only Audit Log, and External Payment Gateway.

These are logical components within one layered architecture. They are **not** asserted to be separately deployed microservices.

## UML interface notation check

The diagram legend identifies provided interfaces (lollipop/ball) and required interfaces (socket). Before final submission, inspect the exported diagram at normal zoom and ensure at least four interfaces are visibly connected to the appropriate component boundaries. If the instructor expects exact UML port-level ball/socket notation, refine the diagram in a UML-capable editor before submission.
