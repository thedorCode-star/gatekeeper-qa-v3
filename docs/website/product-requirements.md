
# Gatekeeper QA — Website MVP Product Requirements

**Document status:** Approved - Development Baseline
**Product:** Gatekeeper QA Website
**Version:** 0.1

## 1. Product Vision

Build a professional B2B Quality Engineering website that helps startups and growing software businesses understand Gatekeeper QA's services, evaluate its approach, and request a QA Discovery Call.

## 2. Problem Statement

Growing software teams may lack independent quality assurance, clear visibility into release risks, and sufficient testing capacity.

The website must explain how Gatekeeper QA helps these teams identify quality risks and make informed release decisions.

## 3. Target Users

Primary:
- CTOs
- Heads of Engineering
- Technical founders

Secondary:
- Startup founders
- Engineering and product managers
- Software developers

## 4. Business Goals

- Establish Gatekeeper QA's professional credibility.
- Explain the company's services and methodology.
- Generate qualified Discovery Call requests.
- Demonstrate real Quality Engineering evidence through a case study.
- Support future client acquisition.


### Success Indicators

The website's effectiveness will be evaluated using:

- Number of qualified Discovery Call requests per month.
- Percentage of visitors who start and complete the qualification form.
- Number of successfully verified Discovery Call bookings.
- Publication of at least one genuine, evidence-backed Gatekeeper QA case study.
- Availability of clear descriptions for all three core services.

Numerical conversion targets will be established after initial usage data is available.

These indicators measure website performance and business outcomes. They do not represent guaranteed results.


## 5. MVP Scope

### Included

- Home
- Services
- How We Work
- About
- Case Study
- Discovery Call qualification form
- Third-party scheduling integration
- Booking confirmation

### Deferred

- Blog
- Public pricing page
- Client portal
- Custom scheduling engine
- Online payments
- AI chatbot

## 6. Core Services

1. QA Health Check
2. Release Readiness Testing
3. Continuous QA Partnership

## 7. Customer Journey

Visitor arrives on the website
→ Understands Gatekeeper QA
→ Explores services and methodology
→ Reviews available evidence
→ Selects Book a QA Discovery Call
→ Completes qualification form
→ Selects an available appointment
→ Receives verified booking confirmation


The website must also support unsuccessful or interrupted
qualification and booking journeys. Visitors must receive
accurate feedback when validation fails, scheduling is
unavailable, or booking confirmation cannot be verified.
An unverified booking must never be presented as confirmed.


## 8. Product Quality Attributes

- Performance
- Accessibility
- Security
- Responsive design
- Cross-browser compatibility
- Reliability
- Search engine optimization

Detailed, measurable criteria will be defined in the Non-Functional Requirements document.

## 9. Functional Requirements

See `functional-requirements.md`.

Current drafted requirements:

- FR-001 — Global Navigation
- FR-002 — Primary Discovery Call CTA
- FR-003 — Discovery Call Qualification Form
- FR-004 — Third-party Scheduling Integration
- FR-005 — Booking Confirmation

## 10. Constraints and Open Decisions

- The scheduling provider has not yet been selected.
- Booking confirmation must be based on verified provider success.
- Gatekeeper QA must not claim fabricated results or testimonials.
- The website must accurately represent the company's current capabilities.
- Technology and deployment decisions require implementation validation.


## 11. Website Content and Messaging

The Home page shall use the following primary messaging:

- Hero headline: Release Software With Confidence
- Primary CTA: Book a QA Discovery Call
- Secondary CTA: Explore Our Services

The website shall communicate Gatekeeper QA's risk-based approach and its three core services.

## 12. Case Study Evidence Policy

The Case Study page shall present genuine evidence from Gatekeeper QA's work.

Evidence may include requirements, risk assessments, test execution results, automation reports, CI/CD outcomes, and release recommendations.

Hypothetical training exercises must not be presented as real client outcomes.

Unverified testimonials, fabricated metrics, and unsupported claims are prohibited.

## 13. Privacy and Data Handling

Before the Discovery Call form is released:

- Define the purpose of collecting prospect information.
- Collect only information necessary for qualification and scheduling.
- Define appropriate access, storage, retention, and deletion controls.
- Inform visitors how their information will be used.
- Review data sharing with the selected scheduling provider.
- Define security and privacy acceptance criteria.

## 14. Document Governance

Product Owner: Gatekeeper QA Founder
Document status: Approved — Development Baseline
Approval date: 2026-10-10

Outstanding decisions must be documented and assessed before affected functionality is released.

## 15. Acceptance and Approval

This PRD is in initial development baseline as approved, with outstanding decisions tracked as release dependencies.

Requirements will be reviewed before Jira implementation stories are finalized. Implementation and testing evidence will be linked through the requirements traceability process.
