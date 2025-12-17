# Loan Entity

The **Loan** entity represents a credit union **lending relationship** associated with one or more members or households.

Service360 models Loan as a **service-facing entity**, enabling agents to understand loan context and resolve member inquiries without performing financial transactions.

---

## Why a Loan Entity?

Loan servicing is one of the most frequent and sensitive service interactions in a credit union.

Agents need quick visibility into:
- Loan type and status
- Ownership and co-borrower relationships
- Payment context and lifecycle stage

Standard CRM entities do not model these concepts effectively.  
Service360 introduces Loan as a **credit-union-native abstraction**.

---

## Entity Purpose

The Loan entity enables agents to:
- Identify active and historical loans for a member or household
- Understand loan structure without accessing the core system
- Respond confidently to payoff, payment, or status inquiries
- Route complex issues appropriately

Loan is **informational and contextual**, not operational.

---

## Core Attributes (Phase 1)

| Field Name | Type | Description |
|----------|------|-------------|
| Loan ID | Text | Unique loan identifier from core system |
| Loan Type | Choice | Auto, Mortgage, Personal, Credit Card, HELOC |
| Loan Status | Choice | Current, Delinquent, Charged-Off, Closed |
| Primary Borrower | Lookup | Primary member borrower |
| Co-Borrower(s) | Lookup (Multi) | Joint borrowers |
| Origination Date | Date | Loan start date |
| Maturity Date | Date | Loan end date |
| Interest Rate (Display) | Decimal | Read-only interest rate |
| Payment Amount (Display) | Currency | Read-only scheduled payment |
| Next Due Date | Date | Next payment due |
| Last Payment Date | Date | Last payment posted |
| Last Core Sync Date | DateTime | Last data refresh timestamp |

---

## Relationships

| Related Entity | Relationship | Purpose |
|---------------|--------------|---------|
| Member | N:1 | Primary borrower |
| Household | N:1 | Household context |
| Case | 1:N | Loan-related service cases |
| Interaction | 1:N | Service interactions |

---

## Security & Compliance Considerations

- Loan data is **read-only** in Phase 1
- No payment posting or payoff calculations
- Sensitive fields can be masked by role
- All access governed by Dataverse audit and security controls

This aligns with CU service and compliance expectations.

---

## Design Principles

- **Service-first**: Built for inquiry and resolution
- **Non-invasive**: Does not alter loan systems
- **Contextual**: Focused on what agents need to know
- **Extensible**: Ready for future analytics and automation

---

## Example Service Scenarios

- Member calls to confirm next payment due date  
- Agent views loan status, payment amount, and due date  
- No core access required  
- Reduced call duration and error risk

---

## Future Extensions (Out of Scope – Phase 1)

- Payoff quote calculations
- Delinquency workflow automation
- Loan modification tracking
- Copilot-driven loan summaries

These are intentionally excluded from Phase 1.

---

## Status

✅ **Defined – Phase 1**

This entity is stable and open for community feedback.

---
A CUFitt Service360 schema artifact
