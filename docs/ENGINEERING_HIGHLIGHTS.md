# Engineering Highlights

## 1. Single Matching Authority

A common failure mode in financial software is allowing multiple components to independently decide what a "match" means.

InvoMatch establishes one authoritative production decision engine. Other layers consume its persisted result rather than implementing competing business logic.

## 2. Explainability Is Part of the Data Model

A status such as `review_required` is insufficient on its own.

The system persists decision evidence, candidate context, and policy provenance so a user can inspect why the decision exists.

## 3. Ambiguity Is Preserved

When several invoices are plausible candidates, the system does not hide uncertainty behind an arbitrary automatic choice.

Candidate ordering and ambiguity handling are deterministic.

## 4. Human Correction Does Not Replace Machine Evidence

Human workflow is designed as a governed transition.

Authorized correction changes business state while preserving the original machine evidence and policy context for traceability.

## 5. Tenant Isolation Is Tested, Not Assumed

Tenant context is propagated into run ownership and retrieval boundaries.

Regression testing explicitly covers cross-tenant access denial, including export retrieval.

## 6. Recovery Is Part of Readiness

Backup, restore, restart persistence, and runtime smoke behavior are part of validation rather than deferred operational tasks.

## 7. Policy Evolution Is Versioned

Financial rule changes can alter outcomes. InvoMatch therefore treats policy version as provenance, allowing decisions to remain attributable to the rules that produced them.

## 8. Validation Depth

Recent private-repository validation has included:

- 800+ backend tests,
- focused financial-policy suites,
- frontend tests and production builds,
- linting and static typing,
- runtime/container smoke checks,
- restart persistence,
- backup/restore,
- tenant-isolation regression tests.

These numbers are included as engineering context, not as a substitute for system design quality.
