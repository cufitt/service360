# Share Entity

The **Share** entity represents a credit union **deposit account** (commonly referred to as a “share”) associated with one or more members.

Unlike generic “Account” objects in CRM systems, Share is modeled specifically for **credit union service workflows**, not financial transaction processing.

---

## Why a Share Entity?

Credit unions do not think in terms of “bank accounts” — they think in **shares**.

Service agents frequently need visibility into:
- Share ownership and joint relationships
- Share type and status
- Service-relevant patterns (without performing transactions)

Service360 introduces Share as a **read-only, service-aware entity**.

---

## Entity Purpose

The Share entity enables agents to:
- Identify which shares are associated with a member or household
- Understand ownership structure (primary vs joint)
- Quickly answer balance-related or dividend questions (via surfaced data)
- Provide informed service without leaving Dynamics 365

Share is **informational**, not operational.

---

## Core Attributes (Phase 1)

| Field Name | Type | Description |
|----------|------|-------------|
| Share ID | Text | Unique share identifier from core system |
| Share Type | Choice | Savings, Checking, Money Market, Certificate |
| Share Status | Choice | Open, Restricted, Closed |
| Primary Owner | Lookup | Primary member owner |
| Ownership Type | Choice | Individual, Joint |
| Open Date | Date | Share open date |
| Last Activity Date | Date | Last recorded activity |
| Balance (Display) | Currency | Read-only displayed balance |
| Dividend Rate (Display) | Decimal | Read-only dividend rate |
| Dividend Frequency | Choice | Monthly, Quarterly, Annually |
| Last Core Sync Date | DateTime | Last data refresh timestamp |

---

## Relationships

| Related Entity | Relationship | Purpose |
|---------------|--------------|---------|
| Member | N:1 | Primary owner |
| Household | N:1 | Household context |
| Case | 1:N | Service cases related to share |
| Interaction | 1:N | Service touchpoints |

---

## Security & Compliance Considerations

- Share data is **read-only** in Phase 1
- No transaction posting or balance updates
- Field-level security can mask balances if required
- All data governed by Dataverse security and audit logging

This aligns with GLBA and NCUA expectations for service systems.

---

## Design Principles

- **Service-centric**: Optimized for inquiries and issue resolution
- **Non-transactional**: No financial operations performed
- **Transparent**: Clear ownership and status visibility
- **Composable**: Extensible for analytics and automation

---

## Example Service Scenarios

- Member calls about a dividend posting discrepancy  
- Agent sees share type, status, dividend rate, and last activity  
- Issue resolved without accessing the core system  
- Reduced handle time and improved member confidence

---

## Future Extensions (Out of Scope – Phase 1)

- Real-time balance refresh
- Reg D / Reg E rule indicators
- Share behavior analytics
- Automated dividend dispute workflows

These are intentionally excluded from Phase 1.

---

## Status

✅ **Defined – Phase 1**

This entity is stable and designed for incremental extension.

---
A CUFitt Service360 schema artifact
