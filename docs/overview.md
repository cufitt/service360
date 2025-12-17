# CUFitt Service360 – Overview

CUFitt Service360 is an open-source service acceleration layer for **Microsoft Dynamics 365 Customer Service**, purpose-built for the unique operational and regulatory realities of **credit unions**.

It provides a credit-union-native data model that enables frontline agents to see a true **360-degree member view** within Dynamics—without replacing or competing with core banking systems.

---

## The Problem We’re Solving

Dynamics 365 Customer Service is a powerful platform, but out of the box it is **industry-agnostic**.

For credit unions, this creates friction:
- Generic Contact and Account entities do not represent *members*, *shares*, or *households*
- Key service signals (dividend disputes, overdraft patterns, loan-to-share relationships) live outside the agent workspace
- Agents are forced to swivel between systems during live calls

The result:
- Higher average handle time (AHT)
- Frustrated members
- Missed retention and relationship opportunities

---

## What Service360 Is

Service360 is a **Dataverse extension**, not a core replacement.

It introduces:
- Credit-union-specific entities and relationships
- Service-focused views of member financial context
- A clean foundation for analytics, Copilot, and automation

All while staying fully within the Microsoft ecosystem.

---

## What Service360 Is NOT

To be explicit, Service360 does **not**:
- Replace core banking systems
- Perform financial transactions
- Ingest live core data (Phase 1)
- Provide bots, Copilot agents, or fraud detection

Those capabilities may come later as optional extensions—but they are intentionally out of scope today.

---

## Architecture at a Glance

- **Platform:** Microsoft Dataverse
- **Application:** Dynamics 365 Customer Service
- **Data Model:** Credit-union-native entities and relationships
- **Integration:** Read-only by default (Phase 1)
- **Licensing:** MIT (open-core)

Microsoft remains the system of record for security, compliance, and auditability.

---

## Who This Is For

- Credit union service agents and supervisors
- CU IT and Dynamics 365 administrators
- Microsoft partners supporting credit unions
- CUSOs and CU-focused solution builders

---

## Why Open Source

Service360 follows an **open-core model**:
- The data model is free, transparent, and community-driven
- CUFitt acts as the steward and core maintainer
- Paid services (future) focus on integrations, automation, and enterprise hardening—not gating access to the core

This approach lowers adoption friction while preserving long-term sustainability.

---

## Project Status

🚧 **Early development**

The initial focus is:
- Schema design
- Documentation
- Community feedback
- Real-world validation

Breaking changes are expected early and will be clearly versioned.

---

## Governance

Service360 is governed by a **core maintainer model** led by CUFitt:
- Open pull requests
- Transparent roadmap
- Versioned releases
- Clear decision ownership

---

## What’s Next

Immediate next steps:
- Publish initial entity definitions (Member, Share, Loan, Household)
- Add schema diagrams
- Launch a public demo environment

Feedback and contributions are welcome.

---
A CUFitt project | https://cufitt.com
