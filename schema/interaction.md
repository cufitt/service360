# Interaction Entity

The **Interaction** entity represents a single **service touchpoint** between a credit union and a member.

Interactions capture *what happened* during member engagement—without duplicating or replacing core Dynamics 365 activity records.

---

## Why an Interaction Entity?

While Dynamics 365 provides Activities (Phone Call, Email, Task), credit unions often need:
- A **unified, CU-specific service history**
- A lightweight record of meaningful service events
- A way to tag interactions with service context (share, loan, household)

Service360 introduces Interaction as a **service abstraction layer**—not a replacement for native activities.

---

## Entity Purpose

The Interaction entity enables agents and supervisors to:
- View a consolidated service timeline
- Understand interaction context at a glance
- Correlate service events with cases, shares, and loans
- Support analytics and future AI scenarios

Interaction is **contextual**, not operational.

---

## Core Attributes (Phase 1)

| Field Name | Type | Description |
|----------|------|-------------|
| Interaction ID | Text | Unique interaction identifier |
| Interaction Type | Choice | Call, Email, Chat, Branch Visit |
| Interaction Date | DateTime | When the interaction occurred |
| Member | Lookup | Member involved |
| Related Case | Lookup | Associated service case |
| Related Share | Lookup | Related share (if applicable) |
| Related Loan | Lookup | Related loan (if applicable) |
| Channel | Choice | Phone, Digital, In-Person |
| Summary | Text | Short interaction summary |
| Agent | Lookup | Agent handling the interaction |
| Resolution Indicator | Choice | Resolved, Follow-up Required |

---

## Relationships

| Related Entity | Relationship | Purpose |
|---------------|--------------|---------|
| Member | N:1 | Member involved |
| Case | N:1 | Associated case |
| Share | N:1 | Financial context |
| Loan | N:1 | Financial context |
| Agent (User) | N:1 | Service owner |

---

## Security & Compliance Considerations

- Interactions do **not** store sensitive financial data
- No recordings or message content stored in Phase 1
- Dataverse security governs access and auditing
- Designed for GLBA-aligned service usage

---

## Design Principles

- **Service-focused**: Captures meaningful engagement
- **Lightweight**: Avoids duplication of activity data
- **Extensible**: Supports analytics and AI summaries
- **Non-invasive**: Coexists with native D365 activities

---

## Example Service Scenarios

- Member calls regarding loan payment due date  
- Interaction logged with related loan and case  
- Supervisor reviews service timeline for quality  
- No need to search across multiple activity types

---

## Future Extensions (Out of Scope – Phase 1)

- Automatic activity-to-interaction mapping
- Copilot-generated interaction summaries
- Sentiment indicators
- Omnichannel session linking

These are intentionally excluded from Phase 1.

---

## Status

✅ **Defined – Phase 1**

This entity completes the Service360 service interaction model.

---
A CUFitt Service360 schema artifact
