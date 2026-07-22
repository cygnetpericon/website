---
title: Products
subtitle: Components of the CygnetONE Platform
version: 0.1.0
status: Draft
owner: Hendra Suhartanto
reviewers:
  - TBD
last_updated: 2026-07-22
category: Collection
audience:
  - Executive
  - Enterprise Architect
  - Product Manager
  - Solution Architect
---

# Products

> Individually powerful. Collectively transformative.

The CygnetONE platform is composed of a family of products that address different aspects of Regulatory Intelligence.

Each product has a distinct responsibility, yet they are designed to work together through shared knowledge, common metadata, and consistent architectural principles.

Rather than operating as isolated applications, the products form a coherent platform that enables organizations to understand regulations, manage regulatory knowledge, execute compliance processes, and continuously adapt to regulatory change.

---

# Product Architecture

The products naturally align with the architectural layers of the CygnetONE platform.

```
Knowledge
    │
    ▼
Information
    │
    ▼
Execution
    │
    ▼
Applications
```

---

# Knowledge Layer

The Knowledge Layer captures and manages regulatory knowledge independently from implementation technology.

## CRRR

**Compliance Requirements & Regulatory Repository**

CRRR provides a structured repository for regulatory publications, business concepts, reporting requirements, validation rules, reference data, and regulatory metadata.

It represents the authoritative source of regulatory knowledge used throughout the platform.

---

# Information Layer

The Information Layer transforms regulatory knowledge into consistent business information models.

## RRDF

**Regulatory Reporting Data Foundation**

RRDF defines the canonical information model required for regulatory reporting.

It provides a standardized representation of regulatory concepts independent of operational source systems.

---

## CBDF

**Cygnet Banking Data Foundation**

CBDF extends the canonical model beyond regulatory reporting to support broader banking data domains and enterprise-wide compliance capabilities.

---

# Execution Layer

The Execution Layer provides reusable capabilities that execute regulatory knowledge.

## CDAP

**Compliance Data Asset Platform**

CDAP provides metadata-driven execution services including data validation, transformation, metadata management, workflow integration, and extensibility for compliance solutions.

---

## CRTP

**Compliance Regression Testing Platform**

CRTP automates testing and validation of regulatory implementations, ensuring that regulatory changes can be introduced safely and consistently.

---

# Application Layer

Applications combine execution capabilities into complete business solutions.

## CRRS

**Cygnet Regulatory Reporting Solution**

CRRS is an end-to-end regulatory reporting application built upon the CygnetONE platform.

Its core capabilities include:

- GoETL — Data acquisition and transformation
- GoDQ — Data quality and regulatory validation
- GoReport — Regulatory reporting generation and submission
- GoWFM — Workflow orchestration and operational management

Together these components provide a complete operational environment for regulatory reporting.

---

# Shared Philosophy

Although each product serves a different purpose, they all share the same architectural principles.

- Knowledge before execution
- Metadata over hard-coded logic
- Explainability by design
- Traceability across the lifecycle
- Compliance by construction

Every product contributes to a common body of regulatory knowledge.

---

# Related Collections

To learn more about the ideas behind these products, explore the **Philosophy** collection.

To understand the overall architecture, continue to the **Platform** collection.

For implementation technologies, see the **Technology** collection.

---

> **Knowledge Once. Execution Everywhere.**
