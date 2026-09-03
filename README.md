# 🎓 Software Engineering Academic Repository

[![Degree](https://img.shields.io/badge/Degree-Systems_Analysis_%26_Development_(ADS)-blue.svg?style=for-the-badge&logo=academic-pages)](https://www.ceub.br)
[![Course](https://img.shields.io/badge/Course-Software_Engineering-00599C.style=for-the-badge&logo=diagramsdotnet)](https://github.com/oThiagoDSS)
[![Status](https://img.shields.io/badge/Status-Completed-brightgreen.svg?style=for-the-badge)]()
[![License](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![Mermaid](https://img.shields.io/badge/Diagrams-Mermaid.js-ff69b4.svg?style=for-the-badge&logo=mermaid)](https://mermaid.js.org/)

This repository contains the complete academic coursework, technical documentation, UML 2.0 diagrams, architectural designs, requirements specifications, and case studies developed for the **Software Engineering** discipline in the **Systems Analysis and Development (ADS)** undergraduate program at **CEUB**.

---

## 📌 Course Overview & Objectives

The primary objective of this discipline is to instill solid software engineering principles, covering the complete Software Development Life Cycle (SDLC):
* **Requirements Engineering:** Elicitation, analysis, classification (User, System, Functional, Non-Functional), and validation.
* **Systems Modeling:** Object-Oriented Analysis & Design (OOAD) using standard UML 2.0 notation (Use Cases, Class Diagrams, Sequence Diagrams).
* **Software Architecture & Component Design:** Monolithic vs. Microservices, RESTful API design, Component Diagrams, and Entity-Relationship Modeling (ERD).
* **Quality Assurance, DevOps & Maintenance:** CI/CD pipelines, deployment strategies (Canary, Blue/Green), ITIL 4 Change Management, and maintenance classification.
* **Capstone Project Integration:** Real-world application of software engineering methodologies to build production-ready platforms.

---

## 📑 Coursework Index & Navigation

| Module / Topic | Description | Core Artifacts / Tools | Link |
| :--- | :--- | :--- | :---: |
| **01. Requirements Engineering** | University Party App MVP proposal & classification of 5 complex real-world case studies. | User/System Requirements, FR/NFR Elicitation, Risk Matrix | [View Folder](./01-requirements-engineering/) |
| **02. UML Modeling (SiCAd & Case Studies)** | Modeling an Academic Control System (SiCAd), Delivery, Digital Banking, and Ride-Hailing platforms. | Use Case, Class, & Sequence Diagrams (StarUML / Mermaid) | [View Folder](./02-uml-modeling/) |
| **03. Architecture & Component Design** | Full technical stack modeling for Healthcare, Library, IT Service Desk, and Delivery systems. | Component Diagrams, C4/Layered Architecture, Flowcharts, ERD | [View Folder](./03-architecture-and-design/) |
| **04. Testing, DevOps & ITIL** | Domain software applications study & CrowdStrike outage incident response analysis. | CI/CD Pipelines, Canary Releases, ITIL 4, Maintenance Types | [View Folder](./04-testing-devops-and-maintenance/) |
| **05. Capstone Project** | Integrated final platform (**PsiCare**) for a real-world client. | PRD, Wireframes, Test Plans, Backlog, Class Diagrams | [PsiCare Repository](https://github.com/oThiagoDSS/psicare-platform) |

---

## 📊 Visual Diagram Highlights

All diagrams in this repository are authored in **Mermaid.js**, rendering natively in GitHub Markdown. Raw image assets exported from modeling tools are archived in [`/docs/assets`](./docs/assets).

### Academic Control System (SiCAd) - Class Diagram Preview
```mermaid
classDiagram
    class Person {
        #String name
        #String address
        #String phone
        +register() void
    }
    class Student {
        -String registrationId
        +enrollCourse() void
        +suspend() void
        +graduate() void
        +getEvaluations() void
        +generateTranscript() void
    }
    class Professor {
        -String maxDegree
        +register() void
        +submitGrades() void
    }
    Person <|-- Student
    Person <|-- Professor
