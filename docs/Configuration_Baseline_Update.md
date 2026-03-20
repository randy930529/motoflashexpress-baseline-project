# Configuration Baseline Update

## 1. Project description
Motorcycle Delivery Service is a last‑mile logistics system based on motorcycles, designed to deliver errands and packages in Ameca. The project is currently in the preparation stage for pilot launch, with initial modules including:
- Order management
- Rider assignment
- Delivery tracking
- Payment control

## 2. Change request identification
**ID:** CR-MOTO-001  
**Description:** Development of a web and mobile platform for customers to request errands online, integrated with the internal operations system.

## 3. Impact analysis
### 3.1 Functional impact
- Customer registration and authentication
- Service catalog (errands, express deliveries, local purchases)
- Order cart
- Online order and payment management
- Integration with rider assignment module

### 3.2 Architectural impact
The architecture evolves from an internal operations system to a hybrid platform:
  Web/Mobile Frontend – REST API – Central Database – Shared Logistics Module

### 3.3 Project impact
- System requirements
- Architecture and database design
- Development schedule
- Testing and validation activities
Overall impact level: high but manageable.

## 4. Feasibility evaluation
- **Technical feasibility:** Feasible with modular extension
- **Operational feasibility:** High value for customers and local businesses
- **Economic feasibility:** Acceptable with moderate investment
- **Risk level:** Medium

## 5. Change control board decision
**Decision:** APPROVED

## 6. Justification for approval
1. The digital platform expands service reach.
2. Existing modules (order management, rider assignment) can be reused.
3. Motorcycle Delivery Service evolves into a hybrid physical/digital model.
4. Configuration management ensures traceability and stability.

## 7. Configuration baseline definition
**Baseline 1.0:**
- Internal errand operations
- Modules for orders, riders, basic payments

**Baseline 2.0:**
- Web/mobile platform for customers
- User management
- Online orders and digital payments
- Centralized logistics integration

## 8. Software configuration items (SCI)
- SCI-REQ-MOTO-02: Updated Requirements Specification
- SCI-DES-MOTO-02: Updated System Architecture Design
- SCI-WEB-MOTO-01: Web/Mobile Application Module
- SCI-API-MOTO-01: REST API Services
- SCI-DB-MOTO-02: Updated Database Schema
- SCI-TEST-MOTO-02: Test Plan and Test Cases
- SCI-DOC-MOTO-02: Updated User Documentation

## 9. Configuration control process
- Version control
- Change request documentation
- Approval by the Change Control Board
- Configuration audits
- Traceability between requirements, design, code, and tests
