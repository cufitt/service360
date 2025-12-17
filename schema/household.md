# Household Entity

The **Household** entity represents a group of related members who share financial relationships, service context, or ownership structures within a credit union.

Householding is a **core credit union concept** and a critical missing layer in standard CRM models.

---

## Why Household Matters

In real credit union operations:
- Shares and loans are frequently joint-owned
- Service decisions often impact multiple members
- High-value relationships are evaluated at the household level, not the individual

Standard CRM models force agents to infer these relationships manually.  
Service360 makes them explicit.

---

## Entity Purpose

The Household entity enables agents to:
- View all related members in one place
- Understand shared financial exposure
- Resolve service issues holistically
- Avoid fragmented or conflicting member interactions

Household is a **contextual entity**, not a billing or transactional construct.

---

## Core Attributes (Phase 1)

| Field Name | Type | Description |
|----------|------|-------------|
| Household ID | Text | Unique household identifier |
| Household Name | Text | Display name (e.g., "Smith Household") |
| Primary Member | Lookup | Designated primary contact |
| Household Type | Choice | Individual, Joint, Family |
| Relationship Start Date | Date | When household was established |
| Total Members | Number | Count of associated members |
| Service Tier | Choice | Derived or assigned service tier |
| Notes | Text | Service-relevant notes |

---

## Relationships

| Related Entity | Relationship | Purpose |
|---------------|--------------|---------|
| Member | 1:N | Members belonging to household |
| Share | 1:N | Jointly owned share accounts |
| Loan | 1:N | Jointly owned loans |
| Case | 1:N | Household-level service cases |

---

## Security & Compliance Considerations

- Household does **not** store financial balances
- Sensitive attributes remain on related entities
- Visibility can be restricted by service role
- All data remains within Microsoft Dataverse security boundaries

---

## Design Principles

- **Relationship-first**: Models real CU relationships
- **Service-aware**: Optimized for support workflows
- **Non-transactional**: No financial posting or updates
- **Extensible**: Supports future analytics and Copilot scenarios

---

## Example Service Scenarios

- Joint account holder calls regarding overdraft activity  
- Agent sees all household members and related shares  
- Prevents duplicate or conflicting responses  
- Improves service consistency and trust

---

## Future Extensions (Out of Scope – Phase 1)

- Household risk scoring
- Cross-member behavioral insights
- Advanced relationship hierarchies
- Marketing or sales automation logic

These are intentionally excluded from Phase 1.

---

## Status

✅ **Defined – Phase 1**

This entity is stable but open to feedback.

---
A CUFitt Service360 schema artifact
