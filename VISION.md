# Outcome CRM Vision

## Mission Statement

**Outcome CRM** is a consulting-focused customer relationship management platform designed specifically for professional services firms. Built on the foundation of [Twenty CRM](https://github.com/twentyhq/twenty), Outcome CRM extends the core CRM capabilities with deep industry-specific functionality for consulting, advisory, and managed services organizations.

## The Problem We Solve

Professional services firms face unique challenges that generic CRMs don't address:

- **Complex Sales Cycles**: Multi-stage qualification, stakeholder mapping, and long pursuit timelines
- **Revenue Recognition**: Time & materials, fixed-fee, milestone-based, and subscription billing models
- **Resource Management**: Matching consultant skills to project requirements
- **Engagement Lifecycle**: Seamless handoff from sales to delivery with revenue planning
- **Client Relationships**: Deep stakeholder relationships across multiple accounts over years

## Target Users

### Primary Personas

| Persona | Role | Key Jobs-to-be-Done |
|---------|------|---------------------|
| **BU Head** | Business Unit Leader | Pipeline visibility, revenue forecasting, team performance |
| **Account Executive** | Sales Lead | Deal management, stakeholder mapping, proposal development |
| **Engagement Manager** | Delivery Lead | Engagement planning, resource allocation, revenue tracking |
| **Executive** | C-Suite / Partner | Strategic accounts, cross-BU visibility, board reporting |
| **Delivery Manager** | PMO / Resourcing | Skill matching, utilization, capacity planning |

### Secondary Personas

- **Business Development**: Lead qualification, market research, prospecting
- **Support Manager**: Ticket management, client satisfaction, NPS tracking
- **Marketing**: Campaign management, lead nurturing, content effectiveness

## Core Differentiators

### 1. Consulting-Native Data Model
- **Account Tiers**: PLATINUM, GOLD, SILVER, BRONZE, GROWTH, TRANSACTIONAL
- **Account Stages**: PROSPECT → ACTIVE_PURSUIT → NEW_CLIENT → ACTIVE_CLIENT → AT_RISK → DORMANT → CHURNED → REACTIVATED
- **Stakeholder Management**: Role, influence, decision-making power, relationship strength

### 2. Professional Services Automation (PSA)
- Project management with budget vs actual tracking
- Resource allocation with skill matching
- Time entry and utilization dashboards
- Health status monitoring (GREEN/YELLOW/RED)

### 3. 10-Stage Sales Pipeline
Purpose-built for consulting sales cycles:
1. IDENTIFIED (10%)
2. SCOPED (20%)
3. QUALIFIED (30%)
4. PROPOSAL_REQUESTED (40%)
5. PROPOSAL_SUBMITTED (50%)
6. SHORTLISTED (60%)
7. ORAL_PRESENTATION (70%)
8. COMMERCIAL_NEGOTIATION (80%)
9. CLOSED_WON (100%)
10. CLOSED_LOST (0%)

### 4. Revenue Planning
- Engagement-level monthly revenue plans
- Recognition rules based on engagement status
- Integration with ERP (NetSuite) for billing and rev rec

### 5. AI-Powered Intelligence
- GraphRAG for relationship insights and warm introductions
- Deal win probability analysis
- Account health scoring
- Natural language querying

### 6. Agentic Workflows
21 pre-built workflow types for automation:
- Lead qualification and enrichment
- Document generation (SOW, contracts)
- Risk detection and next-step recommendations
- Meeting scheduling and follow-ups

## Guiding Principles

1. **Consulting-First**: Every feature designed with professional services in mind
2. **Data Ownership**: Open-source core with full data portability
3. **Integration-Ready**: First-class connectors for NetSuite, HubSpot, O365, Teams
4. **AI-Augmented**: Intelligence embedded throughout, not bolted on
5. **User-Centric**: Role-based experiences optimized for each persona

## Relationship with Twenty CRM

Outcome CRM is built as a fork of [Twenty CRM](https://twenty.com), an open-source CRM platform. We:

- **Maintain compatibility** with Twenty's core architecture and updates
- **Extend** with consulting-specific modules (PSA, Engagements, Contracts)
- **Customize** the data model for professional services use cases
- **Contribute back** generalizable improvements to the upstream project

## Milestones

| Milestone | Focus | Status |
|-----------|-------|--------|
| **v2.0-Core-CRM** | Accounts, Contacts, Leads, Deals, Contracts, Engagements, Analytics | 🔄 Active |
| **v2.1-PSA** | Projects, Resources, Time Tracking, Deliverables | 📋 Planned |
| **v2.2-AI-Agentic** | GraphRAG, LLM Gateway, Workflow Automation | 📋 Planned |
| **v2.3-Support-Comms** | Tickets, Communications, Email/Calendar Integration | 📋 Planned |

---

*Outcome CRM - Relationships that deliver results.*
