# Gatekeeper QA — Quality Engineering Methodology & Delivery Workflow

## 1. Purpose

The purpose of the Gatekeeper QA Quality Engineering Methodology is to provide a structured, repeatable, and risk-based approach for delivering quality engineering services to software teams.

The methodology ensures that Gatekeeper QA understands the product, users, business objectives, requirements, and critical workflows before testing begins.

It provides a consistent process for identifying and prioritizing quality risks, planning and executing testing, collecting evidence, managing defects, assessing release readiness, and continuously improving product quality.

Gatekeeper QA uses this methodology to help clients make informed release decisions based on evidence and business risk rather than defect counts alone.

The methodology is designed to support collaboration between Gatekeeper QA, developers, product teams, and business stakeholders while maintaining an independent quality perspective.

## 2. Quality Engineering Principles

Gatekeeper QA applies the following principles throughout every Quality Engineering engagement.

### 2.1 Quality Is a Shared Responsibility

Quality is not the responsibility of QA alone. Developers, product teams, business stakeholders, and QA contribute to delivering reliable software.

Gatekeeper QA works collaboratively with client teams while maintaining an independent quality perspective.

### 2.2 Understand Before Testing

Testing should not begin without sufficient understanding of the product, its users, business objectives, requirements, and critical workflows.

When requirements are unclear or incomplete, Gatekeeper QA will clarify and document them with the appropriate client stakeholders rather than inventing expected business behavior.

### 2.3 Test Based on Risk

Testing effort should be prioritized according to risk rather than treating every feature equally.

Gatekeeper QA considers factors such as:

- Business impact
- Customer impact
- Likelihood of failure
- Critical user journeys
- Recent code or configuration changes
- System dependencies
- Financial, data, security, and operational consequences

A simple risk model may be expressed as:

**Risk = Impact × Likelihood**

### 2.4 Prevent Defects, Not Just Find Them

The purpose of Quality Engineering is not to maximize the number of defects reported.

Gatekeeper QA aims to identify risks early, clarify requirements, improve testability, prevent recurring problems, and reduce the likelihood of defects reaching customers.

### 2.5 Evidence Over Assumptions

Quality findings and release recommendations should be supported by evidence.

Evidence may include test results, reproduction steps, screenshots, screen recordings, API responses, network information, logs, transaction records, environment details, and other relevant technical information.

Gatekeeper QA should clearly distinguish confirmed findings from assumptions or areas requiring further investigation.

### 2.6 Release Decisions Are Risk-Based

Test completion does not automatically mean that a product is ready for release.

Gatekeeper QA evaluates open defects, affected workflows, business impact, customer impact, available workarounds, test coverage, unresolved risks, and other relevant evidence before providing a release recommendation.

Gatekeeper QA may provide one of the following recommendations:

- **RELEASE**
- **RELEASE WITH KNOWN RISK**
- **HOLD**

Gatekeeper QA provides the quality recommendation. The authorized client stakeholder remains responsible for the final business release decision.

### 2.7 Retesting and Regression Serve Different Purposes

Retesting confirms whether a specific reported defect has been successfully fixed.

Regression testing evaluates whether a change or fix has negatively affected other functionality.

Regression scope should be selected according to the risk, affected components, dependencies, and significance of the change rather than automatically executing the entire test suite after every fix.

### 2.8 Quality Must Continuously Improve

Testing does not end when a release reaches production.

Gatekeeper QA reviews testing outcomes, escaped defects, recurring defects, process weaknesses, release problems, and other relevant evidence to identify opportunities for improvement.

Where appropriate, improvements should be implemented and measured in future delivery cycles.

## 3. Client Engagement & Kickoff

The Client Engagement & Kickoff phase establishes a shared understanding between Gatekeeper QA and the client before Quality Engineering activities begin.

The objective is to understand why the client requires QA support, establish the engagement scope, identify key stakeholders, understand the delivery environment, and confirm the information and access required for the engagement.

### 3.1 Kickoff Participants

Relevant participants may include:

- Gatekeeper QA Lead or assigned QA Engineer
- CTO or Head of Engineering
- Product Manager or Product Owner
- Engineering representative
- Founder or business stakeholder when relevant
- Other technical or business stakeholders required for the engagement

Attendance should be based on the needs of the engagement. Not every stakeholder needs to participate in every meeting.

### 3.2 Business and Product Context

Gatekeeper QA should understand:

- What the product does
- Why the product exists
- Who the primary users are
- What business problem the product solves
- Which workflows are most important to customers
- Which workflows are most important to the business
- Upcoming releases, features, or significant changes
- Known quality concerns or previous production incidents

### 3.3 Engagement Objectives

Gatekeeper QA and the client should establish why the engagement is taking place.

Examples may include:

- Assessing the current quality of a product
- Supporting an upcoming release
- Reducing production defects
- Testing a new feature
- Improving regression coverage
- Establishing a QA process
- Evaluating release risk
- Improving existing quality practices

The engagement objective should be clear enough to guide the later risk assessment and test strategy.

### 3.4 Scope and Boundaries

The initial engagement scope should identify:

- Products, modules, or features included
- Platforms included, such as web, mobile, or API
- Relevant browsers, devices, and operating systems
- Environments available for testing
- Features or activities explicitly excluded
- Known time, resource, or technical constraints

Scope may be refined after Product and Requirements Discovery identifies additional information or risks.

### 3.5 Existing Quality and Delivery Process

Gatekeeper QA should understand how the client currently develops, tests, and releases software.

Relevant questions may include:

- How frequently does the team release?
- Who currently performs testing?
- What testing is already performed?
- What environments exist?
- How are builds deployed?
- How are defects reported and tracked?
- Are automated tests already available?
- Is CI/CD being used?
- What quality problems have occurred in previous releases?

This information helps Gatekeeper QA complement the client's existing process rather than unnecessarily replacing it.

### 3.6 Documentation and Access

Gatekeeper QA may request access to relevant resources such as:

- Requirements and acceptance criteria
- Jira or another work management system
- Test environments
- Test accounts and user roles
- Existing test cases
- API documentation
- Architecture or technical documentation
- Previous defect reports
- Release notes
- Logs or monitoring information where appropriate
- Source repositories or CI/CD systems where required by the engagement

Gatekeeper QA should request only the access necessary to perform the agreed work.

Credentials, secrets, production data, and other sensitive information must be handled according to the client's approved security and access procedures.

### 3.7 Communication and Responsibilities

The kickoff should establish:

- Primary client contact
- Requirement and product decision-maker
- Technical contact
- Defect escalation process
- Communication channels
- Reporting frequency
- Expected response times where necessary
- Person authorized to make the final release decision

Gatekeeper QA provides quality findings and release recommendations but does not replace the client's authority over business release decisions.

### 3.8 Kickoff Outputs

The kickoff should conclude with documented actions and owners.

Expected outputs may include:

- Confirmed engagement objective
- Initial scope
- Identified stakeholders and responsibilities
- Required access and documentation
- Known constraints
- Initial quality concerns
- Communication and reporting approach
- Outstanding questions
- Assigned actions and owners
- Agreed next steps

The completion of the kickoff does not mean that testing begins immediately.

Gatekeeper QA proceeds to Product, Business & Requirements Discovery to review and validate the information received before finalizing the risk assessment and test plan.

## 4. Product, Business & Requirements Discovery

The Product, Business & Requirements Discovery phase ensures that Gatekeeper QA develops sufficient understanding of the product, its users, business objectives, requirements, and critical workflows before finalizing the testing strategy.

The objective is to reduce assumptions, identify missing or ambiguous requirements, understand expected product behavior, and establish a reliable basis for risk assessment and test design.

### 4.1 Product Understanding

Gatekeeper QA should understand:

- What the product does
- Why the product exists
- Who uses the product
- What users are trying to accomplish
- What business outcomes the product supports
- Which workflows are critical to the product
- Which integrations or external systems are important
- Which areas have historically experienced quality problems

Product understanding may be developed through documentation review, stakeholder discussions, product demonstrations, exploratory product review, and examination of existing work items.

### 4.2 Requirements Review

Gatekeeper QA should review available requirements and supporting documentation.

Sources may include:

- Jira work items
- User stories
- Acceptance criteria
- Product requirements
- Business rules
- Design specifications
- API documentation
- Existing test cases
- Release notes
- Technical documentation
- Previous defects
- Stakeholder explanations

Requirements should be reviewed for clarity, completeness, consistency, and testability.

### 4.3 Requirements Clarification

When a requirement is vague, incomplete, contradictory, or not testable, Gatekeeper QA should raise questions with the appropriate stakeholder before making assumptions about expected behavior.

For example, a requirement such as:

> "Customer should be able to pay an invoice."

does not provide enough information to fully understand the expected behavior.

Gatekeeper QA may clarify questions such as:

- Must the invoice be paid in full?
- Are partial payments supported?
- Which payment methods are supported?
- What happens after successful payment?
- What happens when payment fails?
- What happens when payment status is uncertain?
- How are duplicate payment attempts prevented?
- What happens if the customer clicks Pay multiple times?
- How should an already-paid invoice behave?
- Is a payment confirmation required?
- How quickly should a confirmation notification be sent?
- What happens if notification delivery fails?

The answers become part of the agreed expected behavior and may later be transformed into acceptance criteria and test scenarios.

### 4.4 Missing Requirements

Gatekeeper QA may help identify, structure, and document missing requirements but must not independently invent client business rules.

When important behavior is undocumented, Gatekeeper QA should:

1. Review available evidence and documentation.
2. Explore the existing product behavior where appropriate.
3. Identify missing or ambiguous information.
4. Ask the appropriate stakeholder for clarification.
5. Draft the clarified requirement or acceptance criteria when useful.
6. Obtain stakeholder validation of the expected behavior.
7. Test against the agreed requirement.

The authorized client stakeholder remains the source of truth for business decisions and expected product behavior.

### 4.5 Acceptance Criteria

Requirements should be translated into clear and testable acceptance criteria where appropriate.

Acceptance criteria should describe observable expected behavior and reduce ambiguity between business, product, engineering, and QA.

Gatekeeper QA may use Behavior-Driven Development (BDD) style and Gherkin syntax where it improves clarity.

A common structure is:

- **Given** — the initial state or precondition
- **When** — the action or event
- **Then** — the expected outcome
- **And / But** — additional conditions or outcomes

Example:

```gherkin
Feature: Invoice Payment

Scenario: Customer successfully pays an invoice
  Given the customer has an unpaid invoice with an outstanding balance of $100
  When the customer pays the full $100 using a valid payment method
  Then the invoice status should be "Paid"
  And the "Pay" button should not be displayed
  And the payment confirmation email should be sent within 2 minutes
```

### 4.6 Critical Workflow Identification

During discovery, Gatekeeper QA should identify workflows where failure could significantly affect customers or the business.

Examples may include:

- Authentication
- Registration
- Checkout
- Billing and payment
- Subscription management
- Data creation or modification
- Critical API integrations
- Customer onboarding
- Account access
- Business-specific core workflows

A workflow should not be classified as critical solely because it appears important to QA. Business impact should be confirmed with appropriate stakeholders when necessary.

### 4.7 Discovery Outputs

Expected outputs from this phase may include:

- Improved understanding of the product and users
- Reviewed requirements
- Clarified business rules
- Identified missing or ambiguous requirements
- Validated acceptance criteria
- Identified critical user and business workflows
- Known integrations and dependencies
- Documented assumptions and open questions
- Initial quality risks requiring further assessment

These outputs become inputs to the Quality Risk Assessment & Prioritization phase.

## 5. Quality Risk Assessment & Prioritization

The Quality Risk Assessment & Prioritization phase determines where testing effort should be concentrated based on the potential impact and likelihood of product failure.

Gatekeeper QA does not assume that every feature requires the same level of testing. Testing priority should reflect the risk that a failure presents to customers and the business.

### 5.1 Risk Identification

Gatekeeper QA should identify potential quality risks using information gathered during kickoff and discovery.

Risk indicators may include:

- Business-critical functionality
- Customer-critical workflows
- Financial transactions
- Authentication and authorization
- Sensitive or important data
- New functionality
- Recently changed functionality
- Complex business logic
- External integrations
- Frequently failing components
- Areas with previous production incidents
- High-usage functionality
- Dependencies between systems or components
- Regulatory, security, or operational concerns where applicable

### 5.2 Risk Assessment

Gatekeeper QA evaluates identified risks using two primary factors:

- **Impact** — How serious would the consequences be if the functionality failed?
- **Likelihood** — How likely is the functionality to fail?

A simple risk model may be expressed as:

**Risk = Impact × Likelihood**

Risk assessment should use available evidence and business context rather than QA assumptions alone.

### 5.3 Impact Assessment

Impact considers the consequences of failure.

Questions may include:

- Would customers be unable to use the product?
- Would a critical business workflow be blocked?
- Could revenue or payments be affected?
- Could customer or business data be lost or corrupted?
- Could many users be affected?
- Could the failure damage customer trust?
- Could the issue create security, compliance, or operational consequences?
- Is there an acceptable workaround?

Impact may be classified as:

| Level | Description |
|---|---|
| High | Failure could significantly affect customers, revenue, data, security, or a critical business workflow. |
| Medium | Failure causes meaningful disruption, but core business operations can continue or a reasonable workaround exists. |
| Low | Failure has limited business or customer impact and does not prevent important workflows. |

### 5.4 Likelihood Assessment

Likelihood considers the probability that a failure may occur.

Factors may include:

- Recent code changes
- New functionality
- Technical complexity
- Number of dependencies
- Previous defects
- Historical instability
- Integration changes
- Limited previous test coverage
- Configuration changes
- Significant data variations

Likelihood may be classified as:

| Level | Description |
|---|---|
| High | Failure is reasonably likely because of significant change, complexity, instability, or previous problems. |
| Medium | Some factors increase the possibility of failure, but evidence does not indicate consistently high instability. |
| Low | Functionality is stable, unchanged, well understood, and has a strong history of successful operation. |

### 5.5 Risk Matrix

Gatekeeper QA may combine Impact and Likelihood to establish testing priority.

| Impact | Likelihood | Risk Priority |
|---|---|---|
| High | High | Critical |
| High | Medium | High |
| High | Low | Medium |
| Medium | High | High |
| Medium | Medium | Medium |
| Medium | Low | Low |
| Low | High | Medium |
| Low | Medium | Low |
| Low | Low | Low |

The risk priority guides testing effort. It does not automatically determine defect severity or release decisions.

Risk priority, defect severity, and defect priority are related but distinct concepts:

- **Risk Priority** determines where testing effort should be focused before and during testing.
- **Defect Severity** describes the impact of an identified defect on the system, users, or business.
- **Defect Priority** describes how urgently an identified defect should be addressed.

A defect found in a high-risk area is not automatically a high-severity defect. Each defect must be assessed according to its actual impact and context.

### 5.6 Risk-Based Test Prioritization

Higher-risk areas should generally receive earlier and deeper testing.

Testing priority may influence:

- Test execution order
- Exploratory testing effort
- Regression coverage
- Negative testing
- API testing
- Automation priority
- Performance testing
- Browser or device coverage
- Integration testing
- Amount of evidence required

For example, if Billing contains recently changed payment logic and failure could prevent customers from paying, it may receive a higher testing priority than an unchanged low-impact reporting feature.

### 5.7 Dependencies and Change Analysis

Risk should not be assessed only at the individual feature level.

Gatekeeper QA should consider dependencies between components and the potential impact of changes on connected functionality.

For example:

**Login → Account → Billing → Payment Provider**

A change to authentication may affect downstream workflows even if those workflows were not directly modified.

This information should influence regression scope and test prioritization.

### 5.8 Unknown Risk

When Gatekeeper QA does not have enough information to determine business impact or expected behavior, the missing information should not be replaced with assumptions.

The appropriate stakeholder should be consulted where possible.

Unknown or unresolved risks should be documented and considered when evaluating test coverage and release readiness.

### 5.9 Risk Assessment Outputs

Expected outputs may include:

- Identified product and quality risks
- Impact assessments
- Likelihood assessments
- Risk priorities
- Critical workflows requiring focused testing
- Dependencies requiring regression coverage
- Areas requiring additional clarification
- Recommended testing priorities

These outputs become inputs to the Test Planning & Preparation phase.

## 6. Test Planning & Preparation

The Test Planning & Preparation phase defines how Gatekeeper QA will perform testing based on the engagement objectives, agreed scope, identified requirements, available resources, and assessed product risks.

The test plan should provide enough direction for testing to be controlled, traceable, and aligned with business priorities without creating unnecessary documentation.

### 6.1 Test Objectives

The test objective defines what the testing activity is intended to achieve.

Objectives should be specific to the engagement and aligned with identified business and product risks.

Examples may include:

- Validate critical customer workflows before release
- Identify high-impact product risks
- Verify new or changed functionality
- Evaluate regression risk
- Assess release readiness
- Validate critical integrations
- Provide evidence to support a release decision

The objective should not be defined simply as "find all bugs," because testing cannot guarantee that every defect will be discovered.

### 6.2 Test Scope

The test plan should clearly identify what is included and excluded from the testing activity.

#### In Scope

Examples may include:

- Authentication and login
- Billing and payment
- New customer import functionality
- Critical user journeys
- Recently changed functionality
- Targeted regression testing
- Relevant API behavior

#### Out of Scope

Examples may include:

- Full performance testing
- Full security penetration testing
- Unsupported browsers or devices
- Unchanged low-risk functionality
- Features unavailable in the test environment

Out-of-scope items should be documented so that stakeholders understand the boundaries of the testing performed.

### 6.3 Test Approach

The test approach defines which testing techniques will be used to address the identified risks.

Depending on the engagement, the approach may include:

- Functional testing
- Exploratory testing
- Regression testing
- Negative testing
- API testing
- Integration testing
- Cross-browser testing
- Responsive testing
- Accessibility testing
- Performance testing
- Automated testing

Gatekeeper QA should select testing techniques according to product risk and engagement needs rather than applying every available testing type to every project.

### 6.4 Test Environment

The test plan should identify the environment in which testing will be performed.

Relevant information may include:

- Environment name, such as QA, Staging, or UAT
- Application build or version
- Application URL
- Browser versions
- Operating systems
- Mobile devices where applicable
- API environment
- External service integrations
- Environment-specific limitations

Testing should normally be performed in an approved non-production environment unless production testing has been explicitly authorized and appropriately controlled.

### 6.5 Test Data

Gatekeeper QA should identify the data required to execute planned testing.

Examples may include:

- Test user accounts
- Different user roles and permissions
- Paid and unpaid invoices
- Valid and invalid payment data
- Customer records
- Boundary-value data
- API request data
- Integration test data

Test data should support positive, negative, boundary, and risk-based scenarios where appropriate.

Sensitive production data should not be used unless specifically authorized and handled according to applicable client security and privacy requirements.

### 6.6 Schedule and Test Prioritization

Testing activities should be scheduled according to available time, dependencies, release deadlines, and risk priority.

Higher-risk functionality should generally be tested earlier so that significant problems are discovered with enough time for investigation, correction, and retesting.

The schedule should allow time for:

- Test preparation
- Test execution
- Defect investigation and reporting
- Developer fixes where applicable
- Retesting
- Risk-based regression
- Final reporting and release assessment

Testing should not consume the entire available release window without leaving reasonable time for defect resolution and verification.

### 6.7 Entry Criteria

Entry criteria define the minimum conditions that should be satisfied before planned test execution begins.

Examples may include:

- Testable build is deployed
- Required environment is available
- Required access has been provided
- Test accounts are available
- Critical requirements have been sufficiently clarified
- Required test data is available
- Known environment blockers have been resolved
- Relevant integrations are available or limitations documented

If entry criteria are not satisfied, Gatekeeper QA should assess whether testing can proceed safely or whether the limitation should be escalated and documented.

### 6.8 Exit Criteria

Exit criteria define the conditions used to determine when the planned testing cycle can be considered complete.

Examples may include:

- Planned critical tests have been executed
- Agreed testing scope has been sufficiently covered
- Critical and High defects have been assessed
- Required defect retesting has been completed where possible
- Appropriate regression testing has been performed
- Known unresolved defects and risks are documented
- Test evidence has been collected
- QA results are ready for reporting and release assessment

Meeting exit criteria means that the planned testing activity has reached its defined completion conditions.

It does not automatically mean that Gatekeeper QA recommends releasing the product.

### 6.9 Test Plan Outputs

Expected outputs may include:

- Test objectives
- In-scope and out-of-scope areas
- Selected testing approaches
- Test environment information
- Required test data
- Test schedule and priorities
- Entry criteria
- Exit criteria
- Known constraints and assumptions
- Identified dependencies

These outputs provide the foundation for Test Design & Acceptance Criteria.

## 7. Test Design & Acceptance Criteria

The Test Design & Acceptance Criteria phase transforms agreed requirements, business rules, identified risks, and critical workflows into structured and traceable test scenarios.

Gatekeeper QA designs tests to validate expected behavior, investigate important risks, and provide sufficient coverage of the agreed testing scope.

### 7.1 Test Design Inputs

Test design may use information from:

- Business and product requirements
- User stories
- Acceptance criteria
- Identified quality risks
- Critical user workflows
- Business rules
- API documentation
- Designs and specifications
- Previous defects
- Production incidents
- Change history
- Integration dependencies
- Exploratory testing findings

Test scenarios should be based on validated information rather than assumptions about expected business behavior.

### 7.2 Test Scenario Design

Gatekeeper QA should design scenarios that cover relevant expected and unexpected behavior.

Depending on the feature and associated risks, scenarios may include:

- Positive scenarios
- Negative scenarios
- Boundary conditions
- Error handling
- Validation rules
- User permissions and roles
- State transitions
- Integration behavior
- Data variations
- Retry behavior
- Duplicate actions
- Failure recovery
- Critical end-to-end workflows

Not every feature requires every scenario type. Test depth should reflect the assessed risk.

### 7.3 Positive and Negative Testing

Positive testing verifies that the system behaves correctly when valid inputs and expected user actions are used.

Negative testing evaluates how the system behaves when invalid inputs, unexpected actions, failures, or prohibited operations occur.

For example, for an invoice payment:

**Positive scenario:**

A customer successfully pays the full outstanding invoice using a valid payment method.

**Negative scenarios may include:**

- Payment is declined
- Partial payment is attempted when partial payments are not supported
- Customer attempts to pay an already-paid invoice
- Customer clicks Pay multiple times
- Payment status becomes uncertain
- Invalid payment information is submitted

Negative testing should focus on realistic risks rather than generating arbitrary invalid scenarios without purpose.

### 7.4 Acceptance Criteria

Acceptance criteria define observable conditions that must be satisfied for a requirement or behavior to meet the agreed expectation.

Good acceptance criteria should be:

- Clear
- Specific
- Testable
- Observable
- Relevant to the business requirement
- Agreed with the appropriate stakeholder when clarification is required

Acceptance criteria should reduce ambiguity between business, product, development, and QA.

### 7.5 BDD and Gherkin

Gatekeeper QA may use Behavior-Driven Development (BDD) techniques when they improve communication and make expected behavior easier to understand and test.

Gherkin may be used to express behavior using:

- **Given** — starting state or precondition
- **When** — action or event
- **Then** — expected result
- **And / But** — additional conditions or results

Example:

```gherkin
Feature: Invoice Payment

Scenario: Customer successfully pays an invoice
  Given the customer has an unpaid invoice with an outstanding balance of $100
  When the customer pays the full $100 using a valid payment method
  Then the invoice status should be "Paid"
  And the "Pay" button should not be displayed
  And the payment confirmation email should be sent within 2 minutes
```

BDD scenarios should describe business behavior rather than unnecessary UI or implementation details.

### 7.6 Optional BDD Automation Tooling

Cucumber may be used when executable BDD specifications provide value to the project.

Gatekeeper QA distinguishes between:

- **BDD** — the collaborative approach used to define expected behavior
- **Gherkin** — the language used to express behavior in Given/When/Then form
- **Cucumber** — a tool that can connect Gherkin scenarios to executable automation code

Using Gherkin does not require every scenario to be automated with Cucumber.

Cucumber should be introduced when it improves collaboration, traceability, maintainability, or automation value rather than being used solely because the tool is available.

### 7.7 Test Case Detail

Where formal test cases are required, they may contain:

- Test case identifier
- Test case title
- Requirement or story reference
- Risk or priority
- Preconditions
- Test data
- Test steps
- Expected results
- Environment
- Execution result
- Evidence
- Defect reference where applicable

The level of documentation should reflect the engagement, product risk, client requirements, and need for repeatability.

### 7.8 Requirements Traceability

Where appropriate, Gatekeeper QA should maintain traceability between:

**Requirement → Acceptance Criteria → Test Scenario/Test Case → Test Result → Defect**

For example:

```text
Requirement: BILL-001
      ↓
Acceptance Criteria: AC-001
      ↓
Test Case: TC-BILL-001
      ↓
Execution: FAILED
      ↓
Defect: BUG-BILL-014
```

Traceability helps determine whether important requirements have been tested and provides evidence of what was validated.

### 7.9 Exploratory Testing

Structured test cases should not eliminate exploratory testing.

Gatekeeper QA may use exploratory testing to investigate risks, unexpected behavior, workflow combinations, usability concerns, and conditions that predefined test cases may not cover.

Exploratory testing should be purposeful and guided by product knowledge and identified risks.

Important findings should be documented with sufficient evidence and traceability.

### 7.10 Test Design Review

Before or during execution, high-risk scenarios should be reviewed where appropriate to confirm that:

- Critical requirements are covered
- High-risk workflows receive sufficient attention
- Important negative scenarios are included
- Required test data is available
- Dependencies are considered
- Ambiguous expected results have been clarified

### 7.11 Test Design Outputs

Expected outputs may include:

- Test scenarios
- Formal test cases where required
- Acceptance criteria
- BDD/Gherkin scenarios where appropriate
- Exploratory testing charters
- Test data requirements
- Requirements-to-test traceability
- Prioritized test coverage

These outputs become inputs to Test Execution & Evidence Collection.

## 8. Test Execution & Evidence Collection

The Test Execution & Evidence Collection phase validates the product against agreed requirements, acceptance criteria, identified risks, and planned test scenarios.

Gatekeeper QA executes testing systematically while remaining alert to unexpected behavior and emerging risks.

The objective is not simply to mark tests as passed or failed. Testing should produce reliable evidence that helps the client understand product quality, investigate defects, and make informed decisions.

### 8.1 Test Execution

Testing should be performed according to the agreed test plan, risk priorities, and available testing window.

Higher-risk functionality should generally be executed earlier.

During execution, Gatekeeper QA should:

- Confirm the correct environment and application version
- Verify required preconditions
- Use appropriate test data
- Execute planned scenarios
- Perform exploratory testing where appropriate
- Compare actual behavior with agreed expected behavior
- Record test results
- Investigate unexpected behavior
- Capture relevant evidence
- Identify new risks discovered during testing

Test execution should remain adaptable. If testing reveals a significant new risk, Gatekeeper QA may adjust testing priorities and investigate the affected area more deeply.

### 8.2 Test Result Classification

Executed tests should have a clear status.

Common statuses may include:

- **Passed** — Actual behavior matches the expected result.
- **Failed** — Actual behavior does not match the expected result.
- **Blocked** — Testing cannot continue because of an external dependency, environment issue, unavailable functionality, or another blocker.
- **Not Executed** — The test has not yet been performed.
- **Not Applicable** — The test does not apply to the current build, configuration, scope, or environment.

The reason for Blocked or Not Applicable results should be documented where relevant.

### 8.3 Investigating Unexpected Behavior

Unexpected behavior should not automatically be reported as a confirmed product defect.

Gatekeeper QA should first investigate sufficiently to determine whether the behavior may be caused by:

- A product defect
- Incorrect test data
- Environment configuration
- An external dependency
- An unclear requirement
- An expected business rule
- User permissions
- Network or service availability
- Test execution error
- Another known limitation

When the cause cannot yet be confirmed, the finding should be documented as requiring investigation rather than presented as a confirmed conclusion.

### 8.4 Reproduction

When a potential defect is identified, Gatekeeper QA should attempt to reproduce the behavior where practical.

Reproduction helps determine:

- Whether the issue occurs consistently
- Which conditions trigger the issue
- Whether specific data is required
- Whether the problem is environment-specific
- Whether particular browsers or devices are affected
- Whether the issue affects multiple user roles
- Whether an integration or dependency contributes to the behavior

Reproducibility should be documented when reporting the defect.

An issue that cannot be consistently reproduced should not automatically be ignored. Intermittent failures may represent significant quality risks and should be investigated according to their potential impact.

### 8.5 Evidence Collection

Gatekeeper QA should collect sufficient evidence to support important test results and defect findings.

Evidence may include:

- Screenshots
- Screen recordings
- Test execution results
- Browser and operating system information
- Application version or build number
- Timestamps
- Console errors
- Network requests and responses
- API requests and responses
- HTTP status codes
- Application logs where available
- Relevant database evidence where authorized
- Transaction or correlation identifiers
- Test data references
- CI/CD execution results
- Performance results where applicable

Evidence should be relevant to the finding. Collecting excessive information that does not help reproduce, investigate, or understand the issue should be avoided.

### 8.6 Technical Evidence

Where appropriate, Gatekeeper QA should investigate beyond the visible user interface.

For example, if a customer attempts to pay an invoice and the application displays:

> "Payment Failed"

the visible message alone may not explain what occurred.

Gatekeeper QA may review:

- Browser network activity
- Payment API response
- HTTP status
- Request and response data
- Console errors
- Application logs
- Transaction identifiers
- Relevant timestamps

This may reveal that the payment provider successfully processed the charge while the application failed to update the invoice correctly.

Gatekeeper QA should report the observed evidence without assigning technical blame to a specific component or team unless the evidence supports that conclusion.

### 8.7 Evidence Quality

Evidence should be:

- Relevant
- Clear
- Traceable
- Reproducible where possible
- Associated with the correct environment and build
- Sufficient to support investigation
- Free from unnecessary sensitive information

Screenshots and recordings should clearly show the relevant behavior.

Logs, API responses, or network evidence should include enough context to support investigation without unnecessarily exposing credentials, tokens, personal information, or other sensitive data.

### 8.8 Evidence and Sensitive Information

Gatekeeper QA should handle evidence according to the client's security and privacy requirements.

Evidence should not unnecessarily expose:

- Passwords
- Authentication tokens
- API keys
- Payment card information
- Personally identifiable information
- Confidential customer information
- Production secrets
- Other restricted business data

Sensitive information should be masked, redacted, or excluded where appropriate.

### 8.9 Test Traceability

Where appropriate, test execution results should remain traceable to the requirement, risk, acceptance criterion, or test scenario being validated.

For example:

```text
Requirement: BILL-001
      ↓
Acceptance Criteria: AC-001
      ↓
Test Case: TC-BILL-001
      ↓
Execution Result: FAILED
      ↓
Evidence: Network response + screen recording
      ↓
Defect: BUG-BILL-014
```

Traceability helps Gatekeeper QA and the client understand what was tested, what failed, and which evidence supports the finding.

### 8.10 Exploratory Findings

During exploratory testing, Gatekeeper QA may identify risks or behaviors that were not covered by predefined test cases.

Important exploratory findings should be documented with sufficient context, including:

- Area explored
- Test conditions
- Observed behavior
- Expected behavior where known
- Relevant evidence
- Associated risk
- Follow-up action where required

Exploratory testing should produce useful information rather than undocumented ad hoc activity.

### 8.11 New Risks During Execution

Testing may reveal risks that were not identified during initial planning.

For example, testing one payment scenario may reveal unexpected behavior in invoice status synchronization.

Gatekeeper QA should:

1. Document the newly identified risk.
2. Assess its potential impact and likelihood.
3. Determine whether testing priorities should change.
4. Inform relevant stakeholders when the risk is significant.
5. Expand or adjust testing where justified and within the agreed engagement constraints.

This allows the testing strategy to respond to evidence rather than remaining fixed when new information becomes available.

### 8.12 Test Execution Outputs

Expected outputs may include:

- Test execution results
- Pass, fail, blocked, and other relevant statuses
- Exploratory testing findings
- Screenshots and recordings
- API and network evidence
- Logs and technical evidence where available
- Reproduction information
- Newly identified risks
- Defect candidates
- Updated test coverage information

Confirmed defects proceed into the Defect Management, Retesting & Regression process.

## 9. Defect Management, Retesting & Regression

The Defect Management, Retesting & Regression phase ensures that confirmed product defects are clearly documented, appropriately assessed, communicated to the relevant stakeholders, verified after correction, and followed by appropriate regression testing.

Gatekeeper QA treats defect management as a collaborative Quality Engineering activity rather than a process for assigning blame.

The objective is to provide developers and stakeholders with sufficient information to understand the problem, evaluate its impact, reproduce it where possible, resolve it efficiently, and understand any remaining product risk.

### 9.1 Defect Confirmation

Before reporting unexpected behavior as a confirmed defect, Gatekeeper QA should investigate whether the behavior conflicts with an agreed requirement, acceptance criterion, business rule, or established expected behavior.

Where practical, Gatekeeper QA should:

- Reproduce the behavior
- Confirm the environment and build
- Verify the test data
- Review relevant requirements
- Check known limitations
- Collect supporting evidence
- Determine the affected workflow
- Identify conditions that trigger the problem

If expected behavior remains unclear, clarification should be obtained from the appropriate stakeholder rather than making an unsupported assumption.

### 9.2 Defect Report

A professional defect report should provide enough information for the issue to be understood, reproduced, investigated, and assessed.

A defect report may include:

- Defect identifier
- Clear and specific title
- Requirement, story, or test case reference
- Environment
- Application version or build
- Preconditions
- Test data where appropriate
- Steps to reproduce
- Expected result
- Actual result
- Reproducibility
- Severity
- Priority where applicable
- Business or customer impact
- Supporting evidence
- Technical evidence where available
- Related defects or dependencies
- Reporter
- Date and time where relevant

Defect reports should be factual and concise.

Titles such as:

> "Payment broken"

should be avoided.

A more useful title would be:

> "Invoice remains Unpaid after payment provider confirms successful charge"

The second title communicates the affected functionality and observed failure without making unsupported assumptions about the root cause.

### 9.3 Defect Severity

Severity describes the impact of the defect on the product, users, or business.

Gatekeeper QA may use the following severity model:

| Severity | General Meaning |
|---|---|
| Critical | Failure causes severe business or customer impact, such as preventing a critical workflow, creating serious financial or data risk, or making the product substantially unusable, with no acceptable workaround. |
| High | Significant functionality is affected and the impact is substantial, but the product or business may continue operating with limitations or a workaround. |
| Medium | Functionality is affected, but the impact is moderate and important workflows can generally continue. |
| Low | Limited-impact issue that does not significantly affect important workflows, such as a minor visual or content problem. |

Severity should be determined from actual impact and context rather than solely from the technical nature of the defect.

### 9.4 Defect Priority

Priority describes how urgently a defect should be addressed.

Priority may be influenced by:

- Severity
- Release timing
- Number of affected customers
- Business commitments
- Availability of a workaround
- Frequency of occurrence
- Regulatory or operational deadlines
- Dependency on other work
- Strategic importance of the affected functionality

Severity and priority are related but are not identical.

For example, a relatively low-severity defect on a highly visible customer-facing page may receive higher repair priority because of an imminent release or important business event.

Final repair priority may be determined collaboratively with product, engineering, and business stakeholders.

### 9.5 Defect Triage

Defect triage is the process of reviewing reported defects to determine their validity, impact, urgency, ownership, and next action.

During triage, relevant participants may review:

- Defect evidence
- Reproducibility
- Severity
- Priority
- Business impact
- Customer impact
- Technical implications
- Release impact
- Workarounds
- Dependencies
- Ownership
- Planned resolution

Gatekeeper QA contributes quality evidence and risk analysis to the triage process.

Triage should focus on resolving product risk rather than assigning blame to individuals or teams.

### 9.6 Defect Lifecycle

A defect may move through statuses such as:

```text
New
  ↓
Confirmed
  ↓
Assigned / In Progress
  ↓
Fixed
  ↓
Ready for QA Retest
  ↓
Retested
  ↓
Closed
```

Alternative paths may include:

```text
Retest Failed → Reopened
```

or:

```text
Not a Defect
Duplicate
Cannot Reproduce
Deferred
Accepted Risk
```

The exact workflow may vary according to the client's issue-tracking process.

Gatekeeper QA should adapt to the client's approved workflow rather than unnecessarily forcing a separate defect lifecycle.

### 9.7 Retesting

Retesting verifies whether a specific reported defect has been successfully corrected.

The primary question is:

> **Did the fix resolve the reported defect?**

Retesting should normally use the original defect conditions, including relevant:

- Environment
- Preconditions
- Test data
- Reproduction steps
- Expected behavior

Where appropriate, Gatekeeper QA should also verify closely related conditions that could affect the fix.

If the defect still occurs, the defect should be reopened or returned to the appropriate status with updated evidence.

If the defect no longer occurs, the retest result should be documented.

### 9.8 Regression Testing

Regression testing evaluates whether a change or defect fix has negatively affected existing functionality.

The primary question is:

> **Did this change break something else?**

Regression scope should be selected according to risk rather than automatically executing the entire test suite after every change.

Factors influencing regression scope may include:

- Component changed
- Size and complexity of the change
- Dependencies
- Critical workflows
- Shared services
- Integration points
- Historical defect areas
- Business impact
- Technical architecture where known

For example, a payment fix may require regression coverage around:

- Invoice status
- Payment processing
- Duplicate payment prevention
- Payment history
- Confirmation notifications
- Refund or transaction handling where applicable
- Related API behavior

### 9.9 Retesting vs Regression

Gatekeeper QA should clearly distinguish between retesting and regression testing.

| Activity | Primary Question |
|---|---|
| Retesting | Did we fix this specific defect? |
| Regression Testing | Did the change negatively affect other functionality? |

Both may be required after a defect is fixed.

Passing the original defect retest does not prove that the fix introduced no regression elsewhere.

### 9.10 Defect Closure

A defect should be closed when sufficient evidence indicates that the agreed problem has been resolved and required verification has been completed.

Closure information may include:

- Retest result
- Build or version tested
- Environment
- Date of verification
- Supporting evidence
- Related regression results
- Remaining known limitations where applicable

Defect closure should be based on verification rather than simply assuming that a developer's code change resolved the problem.

### 9.11 Deferred Defects and Accepted Risk

Not every confirmed defect will necessarily be fixed before release.

A client may decide to defer a defect because of factors such as:

- Low business impact
- Low customer impact
- Acceptable workaround
- Release deadline
- Technical complexity
- Planned future redesign
- Limited exposure

When a defect remains unresolved, Gatekeeper QA should clearly document the remaining risk.

Gatekeeper QA may provide a recommendation regarding the quality risk, while the authorized client stakeholder makes the final business decision about accepting that risk.

An accepted or deferred defect should not be represented as technically resolved if the underlying problem still exists.

### 9.12 Defect Trends and Recurrence

Gatekeeper QA should look beyond individual defects where sufficient data exists.

Recurring defects may indicate broader problems such as:

- Unclear requirements
- Missing acceptance criteria
- Weak regression coverage
- Insufficient automated checks
- Repeated integration failures
- Environment instability
- Process gaps
- Inadequate validation
- High-risk areas receiving insufficient early testing

These patterns may later become inputs to the Retrospective & Continuous Improvement process.

### 9.13 Defect Management Outputs

Expected outputs may include:

- Confirmed defect reports
- Severity assessments
- Priority recommendations where appropriate
- Supporting evidence
- Triage information
- Retest results
- Regression results
- Reopened defects
- Closed defects
- Deferred or accepted risks
- Remaining quality risks
- Defect trends where sufficient evidence exists

These outputs become important inputs to QA Reporting & Release Assessment.

## 10. QA Reporting & Release Assessment

The QA Reporting & Release Assessment phase consolidates testing results, defect information, coverage, limitations, and remaining quality risks into a clear assessment that supports informed release decisions.

Gatekeeper QA does not determine release readiness solely from the number of passed tests or reported defects.

Release assessment should consider the significance of the affected functionality, unresolved defects, business and customer impact, test coverage, available workarounds, known limitations, and residual risk.

### 10.1 Purpose of QA Reporting

QA reporting should provide stakeholders with a clear and evidence-based understanding of the current quality position of the product.

The report should help answer questions such as:

- What was tested?
- What was not tested?
- What passed?
- What failed?
- Which defects remain unresolved?
- Which critical workflows were validated?
- What limitations affected testing?
- What risks remain?
- Are acceptable workarounds available?
- What does Gatekeeper QA recommend regarding release?

The level of reporting detail should reflect the audience and engagement.

Technical teams may require detailed execution and defect information, while executives may require a concise summary of quality status, business risk, and release recommendation.

### 10.2 Test Execution Summary

The QA report should summarize the testing performed.

Relevant information may include:

- Testing period
- Environment
- Application version or build
- Testing scope
- Testing approaches used
- Number of tests planned
- Number of tests executed
- Passed tests
- Failed tests
- Blocked tests
- Not executed tests
- Critical workflows tested
- Relevant exploratory testing performed

Test statistics provide useful context but should not be interpreted independently from product risk.

For example:

```text
Planned Tests:      120
Executed Tests:     120
Passed:             112
Failed:               8
Blocked:              0
```

A high pass percentage does not automatically mean that the product is safe to release.

The significance of the failed tests must also be assessed.

### 10.3 Defect Summary

The report should provide an appropriate summary of defects identified during testing.

This may include:

- Total confirmed defects
- Defects by severity
- Open defects
- Fixed defects
- Retested defects
- Reopened defects
- Deferred defects
- Accepted risks
- Defects affecting critical workflows

For example:

```text
Critical: 0
High:     1
Medium:   3
Low:      4
```

Defect counts should not be used as the sole measurement of product quality.

A single defect affecting a critical payment workflow may represent more release risk than several low-impact visual defects.

### 10.4 Coverage and Limitations

Gatekeeper QA should clearly communicate what testing covered and any important limitations.

Limitations may include:

- Insufficient testing time
- Unavailable environments
- Missing devices or browsers
- Unavailable integrations
- Incomplete requirements
- Missing test data
- Environment instability
- Blocked scenarios
- Features delivered too late for complete testing
- Areas explicitly excluded from scope

These limitations are important because they affect the confidence that can reasonably be placed in the test results.

Gatekeeper QA should not imply complete coverage where testing evidence does not support that conclusion.

### 10.5 Residual Risk

Residual risk is the quality risk that remains after planned testing, defect correction, retesting, and regression activities have been performed.

Residual risk may result from:

- Unresolved defects
- Deferred defects
- Incomplete test coverage
- Blocked testing
- Known environment limitations
- Unverified integrations
- Unresolved requirements
- Areas with limited evidence
- Accepted technical or business limitations

Gatekeeper QA should communicate significant residual risks clearly enough for stakeholders to understand their possible impact.

### 10.6 Workarounds

Where unresolved defects have known workarounds, the workaround should be documented as part of the release assessment.

A workaround should be evaluated according to factors such as:

- Whether it is reliable
- Whether customers can reasonably use it
- Whether it creates additional risk
- Whether support teams understand it
- Whether it materially reduces the impact of the defect

The existence of a workaround does not automatically make a defect acceptable for release.

It is one factor in the overall risk assessment.

### 10.7 Release Recommendation

Based on available evidence, Gatekeeper QA may provide one of the following release recommendations:

#### RELEASE

Gatekeeper QA recommends release when the tested scope provides sufficient quality confidence and no known unresolved risk has been identified that, in Gatekeeper QA's assessment, requires holding the release.

This recommendation does not mean that the product is guaranteed to contain no defects.

#### RELEASE WITH KNOWN RISK

Gatekeeper QA may recommend release with known risk when unresolved issues or limitations remain, but they are clearly understood, documented, and considered manageable within the business context.

The recommendation should identify:

- The known risk
- Affected functionality
- Potential customer or business impact
- Available workaround where applicable
- Recommended follow-up action
- Required monitoring where appropriate

#### HOLD

Gatekeeper QA recommends holding the release when available evidence indicates that unresolved quality risk could cause unacceptable impact to critical users, business operations, revenue, data, security, or other important product outcomes.

The recommendation should clearly identify the reason for the hold and the conditions that should be addressed before reassessment.

### 10.8 Testing Completion vs Release Recommendation

Completion of planned testing and release recommendation are separate decisions.

For example:

```text
Testing Status:          COMPLETE
Exit Criteria:           MET
Critical Defects:        0
High Defects:            1
Release Recommendation:  RELEASE WITH KNOWN RISK
```

Testing may be complete while product risk remains.

Similarly, incomplete testing may reduce Gatekeeper QA's confidence in providing a release recommendation.

Gatekeeper QA should clearly communicate both the testing status and the release assessment.

### 10.9 Release Decision Authority

Gatekeeper QA provides an independent quality recommendation based on available evidence and identified risk.

The authorized client stakeholder remains responsible for the final business release decision.

For example:

```text
Gatekeeper QA Recommendation: HOLD
Client Release Decision:      RELEASE
```

If the client chooses to release against Gatekeeper QA's recommendation, Gatekeeper QA should professionally document:

- The recommendation provided
- The significant risks communicated
- The client's final decision
- Any agreed monitoring or follow-up actions

The purpose of this documentation is traceability and risk communication, not blame.

### 10.10 Release Conditions and Follow-Up Actions

A release recommendation may include specific follow-up actions.

Examples may include:

- Fix and retest a deferred defect
- Monitor a specific production workflow
- Perform targeted post-release validation
- Add regression coverage
- Add automated coverage for a recurring risk
- Improve monitoring or logging
- Clarify missing requirements
- Investigate recurring failures
- Schedule additional performance testing

Follow-up actions should have clear ownership where appropriate.

### 10.11 Reporting for Different Stakeholders

Gatekeeper QA should communicate quality information at an appropriate level for the audience.

For example:

**Engineering teams may need:**

- Detailed defect evidence
- Reproduction information
- Logs
- API responses
- Regression results
- Technical observations

**Product stakeholders may need:**

- Affected workflows
- Requirement coverage
- Customer impact
- Known limitations
- Workarounds

**CTOs, founders, or business stakeholders may need:**

- Overall quality position
- Significant product risks
- Critical workflow status
- Release recommendation
- Business impact
- Important follow-up actions

The underlying evidence should remain consistent even when the presentation is adapted to different audiences.

### 10.12 Example Release Assessment

Consider the following test results:

```text
Tests Executed: 120
Passed:         112
Failed:           8

Critical Defects: 0
High Defects:     1
Medium Defects:   3
Low Defects:      4
```

The High-severity defect affects PDF invoice export.

Billing, authentication, and payment workflows have passed their critical tests.

Customers can still export invoice information through an available CSV workaround.

The client understands the PDF limitation and accepts the temporary business impact.

An example assessment may therefore be:

```text
Testing Status:
Complete for the agreed scope.

Significant Known Risk:
PDF invoice export remains unavailable.

Customer Impact:
Customers requiring PDF export are affected.

Available Workaround:
CSV export remains available.

Critical Workflow Status:
Billing, authentication, and payment validation passed.

Gatekeeper QA Recommendation:
RELEASE WITH KNOWN RISK

Recommended Follow-Up:
Resolve the PDF export defect, retest the fix,
perform targeted regression, and close the defect
with verification evidence.
```

The recommendation is based on the overall risk context rather than the number of defects alone.

### 10.13 QA Reporting Outputs

Expected outputs may include:

- QA test summary
- Test execution statistics
- Defect summary
- Critical workflow status
- Coverage information
- Testing limitations
- Residual risks
- Known workarounds
- Release recommendation
- Client release decision
- Follow-up actions
- Supporting evidence references

These outputs become inputs to the Retrospective & Continuous Improvement process.

## 11. Retrospective & Continuous Improvement

The Retrospective & Continuous Improvement phase evaluates what was learned during testing and release activities and identifies opportunities to improve product quality, testing effectiveness, engineering practices, and future delivery.

Gatekeeper QA does not treat every release as an isolated testing event.

Where sufficient evidence exists, testing results, production outcomes, recurring defects, escaped defects, delivery challenges, and quality trends should be reviewed to identify improvements that can reduce future risk.

The objective is to move from repeatedly detecting the same problems toward preventing them or detecting them earlier.

### 11.1 Retrospective Review

After an appropriate delivery cycle or release, Gatekeeper QA may review the quality outcomes with relevant client stakeholders.

The review may consider:

- What worked well
- What did not work well
- Which significant defects were discovered
- Which defects escaped into production
- Which defects occurred repeatedly
- Which testing activities provided the most value
- Which risks were identified correctly
- Which risks were missed
- Which tests were blocked or delayed
- Whether requirements were sufficiently clear
- Whether test environments were reliable
- Whether test data was adequate
- Whether defect communication was effective
- Whether sufficient time was available for retesting and regression
- Whether the release recommendation accurately reflected the known risk

The retrospective should focus on learning and improvement rather than assigning blame.

### 11.2 Escaped Defects

An escaped defect is a defect that was not identified during the relevant pre-release quality activities and was later discovered in production or by customers.

Gatekeeper QA should evaluate significant escaped defects to understand why they were not identified earlier.

Questions may include:

- Was the affected functionality within the agreed test scope?
- Was the relevant scenario tested?
- Was the requirement documented and understood?
- Was appropriate test data available?
- Was the scenario considered during risk assessment?
- Was testing limited by time, environment, access, or another constraint?
- Did existing tests fail to cover the condition?
- Was the failure caused by a production-specific condition?
- Could monitoring or automated checks have detected the problem earlier?

The purpose is not simply to ask why QA missed the defect.

The objective is to understand which part of the overall quality process could be improved.

### 11.3 Recurring Defects

Repeated defects or similar failures may indicate a systemic quality problem.

Examples may include:

- Repeated payment failures
- Repeated authentication regressions
- Recurring validation problems
- Frequent integration failures
- Repeated browser compatibility issues
- Repeated defects caused by ambiguous requirements

Gatekeeper QA should identify patterns where sufficient evidence exists rather than treating every recurring issue as unrelated.

### 11.4 Root Cause Analysis

For significant or recurring quality problems, Gatekeeper QA may participate in root cause analysis with the relevant client teams.

The analysis should investigate why the problem occurred and why existing controls failed to prevent or detect it earlier.

Potential contributing factors may include:

- Unclear requirements
- Missing acceptance criteria
- Inadequate test coverage
- Missing regression coverage
- Insufficient automated checks
- Complex dependencies
- Environment differences
- Test data limitations
- Inadequate monitoring
- Process gaps
- Communication problems
- Technical design issues

Root cause conclusions should be supported by available evidence and relevant technical expertise.

Gatekeeper QA should avoid assigning a root cause without sufficient investigation.

### 11.5 Improvement Actions

Identified lessons should be converted into practical improvement actions where appropriate.

Examples may include:

- Clarifying requirements earlier
- Improving acceptance criteria
- Adding missing test scenarios
- Expanding risk-based regression coverage
- Automating stable and valuable regression scenarios
- Adding API-level validation
- Introducing CI/CD quality checks
- Improving test data management
- Improving environment stability
- Improving logging and observability
- Strengthening defect triage
- Improving release readiness criteria
- Adding performance testing for identified performance risks
- Improving stakeholder communication

Each improvement should address an identified problem or risk rather than introducing process or tooling without a clear purpose.

### 11.6 Automation Opportunities

Repeated manual checks, stable regression scenarios, and high-value critical workflows may become candidates for automation.

Automation candidates should be evaluated according to factors such as:

- Business importance
- Execution frequency
- Stability of the functionality
- Regression value
- Manual execution effort
- Maintenance cost
- Technical feasibility
- Risk reduction value

Gatekeeper QA should not automate a test simply because it can be automated.

Automation should provide measurable or practical Quality Engineering value.

### 11.7 Preventive Quality Improvements

Continuous improvement should not focus only on improving testing after development is complete.

Gatekeeper QA may recommend earlier quality activities such as:

- Requirement reviews
- Acceptance criteria reviews
- Risk analysis before implementation
- Testability discussions
- API contract validation
- Developer quality checks
- Automated checks during CI/CD
- Earlier integration testing
- Improved monitoring and observability

These activities help move quality earlier in the Software Development Life Cycle and reduce reliance on late defect detection.

### 11.8 Improvement Ownership

Improvement actions should have clear ownership where appropriate.

For example:

| Improvement | Owner | Target |
|---|---|---|
| Add payment API regression tests | QA / Engineering | Next sprint |
| Clarify payment timeout behavior | Product | Before next billing change |
| Add duplicate-payment protection test to CI | QA Automation / Engineering | Next release cycle |
| Improve payment transaction logging | Engineering | Planned technical improvement |

Gatekeeper QA may recommend improvements, but implementation responsibility should be agreed with the appropriate client stakeholders.

### 11.9 Measuring Improvement

Where practical, Gatekeeper QA should evaluate whether implemented improvements actually reduce quality risk.

Useful indicators may include:

- Reduction in recurring defects
- Reduction in escaped defects
- Improved critical workflow coverage
- Faster defect detection
- Faster regression feedback
- Reduced blocked testing
- Improved requirement clarity
- Improved automation stability
- Reduced release-related incidents

Metrics should be interpreted in context.

For example, a lower defect count does not automatically prove that product quality improved. It could also result from reduced testing scope or reduced product change.

### 11.10 Continuous Improvement Cycle

Gatekeeper QA may use the following improvement cycle:

```text
Review
   ↓
Analyze
   ↓
Identify Root Cause
   ↓
Define Improvement
   ↓
Implement
   ↓
Measure
   ↓
Apply Learning to the Next Delivery Cycle
```

The purpose is to create a feedback loop where evidence from previous releases improves future quality activities.

### 11.11 Continuous Improvement Outputs

Expected outputs may include:

- Retrospective findings
- Escaped defect analysis
- Recurring defect trends
- Root cause findings where appropriate
- Process improvement recommendations
- Additional test coverage recommendations
- Automation candidates
- CI/CD quality improvement opportunities
- Monitoring or observability recommendations
- Assigned improvement actions
- Improvement measurements
- Lessons to apply to future releases

These outputs should feed into future discovery, risk assessment, test planning, and delivery activities.

## 12. End-to-End Delivery Workflow

The Gatekeeper QA End-to-End Delivery Workflow connects the Quality Engineering activities defined in this methodology into a structured and repeatable client delivery lifecycle.

The workflow is designed to ensure that Gatekeeper QA understands the business and product before testing, prioritizes quality activities according to risk, produces traceable evidence, communicates residual risk clearly, and uses delivery outcomes to improve future quality activities.

The workflow should be adapted to the size, risk, complexity, delivery model, and needs of each engagement.

### 12.1 Delivery Workflow

The standard Gatekeeper QA delivery workflow is:

```text
Client Engagement & Kickoff
            ↓
Product, Business & Requirements Discovery
            ↓
Quality Risk Assessment & Prioritization
            ↓
Test Planning & Preparation
            ↓
Test Design & Acceptance Criteria
            ↓
Test Execution & Evidence Collection
            ↓
Defect Management
            ↓
Fix Verification / Retesting
            ↓
Risk-Based Regression Testing
            ↓
QA Reporting & Release Assessment
            ↓
Client Release Decision
            ↓
Retrospective & Continuous Improvement
            ↓
Learning Applied to the Next Delivery Cycle
```

The workflow is not intended to prevent iteration.

New information discovered during testing may require Gatekeeper QA to revisit requirements, risks, test design, scope, or priorities.

### 12.2 Phase 1 — Client Engagement & Kickoff

**Purpose:** Establish the engagement, understand why QA support is required, identify stakeholders, confirm initial scope, and establish the working model.

Key activities may include:

- Understand the engagement objective
- Identify relevant stakeholders
- Confirm initial scope and constraints
- Understand the existing development and release process
- Identify required documentation and access
- Establish communication channels
- Establish reporting expectations
- Confirm responsibilities and decision authority

**Primary Output:** Agreed engagement context, initial scope, responsibilities, required access, and next actions.

### 12.3 Phase 2 — Product, Business & Requirements Discovery

**Purpose:** Understand the product, users, business objectives, expected behavior, requirements, and critical workflows.

Key activities may include:

- Review requirements and documentation
- Explore the product
- Understand user goals
- Identify critical business workflows
- Clarify ambiguous requirements
- Identify missing requirements
- Validate business rules with authorized stakeholders
- Develop or refine acceptance criteria where appropriate

**Primary Output:** Validated understanding of expected behavior, critical workflows, requirements, acceptance criteria, assumptions, and open questions.

### 12.4 Phase 3 — Quality Risk Assessment & Prioritization

**Purpose:** Determine which areas present the greatest potential quality risk and should receive the greatest testing attention.

Key activities may include:

- Identify product and business risks
- Assess impact
- Assess likelihood
- Review recent changes
- Identify dependencies
- Consider previous defects and incidents
- Determine testing priorities

**Primary Output:** Prioritized quality risks and recommended areas of testing focus.

### 12.5 Phase 4 — Test Planning & Preparation

**Purpose:** Convert identified risks and engagement objectives into an executable testing plan.

Key activities may include:

- Define test objectives
- Define in-scope and out-of-scope areas
- Select appropriate testing approaches
- Confirm environments
- Prepare test data
- Establish testing schedule
- Define entry criteria
- Define exit criteria
- Document dependencies and constraints

**Primary Output:** Risk-based test plan and testing readiness information.

### 12.6 Phase 5 — Test Design & Acceptance Criteria

**Purpose:** Transform validated requirements, business rules, and identified risks into testable scenarios.

Key activities may include:

- Design positive scenarios
- Design negative scenarios
- Design boundary and error conditions
- Create formal test cases where appropriate
- Develop or refine acceptance criteria
- Use BDD/Gherkin where it provides value
- Prepare exploratory testing charters
- Establish requirements-to-test traceability where appropriate

**Primary Output:** Prioritized test scenarios, test cases, exploratory charters, and traceability information.

### 12.7 Phase 6 — Test Execution & Evidence Collection

**Purpose:** Execute planned and exploratory testing and produce reliable evidence about product behavior and quality risk.

Key activities may include:

- Execute tests according to risk priority
- Record test results
- Investigate unexpected behavior
- Reproduce potential defects
- Capture screenshots or recordings
- Review API and network behavior where appropriate
- Review logs or other technical evidence where available
- Document newly discovered risks

A useful execution mindset is:

```text
Execute
   ↓
Observe
   ↓
Investigate
   ↓
Reproduce
   ↓
Capture Evidence
   ↓
Report
```

**Primary Output:** Test results, supporting evidence, exploratory findings, newly identified risks, and confirmed defect candidates.

### 12.8 Phase 7 — Defect Management, Retesting & Regression

**Purpose:** Ensure confirmed defects are clearly communicated, appropriately assessed, verified after correction, and evaluated for regression risk.

Key activities may include:

- Report confirmed defects
- Assess severity
- Support defect triage
- Determine repair priority collaboratively where appropriate
- Track defect status
- Retest implemented fixes
- Perform risk-based regression testing
- Reopen defects when verification fails
- Close verified defects with supporting evidence
- Document deferred or accepted risks

The verification flow may be represented as:

```text
Defect Reported
       ↓
Triage
       ↓
Fix Implemented
       ↓
Retest
       ↓
Risk-Based Regression
       ↓
Verification Evidence
       ↓
Close / Reopen
```

**Primary Output:** Verified defect status, retest evidence, regression results, and remaining known risks.

### 12.9 Phase 8 — QA Reporting & Release Assessment

**Purpose:** Convert testing evidence into clear quality information that supports an informed release decision.

Key activities may include:

- Consolidate test results
- Review open defects
- Review critical workflow status
- Assess testing coverage
- Document testing limitations
- Assess residual risk
- Document available workarounds
- Provide release recommendation
- Document the client's final release decision
- Define required follow-up actions

Gatekeeper QA may provide one of three recommendations:

```text
RELEASE
RELEASE WITH KNOWN RISK
HOLD
```

Gatekeeper QA provides the quality recommendation.

The authorized client stakeholder remains responsible for the final business release decision.

**Primary Output:** QA report, residual risk assessment, release recommendation, client decision, and follow-up actions.

### 12.10 Phase 9 — Retrospective & Continuous Improvement

**Purpose:** Learn from the delivery and improve future product quality and Quality Engineering activities.

Key activities may include:

- Review delivery outcomes
- Analyze significant escaped defects
- Identify recurring defect patterns
- Participate in root cause analysis where appropriate
- Identify process improvements
- Identify additional test coverage
- Identify appropriate automation opportunities
- Recommend CI/CD quality improvements
- Recommend monitoring or observability improvements
- Assign improvement actions
- Measure improvement where practical

The improvement cycle may be represented as:

```text
Review
   ↓
Analyze
   ↓
Identify Root Cause
   ↓
Define Improvement
   ↓
Implement
   ↓
Measure
   ↓
Apply Learning to the Next Cycle
```

**Primary Output:** Lessons learned, improvement actions, preventive quality recommendations, and inputs for future delivery cycles.

### 12.11 Roles and Decision Responsibilities

Gatekeeper QA and the client should maintain clear responsibilities throughout the delivery workflow.

#### Gatekeeper QA Responsibilities

Gatekeeper QA may be responsible for:

- Independent quality assessment
- Risk identification and analysis
- Test planning
- Test design
- Test execution
- Evidence collection
- Defect reporting
- Retesting
- Regression assessment
- Quality reporting
- Release recommendations
- Continuous improvement recommendations

#### Client Responsibilities

The client remains responsible for areas such as:

- Business objectives
- Product decisions
- Approval of business requirements
- Access and environment authorization
- Development and technical implementation
- Business prioritization
- Acceptance of known business risk
- Final release decision

Specific responsibilities should be agreed according to the engagement.

### 12.12 Traceability Across the Delivery Lifecycle

Where appropriate, Gatekeeper QA should maintain traceability from business expectations through testing and release assessment.

For example:

```text
Business Requirement
        ↓
Acceptance Criteria
        ↓
Quality Risk
        ↓
Test Scenario / Test Case
        ↓
Test Execution
        ↓
Evidence
        ↓
Defect (if identified)
        ↓
Retest / Regression
        ↓
Residual Risk
        ↓
Release Assessment
        ↓
Improvement Action
```

This traceability helps demonstrate how Gatekeeper QA's testing activities connect to actual product and business risks.

### 12.13 Adaptive Delivery

The Gatekeeper QA methodology provides structure but should not become unnecessary bureaucracy.

A small startup release may require a lightweight version of the workflow, while a complex or high-risk engagement may require more formal documentation, traceability, reporting, and controls.

Gatekeeper QA should apply enough process to manage the quality risk effectively without creating process solely for its own sake.

Tools should support the methodology rather than define it.

Gatekeeper QA may therefore work within client systems such as Jira, Azure DevOps, Linear, GitHub, TestRail, or other approved platforms depending on the engagement.

### 12.14 Continuous Quality Partnership

For recurring engagements, the end of one delivery cycle becomes the beginning of the next.

Information learned from previous releases should influence future:

- Requirements reviews
- Risk assessments
- Test planning
- Regression coverage
- Automation priorities
- API testing
- Performance testing
- CI/CD quality controls
- Monitoring
- Quality reporting

The long-term objective is not simply to execute more tests.

The objective is to help the client progressively reduce product risk, prevent recurring quality problems, improve release confidence, and strengthen quality throughout the software delivery lifecycle.