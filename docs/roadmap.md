# Outcome CRM Roadmap

This document maps all product requirements to milestones and tracks implementation progress.

## Overview

| Milestone | Focus Area | Total Issues | Open | Closed |
|-----------|-----------|--------------|------|--------|
| [v2.0-Core-CRM](#v20-core-crm) | Core CRM functionality | 123 | 121 | 2 |
| [v2.1-PSA](#v21-psa) | Professional Services Automation | 18 | 18 | 0 |
| [v2.2-AI-Agentic](#v22-ai-agentic) | AI Intelligence & Workflow Automation | 28 | 28 | 0 |
| [v2.3-Support-Comms](#v23-support-comms) | Support & Communications | 20 | 20 | 0 |
| **Total** | | **189** | **187** | **2** |

---

## 🎯 MVP Focus: Opportunity Pipeline & Contacts

> [!IMPORTANT]
> **MVP Scope**: The initial release focuses on **Opportunity Pipeline** and **Contacts** modules. These are the critical path items for sales execution.

### MVP Priority 1: Opportunity Pipeline (20 issues)
The 10-stage sales pipeline is the core of the CRM:
- Stage progression with gating validation
- Stage history tracking with duration metrics
- Pipeline Kanban board and list views
- BU Pipeline views for leadership
- Win/loss analysis reporting

### MVP Priority 2: Contacts & Stakeholder Management (12 issues)
Stakeholder mapping is essential for enterprise sales:
- Contact entity with relationship fields
- Stakeholder role and influence tracking
- Org chart visualization
- Key stakeholder identification

### Data Foundation
- **475 Accounts** from CY25 Customer BU Revenue master list
- **469+ Deals** imported from HubSpot
- **100 Owner mappings** to CRM users

---

## v2.0-Core-CRM

The foundational milestone establishing all core CRM entities and workflows.

### Foundation (6 issues)

| Status | Title | Labels |
|--------|-------|--------|
| ✅ | [Foundation] Add VISION.md documenting Outcome CRM positioning and target users | `module:foundation`, `type:documentation` |
| ✅ | [Foundation] Update README.md to reflect Outcome CRM branding and consulting focus | `module:foundation`, `type:documentation` |
| ⬜ | [Foundation] Create docs/roadmap.md mapping PRD v2 modules to milestones | `module:foundation`, `type:documentation` |
| ⬜ | [Foundation] Create GitHub milestones (v2.0-Core-CRM, v2.1-PSA, v2.2-AI-Agentic, v2.3-Support-Comms) | `module:foundation`, `type:admin` |
| ⬜ | [Foundation] Define and document upstream sync strategy with Twenty | `module:foundation`, `type:strategy` |
| ⬜ | [Foundation] Create module labels (module:accounts, module:psa, module:ai, etc.) | `module:foundation`, `type:admin` |

### Strategy (2 issues)

| Status | Title | Labels |
|--------|-------|--------|
| ⬜ | [Strategy] Run vision & guardrails workshop with BU Heads | `module:strategy`, `type:workshop` |
| ⬜ | [Strategy] Create one-page Outcome CRM v2 Strategy document linking modules to KPIs | `module:strategy`, `type:documentation` |

### Accounts Module (15 issues)

| Status | Title | Description | Labels |
|--------|-------|-------------|--------|
| ⬜ | [Accounts] Define Account entity data model with core fields | Fields: name, legal_name, domain, website | `module:accounts`, `type:backend` |
| ⬜ | [Accounts] Add firmographics fields | Fields: industry, employee_size_range, annual_revenue_range, IT_spend | `module:accounts`, `type:backend` |
| ⬜ | [Accounts] Add sales ownership fields | Fields: originBU, currentBU, accountExecutive, deliveryLead, executiveSponsor | `module:accounts`, `type:backend` |
| ⬜ | [Accounts] Implement AccountStage enum | Values: PROSPECT, ACTIVE_PURSUIT, NEW_CLIENT, ACTIVE_CLIENT, AT_RISK, DORMANT, CHURNED, REACTIVATED | `module:accounts`, `type:backend` |
| ⬜ | [Accounts] Implement AccountTier enum | Values: PLATINUM, GOLD, SILVER, BRONZE, GROWTH, TRANSACTIONAL | `module:accounts`, `type:backend` |
| ⬜ | [Accounts] Add integration fields | Fields: hubspotId, netsuite_customer_id, netsuite_sync_status | `module:accounts`, `type:backend` |
| ⬜ | [Accounts] Implement account parent-child hierarchy | Field: parentAccountId | `module:accounts`, `type:backend` |
| ⬜ | [Accounts] Create account merge functionality with audit trail | Ensure history is preserved during merge | `module:accounts`, `type:feature` |
| ⬜ | [Accounts] Build account detail view with all v2 fields | Frontend implementation | `module:accounts`, `type:frontend` |
| ⬜ | [Accounts] Build account list view with filters | Filters: tier, stage, BU, industry | `module:accounts`, `type:frontend` |
| ⬜ | [Accounts] Create 'Strategic Accounts' saved view | Filter: PLATINUM/GOLD/SILVER/BRONZE tiers | `module:accounts`, `type:frontend` |
| ⬜ | [Accounts] Create 'Accounts without EM' alert view | Alert for missing Engagement Manager | `module:accounts`, `type:frontend` |
| ⬜ | [Accounts] Implement audit logging for account BU changes | Track BU assignment changes | `module:accounts`, `type:backend` |
| ⬜ | [Accounts] Implement audit logging for account EM changes | Track Engagement Manager changes | `module:accounts`, `type:backend` |

### Contacts Module (12 issues)

| Status | Title | Description | Labels |
|--------|-------|-------------|--------|
| ⬜ | [Contacts] Define Contact entity with core fields | Fields: name, email, phone, title, department, linkedinUrl | `module:contacts`, `type:backend` |
| ⬜ | [Contacts] Add relationship fields | Fields: role, influence, relationshipStrength, decisionMakingPower | `module:contacts`, `type:backend` |
| ⬜ | [Contacts] Implement ContactStage enum | Values: SUBSCRIBER, LEAD, LEADGENQUAL, SQL, OPPORTUNITY, CUSTOMER, EVANGELIST, INACTIVE | `module:contacts`, `type:backend` |
| ⬜ | [Contacts] Add org chart support | Field: reportsToId | `module:contacts`, `type:backend` |
| ⬜ | [Contacts] Define Stakeholder entity linking Contact to Account | Join table/entity definition | `module:contacts`, `type:backend` |
| ⬜ | [Contacts] Add stakeholder fields | Fields: stakeholder_role, hierarchy_level, decision_authority, relationship_status | `module:contacts`, `type:backend` |
| ⬜ | [Contacts] Add key stakeholder flag | Field: is_key_stakeholder | `module:contacts`, `type:backend` |
| ⬜ | [Contacts] Build contact detail view with org chart visualization | Frontend with visual hierarchy | `module:contacts`, `type:frontend` |
| ⬜ | [Contacts] Build contact list view with filters | Standard filtering capabilities | `module:contacts`, `type:frontend` |
| ⬜ | [Contacts] Create 'Stakeholders' related view on Account detail page | Show associated contacts on Account page | `module:contacts`, `type:frontend` |
| ⬜ | [Contacts] Create 'Key Stakeholders' view per account | Filtered view for key stakeholders | `module:contacts`, `type:frontend` |

### Leads Module (8 issues)

| Status | Title | Description | Labels |
|--------|-------|-------------|--------|
| ⬜ | [Leads] Define Lead entity with core fields | Fields: companyName, primaryContact, status, source | `module:leads`, `type:backend` |
| ⬜ | [Leads] Implement 4T qualification fields | Fields: qualTech, qualTeamSize, qualTiming, qualType | `module:leads`, `type:backend` |
| ⬜ | [Leads] Add qualificationScore calculation | Logic: 0-4 based on 4T criteria | `module:leads`, `type:backend` |
| ⬜ | [Leads] Implement lead status enum | Values: NEW, CONTACTED, QUALIFIED, CONVERTED, LOST | `module:leads`, `type:backend` |
| ⬜ | [Leads] Build lead conversion flow | Logic: 2 of 4T required to convert to Deal/Account | `module:leads`, `type:feature` |
| ⬜ | [Leads] Implement deal category selection during conversion | Options: NN (New New), ENN (Existing New New), EN (Existing New) | `module:leads`, `type:feature` |
| ⬜ | [Leads] Create lead list view with 4T scoring | Display score prominently | `module:leads`, `type:frontend` |
| ⬜ | [Leads] Build lead qualification UI | Interface for entering 4T data | `module:leads`, `type:frontend` |

### Deals/Opportunities Module (20 issues)

| Status | Title | Description | Labels |
|--------|-------|-------------|--------|
| ⬜ | [Deals] Define Opportunity entity with core fields | Fields: name, accountId, stage, value, probability | `module:opportunities`, `type:backend` |
| ⬜ | [Deals] Add commercial fields | Fields: expectedRevenue, expectedCloseDate, actualCloseDate | `module:opportunities`, `type:backend` |
| ⬜ | [Deals] Add consulting fields | Fields: dealType, serviceType, engagementType, serviceLineId, practiceAreaId, lobId | `module:opportunities`, `type:backend` |
| ⬜ | [Deals] Implement 10-stage sales pipeline | Stages: 01-IDENTIFIED to 09-CLOSED_WON plus CLOSED_LOST | `module:opportunities`, `type:backend` |
| ⬜ | [Deals] Map probability to each stage | Range: 10% to 100% | `module:opportunities`, `type:backend` |
| ⬜ | [Deals] Define required fields per stage | Validation rules per stage | `module:opportunities`, `type:backend` |
| ⬜ | [Deals] Implement stage gating validation | Enforce progression: 10→20→30→40, etc. | `module:opportunities`, `type:backend` |
| ⬜ | [Deals] Build StageHistory tracking | Fields: fromStage, toStage, changedAt, changedBy, durationDays | `module:opportunities`, `type:backend` |
| ⬜ | [Deals] Implement audit logging for stage changes | Log all stage movements | `module:opportunities`, `type:backend` |
| ⬜ | [Deals] Implement audit logging for deal owner changes | Log assignment changes | `module:opportunities`, `type:backend` |
| ⬜ | [Deals] Build deal detail view with stage progression timeline | Visual timeline of stage history | `module:opportunities`, `type:frontend` |
| ⬜ | [Deals] Build pipeline Kanban board view grouped by stage | Drag and drop interface | `module:opportunities`, `type:frontend` |
| ⬜ | [Deals] Create pipeline list view filtered by BU | Business Unit filtering | `module:opportunities`, `type:frontend` |
| ⬜ | [Deals] Create 'My Deals' view for deal owners | Personalized view | `module:opportunities`, `type:frontend` |
| ⬜ | [Deals] Create 'BU Pipeline' view for BU Heads | Aggregated view for leadership | `module:opportunities`, `type:frontend` |
| ⬜ | [Deals] Implement deal-to-engagement trigger on CLOSED_WON | Automation hook | `module:opportunities`, `type:backend` |
| ⬜ | [Deals] Build win/loss analysis report with loss reasons | Reporting feature | `module:opportunities`, `type:analytics` |
| ⬜ | [Deals] Create 'Deals stuck in stage' alert | Trigger: Time in stage > threshold days | `module:opportunities`, `type:feature` |
| ⬜ | [Deals] Create 'Deals without next step' hygiene alert | Data quality alert | `module:opportunities`, `type:feature` |

### Contracts Module (12 issues)

| Status | Title | Description | Labels |
|--------|-------|-------------|--------|
| ⬜ | [Contracts] Define Contract entity with core fields | Fields: contractType, status, value, startDate, endDate | `module:contracts`, `type:backend` |
| ⬜ | [Contracts] Implement ContractType enum | Values: MSA, SOW, CHANGE_ORDER, NDA | `module:contracts`, `type:backend` |
| ⬜ | [Contracts] Implement ContractStatus enum | Values: DRAFT, INTERNAL_REVIEW, CLIENT_REVIEW, NEGOTIATION, SIGNED, EXPIRED | `module:contracts`, `type:backend` |
| ⬜ | [Contracts] Add renewal fields | Fields: autoRenew, renewalTermMonths | `module:contracts`, `type:backend` |
| ⬜ | [Contracts] Implement multi-step approval workflow based on value thresholds | Internal approval logic | `module:contracts`, `type:backend` |
| ⬜ | [Contracts] Add signature tracking | Fields: signerName, signedAt, ipAddress | `module:contracts`, `type:backend` |
| ⬜ | [Contracts] Build contract detail view with approval chain visualization | Frontend view | `module:contracts`, `type:frontend` |
| ⬜ | [Contracts] Build contract list view with filters | Filters: status, type, account | `module:contracts`, `type:frontend` |
| ⬜ | [Contracts] Create amendment and renewal tracking | Link new contracts to original MSA/SOW | `module:contracts`, `type:feature` |
| ⬜ | [Contracts] Implement audit logging for contract status changes | Compliance logging | `module:contracts`, `type:backend` |
| ⬜ | [Contracts] Create 'Contracts expiring in 60 days' alert view | Renewal management | `module:contracts`, `type:frontend` |
| ⬜ | [Contracts] Integrate contract creation from deals at stage 80+ | Auto-drafting trigger | `module:contracts`, `type:integration` |

### Engagements Module (10 issues)

| Status | Title | Description | Labels |
|--------|-------|-------------|--------|
| ⬜ | [Engagements] Define Engagement entity with core fields | Fields: dealId, accountId, status, contractValue | `module:engagements`, `type:backend` |
| ⬜ | [Engagements] Implement EngagementStatus enum | Values: PLANNING, RESOURCE_RAMP_UP, ACTIVE, ON_HOLD, COMPLETED | `module:engagements`, `type:backend` |
| ⬜ | [Engagements] Add revenue type field | Values: TIME_MATERIALS, FIXED_FEE, MILESTONE, SUBSCRIPTION | `module:engagements`, `type:backend` |
| ⬜ | [Engagements] Implement engagement auto-creation from CLOSED_WON deals | Transition workflow | `module:engagements`, `type:backend` |
| ⬜ | [Engagements] Implement revenue rule: recognize only when status=ACTIVE | Financial logic | `module:engagements`, `type:backend` |
| ⬜ | [Engagements] Define MonthlyRevenuePlan entity | Fields: plannedRevenue, actualRevenue, month, year | `module:engagements`, `type:backend` |
| ⬜ | [Engagements] Build engagement detail view with revenue plan table | Frontend for financial planning | `module:engagements`, `type:frontend` |
| ⬜ | [Engagements] Create 'Engagements starting in 60/90 days' view for delivery | Resource forecasting view | `module:engagements`, `type:frontend` |
| ⬜ | [Engagements] Implement sales-to-delivery handoff checklist | Process enforcement | `module:engagements`, `type:feature` |
| ⬜ | [Engagements] Create 'Engagements without revenue plan' alert | Data hygiene | `module:engagements`, `type:feature` |

### Integration Module - Core (8 issues)

| Status | Title | Description | Labels |
|--------|-------|-------------|--------|
| ⬜ | [Integration] Implement HubSpot company import | Scope: 475+ accounts | `module:integration`, `type:migration` |
| ⬜ | [Integration] Implement HubSpot contact import with account linking | Link contacts to migrated accounts | `module:integration`, `type:migration` |
| ⬜ | [Integration] Implement HubSpot deal import | Scope: 469+ deals with pipeline mapping | `module:integration`, `type:migration` |
| ⬜ | [Integration] Implement HubSpot owner mapping | Scope: 100 owners → CRM users | `module:integration`, `type:migration` |
| ⬜ | [Integration] Implement HubSpot field mapping configuration | Mapping utility | `module:integration`, `type:migration` |
| ⬜ | [Integration] Implement NetSuite customer bi-directional sync | ERP integration | `module:integration`, `type:backend` |
| ⬜ | [Integration] Implement NetSuite invoice generation from engagement data | ERP billing integration | `module:integration`, `type:backend` |
| ⬜ | [Integration] Implement NetSuite revenue recognition sync | ERP rev rec integration | `module:integration`, `type:backend` |

### Analytics Module (10 issues)

| Status | Title | Description | Labels |
|--------|-------|-------------|--------|
| ⬜ | [Analytics] Build configurable dashboard widget framework | Flexible UI architecture | `module:analytics`, `type:frontend` |
| ⬜ | [Analytics] Implement role-based default dashboard views | Different views for Sales vs Execs vs Delivery | `module:analytics`, `type:feature` |
| ⬜ | [Analytics] Build pipeline report | Deals by stage with values | `module:analytics`, `type:feature` |
| ⬜ | [Analytics] Build revenue forecast report | Monthly projections | `module:analytics`, `type:feature` |
| ⬜ | [Analytics] Build win/loss analysis report | Outcome analysis | `module:analytics`, `type:feature` |
| ⬜ | [Analytics] Build account health dashboard | Scores and trends visualization | `module:analytics`, `type:feature` |
| ⬜ | [Analytics] Implement dashboard sharing and permissions | Access control | `module:analytics`, `type:feature` |
| ⬜ | [Analytics] Implement anomaly alerts | Outlier detection | `module:analytics`, `type:feature` |
| ⬜ | [Analytics] Build recommended actions widget | Actionable insights | `module:analytics`, `type:feature` |

---

## v2.1-PSA

Professional Services Automation module for project and resource management.

### Projects & Resources (18 issues)

| Status | Title | Description | Labels |
|--------|-------|-------------|--------|
| ⬜ | [PSA] Define Project entity with core fields | Fields: name, accountId, opportunityId, status, projectType | `module:psa`, `type:backend` |
| ⬜ | [PSA] Add budget fields | Fields: budget, actualCost | `module:psa`, `type:backend` |
| ⬜ | [PSA] Implement ProjectStatus enum | Values: PLANNING, ACTIVE, ON_HOLD, COMPLETED, CANCELLED | `module:psa`, `type:backend` |
| ⬜ | [PSA] Implement ProjectType enum | Values: IMPLEMENTATION, ADVISORY, MANAGED_SERVICES, SUPPORT | `module:psa`, `type:backend` |
| ⬜ | [PSA] Add healthStatus field | Values: GREEN, YELLOW, RED | `module:psa`, `type:backend` |
| ⬜ | [PSA] Define TechnicalResource entity | Fields: name, skills, rate, availability | `module:psa`, `type:backend` |
| ⬜ | [PSA] Define ProjectResource entity | Assignment linking resource to project | `module:psa`, `type:backend` |
| ⬜ | [PSA] Define TimeEntry entity | Hours logged per resource per day | `module:psa`, `type:backend` |
| ⬜ | [PSA] Define ProjectDeliverable entity | Milestones with due dates | `module:psa`, `type:backend` |
| ⬜ | [PSA] Build project detail view with resources, time, budget | Comprehensive dashboard | `module:psa`, `type:frontend` |
| ⬜ | [PSA] Build resource allocation view | Gantt or timeline view | `module:psa`, `type:frontend` |
| ⬜ | [PSA] Build timesheet entry UI | Input mechanism for time | `module:psa`, `type:frontend` |
| ⬜ | [PSA] Implement project budget vs actual tracking | Financial calculation | `module:psa`, `type:backend` |
| ⬜ | [PSA] Create resource utilization dashboard | Metric: % utilized vs available | `module:psa`, `type:analytics` |
| ⬜ | [PSA] Create 'Projects at risk' view | Filter: RED health status | `module:psa`, `type:frontend` |
| ⬜ | [PSA] Implement skill matching for resource recommendations | Logic to match requirements to skills | `module:psa`, `type:feature` |
| ⬜ | [PSA] Build project margin analysis report | Profitability reporting | `module:psa`, `type:analytics` |

---

## v2.2-AI-Agentic

AI intelligence, semantic search, and agentic workflow automation.

### AI Infrastructure (12 issues)

| Status | Title | Description | Labels |
|--------|-------|-------------|--------|
| ⬜ | [AI] Set up Neo4j GraphRAG database | Infrastructure setup | `module:ai`, `type:infrastructure` |
| ⬜ | [AI] Implement relationship graph | Nodes: contact-to-contact, contact-to-account | `module:ai`, `type:backend` |
| ⬜ | [AI] Build warm introduction pathfinding algorithm | Graph traversal for intro paths | `module:ai`, `type:backend` |
| ⬜ | [AI] Implement embedding storage for semantic search | Vector database integration | `module:ai`, `type:backend` |
| ⬜ | [AI] Set up LLM gateway with model routing | Models: DeepSeek, Llama, Mistral, OpenAI | `module:ai`, `type:infrastructure` |
| ⬜ | [AI] Implement SQL generation using deepseek-coder:6.7b | Text-to-SQL features | `module:ai`, `type:backend` |
| ⬜ | [AI] Implement autocomplete using llama3.2:3b | Frontend assistance | `module:ai`, `type:frontend` |
| ⬜ | [AI] Implement insights/analysis using mistral:7b-instruct | Summary generation | `module:ai`, `type:backend` |
| ⬜ | [AI] Build company autocomplete with AI enrichment | Data enrichment feature | `module:ai`, `type:feature` |
| ⬜ | [AI] Implement deal intelligence | Win probability analysis (Backend) | `module:ai`, `type:backend` |
| ⬜ | [AI] Implement account health scoring with predictive indicators | Predictive modeling | `module:ai`, `type:backend` |
| ⬜ | [AI] Build contact parsing | Extract structured data from text/email signatures | `module:ai`, `type:feature` |

### AI-Enhanced Entity Fields (2 issues)

| Status | Title | Description | Labels |
|--------|-------|-------------|--------|
| ⬜ | [Accounts] Add GraphRAG fields | Fields: embeddingText, lastIndexed | `module:accounts`, `type:backend` |
| ⬜ | [Contacts] Implement relationship strength scoring | Scale: 0-100 | `module:contacts`, `type:backend` |
| ⬜ | [Deals] Implement AI deal intelligence | Win probability analysis | `module:opportunities`, `type:ai` |
| ⬜ | [PSA] Create 'Resource allocation' workflow in agentic system | AI-assisted allocation | `module:psa`, `type:ai` |
| ⬜ | [Analytics] Build AI insights panel | Automated pattern detection via Mistral/Deepseek | `module:analytics`, `type:ai` |

### Agentic Workflows (14 issues)

| Status | Title | Description | Labels |
|--------|-------|-------------|--------|
| ⬜ | [Agentic] Design workflow type enum | Values: 21 types including LEAD_QUALIFICATION, LEAD_NURTURE, etc. | `module:agentic`, `type:backend` |
| ⬜ | [Agentic] Implement AGENTIC_ENRICH_LEAD handler | Tech: Neo4j + web search | `module:agentic`, `type:backend` |
| ⬜ | [Agentic] Implement AGENTIC_SCORE_LEAD handler | Logic: ICP matching | `module:agentic`, `type:backend` |
| ⬜ | [Agentic] Implement AGENTIC_DRAFT_DOCUMENT handler | Output: SOW/contract generation | `module:agentic`, `type:backend` |
| ⬜ | [Agentic] Implement AGENTIC_DETECT_RISK handler | Logic: real-time account health monitoring | `module:agentic`, `type:backend` |
| ⬜ | [Agentic] Implement AGENTIC_RECOMMEND_NEXT_STEP handler | Sales coaching logic | `module:agentic`, `type:backend` |
| ⬜ | [Agentic] Implement AGENTIC_SCHEDULE_MEETING handler | Calendar integration logic | `module:agentic`, `type:backend` |
| ⬜ | [Agentic] Implement additional 7 handlers | Remaining 7 of 14 total handlers | `module:agentic`, `type:backend` |
| ⬜ | [Agentic] Build React Flow visual workflow builder UI | Drag and drop workflow editor | `module:agentic`, `type:frontend` |
| ⬜ | [Agentic] Implement trigger condition configuration | Logic for when workflows start | `module:agentic`, `type:backend` |
| ⬜ | [Agentic] Implement workflow step sequencing | Ordering logic | `module:agentic`, `type:backend` |
| ⬜ | [Agentic] Implement branch and conditional logic | If/Else logic in workflows | `module:agentic`, `type:backend` |
| ⬜ | [Agentic] Create workflow execution engine | The core runner for agents | `module:agentic`, `type:backend` |
| ⬜ | [Agentic] Build workflow monitoring dashboard | Observability for agents | `module:agentic`, `type:frontend` |
| ⬜ | [Agentic] Implement workflow audit logging | Traceability for agent actions | `module:agentic`, `type:backend` |

---

## v2.3-Support-Comms

Support ticketing, communications, and external integrations.

### Integration - Communications (4 issues)

| Status | Title | Description | Labels |
|--------|-------|-------------|--------|
| ⬜ | [Integration] Implement Office 365 calendar integration | Two-way sync | `module:integration`, `type:backend` |
| ⬜ | [Integration] Implement Office 365 email sending via Outlook | SMTP/Graph API | `module:integration`, `type:backend` |
| ⬜ | [Integration] Implement Teams message sending | Notification integration | `module:integration`, `type:backend` |
| ⬜ | [Integration] Implement Twilio SMS integration with delivery tracking | SMS gateway | `module:integration`, `type:backend` |

### Communications Module (10 issues)

| Status | Title | Description | Labels |
|--------|-------|-------------|--------|
| ⬜ | [Comms] Define EmailTemplate entity with variable substitution | Dynamic templating | `module:communications`, `type:backend` |
| ⬜ | [Comms] Implement template categories | Categories: MEETING, FOLLOW_UP, INTRO, PROPOSAL | `module:communications`, `type:backend` |
| ⬜ | [Comms] Build email template editor with variable picker | Rich text editor | `module:communications`, `type:frontend` |
| ⬜ | [Comms] Define Meeting entity with calendar integration | Core scheduling entity | `module:communications`, `type:backend` |
| ⬜ | [Comms] Build booking page generation | External facing scheduling | `module:communications`, `type:frontend` |
| ⬜ | [Comms] Implement attendee management | Invite handling | `module:communications`, `type:feature` |
| ⬜ | [Comms] Link meetings to Account/Contact/Opportunity | Activity associations | `module:communications`, `type:backend` |
| ⬜ | [Comms] Build unified Activities Panel timeline | Aggregated view: calls, meetings, emails, notes | `module:communications`, `type:frontend` |
| ⬜ | [Comms] Implement SMS messaging UI | Chat interface | `module:communications`, `type:frontend` |
| ⬜ | [Comms] Build activity logging for all interaction types | Universal logger | `module:communications`, `type:backend` |

### Support Module (8 issues)

| Status | Title | Description | Labels |
|--------|-------|-------------|--------|
| ⬜ | [Support] Define Ticket entity | Fields: title, description, priority, status, assignee | `module:support`, `type:backend` |
| ⬜ | [Support] Implement TicketPriority enum | Values: LOW, MEDIUM, HIGH, URGENT | `module:support`, `type:backend` |
| ⬜ | [Support] Implement TicketStatus enum | Values: OPEN, IN_PROGRESS, RESOLVED, CLOSED | `module:support`, `type:backend` |
| ⬜ | [Support] Link tickets to Account/Contact | Association logic | `module:support`, `type:backend` |
| ⬜ | [Support] Define Survey entity with response collection | Feedback mechanism | `module:support`, `type:backend` |
| ⬜ | [Support] Implement NPS tracking | Net Promoter Score logic | `module:support`, `type:feature` |
| ⬜ | [Support] Build support campaign management | Proactive outreach tools | `module:support`, `type:feature` |
| ⬜ | [Support] Create support analytics dashboard | Metrics: ticket volume, resolution time, CSAT/NPS | `module:support`, `type:analytics` |

---

## Labels Reference

### Module Labels

| Label | Description |
|-------|-------------|
| `module:foundation` | Project setup, documentation, configuration |
| `module:strategy` | Strategic planning and alignment |
| `module:accounts` | Account/Company management |
| `module:contacts` | Contact and stakeholder management |
| `module:leads` | Lead qualification and conversion |
| `module:opportunities` | Deal/Opportunity pipeline |
| `module:contracts` | Contract lifecycle management |
| `module:engagements` | Engagement and revenue planning |
| `module:psa` | Professional Services Automation |
| `module:ai` | AI capabilities and integrations |
| `module:agentic` | Agentic workflow automation |
| `module:integration` | External system integrations |
| `module:communications` | Email, calendar, messaging |
| `module:support` | Ticketing and customer support |
| `module:analytics` | Dashboards and reporting |

### Type Labels

| Label | Description |
|-------|-------------|
| `type:backend` | Server-side implementation |
| `type:frontend` | Client-side UI implementation |
| `type:feature` | Complete feature with UI and logic |
| `type:documentation` | Documentation work |
| `type:admin` | Administrative setup |
| `type:strategy` | Strategic planning |
| `type:workshop` | Stakeholder workshops |
| `type:infrastructure` | Infrastructure setup |
| `type:migration` | Data migration work |
| `type:integration` | Integration development |
| `type:analytics` | Analytics and reporting |
| `type:ai` | AI/ML implementation |

---

## Progress Tracking

Last updated: 2026-01-02

| Module | Backend | Frontend | Features | Total | Progress |
|--------|---------|----------|----------|-------|----------|
| Foundation | 0/0 | 0/0 | 2/6 | 2/6 | 33% |
| Strategy | 0/0 | 0/0 | 0/2 | 0/2 | 0% |
| Accounts | 0/9 | 0/4 | 0/1 | 0/14 | 0% |
| Contacts | 0/6 | 0/5 | 0/0 | 0/11 | 0% |
| Leads | 0/4 | 0/2 | 0/2 | 0/8 | 0% |
| Opportunities | 0/10 | 0/5 | 0/4 | 0/19 | 0% |
| Contracts | 0/6 | 0/3 | 0/2 | 0/11 | 0% |
| Engagements | 0/5 | 0/2 | 0/3 | 0/10 | 0% |
| PSA | 0/9 | 0/5 | 0/3 | 0/17 | 0% |
| AI | 0/8 | 0/1 | 0/3 | 0/12 | 0% |
| Agentic | 0/12 | 0/2 | 0/0 | 0/14 | 0% |
| Integration | 0/7 | 0/0 | 0/5 | 0/12 | 0% |
| Communications | 0/4 | 0/4 | 0/1 | 0/9 | 0% |
| Support | 0/4 | 0/0 | 0/3 | 0/7 | 0% |
| Analytics | 0/0 | 0/1 | 0/8 | 0/9 | 0% |
| **Total** | **0/84** | **0/34** | **2/43** | **2/161** | **1%** |

---

*This roadmap is automatically generated from the project's issue tracker and updated with each milestone completion.*
