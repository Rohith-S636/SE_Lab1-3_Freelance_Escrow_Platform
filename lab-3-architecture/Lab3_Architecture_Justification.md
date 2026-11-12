# Lab 3 — Architecture Selection and Justification

**Project:** Freelance Content Creator Escrow Platform  
**Problem statement:** #53  
**Selected architecture:** Layered Architecture with modular business components

## 1. Architecture comparison

| Architecture | Advantages | Limitations for this platform |
|---|---|---|
| Layered | Separates presentation, business rules, and data/integration concerns; supports maintainability, testing, and coordinated transaction workflows. | Cross-layer calls add some overhead; independent scaling is less granular. |
| Microservices | Business capabilities can be independently deployed and scaled. | Requires service discovery, network communication, distributed consistency/transactions, observability, and more deployment operations. |
| Client-Server | Centralizes business logic and data; simple interaction model and access control. | Can concentrate load and availability risk; internal modules can become tightly coupled without explicit boundaries. |

## 2. Selection and justification

Layered Architecture is the best fit for the current academic scope. The system has a cohesive workflow: parties define milestone terms, creators submit drafts, the platform watermarks previews, sponsors approve or request revisions, escrow is released only after approval, and disputes are escalated after two rejections. These operations share business state and need coordinated transaction boundaries.

Two primary reasons support the selection:

1. **Workflow cohesion and control.** The application/business layer can enforce approval gating, keep funds locked during revision, freeze escrow during a qualifying dispute, and coordinate audit events. The user interface does not directly manipulate wallet balances.
2. **Proportionate complexity.** The project does not currently require independently deployed services. Modular business components preserve separation of concerns without adding microservice orchestration and distributed consistency overhead.

## 3. Security and quality attributes

The Escrow & Payment component checks for recorded sponsor approval/sign-off before initiating release. A rejection with written comments returns the milestone to Pending Revision while funds remain locked. After two rejections, the dispute workflow freezes escrow and routes the case to a neutral Escrow Moderator. Escrow wallet data is encrypted, and lock/release/refund events are retained in an append-only audit log with timestamp, actor ID, milestone ID, and transaction reference (NFR-002).

Watermarking is isolated in the Deliverable & Watermark component. This creates a clear performance boundary for NFR-001, which requires image/video preview watermarking within five seconds. This is a target, not a measured result: validation requires defined asset sizes, hardware, concurrency, and timing methodology.

## 4. Component model

The component diagram contains ten logical components across three layers:

- **Presentation:** User Interface; Application/API Facade.
- **Application / Business:** Milestone Contract; Deliverable & Watermark; Review & Revision; Escrow & Payment; Dispute Resolution.
- **Data & External Integration:** Platform Data Store; Append-only Audit Log; External Payment Gateway.

The diagram explicitly uses provided-interface lollipops and required-interface sockets, connected as named interface pairs. Examples include IApplicationAPI, IMilestoneContract, IWatermarkProcessing, IReviewWorkflow, IEscrowOperations, IPaymentGateway, and IAuditEvents. These are logical components within one layered system, not separately deployed microservices.

## 5. Requirement traceability

| Requirement | Architectural responsibility |
|---|---|
| FR-001 | Review & Revision records sponsor approval; Escrow & Payment gates release on that approval. |
| FR-002 | Milestone Contract stores jointly agreed description, due date, and escrow amount. |
| FR-003 | Deliverable & Watermark processes image/video drafts before sponsor preview. |
| FR-004 | Review & Revision records written rejection comments, Pending Revision state, and creator notification. |
| FR-005 | Dispute Resolution supports escalation after two rejections; Escrow & Payment freezes the funds. |
| NFR-001 | Deliverable & Watermark provides an isolated path for measuring the five-second target. |
| NFR-002 | Escrow & Payment, Platform Data Store, and Append-only Audit Log support encryption and traceable financial events. |

## 6. Conclusion

Layered Architecture with modular business components provides a maintainable and testable structure while keeping escrow, approval, and dispute rules under clear application-level control. It meets the current design scope with less operational complexity than a microservices architecture. The diagram and justification describe a proposed design; they do not claim that the platform has been implemented or deployed.
