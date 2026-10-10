
# Gatekeeper QA — Website Functional Requirements

**Version:** 0.1
**Status:** Approved - Development Baseline
**Related PRD:** product-requirements.md

## FR-001 — Global Navigation

The website shall provide consistent primary navigation across all primary pages.

Navigation destinations:
- Home
- Services
- How We Work
- About
- Case Study
- Book a QA Discovery Call

### Acceptance Criteria

- AC-001.1: Primary navigation is available on every primary page.
- AC-001.2: Selecting Services opens a page identifying QA Health Check, Release Readiness Testing, and Continuous QA Partnership.
- AC-001.3: Selecting the Gatekeeper QA logo navigates to Home.
- AC-001.4: Selecting Book a QA Discovery Call starts the Discovery Call journey.
- AC-001.5: On smaller viewports, every navigation destination remains accessible without horizontal page scrolling.
- AC-001.6: Each navigation destination opens its intended page with the correct page heading.
- AC-001.7: Navigation links remain functional on desktop and mobile viewports.
- AC-001.8: The current page is identifiable to users, including assistive technology.


## FR-002 — Primary Discovery Call CTA

The website shall provide a clearly identifiable Book a QA Discovery Call action at relevant conversion points.

### Acceptance Criteria

- AC-002.1: The primary navigation includes the Discovery Call CTA on all primary pages.
- AC-002.2: The Home hero contains the Discovery Call CTA.
- AC-002.3: Services, How We Work, and Case Study pages include a conversion CTA.
- AC-002.4: Selecting the CTA opens the qualification form.

## FR-003 — Discovery Call Qualification Form

The website shall collect minimum prospect information before allowing the visitor to access scheduling.

Required fields:
- Full Name
- Work Email
- Company Name
- Job Title / Role
- How can Gatekeeper QA help?

The problem description shall contain 20–1,000 characters after trimming leading and trailing whitespace.

### Acceptance Criteria

- AC-003.1: Valid input is accepted and the visitor proceeds to scheduling, not immediate booking confirmation.
- AC-003.2: A whitespace-only Company Name is rejected with a clear validation message.
- AC-003.3: If submission fails due to a server or network error, an error is displayed and entered information is preserved where possible.
- AC-003.4: The problem description must contain 20–1,000 characters after trimming.
- AC-003.5: A 19-character description is rejected with an appropriate minimum-length message.
- AC-003.6: A 1,001-character description is rejected with an appropriate maximum-length message.
- AC-003.7: An invalid email address is rejected without clearing other valid inputs.
- AC-003.8: Valid personal email domains, such as gmail.com, are accepted.
- AC-003.9: An empty Work Email is rejected with a clear required-field message.
- AC-003.10: Leading and trailing whitespace is normalized without removing legitimate internal spaces.
- AC-003.11: A description that falls below 20 characters after trimming is rejected.
- AC-003.12: Multiple invalid fields display their relevant errors together while preserving valid inputs.
- AC-003.13: Multiple rapid submissions result in only one qualification request and no duplicate downstream actions.
- AC-003.14: Each required field rejects an empty or whitespace-only value with a clear field-specific error.
- AC-003.15: A problem description containing exactly 20 characters is accepted.
- AC-003.16: A problem description containing exactly 1,000 characters is accepted.
- AC-003.17: The visitor cannot proceed to scheduling until the qualification request has been successfully processed.


## FR-004 — Third-Party Scheduling Integration

After successful qualification, the website shall direct the visitor to an approved third-party scheduling provider.

The scheduling provider has not yet been selected.

### Acceptance Criteria

- AC-004.1: If scheduling is unavailable, the visitor receives a clear error, no false booking confirmation, and a safe recovery option.
- AC-004.2: Available appointment times have identifiable timezones, and confirmed appointment details include accurate date, time, and timezone.
- AC-004.3: A single-capacity appointment cannot be successfully booked by two visitors. A visitor who loses the slot receives an unavailable-slot message and can select an alternative.
- AC-004.4: If a booking succeeds but its response is lost, recovery verifies the existing booking before attempting another, avoiding duplicates.
- AC-004.5: If booking status cannot be verified, the website does not claim success or failure and provides appropriate recovery guidance without automatically creating a duplicate booking.

## FR-005 — Booking Confirmation

The website shall display a clear booking confirmation only after the scheduling provider's successful booking has been verified.

### Acceptance Criteria

- AC-005.1: A successful confirmation is displayed only after verified booking success.
- AC-005.2: The confirmation displays accurate appointment date, time, and timezone.
- AC-005.3: A booking reference or provider confirmation identifier is displayed when available.
- AC-005.4: Refreshing the confirmation page does not trigger another booking.
- AC-005.5: If confirmation details cannot be verified, the visitor receives an honest status and recovery guidance instead of a false success message.


## FR-006 — Homepage Content

The Home page shall communicate Gatekeeper QA's value
proposition, core services, methodology, and evidence.

### Acceptance Criteria

- AC-006.1: The hero displays "Release Software With Confidence".
- AC-006.2: The hero displays "Book a QA Discovery Call" and "Explore Our Services".
- AC-006.3: Explore Our Services opens the Services page.
- AC-006.4: The page identifies all three core services.
- AC-006.5: The page introduces Gatekeeper QA's risk-based approach.
- AC-006.6: The page provides access to the Case Study page.

## FR-007 — Services Page

The Services page shall explain Gatekeeper QA's three
core Quality Engineering services.

### Acceptance Criteria

- AC-007.1: QA Health Check is identified and described.
- AC-007.2: Release Readiness Testing is identified and described.
- AC-007.3: Continuous QA Partnership is identified and described.
- AC-007.4: The page provides a Discovery Call CTA.

## FR-008 — How We Work Page

The How We Work page shall explain Gatekeeper QA's
five-stage client delivery methodology.

### Acceptance Criteria

- AC-008.1: The page presents Discover.
- AC-008.2: The page presents Assess & Prioritize Risk.
- AC-008.3: The page presents Test & Investigate.
- AC-008.4: The page presents Report & Recommend.
- AC-008.5: The page presents Improve & Measure.
- AC-008.6: The stages are presented in their intended order.

## FR-009 — About Page

The About page shall accurately represent Gatekeeper QA,
its founder, mission, vision, and values.

### Acceptance Criteria

- AC-009.1: The page describes Gatekeeper QA's mission.
- AC-009.2: The page describes its vision.
- AC-009.3: The page identifies its core values.
- AC-009.4: Founder and company information is factual.
- AC-009.5: The page does not imply an established team,
  client history, or credentials without evidence.

## FR-010 — Case Study Page

The Case Study page shall present genuine and
verifiable Quality Engineering evidence.

### Acceptance Criteria

- AC-010.1: Published outcomes are supported by evidence.
- AC-010.2: Hypothetical exercises are not represented
  as actual client results.
- AC-010.3: The page identifies the scope of the work.
- AC-010.4: The page distinguishes completed work
  from planned work.
- AC-010.5: The page includes a Discovery Call CTA.

## Open Decisions

- Select and validate the third-party scheduling provider.
- Define detailed field validation and security requirements.
- Define measurable non-functional acceptance criteria.
- Confirm the booking recovery mechanism supported by the selected provider.
- Define successful qualification processing for AC-003.17,
  including persistence or an approved provider handoff.
- Validate scheduling provider capabilities against
  AC-004.1 through AC-005.5 before booking functionality is released.

## Implementation Status

All requirements are drafted.

No website functionality has been implemented or tested against these requirements.
