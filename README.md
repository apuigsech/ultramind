# Ultramind Skills Marketplace

A comprehensive, layered skills marketplace for Claude Code, organized in 4 architectural layers with 74 professional-grade skills across 17 plugins.

---

## Overview

Ultramind provides a structured approach to AI-assisted development through:

- **4 Architectural Layers**: From cognitive foundations to technical specialization
- **17 Specialized Plugins**: Focused collections of related skills
- **74 Skills**: Covering methodology, engineering, workflows, and technical specializations
- **5 Subagents**: Orchestrating specialists for frontend, security, backend, data, and devops
- **Intelligent Activation**: Progressive loading based on context and token budgets

---

## Quick Start

### Installation

```bash
# Clone repository
git clone https://github.com/ultramind/claude-skills
cd claude-skills

# Verify structure
cat .claude-marketplace/marketplace.json | jq .

# Check documentation
ls docs/architecture/
```

### Usage

Skills activate automatically based on context and layer configuration:

- **Layer 1-2**: Always active (cognitive & engineering foundations)
- **Layer 3**: Contextual (workflow skills when triggered)
- **Layer 4**: Suggested (technical specialization on demand)

---

## Architecture

### System Diagram

```
┌─────────────────────────────────────────────┐
│           USER DEVELOPMENT CONTEXT          │
└──────────────────┬──────────────────────────┘
                   │
    ┌──────────────▼──────────────┐
    │  Layer 4: Specialization    │   🔵 Suggested (~6.7K)
    │  Frontend│Security│Backend  │      ↓ depends on ↓
    │    Data  │ DevOps           │
    ├─────────────────────────────┤
    │  Layer 3: Practice          │   🟡 Contextual (~4K)
    │  Workflow & Collaboration   │      ↓ depends on ↓
    ├─────────────────────────────┤
    │  Layer 2: Engineering Core  │   🟢 Always Active (~4K)
    │  Architecture & Quality     │      ↓ depends on ↓
    ├─────────────────────────────┤
    │  Layer 1: Cognitive         │   🟢 Always Active (~2K)
    │  Problem Solving & Analysis │
    └─────────────────────────────┘

    17 plugins • 74 skills • 5 subagents
```

### Skills Distribution

| Layer | Plugins | Skills | Subagents | Token Budget | Activation |
|-------|---------|--------|-----------|--------------|------------|
| **Layer 1** | 3 | 11 | 0 | ~2,000 | Auto |
| **Layer 2** | 5 | 22 | 0 | ~4,000 | Auto |
| **Layer 3** | 4 | 21 | 0 | ~4,000 | Contextual |
| **Layer 4** | 5 | 20 | 5 | ~6,680 | Suggested |

**Total**: 17 plugins, 74 skills, 5 subagents

---

## Complete Skills List

### Layer 1: Cognitive & Method Skills (11 skills)

**Plugin: problem-solving**
- `abstraction-layering` - Hierarchical abstraction for managing complexity
- `problem-decomposition` - Breaking complex problems into manageable components
- `first-principles-thinking` - Reasoning from fundamental truths
- `constraint-identification` - Identifying and documenting system constraints

**Plugin: design-and-analysis**
- `systems-thinking` - Understanding interconnections and feedback loops
- `tradeoff-analysis` - Systematic evaluation of design tradeoffs
- `impact-assessment` - Evaluating ripple effects of decisions

**Plugin: evaluation-methods**
- `root-cause-analysis` - Identifying underlying causes of issues
- `postmortem-analysis` - Learning from incidents and failures
- `evidence-based-reasoning` - Making decisions based on data
- `decision-frameworks` - Structured approaches to complex decisions

---

### Layer 2: Engineering Core Skills (22 skills)

**Plugin: architecture-patterns**
- `software-architecture-thinking` - High-level system design principles
- `design-patterns` - Reusable solutions to common problems
- `scalability-patterns` - Designing for horizontal and vertical scaling
- `defensive-design` - Robust error handling and failure anticipation
- `api-design` - RESTful and contract-first API principles

**Plugin: quality-assurance**
- `test-driven-development` - RED-GREEN-REFACTOR methodology
- `code-review` - Systematic review practices
- `technical-debt-management` - Identifying and paying down debt
- `refactoring-strategies` - Safe code improvement techniques

**Plugin: security-practices**
- `secure-coding-practices` - OWASP Top 10 prevention
- `threat-modeling` - STRIDE threat identification
- `authentication-authorization` - Identity and access control
- `data-protection` - Encryption and secure storage

**Plugin: operability**
- `observability-thinking` - Metrics, logs, and traces
- `incident-response` - On-call and incident management
- `deployment-safety` - Safe rollout strategies
- `monitoring-alerting` - Proactive system monitoring

**Plugin: database-design**
- `data-modeling` - Entity relationships and normalization
- `schema-design` - Efficient database schema patterns
- `query-optimization` - Performance tuning for databases
- `database-scalability` - Replication, sharding, and partitioning
- `transaction-management` - ACID properties and isolation levels

---

### Layer 3: Practice & Workflow Skills (21 skills)

**Plugin: project-lifecycle**
- `requirements-analysis` - Gathering and validating requirements
- `sprint-planning` - Agile sprint organization
- `estimation-techniques` - Story points and planning poker
- `project-retrospectives` - Continuous improvement practices
- `stakeholder-management` - Managing expectations and communication

**Plugin: collaboration-workflows**
- `code-review-practices` - Effective peer review workflows
- `pair-programming` - Collaborative coding techniques
- `async-collaboration` - Distributed team coordination
- `technical-communication` - Writing effective tech specs
- `conflict-resolution` - Resolving technical disagreements

**Plugin: documentation-practices**
- `technical-writing` - Clear and concise documentation
- `api-documentation` - OpenAPI/Swagger documentation
- `architecture-documentation` - ADRs and architecture diagrams
- `runbook-creation` - Operational playbooks
- `documentation-maintenance` - Keeping docs up to date

**Plugin: deployment-strategies**
- `continuous-integration` - Automated build and test pipelines
- `continuous-deployment` - Automated deployment workflows
- `deployment-automation` - Infrastructure and app deployment
- `rollback-strategies` - Safe rollback procedures
- `feature-flags` - Progressive feature rollouts
- `canary-deployments` - Gradual traffic shifting

---

### Layer 4: Technical Specialization (20 skills + 5 subagents)

**Plugin: frontend-engineering** (6 skills + `frontend-engineer` subagent)
- `component-architecture-review` - React/Vue component patterns
- `accessibility-audit` - WCAG 2.1 AA compliance
- `frontend-testing` - RTL, Playwright, Cypress strategies
- `performance-profiling` - Core Web Vitals optimization
- `bundle-analysis` - Code splitting and tree shaking
- `state-management-review` - Redux, Zustand, Context patterns

**Plugin: security-engineering** (4 skills + `security-engineer` subagent)
- `threat-modeling` - STRIDE methodology and attack trees
- `vulnerability-scanning` - SAST/DAST and dependency scanning
- `penetration-testing` - Ethical hacking and exploitation
- `security-code-review` - Security-focused code audits

**Plugin: backend-engineering** (4 skills + `backend-engineer` subagent)
- `api-design-review` - REST/GraphQL best practices
- `database-optimization` - Query tuning and indexing
- `caching-strategy` - Multi-layer caching with Redis
- `microservices-patterns` - Service boundaries and resilience

**Plugin: data-engineering** (4 skills + `data-engineer` subagent)
- `data-pipeline-design` - ETL/ELT with Airflow and Spark
- `data-quality-validation` - Completeness and accuracy checks
- `etl-optimization` - Pipeline performance tuning
- `data-modeling` - Dimensional modeling and data warehouses

**Plugin: devops-engineering** (4 skills + `devops-engineer` subagent)
- `ci-cd-pipeline` - Automated build, test, deploy
- `infrastructure-as-code` - Terraform, CloudFormation, Pulumi
- `container-orchestration` - Kubernetes deployment and scaling
- `observability-stack` - Prometheus, Grafana, ELK, tracing

---

## Features

### Intelligent Activation

Skills load based on:
- **Context**: Current work and file types
- **Layer mode**: Auto, contextual, suggested, or manual
- **Token budget**: Staying within limits
- **User preference**: Explicit activation/deactivation

### Progressive Disclosure

Large skills use modular structure:
```
skill-name/
├── SKILL.md           # Core process (< 500 lines)
├── modules/           # Detailed reference
├── examples/          # Usage examples
├── templates/         # Output templates
└── scripts/           # Automation tools
```

### Quality Assurance

Every skill includes:
- ✅ Clear "When to Use" section
- ✅ Anti-rationalization patterns (red flags)
- ✅ Practical examples and checklists
- ✅ Tool commands and references
- ✅ Verification criteria

Every Layer 4 plugin includes:
- ✅ 1 orchestrating subagent
- ✅ 3-6 focused skills
- ✅ Comprehensive system prompts
- ✅ Integration with foundational layers


## License

MIT License - See [LICENSE](LICENSE) for details

---

## Acknowledgments

Built following principles from:
- Claude Code Plugin System
- Agent Skills Standard (agentskills.io)
- TDD Methodology
- Compliance Psychology Research
- Superpowers Plugin (obra/superpowers)
- Abstract Plugin (claude-night-market/abstract)

---

*Project initiated: 2025-02-02*
*Status: MVP Complete - 4 Layers Implemented*
