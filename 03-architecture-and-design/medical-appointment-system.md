# Medical Appointment System - Software Architecture

## 1. Architectural Style & Overview

The Medical Appointment System utilizes a Service-Oriented / Microservices Architecture to separate scheduling, notification, electronic health record (EHR) integration, and patient identity management.

## 2. Core Architectural Components

* **API Gateway:** Handles routing, authentication (JWT), and rate limiting.
* **Appointment Service:** Core microservice managing doctor availability, slot booking, and cancellation rules.
* **Notification Service:** Asynchronous messaging worker consuming events from RabbitMQ/Kafka to send SMS and email reminders.
* **EHR Integration Adapter:** Interface layer integrating with HL7/FHIR legacy health databases.

## 3. Architecture Overview Diagram

```mermaid
graph TD
    Client[Mobile App / Web UI] -->|HTTPS / REST| Gateway[API Gateway]
    Gateway -->|Auth Check| AuthService[Identity Service]
    Gateway -->|Manage Slots| ApptService[Appointment Service]
    ApptService -->|Publish Event| MessageQueue[(RabbitMQ / Kafka)]
    MessageQueue -->|Consume Event| NotificationService[Notification Service]
    NotificationService -->|Send Reminders| ExternalSMS[SMS / WhatsApp Provider]
    ApptService -->|Read/Write| ApptDB[(PostgreSQL)]
