<p align="center">
  <img src="./packages/twenty-website/public/images/core/logo.svg" width="100px" alt="Outcome CRM logo" />
</p>

<h2 align="center">Outcome CRM - The Consulting-Focused CRM</h2>

<p align="center">Built on <a href="https://twenty.com">Twenty CRM</a> | 📚 <a href="./docs/roadmap.md">Roadmap</a> | 🎯 <a href="./VISION.md">Vision</a></p>

<br />

# Overview

**Outcome CRM** is a customer relationship management platform purpose-built for professional services firms. Built as an extension of the open-source [Twenty CRM](https://github.com/twentyhq/twenty), it adds deep industry-specific functionality for consulting, advisory, and managed services organizations.

## Why Outcome CRM?

Professional services firms face unique challenges that generic CRMs don't address:

| Challenge | Outcome CRM Solution |
|-----------|---------------------|
| **Complex Sales Cycles** | 10-stage pipeline with stage gating and qualification scoring |
| **Stakeholder Management** | Role, influence, and decision-making power tracking |
| **Revenue Recognition** | T&M, fixed-fee, milestone, and subscription billing models |
| **Resource Planning** | PSA module with skill matching and utilization tracking |
| **Engagement Lifecycle** | Seamless sales-to-delivery handoff with revenue planning |

## Key Features

### 🎯 Consulting-Native Pipeline
- 10-stage sales process (IDENTIFIED → CLOSED_WON)
- Stage gating with required fields validation
- 4T lead qualification (Tech, TeamSize, Timing, Type)
- Deal category tracking (NN, ENN, EN)

### 👥 Stakeholder Intelligence
- Contact-to-account stakeholder mapping
- Influence and decision-making power tracking
- Org chart visualization
- Relationship strength scoring

### 📊 Revenue & Engagement Management
- Engagement auto-creation from closed deals
- Monthly revenue planning (planned vs actual)
- Multiple revenue types (T&M, Fixed, Milestone, Subscription)
- Sales-to-delivery handoff checklists

### 🤖 AI-Powered Intelligence (v2.2)
- GraphRAG for relationship insights
- Warm introduction pathfinding
- Deal win probability analysis
- Account health scoring

### 🔄 Agentic Workflows (v2.2)
- 21 workflow types with visual builder
- Lead enrichment and scoring agents
- Document generation (SOW, contracts)
- Risk detection and next-step recommendations

## Target Users

| Persona | Key Value |
|---------|-----------|
| **BU Head** | Pipeline visibility, revenue forecasting, team performance |
| **Account Executive** | Deal management, stakeholder mapping, proposal tracking |
| **Engagement Manager** | Revenue planning, resource allocation, delivery handoff |
| **Executive** | Strategic accounts, cross-BU visibility, board reporting |
| **Delivery Manager** | Skill matching, utilization, capacity planning |

## Milestones

| Version | Focus | Status |
|---------|-------|--------|
| **v2.0-Core-CRM** | Accounts, Contacts, Deals, Contracts, Engagements | 🔄 Active |
| **v2.1-PSA** | Projects, Resources, Time Tracking | 📋 Planned |
| **v2.2-AI-Agentic** | GraphRAG, LLM Gateway, Workflow Automation | 📋 Planned |
| **v2.3-Support-Comms** | Tickets, Email/Calendar Integration | 📋 Planned |

See the full [Roadmap](./docs/roadmap.md) for detailed issue tracking.

---

# Installation

## Self-Hosting

See Twenty's documentation:
- 🚀 [Self-hosting with Docker](https://docs.twenty.com/developers/self-hosting/docker-compose)
- 🖥️ [Local Development Setup](https://docs.twenty.com/developers/local-setup)

## Quick Start

```bash
# Clone the repository
git clone https://github.com/your-org/outcome-crm.git
cd outcome-crm

# Install dependencies
yarn install

# Start development environment
yarn start
```

---

# Tech Stack

| Layer | Technology |
|-------|------------|
| **Frontend** | React 18, TypeScript, Recoil, Emotion, Vite |
| **Backend** | NestJS, TypeORM, PostgreSQL, Redis, GraphQL |
| **AI** | Ollama (DeepSeek, Llama, Mistral), Neo4j GraphRAG |
| **Monorepo** | Nx workspace with Yarn 4 |

## Package Structure

```
packages/
├── twenty-front/          # React frontend application
├── twenty-server/         # NestJS backend API
├── twenty-ui/             # Shared UI components
├── twenty-shared/         # Common types and utilities
├── twenty-emails/         # Email templates
└── twenty-e2e-testing/    # Playwright E2E tests
```

---

# Documentation

| Document | Description |
|----------|-------------|
| [VISION.md](./VISION.md) | Product vision and positioning |
| [docs/roadmap.md](./docs/roadmap.md) | Full product roadmap with issue tracking |
| [docs/upstream-sync.md](./docs/upstream-sync.md) | Sync strategy with Twenty CRM |
| [CLAUDE.md](./CLAUDE.md) | AI assistant development guide |

---

# Built on Twenty

Outcome CRM is built on [Twenty](https://twenty.com), the #1 open-source CRM. We:

- **Maintain compatibility** with Twenty's core architecture
- **Extend** with consulting-specific modules (PSA, Engagements, Contracts)
- **Customize** the data model for professional services
- **Contribute back** generalizable improvements

<p align="center">
  <a href="https://www.twenty.com">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/refs/heads/main/packages/twenty-website/public/images/readme/github-cover-dark.png" />
      <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/twentyhq/twenty/refs/heads/main/packages/twenty-website/public/images/readme/github-cover-light.png" />
      <img src="./packages/twenty-website/public/images/readme/github-cover-light.png" alt="Twenty CRM" />
    </picture>
  </a>
</p>

---

# License

This project is licensed under the [AGPL-3.0 License](./LICENSE), consistent with Twenty CRM's licensing.
