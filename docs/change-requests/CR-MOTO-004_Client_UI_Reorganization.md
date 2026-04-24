# CR-MOTO-004 - Client Screen Reorganization for Marketing Strategy

## 1. Request Summary

The client requires a reorganization of the client-facing screen layout according to a new marketing strategy.

## 2. Business Driver

- Increase conversion and service adoption.
- Improve visibility of promoted services.
- Align UI hierarchy with campaign priorities.

## 3. Scope

### In scope

- Redesign information hierarchy on client screens.
- Reorder service cards, promotions, and call-to-action blocks.
- Update navigation flow for marketing priority journeys.
- Validate usability impact with pilot users.

### Out of scope

- Full visual rebranding (logo/colors) unless explicitly approved.
- Back-end service logic changes not related to presentation.

## 4. Impact Analysis

- Functional impact: medium.
- UX/branding impact: high.
- Architectural impact: low-medium.
- Schedule impact: short-medium.

## 5. SCI Affected

- SCI-REQ-MOTO-05: Client UI and marketing journey requirements.
- SCI-WEB-MOTO-02: Client interface module updates.
- SCI-TEST-MOTO-05: UI regression and usability test cases.
- SCI-DOC-MOTO-04: UX decision and screen flow documentation.

## 6. Risks and Mitigation

- User confusion after layout changes: run A/B pilot and onboarding hints.
- Conversion drop risk: release behind feature flag and monitor KPIs.
- Accessibility regressions: include accessibility checks in QA.

## 7. Proposed State and Decision

- Current state: PROPOSED
- Priority: MEDIUM-HIGH

## 8. Time and Team Effort Estimation

### 8.1 Estimated timeline

- UX proposal and marketing alignment: 1 week
- UI implementation and navigation updates: 2 weeks
- A/B pilot and usability validation: 1 week
- QA regression and release preparation: 1 week
- Total estimated duration: 5 weeks

### 8.2 Team effort estimate

| Role                           | Estimated effort (person-weeks) |
| ------------------------------ | ------------------------------- |
| UI/UX Designer                 | 1.0                             |
| Semi-Senior Frontend Developer | 1.5                             |
| Junior Frontend Developer      | 1.0                             |
| QA Engineer                    | 1.0                             |
| Product/Marketing Owner        | 0.5                             |
| Total                          | 5.0 person-weeks                |

### 8.3 Planning assumptions

- Marketing priorities are frozen before UI implementation starts.
- No full rebranding is included in this CR.
- A/B metrics can be measured with existing analytics tools.
