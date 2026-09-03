# IT Service Desk - Software Architecture

## 1. System Overview

An IT Service Desk platform managing incident ticketing, SLA tracking, automated routing, and escalation management using an Event-Driven Architecture.

## 2. Architecture & Design Decisions

* **Event-Driven Ticket Lifecycle:** Ticket creation, updates, and assignments emit domain events to trigger automated escalation timers.
* **State Pattern:** Manages ticket status transitions (e.g., Open, In Progress, Pending User, Resolved, Closed).
* **Role-Based Access Control (RBAC):** Restricts ticket queues and administrative operations based on technician roles.

## 3. Ticket Lifecycle State Diagram

```mermaid
stateDiagram-v2
    [*] --> New
    New --> Assigned : Dispatcher assigns Tech
    Assigned --> InProgress : Tech starts work
    InProgress --> PendingUser : Info needed
    PendingUser --> InProgress : User responds
    InProgress --> Resolved : Solution provided
    Resolved --> Closed : Auto-closed after 48h
    Resolved --> InProgress : User reopens ticket
    Closed --> [*]
