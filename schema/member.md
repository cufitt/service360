# Member Entity

The **Member** entity is the foundational object in **CUFitt Service360**.  
It represents a credit union *member* — not a generic CRM contact or account.

This distinction is intentional and critical.

---

## Why a Dedicated Member Entity?

In Dynamics 365, the standard **Contact** entity is insufficient for credit unions because it does not natively represent:

- Membership status and lifecycle
- Household relationships
- Share and loan ownership
- Service-relevant financial signals

Service360 introduces **Member** as a first-class entity to anchor all service interactions in a credit-union-native model.

---

## Entity Purpose

The Member entity enables frontline agents to:
- Identify the member instantly
- Understand their relationship with the credit union
- See service-relevant context without navigating external systems
- Resolve issues faster and with confidence

The Member entity is **service-focused**, not transactional.

---

## Core Attributes (Phase 1)

| Field Name | Type | Description |
|----------|------|-------------|
| Member ID | Text | Unique member identifier (from core system) |
| Full Name | Text | Display name of the member |
| Membership Status | Choice | Active, Dormant, Closed |
| Membership Start Date | Date | Date membership was established |
| Primary Household | Lookup | Primary household relationship |
| Preferred Contact Method | Choice | Phone, Email, Secure Message |
| Service Tier | Choice | Standard, Premium, High-Value |
| Risk Flag (Service) | Yes/No | Indicates service sensitivity |
| Last Core Sync Date | DateTime | Last data refresh timestamp |

---

## Relationships

| Related Entity | Relationship | Purpose |
|---------------|--------------|---------|
| Household | N:1 | Group members by household |
| Share | 1:N | Deposit/share accounts owned |
| Loan | 1:N | Loans associated with the member |
| Case | 1:N | Customer service cases |
| Interaction | 1:N | Service touchpoints and history |

---

## Security & Compliance Considerations

- Member data is **read-only by default** in Phase 1
- Field-level security can be applied to sensitive attributes
- All data resides within **Microsoft Dataverse**
- No financial transactions are performed by this entity

Audit, logging, and compliance controls remain under Microsoft’s platform governance.

---

## Design Principles

The Member entity follows these principles:
- **Service-first**: Optimized for agent workflows
- **Minimal but meaningful**: No unnecessary fields
- **Composable**: Extensible without breaking changes
- **Non-invasive**: Does not replace core systems

---

## Example Service Scenarios

- Member calls regarding a dividend discrepancy  
- Agent immediately sees membership status, service tier, and household context  
- Related shares and loans are visible without system hopping  
- Case resolution time is reduced

---

## Future
