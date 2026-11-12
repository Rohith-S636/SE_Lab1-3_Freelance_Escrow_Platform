# Lab 2 — Agile Backlog and Sprint Simulation

**Project:** Freelance Content Creator Escrow Platform  
**Problem statement:** #53  
**Jira project:** FEP —[Backlog](https://vario-pes.atlassian.net/jira/software/c/projects/FEP/boards/34/backlog) · [Board](https://vario-pes.atlassian.net/jira/software/c/projects/FEP/boards/34) · [Completed Sprint Report](https://vario-pes.atlassian.net/jira/software/c/projects/FEP/boards/34/reports/sprint-retrospective?sprint=106) · [Epic Report](https://vario-pes.atlassian.net/jira/software/c/projects/FEP/boards/34/reports/epic-report) 

## Objective

Organize the Lab 1 requirements into an Epic and traceable user stories, estimate the work, allocate it across three sprints, and demonstrate the Jira Scrum workflow.

## Jira structure

- Epic: **FEP-1 — Freelance Content Creator Escrow Platform – Secure Milestone Delivery and Payment**
- User stories: **FEP-2 through FEP-10**
- Workflow: To Do → In Progress → Done
- Estimation: Story Points

## Backlog and allocation

| Issue | User story | Requirement | Priority | Points | Sprint |
|---|---|---|---|---:|---|
| FEP-2 | Define milestone contract with sponsor | FR-002 | Highest | 5 | Sprint 1 |
| FEP-3 | Submit draft deliverable for review | FR-001 | Highest | 5 | Sprint 1 |
| FEP-4 | Automatically watermark image/video drafts | FR-003, NFR-001 | Highest | 8 | Sprint 1 |
| FEP-5 | Review and approve submitted draft | FR-001 | Highest | 5 | Sprint 2 |
| FEP-6 | Reject draft with written revision comments | FR-004 | High | 5 | Sprint 2 |
| FEP-7 | Release escrow payment after sponsor approval | FR-001 | Highest | 8 | Sprint 2 |
| FEP-8 | Process escrow payment transaction | Supporting workflow | High | 5 | Sprint 2 |
| FEP-9 | Raise dispute after two rejections | FR-005 | High | 8 | Sprint 3 |
| FEP-10 | Maintain encrypted escrow data and append-only audit events | NFR-002 | Highest | 8 | Sprint 3 |
| | **Total** | | | **57** | |

## Sprint goals and recorded results

| Sprint | Goal | Planned points | Recorded outcome |
|---|---|---:|---|
| Sprint 1 | Define milestone terms and enable protected draft submission and preview | 18 | Closed; 3/3 stories Done |
| Sprint 2 | Complete sponsor review, revision, and approval-gated payment workflow | 23 | Closed; 4/4 stories Done |
| Sprint 3 | Demonstrate dispute handling and financial traceability backlog completion | 16 | Closed; 2/2 stories Done |
| **Total** | | **57** | **9/9 stories recorded Done** |

## Sprint date and report qualification

The sprints were executed as a compressed academic Jira simulation on **12 November 2026**. The planned Jira date windows were:

- Sprint 1: 12–19 November 2026
- Sprint 2: 19–26 November 2026
- Sprint 3: 26 November–3 December 2026

Jira records Sprint 1 stories as completed issues. Sprint 2 and Sprint 3 stories appear under **Issues completed outside this sprint**, because their completion timestamps on 12 November precede their planned start dates. The sprint records and actual completion history have been preserved; this report does not disguise that discrepancy.

## Interpretation and limitations

1. The Done statuses are evidence of Jira workflow simulation only. They do **not** prove that any platform feature was implemented, tested, or deployed.
2. The 57 story points are classroom planning estimates, not measured engineering effort or team velocity.
3. The official Lab 2 handout was not supplied. The exercise follows the lab title and the peer example's visible Jira activities; additional instructor-specific criteria may apply.
4. NFR-001 needs a reproducible workload definition (asset sizes, hardware, concurrency, and timing method) before the five-second target can be validated as a performance result.

## Definition of Done proposed for implementation work

A story should only be considered implemented when its acceptance criteria are demonstrated, requirement traceability is retained, relevant test/demo evidence is attached, and unresolved blockers are addressed. Jira simulation status alone is not implementation evidence.
