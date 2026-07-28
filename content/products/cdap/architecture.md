---
title: CDAP Architecture
version: 0.1.0
status: Draft
owner: Hendra Suhartanto
reviewers:
  - TBD
last_updated: 2026-07-28
---

# CDAP Architecture

> How CDAP's execution services are structured.

---

# Service Areas

CDAP is organized around four service areas, each consuming metadata from the Knowledge and Information layers rather than embedding logic directly.

```mermaid
flowchart TD
    Metadata["CRRR / RRDF / CBDF metadata"] --> Validation["Validation Service"]
    Metadata --> Transformation["Transformation Service"]
    Metadata --> MetadataMgmt["Metadata Management Service"]
    Metadata --> Workflow["Workflow Integration"]
```

**Validation Service** — evaluates data against rules defined in CRRR, applied to data represented in RRDF/CBDF's canonical models.

**Transformation Service** — converts operational, source-system-shaped data into the canonical models defined by RRDF/CBDF.

**Metadata Management Service** — the runtime layer that resolves and serves metadata from CRRR, RRDF, and CBDF to the other services.

**Workflow Integration** — exposes CDAP's services so external orchestration tools (such as Apache Airflow) can sequence them as part of a larger process.

---

# Request Flow

A typical validation or transformation request flows through CDAP as follows:

```mermaid
flowchart TD
    A["Request arrives (validate or transform)"] --> B["Metadata Management Service resolves relevant rules/models"]
    B --> C["Validation or Transformation Service applies them to the data"]
    C --> D["Result returned with traceability back to the source metadata"]
```

Every result CDAP produces is traceable back to the specific piece of metadata that produced it — which rule failed validation, or which canonical field a value was mapped to — rather than being an opaque pass/fail.

---

# Pluggable Execution Technology

CDAP's service areas are implemented on top of interchangeable execution technology. The service interface stays stable even as the underlying engine changes — CDAP is execution-engine agnostic by design.

```mermaid
flowchart TD
    CDAPServices["CDAP Services"] --> GE["Great Expectations"]
    CDAPServices --> DBT["dbt"]
    CDAPServices --> AF["Apache Airflow"]
    CDAPServices --> ORA["Oracle"]
    CDAPServices --> REG["Regnology"]
    CDAPServices --> AXI["AxiomSL"]
```

Today, only Great Expectations is actually wired up behind this interface — built independently, separate from CRRS's GoDQ validation service. The others illustrate what the pluggable architecture is designed to accommodate, not current capability.

This is what allows CygnetONE to adopt new execution technology over time without changing how solutions like CRRS interact with CDAP.

---

# Design Goals

- **Metadata-driven** — behavior is configured by CRRR/RRDF/CBDF metadata, not hard-coded per requirement.
- **Traceable** — every validation or transformation result links back to the metadata that produced it.
- **Technology-agnostic** — service interfaces are stable independent of the underlying execution engine.
- **Composable** — services can be called individually or orchestrated together via workflow integration.

---

# Related Documentation

- [CDAP](/products/cdap) — product overview.
- [Execution Layer](/platform/execution-layer) — the architectural role CDAP implements.
