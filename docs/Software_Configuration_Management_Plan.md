# Software Configuration Management Plan (SCMP)

## 1. Document Control

### 1.1 Document Information

| Field          | Value                  |
| -------------- | ---------------------- |
| Project        | MotoFlash Express      |
| Plan Version   | 1.2                    |
| Date           | 2026-04-17             |
| Status         | Template-aligned draft |
| Document Owner | Configuration Manager  |

### 1.2 Document Version History

| Version | Date       | Author/Role                | Description of Change                       |
| ------- | ---------- | -------------------------- | ------------------------------------------- |
| 0.1     | 2026-04-17 | Configuration Manager      | Initial SCMP structure                      |
| 1.0     | 2026-04-17 | Configuration Manager + PM | Full baseline-ready content                 |
| 1.1     | 2026-04-17 | Configuration Manager      | Reorganized into SCMP template sections     |
| 1.2     | 2026-04-17 | Configuration Manager      | Clean rebuild aligned to template structure |

### 1.3 Distribution List

This document is distributed to:

- Project Manager
- Development Team (Junior, Semi-Senior, Senior)
- QA Team
- Infrastructure Team
- Logistics Team
- Legal/Compliance Team

## 2. Introduction

### 2.1 Purpose

This plan defines how software configuration items are identified, controlled, baselined, audited, traced, and reported in MotoFlash Express to ensure product integrity, controlled evolution, and compliance.

### 2.2 Scope

This SCMP applies to all software and software-related artifacts in the repository, including:

- Project documentation such as `README.md`, `CHANGELOG.md`, `docs/`, and `requirements/`
- Functional and non-functional requirements
- Architecture and process-flow artifacts
- Source code for frontend, backend, and integrations
- Database schema and migrations
- QA artifacts and evidence
- Build, release, and deployment definitions

### 2.3 Definitions and Acronyms

- SCMP: Software Configuration Management Plan.
- SCI: Software Configuration Item.
- CCB: Change Control Board.
- CR: Change Request.
- Baseline: approved and frozen set of SCIs at a control point.
- Status Accounting: recording and reporting SCI and CR states.

### 2.4 References

- [README.md](../README.md)
- [docs/README.md](README.md)
- [docs/Configuration_Baseline_Update.md](Configuration_Baseline_Update.md)
- [docs/Guidelines_Metrics.md](Guidelines_Metrics.md)
- [docs/Risk_Management.md](Risk_Management.md)
- [docs/SWOT_Analysis.md](SWOT_Analysis.md)
- [requirements/functional.md](../requirements/functional.md)
- [requirements/non-functional.md](../requirements/non-functional.md)
- [docs/diagrams/architecture.md](diagrams/architecture.md)
- [docs/diagrams/process_flow](diagrams/process_flow)

### 2.5 Product Overview

MotoFlash Express is a last-mile motorcycle delivery platform for Ameca and the Valles de Jalisco region. The solution includes:

- Client App/Web
- REST API with authentication
- Central database for orders, users, payments, and logistics
- Shared logistics module for rider assignment and tracking
- Internal operations system

## 3. SCM Management

### 3.1 SCM Organization

Configuration management is governed by the CCB and executed by engineering, QA, infrastructure, logistics, and compliance teams.

| Role                                          | SCM Responsibility                                                 |
| --------------------------------------------- | ------------------------------------------------------------------ |
| CCB (PM, Tech Lead, QA Lead, Legal as needed) | Approve/reject medium and high impact CRs                          |
| Configuration Manager                         | Maintain the SCMP, baselines, records, and SCM reporting           |
| Junior Developers                             | Implement low-impact changes and basic unit tests                  |
| Semi-Senior Developers                        | Perform module integration and technical impact analysis           |
| Senior Developers                             | Own architecture, security controls, and high-impact change design |
| QA                                            | Verify requirements compliance and execute regression control      |
| Infrastructure                                | Manage environment configuration, backups, and capacity controls   |
| Legal/Compliance                              | Validate regulatory impact and legal readiness                     |

### 3.2 SCM Policies

All SCI changes must:

1. Be linked to a CR, issue, or approved task.
2. Be versioned in source control.
3. Pass peer review and QA validation as applicable.
4. Update impacted documentation.
5. Be recorded in `CHANGELOG.md` when baseline-relevant.

### 3.3 Applicable Standards and Naming Rules

- Semantic versioning for software artifacts: `MAJOR.MINOR.PATCH`.
- Baseline/document versions: `v1.0`, `v1.1`, `v2.0`.
- CR naming format: `CR-MOTO-###`.
- Release naming format: `MFE-YYYY.MM-R#`.

### 3.4 SCM Tools and Repository Control

- GitHub repository: `randy930529/motoflashexpress-baseline-project`
- Baseline reference branch: `main`
- Current documentation branch: `docs`
- Documentation source: `docs/` and `requirements/`
- Change history artifact: `CHANGELOG.md`

## 4. SCM Activities

### 4.1 Configuration Identification

An artifact is managed as an SCI if it:

- Impacts functional behavior, security, payments, or logistics.
- Impacts module interfaces, architecture, or data structure.
- Is required for audits, release readiness, or compliance evidence.

SCI catalog:

| Category      | SCI                                     | Identifier       |
| ------------- | --------------------------------------- | ---------------- |
| Requirements  | Functional specification                | SCI-REQ-MOTO-02  |
| Requirements  | Non-functional specification            | SCI-NFR-MOTO-01  |
| Architecture  | Architecture design                     | SCI-DES-MOTO-02  |
| Application   | Client web/mobile module                | SCI-WEB-MOTO-01  |
| Services      | REST API and authentication             | SCI-API-MOTO-01  |
| Data          | DB schema/migrations                    | SCI-DB-MOTO-02   |
| Testing       | Test plan and test cases                | SCI-TEST-MOTO-02 |
| Documentation | Manuals, guidelines, SCMP               | SCI-DOC-MOTO-02  |
| Operations    | Deployment and monitoring configuration | SCI-OPS-MOTO-01  |

### 4.2 Baseline Management

Defined baselines:

- Baseline 1.0 (internal operations): internal errands, order/rider/basic payment modules, internal control.
- Baseline 2.0 (hybrid platform): client web/mobile, user/auth management, online orders/payments, centralized logistics integration.

A baseline is declared only when:

1. Scope requirements are approved by CCB.
2. Functional and regression tests are approved by QA.
3. Security and legal compliance evidence is available.
4. Documentation is updated and published.

### 4.3 Configuration Control

Workflow:

1. CR registration.
2. Impact classification (low/medium/high).
3. Technical, operational, economic, and legal analysis.
4. CCB decision (approved/rejected/deferred).
5. Branch-based implementation.
6. Peer review and QA validation.
7. Baseline integration and status update.

Impact levels:

| Level  | Criteria                                                                              |
| ------ | ------------------------------------------------------------------------------------- |
| Low    | Minor changes without architectural or regulatory impact                              |
| Medium | Module/data integration changes with bounded risk                                     |
| High   | Changes affecting architecture, security, payments, legal compliance, or availability |

Evaluation factors per CR:

- Effort (Fibonacci: 1, 2, 3, 5, 8, 13, 21)
- Budget impact (low <10%, medium 10-25%, high >25%)
- Time (short <=2 weeks, medium 3-6, long >6)
- Human resource demand
- Contract and legal obligations
- Technology expansion needs
- Required skill availability
- Project phase impact

Approval thresholds:

- Low: Tech Lead + QA Lead
- Medium: PM + Tech Lead + QA
- High: Full CCB with Legal/Infrastructure as required

### 4.4 Configuration Status Accounting

Mandatory records:

- CR log and status
- SCI version log
- Test result register
- Incident and corrective action register

Standard CR states:

`New -> Under Analysis -> Approved/Rejected -> In Development -> In Testing -> Closed`

Minimum traceability links per change:

- Requirement(s) impacted
- Design/architecture artifact impacted
- Related commit(s)/PR(s)
- Executed test cases
- QA validation evidence

### 4.5 Configuration Verification and Audits

Audit types:

- Functional Configuration Audit (FCA)
- Physical Configuration Audit (PCA)
- Security and compliance audit

Audit frequency:

- Per release: change/configuration audit
- Quarterly: security audit
- Monthly or iteration-close: baseline documentation review

Release acceptance criteria:

1. Regression tests executed with no open blockers.
2. Critical NFR compliance evidence available.
3. No critical order/payment synchronization defects.
4. Documentation and changelog updated.

### 4.6 Build, Release, and Deployment Control

Branch strategy:

- `main`: stable/released line
- `develop` (optional): integration line
- `feature/*`: functional development
- `hotfix/*`: urgent corrections
- `docs/*`: documentation updates

Integration rules:

- Small, descriptive commits
- Mandatory code review for software changes
- No feature merge without minimum tests
- Baseline-relevant documentation changes reflected in `CHANGELOG.md`

Release package must include:

- SCI list
- Associated CRs
- Residual risk summary

### 4.7 Interface and External Control

For external dependencies and interfaces such as maps, payments, and legal entities:

- Interface-impacting changes are at least medium impact.
- Contractual/legal checks are mandatory when applicable.
- API and data interface changes require backward-compatibility analysis or a migration plan.

## 5. SCM Schedule and Milestones

### 5.1 Operational Cadence

- CR triage and status updates: weekly
- Baseline review: monthly
- Security audit: quarterly
- Full SCMP review: quarterly or upon major change

### 5.2 Key SCM Milestones for Baseline 2.0

1. Baseline 2.0 SCI set finalized.
2. Traceability matrix completed.
3. FCA/PCA evidence completed.
4. Release package approved by CCB.

## 6. SCM Resources and Support

### 6.1 Human Resources

- Configuration Manager
- CCB members
- Development team by seniority
- QA and Infrastructure
- Legal/Compliance support

### 6.2 Training Plan

- Team-wide SCM workflow onboarding
- Junior training: version control, traceability, basic testing
- Semi-senior training: integration and impact analysis
- Senior training: security auditing and architecture governance

### 6.3 Infrastructure and Tooling Needs

- Git repository governance
- Branch policy enforcement
- Test evidence storage
- Audit evidence and compliance checklist storage

## 7. SCM Risks and Metrics

### 7.1 Configuration Risks

- Basic security vulnerabilities in forms and payments
- Order/payment desynchronization
- Regression defects due to rapid iteration
- Regulatory non-compliance
- Capacity overload under demand growth

### 7.2 Mitigation Strategy

- Early security checks by impact level
- Multi-scenario synchronization tests before merge
- Legal checklist for regulatory-impact changes
- Progressive scalability and capacity monitoring
- End-to-end traceability for incident diagnosis

### 7.3 SCM Metrics and Thresholds

Mandatory KPIs:

- Average CR approval time
- Approved vs rejected CR ratio
- Hotfix count per release
- Regression defect rate
- SCI complete traceability rate
- Audit findings per period

Initial control thresholds:

- Complete traceability >= 95% of closed CRs
- Critical post-release defects <= 1 per release
- Hotfixes <= 15% of released changes
- Audit finding closure <= 30 days

## 8. SCMP Maintenance

### 8.1 Ownership

The Configuration Manager is responsible for maintaining this document.

### 8.2 Review and Update Frequency

- Regular review: quarterly
- Extraordinary review: architecture, regulation, operating model, or governance change

### 8.3 Triggers for Immediate Update

- Change approval workflow modifications
- Role or CCB composition changes
- Versioning or deployment process updates
- Baseline or critical SCI restructuring
- New legal or security obligations

## 9. Appendices

### Appendix A. Reference Change Request

- `CR-MOTO-001`: development of the web/mobile platform integrated with internal operations.

### Appendix B. Initial Prioritized SCI Set for Baseline 2.0

1. SCI-REQ-MOTO-02
2. SCI-DES-MOTO-02
3. SCI-WEB-MOTO-01
4. SCI-API-MOTO-01
5. SCI-DB-MOTO-02
6. SCI-TEST-MOTO-02
7. SCI-DOC-MOTO-02

### Appendix C. Quick Release Checklist

1. CRs approved and traceable.
2. QA tests approved with no blockers.
3. Configuration audit completed.
4. Residual risks documented.
5. `CHANGELOG.md` and documentation updated.
