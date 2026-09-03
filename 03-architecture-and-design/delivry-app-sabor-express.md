# Delivery App (Sabor Express) - Software Architecture

## 1. Architectural Domain

A high-concurrency, real-time food delivery architecture incorporating geospatial tracking, order dispatching, and dynamic delivery status synchronization.

## 2. Real-Time Tracking & Event Processing

* **WebSockets / gRPC:** Establishes low-latency persistent connections for live courier GPS tracking.
* **Event Sourcing:** Records all order state transitions chronologically to handle order dispute resolutions.
* **CQRS Pattern (Command Query Responsibility Segregation):** Separates high-frequency read operations (menu views, tracking) from write operations (order checkout, payment processing).

## 3. High-Level System Architecture

```mermaid
graph TD
    CustomerApp[Customer App] -->|Order Command| Gateway[API Gateway]
    DriverApp[Courier App] -->|GPS Stream via WebSocket| StreamServer[Real-Time Ingestion Server]
    Gateway -->|Process Payment| OrderService[Order Service]
    OrderService -->|Publish Order Placed| EventBus[Event Bus / NATS]
    EventBus -->|Notify Store| RestaurantApp[Restaurant Dashboard]
    StreamServer -->|Push Location Updates| Redis[(Redis Geospatial Cache)]
    Redis -->|Read Position| CustomerApp
