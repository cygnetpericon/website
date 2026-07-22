# Content Lifecycle

## Purpose

This document describes how ideas evolve into published knowledge within the
Cygnet Knowledge Program.

The repository is intentionally organized so that knowledge progresses through
a series of stages before it becomes part of the public website.

---

## Lifecycle

Experience
      │
      ▼
Idea
      │
      ▼
Draft
      │
      ▼
Review
      │
      ▼
Published
      │
      ▼
Rendered
      │
      ▼
Feedback
      │
      ▼
Experience

---

## Stage 1 – Idea

Ideas may originate from:

- Customer implementations
- Regulatory changes
- Product development
- Internal discussions
- Research
- Industry trends

At this stage, ideas may exist only as notes or conversations.

---

## Stage 2 – Draft

Drafts are working documents.

Drafts are written, refined, and reviewed before publication.

Examples:

- New philosophy paper
- Product description
- Technology article

Drafts may initially reside in the `docs/` directory or a feature branch.

---

## Stage 3 – Review

During review, the document is evaluated for:

- Technical accuracy
- Consistency
- Writing style
- Cross references
- Metadata completeness

Documents remain unpublished until approved.

---

## Stage 4 – Published

Once approved, documents become part of the official knowledge base.

Published documents live under `content/`.

Each document belongs to a single collection.

Examples:

- philosophy/
- platform/
- products/
- technology/
- knowledge/
- case-studies/

---

## Stage 5 – Rendered

Astro consumes the published Markdown content and renders it into the website.

Markdown is the source of truth.

The website is simply one presentation of that knowledge.

---

## Guiding Principles

Knowledge is authored before it is presented.

Presentation should never become the primary source of truth.

Every published document has exactly one canonical location.

Knowledge evolves through versioning rather than replacement.

The repository reflects the editorial process.

The website is not the product of the writing process; it is the presentation layer of the knowledge repository.
