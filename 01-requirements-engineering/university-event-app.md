# Activity 1: University Party App (MVP & Risk Analysis)

## 1. Problem Definition

College students experience friction when purchasing tickets for campus events, including high ticketing fees, insecure manual transfers, entry queue bottlenecks, and ticket scalping via duplicate static QR code screenshots.

## 2. User Personas & Stakeholders

* **Students (Attendees):** Seek fast ticket purchasing, affordable fees, and immediate, seamless event check-in.
* **Sellers / Vendors:** Require real-time inventory synchronization and live sales tracking across POS endpoints.
* **Event Organizers:** Require cash-flow visibility, real-time entry gate management, and fraud protection.

## 3. Core MVP Functional Requirements

1. **Dynamic Check-in QR Code:** System generates a short-lived dynamic QR code (refreshing every 30 seconds) accessible only upon authenticated login to eliminate static screenshot resale.
2. **High Availability Architecture:** Auto-scaling infrastructure capable of handling massive concurrency spikes during high-demand ticket drops.
3. **Automated Tiered Inventory Management:** Real-time pricing transitions and stock updates triggered automatically upon batch exhaustion.

## 4. Risk Analysis & Mitigation Strategies

| Risk | Severity | Mitigation Strategy |
| :--- | :--- | :--- |
| **Server Crash during Traffic Spikes** | Critical | Virtual queue system (e.g., AWS SQS / Cloudflare Waiting Room) + horizontal pod auto-scaling (K8s HPA). |
| **QR Code Fraud / Scalping** | High | Dynamic TOTP-based QR Code generation refreshed on client side via server-validated timestamps. |
| **Data Breach / Privacy Non-Compliance** | High | Data minimization under LGPD/GDPR, field-level encryption (AES-256) for PII, and TLS 1.3 in transit. |
