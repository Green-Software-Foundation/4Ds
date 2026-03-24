---
title: "Responsible AI Procurement Guidelines"
facilitator: "Jamie Chen (jamie@techconsortium.org)"
lead: "Dr. Sarah Okonkwo (sarah@techconsortium.org)"
participants:
  - Participant A (enterprise procurement, financial services)
  - Participant B (AI/ML engineering, healthcare tech)
  - Participant C (legal/compliance, multinational corporation)
  - Participant D (sustainability officer, cloud provider)
  - Participant E (CTO, mid-size SaaS company)
  - Participant F (government technology advisor)
  - Participant G (independent AI ethics researcher)
  - Participant H (vendor relations, retail conglomerate)
  - Participant I (data protection officer, EU-based firm)
  - Participant J (open source programme office lead)
status: discover

# Rules
discover_quorum: "66%"
deliberate_quorum: "66%"
decide_quorum: "100%"
round_duration: "1 week"
max_discover_rounds: 3
max_deliberate_rounds: 3
max_decide_rounds: 3
---

## Deliverable

A "Responsible AI Procurement Guidelines" document for the Tech Consortium, providing member organisations with a practical framework for evaluating and selecting AI vendors and tools. The document will be published as a consortium recommendation and hosted on the consortium's website.

## Constraints

- **Jurisdiction neutrality** (policy): Guidelines must be applicable across jurisdictions. They may reference specific regulations (EU AI Act, NIST AI RMF) as examples but must not assume any single regulatory framework. Source: Consortium charter, Section 4.2.

- **Vendor neutrality** (scope): Guidelines must not name, recommend, or exclude specific vendors or products. Source: Consortium anti-trust policy.

- **Existing procurement compatibility** (technical): Guidelines must be implementable within existing enterprise procurement workflows. They should augment, not replace, current processes. Source: Member organisation feedback from Q1 survey.

- **SME accessibility** (policy): Guidelines must be usable by organisations without dedicated AI ethics teams. Complexity should not exclude small and medium enterprises. Source: Consortium inclusion mandate.

## Section Sequence

### 1. Scope and Applicability

**Depends on:** none
**Word count target:** 150-200 words

- **Purpose:** Define what counts as an "AI procurement decision" for the purposes of these guidelines and who should use them.
- **Contains:** Definition of AI procurement in this context, types of procurement covered (SaaS AI tools, custom model development, API services, embedded AI features), organisational contexts where these guidelines apply.
- **Does NOT contain:** Definitions of AI itself, technical taxonomy of AI systems, regulatory definitions.
- **Constraints:** Must cover both direct AI procurement (buying an AI product) and indirect AI procurement (buying a product that contains AI features).
- **Why this matters:** Without a clear scope, organisations won't know whether these guidelines apply to their specific purchasing decisions.
- **Connection to other sections:** Sets the boundary for all subsequent sections. Risk categories (Section 2) only apply within this scope.

### 2. Risk Categories

**Depends on:** Section 1
**Word count target:** 200-300 words

- **Purpose:** Define the categories of risk that AI procurement decisions should be assessed against.
- **Contains:** Risk categories with brief descriptions (e.g., bias and fairness risk, transparency and explainability risk, data governance risk, operational reliability risk, vendor lock-in risk, environmental impact risk). For each category: what it means, why it matters for procurement, a concrete example.
- **Does NOT contain:** Risk scoring methodologies, mitigation strategies (those come in Section 4), compliance checklists.
- **Constraints:** Categories must be assessable by procurement teams without deep technical AI expertise. Must align with (but not duplicate) ISO 42001 risk categories.
- **Why this matters:** Procurement teams need a structured way to think about AI-specific risks that go beyond traditional vendor assessment.
- **Connection to other sections:** These categories drive the evaluation framework (Section 3) and due diligence requirements (Section 4).

### 3. Evaluation Framework

**Depends on:** Sections 1 and 2
**Word count target:** 250-350 words

- **Purpose:** Provide a practical framework for assessing AI vendors and tools against the risk categories.
- **Contains:** Evaluation approach (how to assess each risk category), minimum information requirements (what vendors should disclose), red flags (what should disqualify a vendor), green flags (indicators of responsible AI practice), how to weight different risk categories based on use case.
- **Does NOT contain:** Specific questionnaire templates (those go in an appendix), scoring algorithms, vendor certification schemes.
- **Constraints:** Must be completable within a typical procurement timeline (weeks, not months). Must not require access to vendor IP or proprietary model details.
- **Why this matters:** The framework must be practical enough that procurement teams actually use it, rather than treating it as a compliance checkbox.
- **Connection to other sections:** Applies risk categories (Section 2) to specific procurement decisions. Informs due diligence (Section 4).

### 4. Due Diligence and Ongoing Governance

**Depends on:** Sections 1, 2, and 3
**Word count target:** 200-300 words

- **Purpose:** Define what happens after initial evaluation — the ongoing responsibilities for monitoring AI procurement decisions.
- **Contains:** Pre-contract due diligence requirements, contractual provisions to request (audit rights, model change notification, incident reporting), post-deployment monitoring expectations, review triggers (when to re-evaluate an existing AI vendor), escalation paths when issues are discovered.
- **Does NOT contain:** Legal contract templates, specific SLA requirements, technical monitoring implementations.
- **Constraints:** Must be proportionate to the risk level identified in Section 3. Low-risk procurements should have lighter governance than high-risk ones.
- **Why this matters:** AI systems change over time (model updates, data drift, capability changes). Procurement is not a one-time decision.
- **Connection to other sections:** Completes the lifecycle: scope (Section 1) → identify risks (Section 2) → evaluate (Section 3) → govern (Section 4).

## DISCOVER Questions (Section 1)

### Round 1

[To be generated by the Discover prompt]

### Follow-up rounds

[To be designed based on Round 1 synthesis]
