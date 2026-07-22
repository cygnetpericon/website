---
title: Terminology
subtitle: Canonical Vocabulary for the CygnetONE Platform
version: 0.1.0
status: Draft
owner: Hendra Suhartanto
reviewers:
  - TBD
last_updated: 2026-07-22
category: Architecture
audience:
  - Business Analyst
  - Enterprise Architect
  - Software Engineer
  - Product Manager
---

# Terminology

> A common language is essential for building a shared understanding.

This document defines the canonical vocabulary used throughout the CygnetONE platform and its associated documentation.

Its purpose is to ensure that business analysts, regulatory specialists, architects, software engineers, testers, implementation partners, and customers use the same terminology when discussing Regulatory Intelligence.

---

# Why Terminology Matters

Complex systems are often difficult not because they contain complicated technology, but because different people use the same words to mean different things.

A shared vocabulary:

- Improves communication
- Reduces ambiguity
- Simplifies documentation
- Encourages consistency
- Supports knowledge reuse

Every document within the Cygnet ecosystem should use the definitions contained in this glossary unless explicitly stated otherwise.

---

# The Three Layers of Regulatory Intelligence

The CygnetONE platform is founded on the distinction between three complementary layers:

1. **Knowledge**
2. **Information**
3. **Execution**

Each layer serves a different purpose and should evolve independently.

Understanding this distinction is fundamental to the platform architecture.

---

## Knowledge

Knowledge describes **what** must be done and **why**.

It captures regulatory intent, business meaning, obligations, interpretations, and governance.

Knowledge answers questions such as:

- What does the regulation require?
- Why does this rule exist?
- What business concept is being described?
- How should the requirement be interpreted?

Examples include:

- Regulations
- Regulatory requirements
- Business concepts
- Regulatory interpretations
- Validation rules
- Business rules
- Reference definitions
- Glossaries

Knowledge is independent of technology.

---

## Information

Information describes **how knowledge is represented**.

It provides structured, governed representations that software can understand and process consistently.

Information answers questions such as:

- How is this concept represented?
- What attributes describe it?
- How are concepts related?
- Which data elements are required?

Examples include:

- Metadata
- Canonical Information Models
- Canonical Data Models
- Reference Data
- Data Dictionaries
- Mapping Specifications

Information translates knowledge into structured form.

---

## Execution

Execution describes **how information is applied**.

Execution engines consume structured information to automate regulatory processes.

Execution answers questions such as:

- How is the rule evaluated?
- How is data transformed?
- How is validation performed?
- How are reports generated?

Examples include:

- Validation engines
- Reporting engines
- Workflow engines
- ETL pipelines
- Testing frameworks
- AI assistants

Execution technology may change over time.

Knowledge and Information should remain stable.

---

These three layers can be visualized as:

```
Knowledge
    │
    ▼
Information
    │
    ▼
Execution
```

This separation enables the platform to evolve while preserving regulatory knowledge and business meaning.

---

# Core Concepts

## Regulation

A formal requirement issued by a regulatory authority that establishes obligations, constraints, reporting requirements, or supervisory expectations.

Examples include central bank regulations, financial reporting standards, prudential regulations, and internal governance policies.

---

## Regulatory Requirement

A specific obligation derived from a regulation that can be interpreted, implemented, validated, tested, and audited.

Regulatory requirements represent the bridge between published regulations and executable implementation.

---

## Regulatory Knowledge

The collective understanding required to satisfy regulatory obligations.

Regulatory knowledge includes:

- Business concepts
- Definitions
- Interpretations
- Validation rules
- Calculations
- Reference data
- Reporting structures
- Implementation decisions

Regulatory knowledge is the primary asset managed by the CygnetONE platform.

---

## Regulatory Intelligence

The discipline of capturing, organizing, governing, and applying regulatory knowledge as structured metadata so that it can be consistently reused across reporting, validation, testing, workflow, analytics, documentation, and AI-assisted processes.

Regulatory Intelligence treats regulatory knowledge as an enterprise asset rather than embedding it within individual applications.

---

# Knowledge Concepts

## Knowledge Asset

Any reusable artifact that captures regulatory or business knowledge.

Examples include:

- Business rules
- Metadata
- Validation rules
- Test cases
- Data models
- Reference data
- Documentation

Knowledge assets are intended to be shared across multiple platform capabilities.

---

## Metadata

Structured information that describes business meaning, relationships, behavior, governance, and context.

Metadata enables both people and software to interpret information consistently.

Metadata extends beyond technical schemas to include business semantics and regulatory intent.

---

## Structured Metadata

Metadata represented using a consistent, governed, machine-readable structure that supports execution, traceability, versioning, and reuse.

---

## Metadata Repository

A governed repository that stores structured metadata and associated knowledge assets.

The repository acts as the authoritative source for regulatory knowledge.

---

# Information Concepts

## Business Concept

A real-world concept recognized by the business domain.

Examples include:

- Customer
- Account
- Facility
- Collateral
- Exposure
- Product

Business concepts are independent of implementation technology.

---

## Canonical Information Model

A technology-independent representation of business concepts and their relationships.

Its purpose is to establish a shared understanding across operational systems and platform capabilities.

---

## Canonical Data Model

The logical or physical implementation of the Canonical Information Model.

It provides a consistent data structure that supports integration and execution.

---

## Reference Data

Controlled values used to classify or interpret business information.

Examples include:

- Currency codes
- Country codes
- Industry classifications
- Regulatory classifications

Reference data should be governed and versioned.

---

# Platform Concepts

## Platform

A collection of interoperable capabilities built upon shared knowledge assets.

A platform is more than a collection of independent products.

---

## Platform Capability

A functional area that contributes to the overall platform.

Examples include:

- Knowledge management
- Data integration
- Validation
- Testing
- Reporting

---

## Platform Component

A deployable software element that implements one or more platform capabilities.

---

## Execution Engine

A software component responsible for executing structured metadata.

Examples include:

- Reporting engines
- Validation engines
- Workflow engines
- Transformation engines
- AI assistants

Execution engines consume knowledge rather than own it.

---

# Architectural Concepts

## Single Source of Truth

The principle that every business concept should have one authoritative definition.

---

## Semantic Fidelity

The preservation of business meaning throughout the lifecycle of regulatory knowledge.

Changes in representation should never alter the intended meaning of a regulatory concept.

---

## Traceability

The ability to follow a regulatory concept from its origin through interpretation, metadata, implementation, validation, testing, reporting, and audit.

---

## Explainability

The ability to understand and justify why a particular regulatory outcome was produced.

Explainability includes visibility into rules, source data, metadata, calculations, and decision history.

---

# CygnetONE Components

## CygnetONE

The unified platform for Metadata-Driven Regulatory Intelligence.

CygnetONE provides the architectural framework within which all platform capabilities operate.

---

## CRRR

Compliance Requirements & Regulatory Repository.

CRRR captures and governs regulatory knowledge, including regulations, interpretations, metadata, validation rules, expressions, reference data, and implementation guidance.

CRRR is the platform's primary knowledge repository.

---

## RRDF

Regulatory Reporting Data Foundation.

RRDF defines the canonical data structures required to support regulatory reporting.

---

## CBDF

Cygnet Banking Data Foundation.

CBDF extends RRDF by providing a broader canonical information model for banking data beyond regulatory reporting.

---

## CDAP

Compliance Data Asset Platform.

CDAP provides the platform capabilities required to transform operational data into governed compliance assets using metadata-driven processes.

---

## CRTP

Compliance Regression Testing Platform.

CRTP automates validation, regression testing, and certification of compliance implementations.

---

## GoDQ

A data quality execution engine that evaluates data against metadata-driven validation rules.

---

## GoReport

A reporting execution engine that transforms governed data into regulatory submissions.

---

# Preferred Vocabulary

To maintain consistency, the following terminology is preferred throughout Cygnet documentation.

| Prefer | Avoid |
|---------|-------|
| Regulatory Knowledge | Business Logic |
| Knowledge Asset | Configuration |
| Platform Capability | Module |
| Platform Component | Program |
| Execution Engine | Processing Engine |
| Metadata Repository | Rules Database |
| Canonical Information Model | Intermediate Model |
| Structured Metadata | Hard-coded Configuration |
| Regulatory Requirement | Report Field |
| Business Concept | Table Definition |

---

# Guiding Principle

The terminology defined in this document is intended to evolve as the platform matures.

Changes should be made deliberately and consistently, recognizing that language shapes architecture, and architecture shapes implementation.

> **Knowledge Once. Execution Everywhere.**

---

# Appendix A — Concept Relationships

The following diagrams illustrate how the principal concepts within the CygnetONE platform relate to one another.

## Regulatory Knowledge Lifecycle

```
Regulation
      │
      ▼
Regulatory Requirement
      │
      ▼
Regulatory Knowledge
      │
      ▼
Structured Metadata
      │
      ▼
Knowledge Asset
      │
      ▼
Platform Capability
      │
      ▼
Platform Component
      │
      ▼
Execution Engine
```

This lifecycle illustrates how regulatory intent is transformed into executable platform capabilities while preserving business meaning.

---

## Information Lifecycle

```
Business Concept
      │
      ▼
Canonical Information Model
      │
      ▼
Canonical Data Model
      │
      ▼
Operational Data
      │
      ▼
Regulatory Reporting
```

This lifecycle illustrates how business concepts are represented consistently before being consumed by reporting and other execution processes.

---

## Regulatory Intelligence Architecture

```
               Regulations
                    │
                    ▼
          Regulatory Knowledge
                    │
                    ▼
          Structured Metadata
                    │
                    ▼
      Canonical Information Model
                    │
                    ▼
         Canonical Data Model
                    │
                    ▼
          Platform Capabilities
                    │
                    ▼
          Platform Components
                    │
                    ▼
            Execution Engines
                    │
                    ▼
 Reporting • Validation • Testing
 Workflow • Analytics • AI
```

The architecture emphasizes that execution technologies consume structured knowledge rather than embedding regulatory logic directly into software.

---

## Knowledge Flow

```
Understand
      │
      ▼
Interpret
      │
      ▼
Structure
      │
      ▼
Execute
      │
      ▼
Validate
      │
      ▼
Learn
      │
      ▼
Improve Knowledge
```

This continuous cycle reflects the philosophy of **Regulatory Intelligence**, where every implementation and every regulatory change contributes to an evolving body of governed knowledge.
