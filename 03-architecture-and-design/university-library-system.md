# University Library System - Software Architecture

## 1. Architectural Strategy

A Layered (N-Tier) Architecture backed by domain-driven design principles to manage book cataloging, loans, renewals, and fine processing.

## 2. Key Subsystems & Design Patterns

* **Repository Pattern:** Decouples data persistence from core domain logic for loans and inventory.
* **Observer Pattern:** Triggers notification alerts when reserved books become available or when loan deadlines approach.
* **Strategy Pattern:** Calculates fine penalties based on user category (e.g., undergraduate, graduate, faculty).

## 3. Component Interaction Diagram

```mermaid
graph LR
    UserInterface[Web Portal] --> Controller[Loan Controller]
    Controller --> Service[Loan Domain Service]
    Service --> Strategy[Fine Calculation Strategy]
    Service --> Repository[Book Repository]
    Repository --> Database[(MySQL Database)]
