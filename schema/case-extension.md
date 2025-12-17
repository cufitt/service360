# Case Entity Extension

CUFitt Service360 extends the standard **Dynamics 365 Customer Service Case (Incident)** entity to support **credit-union-specific service context**.

This extension enhances agent productivity while preserving full compatibility with native Dynamics workflows, SLAs, and reporting.

---

## Why Extend the Case Entity?

The Case entity is the **center of service operations** in Dynamics 365.

Out of the box, it lacks:
- Credit-union-native financial context
- Direct relationships to shares and loans
- Clear member and household visibility

Service360 augments—not replaces—the Case entity to fill these gaps.

---

## Extension Approach

Service360 follows these principles:
- **Extend, don’t customize core behavior**
- **Preserve Microsoft upgrade paths**
- **Avoid breaking changes**
- **Remain SLA- and workflow-safe**

All extensions are additive.

---

## Added Fields (Phase 1)

| Field Name | Type | Description |
|----------|------|-------------|
| Member | Lookup | Primary member associated with case |
| Household | Lookup | Related household context |
| Related Share | Lookup | Share involved in the issue |
| Related Loan | Lookup | Loan involved in the issue |
| Service Category | Choice | Share Inquiry, Loan Inquiry, Dispute, General Service |
| Service Sensitivity | Choice | Normal, High, Sensitive |
| Financial Context Flag | Yes/No | Indicates financial data relevance |
| Last Core Sync Date | DateTime | Last data refresh timestamp |

---

## Added Relationships

| Related Entity | Relationship | Purpose |
|---------------|--------------|---------|
| Member | N:1 | Case ownership context |
| Household | N:1 | Relationship context |
| Share | N:1 | Deposit context |
| Loan | N:1 | Lending context |
| Interaction | 1:N | Service interaction timeline |

---

## Agent Experience

With these extensions:
- Agents see **member, household, and financial context** in one view
- Case resolution becomes faster and more accurate
- Context switching across systems is reduced
- Supervisors gain better insight into service patterns

All within the standard Dynamics 365 Case UI.

---

## Security & Compliance Considerations

- No financial transactions are performed
- Sensitive fields can be protected via field-level security
- All data remains within Dataverse auditing and access controls
- Compatible with GLBA and NCUA-aligned service practices

---

## Design Principles

- **Non-invasive**: No core Case logic modified
- **Composable**: Works with SLAs, queues, routing rules
- **Future-ready**: Supports Copilot and analytics extensions
- **Reversible**: Can be removed without data loss

---

## Example Service Scenarios

- Member reports a disputed dividend posting  
- Agent opens Case with linked Share and Member  
- Interaction history visible in timeline  
- Resolution achieved without core access

---

## Future Extensions (Out of Scope – Phase 1)

- Automated case classification
- Copilot-assisted resolution suggestions
- Regulatory reporting enhancements
- Advanced service analytics

These are intentionally excluded from Phase 1.

---

## Status

✅ **Defined – Phase 1**

This extension completes the Service360 service execution model.

---
A CUFitt Service360 schema artifact
