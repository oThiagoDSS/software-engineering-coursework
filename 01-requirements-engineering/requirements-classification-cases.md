# Activity 2: Case Studies - Requirements Classification

This document categorizes requirements from five industrial case studies into **User Requirements (UR)**, **System Requirements (SR)**, **Functional Requirements (FR)**, and **Non-Functional Requirements (NFR)** with engineering justifications.

---

## Case 1: Digital Banking & Fraud Prevention

| ID | Item Description | Classification | Engineering Justification |
| :--- | :--- | :--- | :--- |
| **C1-01** | App freezing/lagging during instant transfers. | **UR / NFR** | Expresses user dissatisfaction with performance; maps to System Latency and Availability NFRs. |
| **C1-02** | High-value transactions trigger dynamic 2FA considering behavior, location, and device history. | **FR / SR** | Specifies automated business logic (FR) and system integration with historical behavior databases (SR). |
| **C1-03** | Clear user notification on transaction block with dispute option. | **UR / FR** | Defines an end-user interaction capability (UR) fulfilled by notification software services (FR). |
| **C1-04** | Audit logging of automated fraud decisions for regulatory compliance. | **SR / NFR** | Compliance requirement (NFR) enforced by immutable database event-sourcing audit logs (SR). |
| **C1-05** | Anti-fraud engine integration with external REST APIs maintaining legacy core compatibility. | **SR / NFR** | Technical integration constraint (SR) ensuring system interoperability and backwards compatibility (NFR). |

---

## Case 2: Omnichannel E-Commerce & Logistics

| ID | Item Description | Classification | Engineering Justification |
| :--- | :--- | :--- | :--- |
| **C2-01** | Buy online and pick up in-store within 2 hours with synchronized stock. | **UR / FR** | End-user service expectation (UR) implemented via cross-channel inventory synchronization services (FR). |
| **C2-02** | Price consistency across channels; automated coupon validation respecting tax laws. | **FR / SR** | Core pricing logic (FR) enforced across POS and Web endpoints with tax rule validation engine (SR). |
| **C2-03** | End-to-end order tracking (picking, dispatch, delivery attempts). | **FR / UR** | Fulfills customer support needs (UR) through event-driven status tracking workflows (FR). |
| **C2-04** | System crash and cart expiration during peak sales. | **NFR** | Relates to system scalability, reliability, and concurrency constraints under load. |
| **C2-05** | LGPD compliance: data minimization, deletion, and marketing consent tracking. | **SR / NFR** | Legal compliance (NFR) realized via security constraints and data persistence models (SR). |
| **C2-06** | Carrier SLA dashboards and automated delivery delay alerts. | **UR / FR** | Operations team requirement (UR) fulfilled by analytical reporting and background cron notifications (FR). |

---

## Case 3: Healthcare: Integrated Medical Records

| ID | Item Description | Classification | Engineering Justification |
| :--- | :--- | :--- | :--- |
| **C3-01** | Replace manual spreadsheets with integrated agenda, EHR, and billing system. | **UR / SR** | Business modernization goal (UR) translated into an integrated multi-tier enterprise architecture (SR). |
| **C3-02** | Rapid doctor access to patient history, prescriptions, and exams across units. | **UR / NFR** | End-user access requirement (UR) constrained by sub-second database response times and distributed access (NFR). |
| **C3-03** | Role-based access control (RBAC) and immutable access logging for HIPAA/LGPD privacy. | **SR / NFR** | Security constraint (NFR) enforced via JWT/RBAC middleware and write-once audit logs (SR). |
| **C3-04** | Digital signatures on medical evolutions and document export. | **FR / SR** | Functional feature (FR) requiring Integration with Public Key Infrastructure (PKI / X.509) (SR). |
| **C3-05** | Automated WhatsApp/SMS appointment reminders and dynamic waitlist filling. | **FR / UR** | Reduces no-shows for clinic management (UR) through background messaging queue integrations (FR). |

---

## Case 4: Smart City: Public Lighting & Maintenance

| ID | Item Description | Classification | Engineering Justification |
| :--- | :--- | :--- | :--- |
| **C4-01** | Automated telemetry collection (on/off, power, failures) and auto-creation of work orders. | **FR / SR** | IoT ingestion service (SR) triggering automated service ticket generation logic (FR). |
| **C4-02** | GIS map interface displaying critical failure clusters and optimized technician routes. | **UR / FR** | Dispatcher user interface requirement (UR) supported by spatial routing algorithms (FR). |
| **C4-03** | Mobile field app offline-first operation with auto-sync upon reconnection. | **SR / NFR** | Architecture constraint (SR) ensuring system availability in disconnected environments (NFR). |
| **C4-04** | Monthly compliance reporting with geolocated and time-stamped photo evidence. | **UR / FR** | Regulatory reporting requirement (UR) backed by blob storage metadata persistence (FR). |

---

## Case 5: Industry 4.0: Traceability & Quality Control

| ID | Item Description | Classification | Engineering Justification |
| :--- | :--- | :--- | :--- |
| **C5-01** | Full batch traceability (raw materials, supplier, line, operator, inspection, destination). | **UR / FR** | Export auditor requirement (UR) satisfied by relational batch lineage data structures (FR). |
| **C5-02** | Automated shipping block upon critical non-conformity detection with CAPA workflows. | **FR / SR** | Business rule enforcement (FR) locking warehouse ERP dispatch modules (SR). |
| **C5-03** | Ingestion of factory floor IoT temperature/humidity sensors with immutable logging. | **SR / NFR** | Edge hardware integration (SR) delivering data integrity and anti-tampering (NFR). |
| **C5-04** | Real-time OEE dashboards and threshold boundary alerts. | **UR / FR** | Executive management requirement (UR) powered by real-time stream analytical engines (FR). |
