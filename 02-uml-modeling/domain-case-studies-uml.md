# Module 02: UML Domain Case Studies

This document presents UML modeling solutions for real-world enterprise architectures across multiple domain case studies.

---

## Case 1: Digital Banking - Sequence Diagram

```mermaid
sequenceDiagram
    autonumber
    actor User
    participant App as Mobile App
    participant Gateway as API Gateway
    participant Auth as Auth Service
    participant Account as Account Service

    User->>App: Initiate Transfer (Amount, Recipient)
    App->>Gateway: POST /api/v1/transfers
    Gateway->>Auth: Validate JWT & 2FA Token
    Auth-->>Gateway: Token Valid
    Gateway->>Account: Process Transfer Request
    Account-->>Gateway: Transaction Completed
    Gateway-->>App: 200 OK (Receipt ID)
    App-->>User: Display Success Screen

```

---

## Case 2: E-Commerce Order Processing - State Diagram

```mermaid
stateDiagram-v2
    [*] --> PendingPayment
    PendingPayment --> PaymentApproved : Payment Verified
    PendingPayment --> Cancelled : Timeout / Failed
    PaymentApproved --> PreparingShipment : Inventory Reserved
    PreparingShipment --> Shipped : Carrier Picked Up
    Shipped --> Delivered : Customer Receipt Confirmed
    Delivered --> [*]
    Cancelled --> [*]

```
