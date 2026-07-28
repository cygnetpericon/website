---
title: CRRS Security
version: 0.1.0
status: Draft
owner: Hendra Suhartanto
reviewers:
  - TBD
last_updated: 2026-07-28
---

# CRRS Security

> Security principles, not a compliance attestation.

**A note on this page:** this describes the security principles CRRS is designed around. It intentionally does not list specific certifications, audit results, or compliance attestations (e.g. ISO 27001, SOC 2) — those claims must come from actual audit and certification status, confirmed with the security and compliance team before publication. Do not publish specific certification claims on this page until they are verified.

---

# Security as a Design Principle

CRRS handles regulatory reporting data for financial institutions, which means the data it processes is often sensitive by nature — customer information, transaction detail, exposure data. Security is treated as a platform design principle rather than a feature added on top.

This follows from the same architectural principles the platform is built on: explainability, traceability, and compliance by construction apply as much to how the platform protects data as to how it reports on it.

---

# Traceability as a Security Property

Because every value in a CRRS-generated report is traceable back through transformation and validation to its source, the platform provides visibility into exactly where a piece of data came from and how it was handled — a property that supports both security review and audit, not just regulatory explainability.

---

# Application Security Testing

CRRS undergoes static application security testing (SAST) and dynamic application security testing (DAST) as part of every major release.

Findings are tracked through a remediation process before the release ships — issues identified during SAST/DAST are not left open in production code. The bar for a production release is zero unresolved high or critical severity findings.

This is a release-gating practice, not a point-in-time audit: security testing is repeated for every major release rather than performed once and assumed to hold indefinitely.

---

# Authentication and Authorization via LDAP

CRRS integrates with a bank's LDAP server for both authentication and authorization — not just to verify identity, but to determine what a user is allowed to do within the application.

CRRS periodically synchronizes with the organization and group information held in the bank's LDAP server, so a user's role in CRRS reflects their current position in the organization rather than a role assigned once and left stale:

- If a user moves department, the next sync reassigns them to the role group appropriate to their new department.
- If a user is promoted — for example, from maker/user to supervisor/approver — the next sync updates their CRRS permissions to match, without requiring a manual, out-of-band access change inside CRRS itself.

This keeps CRRS's access model aligned with the bank's own organizational structure and reporting lines, rather than requiring a parallel, manually-maintained set of user permissions that can drift out of sync with who actually holds which role.

---

# Metadata-Driven Access Considerations

Because CRRS's behavior is governed by metadata (in CRRR, RRDF, and CBDF) rather than scattered application code, access to that metadata is a meaningful control point: who can define or change a validation rule, a canonical model, or a reporting requirement is itself a security-relevant decision, distinct from who can access reported data.

The specific encryption approach and infrastructure security posture for a given CRRS deployment depend on the deployment environment and should be documented separately with confirmed technical detail.

---

# What Belongs on This Page

Once confirmed with the security and compliance team, this page should be expanded to cover:

- Data encryption in transit and at rest
- Audit logging and retention
- Data residency and deployment model
- Applicable certifications and compliance attestations
- Incident response process

---

# Related Documentation

- [CRRS](/products/crrs) — product overview.
- [CRRS Operations](/products/crrs/operations) — operational procedures, including monitoring and logging.
