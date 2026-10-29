# Title & Parcel Diligence Intelligence Platform

An independent project developing an AI-assisted approach to title and parcel document review, with evidence traceability, explicit uncertainty, and human oversight built into the architecture.

**Author:** Payton K. Maurer  
**Status:** In development — validation foundation implemented  
**Technologies:** Python, JSON Schema  
**Repository:** Public project overview; implementation code and underlying case materials remain private.

## Overview

Title and parcel diligence requires reconciling information across documents that may contain inconsistent identifiers, conflicting ownership claims, incomplete authority records, or unresolved legal-description questions.

The challenge extends beyond extracting facts. Reviewers need to understand what the evidence supports, where uncertainty remains, and what must happen next.

This project is designed around a complete review lifecycle:

**Evidence → Decision → Resolution**

The intended platform helps qualified professionals connect each finding to its supporting evidence, recommended action, actual remediation, and remaining risk.

## My Contribution

I defined the product scope, system architecture, and governance requirements, translating complex diligence needs into structured data contracts and testable validation behavior.

My work includes:

- Designing contracts for candidate case data, findings, source provenance, and review requirements.
- Defining boundaries between extraction, deterministic validation, AI-assisted interpretation, and professional judgment.
- Implementing a Python conformance validator with 12 checks and automated unit tests.
- Developing evaluation requirements that distinguish structural correctness from substantive evidence sufficiency.

The project extends my enterprise analytics background in measurement strategy, data quality, and governance into AI-assisted decision systems.

## Current Implementation

The implemented foundation focuses on validating structured findings before downstream use.

| Component | Implemented scope |
|---|---|
| Data contracts | Machine-readable schemas and controlled vocabulary for candidate cases and findings. |
| Conformance validator | Twelve checks addressing structure, collection consistency, reference integrity, grounding prerequisites, and an authority-related consistency constraint. |
| Evaluation reporting | Explicit outcomes for passed, failed, not-applicable, and not-evaluated checks. |
| Automated tests | Unit tests covering validation behavior, dependencies, malformed inputs, reference resolution, and reporting boundaries. |

**Passing these checks does not establish that a finding is factually correct, legally sufficient, or fully compliant with every platform requirement.** The validator explicitly reports incomplete evaluations and requirements that remain partially supported or deferred.

The broader document-processing and AI interpretation workflow is still in development.

## Intended Architecture

The architecture separates document processing, validation, interpretation, and decision authority.

| Layer | Intended responsibility |
|---|---|
| Ingestion and extraction | Identify document types, capture candidate facts, and retain source references. |
| Normalization | Standardize identifiers and values while preserving original evidence and competing claims. |
| Deterministic validation | Apply explicit rules and consistency checks that can be tested in code. |
| Controlled AI interpretation | Support semantic reconciliation, explanation, and synthesis where deterministic rules are insufficient. |
| Findings and review | Present evidence, uncertainty, conflicts, and escalation requirements for professional assessment. |
| Resolution tracking | Distinguish recommended actions, completed actions, unresolved issues, and residual risk. |

**AI interprets; code calculates.**

The design favors deterministic logic wherever a requirement can be expressed and tested reliably. AI-assisted interpretation is reserved for tasks requiring contextual understanding or synthesis.

The architecture is intended to remain model-agnostic, keeping business rules, schemas, and evaluation criteria independent of individual model providers.

## Key Design Decisions

### Preserve evidence and uncertainty

Material facts and findings should retain references to their supporting documents, locations, and relevant text. Conflicting information should remain available for review rather than being silently overwritten.

The system distinguishes **“not found in the supplied record”** from **“does not exist.”** Missing documentation is not proof that the underlying fact or document does not exist elsewhere.

### Separate extraction from decision authority

Extraction produces candidate facts and evidence links. It does not independently establish legal sufficiency, final transaction disposition, or approval to proceed.

Material ambiguity and final professional determinations remain subject to human review.

### Evaluate source authority in context

A source may support one conclusion without supporting another. For example, a routing record may show who received a document for signature without establishing that person’s authority to sign.

The design preserves that distinction instead of treating every source as equally authoritative.

### Keep recommendations separate from outcomes

Recommended remediation, actual remediation, resolution status, and residual risk are separate concepts.

A transaction proceeding does not establish that an underlying issue was cured. Likewise, mitigation does not automatically mean full resolution.

### Make validation limits visible

Structural validity and evidence sufficiency answer different questions. A well-formed finding with resolvable references may still require substantive review.

The validator therefore distinguishes failed checks from checks that could not be evaluated and reports the limits of its coverage.

## Evaluation Approach

The evaluation design examines intermediate evidence handling as well as final findings. Producing the expected risk label alone is insufficient.

Representative scenarios include:

| Scenario | Intended behavior |
|---|---|
| Unverified signing authority | Preserve uncertainty and require review rather than infer authority from transaction completion. |
| Conflicting parcel identifiers with subsequent remediation | Retain the discrepancy, distinguish recommended from actual remediation, and preserve residual risk. |
| A case without a material title defect | Avoid treating ordinary commercial revisions as title defects. |

These scenarios define expected behavior for development and future evaluation. They are not claims of completed end-to-end platform validation.

Current automated testing focuses on the implemented conformance validator.

## Development Roadmap

Planned work includes:

- Expanding normalization and deterministic diligence rules.
- Evaluating findings against curated benchmark cases.
- Adding controlled AI-assisted extraction and interpretation.
- Developing resolution tracking and reviewer workflows.

Production interfaces, cloud deployment, broad jurisdiction coverage, and autonomous outbound actions remain outside the current implementation.

The immediate objective is to establish reliable, repeatable handling of structured evidence before expanding automation.

## Scope and Access

This platform is intended to assist qualified professionals. It does not provide legal opinions, title insurance commitments, or independent determinations of marketable title.

This repository presents the project’s purpose, architecture, implementation scope, and design decisions. Source code and underlying case materials are maintained separately in a private repository.

## About the Author

**Payton K. Maurer** is a Senior Digital Analytics Consultant whose work connects enterprise measurement strategy, data governance, technical implementation, and business decision support.

[Connect on LinkedIn](https://www.linkedin.com/in/paytonmaurer/)
