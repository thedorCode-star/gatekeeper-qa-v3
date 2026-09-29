# Gatekeeper QA GitHub and Branching Strategy

## 1. Purpose

The purpose of the Gatekeeper QA GitHub and Branching Strategy is to provide a controlled, traceable, and repeatable process for managing changes to business documentation, website code, QA automation, testing assets, and other engineering work.

The strategy protects the `main` branch as the production-ready baseline. Development work should not normally be performed or committed directly on `main`.

Changes should instead be developed in isolated branches, reviewed through pull requests, and integrated through the approved branch workflow before reaching `main`.

The strategy is designed to:

- Protect production-ready work from incomplete or unreviewed changes.
- Isolate individual Jira work items through dedicated feature branches.
- Provide traceability between Jira work items, branches, commits, pull requests, and merged changes.
- Enable changes to be reviewed before integration.
- Use `develop` as the integration branch for approved feature work.
- Use `main` as the production-ready branch.
- Remove temporary feature branches after successful integration.
- Support collaboration as the Gatekeeper QA engineering team grows.

## 2. Repository Principles

Gatekeeper QA uses Git and GitHub according to the following principles:

1. **Protect production-ready work**  
   The `main` branch represents the production-ready baseline and should be protected from direct, unreviewed changes.

2. **Isolate work**  
   New work should normally be performed in a dedicated branch rather than directly in `develop` or `main`.

3. **Integrate reviewed work through `develop`**  
   Completed feature work should normally be reviewed through a pull request before being merged into `develop`.

4. **Maintain traceability**  
   Where work originates from Jira, branch names and commit messages should reference the relevant Jira work-item key.

5. **Review before integration**  
   Changes should be reviewed for correctness, scope, quality, and unintended modifications before they are merged.

6. **Keep commits focused**  
   Commits should represent logical changes and use clear messages that explain what was changed.

7. **Keep branches temporary where appropriate**  
   Feature branches should normally be removed after their changes have been successfully merged.

8. **Protect sensitive information**  
   Passwords, API keys, access tokens, private client information, and other secrets must not be committed to the repository.

9. **Use tools to support the process**  
   GitHub branch protection, pull requests, automated checks, and CI/CD should support the workflow rather than replace engineering judgment.

## 3. Branch Model

Gatekeeper QA uses a branch model with permanent branches for integration and production-ready work, together with temporary branches for individual work items.

The standard branch flow is:

```text
Jira Work Item
      ↓
Feature Branch
      ↓
Development / Documentation / Testing
      ↓
Commit
      ↓
Push Feature Branch
      ↓
Pull Request
      ↓
Review and Validation
      ↓
develop
      ↓
Integration Validation
      ↓
Release Pull Request
      ↓
main
      ↓
Production-Ready Baseline
```

## 4. Branch Responsibilities

Each branch type has a specific responsibility within the Gatekeeper QA development workflow.

### 4.1 `main` Branch

The `main` branch represents the production-ready baseline.

Responsibilities:

- Contain work approved for production release.
- Remain stable and protected from direct, unreviewed changes.
- Receive changes through the approved release workflow.
- Provide a reliable reference for the current production-ready state.
- Support production deployment processes where applicable.

Normal feature development should not be performed directly on `main`.

### 4.2 `develop` Branch

The `develop` branch is the primary integration branch.

Responsibilities:

- Receive reviewed and approved feature work.
- Integrate changes from multiple completed work items.
- Provide a shared location for integration validation.
- Identify conflicts or integration problems before changes reach `main`.
- Provide the source for planned release changes to `main`.

Normal feature development should not be performed directly on `develop`.

### 4.3 Feature Branches

Feature branches isolate work associated with individual Jira work items.

Responsibilities:

- Provide an independent workspace for a specific work item.
- Keep incomplete work away from `develop` and `main`.
- Allow engineers to commit and push work without affecting other active feature branches.
- Support focused pull-request review.
- Maintain traceability to the associated Jira work item.
- Be removed after successful integration when no longer required.

Multiple feature branches may exist at the same time.

A completed feature branch does not normally need to wait for unrelated feature branches before being reviewed and merged into `develop`.

However, where work items have technical dependencies or overlapping changes, those dependencies should be identified and managed before integration.

## 5. Branch Naming Convention

Gatekeeper QA branch names should be clear, consistent, and traceable to the work being performed.

For work originating from Jira, the standard feature branch format is:

```text
feature/<JIRA-KEY>-<short-description>
```

## 6. Jira-to-Git Traceability

Gatekeeper QA should maintain traceability between planned work in Jira and the corresponding changes in Git and GitHub.

Where work originates from a Jira work item, the Jira key should normally appear in:

- The feature branch name
- Relevant commit messages
- The pull request title
- The pull request description or supporting context where appropriate

For example:

```text
Jira:
GKQA-25 — Automate customer login workflow

Branch:
feature/GKQA-25-automate-customer-login

Commit:
GKQA-25: add customer login Playwright coverage

Pull Request:
GKQA-25: automate customer login workflow
```

## 7. Commit Message Convention

Gatekeeper QA commit messages should be clear, concise, and traceable to the work being performed.

For work originating from Jira, the standard commit message format is:

```text
<JIRA-KEY>: <short description of the change>
```

## 8. Pull Request Workflow

Gatekeeper QA uses pull requests as the primary review and integration mechanism for moving completed feature work into `develop`.

After work on a feature branch is completed and pushed to GitHub, a pull request should normally be created with:

- The feature branch as the source branch.
- `develop` as the target branch.
- The relevant Jira key in the pull request title.
- A clear description of the change and its purpose.

Before a pull request is merged, the reviewer should inspect the proposed changes, including the `Files changed` view, to verify that:

- The changed files match the scope of the associated Jira work item.
- No unrelated or accidental changes are included.
- The implementation or documentation satisfies the intended objective.
- No sensitive information or secrets have been committed.
- Relevant automated checks pass where CI/CD checks are configured.
- The changes are understandable and ready for integration.
- Any review comments or required corrections have been addressed.

For example, if the pull request relates to:

```text
GKQA-4 — Define GitHub and branching strategy
```

## 9. Review and Merge Strategy

Gatekeeper QA requires changes to be reviewed before they are integrated into protected or shared branches.

A pull request being technically able to merge does not automatically mean that the change is ready or approved for integration.

Before merging, the reviewer should confirm that:

- The pull request matches the associated Jira work-item scope.
- The changed files have been reviewed.
- No unintended files have been modified or deleted.
- The implementation or documentation satisfies the expected requirements.
- Required automated checks have passed where applicable.
- Review comments have been resolved.
- No secrets or sensitive information are included.
- The change is suitable for integration with other approved work.

### Feature Merge Strategy

Completed feature branches should normally be merged into `develop` through a pull request.

The standard flow is:

```text
feature/*
    ↓
Pull Request
    ↓
Review
    ↓
Approval
    ↓
Merge
    ↓
develop
```

## 10. Branch Protection

Gatekeeper QA should use GitHub branch protection or repository rulesets to protect important shared branches from uncontrolled changes.

The `main` branch represents the production-ready baseline and should receive the strongest protection.

### `main` Protection Expectations

Where supported by the repository configuration, protection for `main` should include:

- Changes should normally reach `main` through a pull request.
- Direct changes to `main` should be restricted.
- Pull requests should be reviewed before merging.
- Required automated checks should pass before merging where CI/CD checks are configured.
- Unresolved review comments should be addressed before merging.
- Force pushes should be restricted.
- Accidental branch deletion should be prevented or restricted.
- Access to bypass protection should be limited and used only when justified.

### `develop` Protection Expectations

Because `develop` is the shared integration branch, it should also be controlled.

Protection should normally include:

- Feature work should reach `develop` through pull requests.
- Direct development on `develop` should be avoided.
- Relevant review and automated checks should be completed before integration.
- Force pushes should be restricted.
- Changes should remain traceable to their originating work items.

### Process Rules and Technical Controls

Gatekeeper QA distinguishes between process rules and technical controls.

A process rule defines the expected behavior:

```text
Do not commit directly to main.
```

## 11. Secrets and Sensitive Information

Gatekeeper QA repositories must not contain secrets, credentials, or confidential information that should not be stored in source control.

Sensitive information may include:

- API keys
- Access tokens
- Passwords
- Database credentials
- Private certificates or keys
- Authentication secrets
- Client credentials
- Confidential client data
- Production environment credentials

### Environment Variables

Application secrets should normally be supplied through environment variables rather than hard-coded into source code.

For local development, environment-specific values may be stored in a local `.env` file where appropriate.

Example:

```text
PAYMENT_API_KEY=<local-secret-value>
```

## 12. Post-Merge Branch Cleanup

Feature branches are temporary and should normally be removed after their work has been successfully reviewed and merged into `develop`.

Before deleting a feature branch, the engineer should confirm that:

- The pull request has been successfully merged.
- The expected changes are present in `develop`.
- The local `develop` branch has been synchronized with the remote repository.
- No additional work is required on the feature branch.

A typical post-merge workflow is:

```text
Feature Branch
      ↓
Pull Request
      ↓
Review and Approval
      ↓
Merge into develop
      ↓
Switch Local Repository to develop
      ↓
Pull Latest develop
      ↓
Verify Synchronization
      ↓
Delete Merged Feature Branch
      ↓
Begin Next Work Item
```

## 13. End-to-End Git Workflow

Gatekeeper QA follows a traceable Git workflow from Jira work-item creation through implementation, review, integration, and branch cleanup.

### Step 1 — Receive or Select a Jira Work Item

Engineering work should begin with a clearly defined work item where applicable.

Example:

```text
GKQA-30 — Add checkout Playwright tests
```
The engineer should review the objective, scope, requirements, acceptance criteria, and dependencies before beginning implementation.

### Step 2 — Synchronize `develop`

Before creating a feature branch, switch to `develop` and synchronize it with the remote repository:

```bash
git switch develop
git pull origin develop
git status
```

This helps ensure that new work starts from the latest integrated baseline.

### Step 3 — Create the Feature Branch

Create a dedicated feature branch from the updated `develop` branch:

```bash
git switch -c feature/GKQA-30-checkout-playwright-tests
```

Verify the active branch:

```bash
git branch --show-current
```

### Step 4 — Perform the Work

Implement the changes required by the Jira work item.

Work should remain focused on the defined scope of the feature branch.

### Step 5 — Review and Validate Locally

Before committing, review the changes and perform relevant local validation or testing.

```bash
git status
git diff
```

Relevant application, documentation, or automated tests should also be executed where applicable.

### Step 6 — Stage and Commit

Stage only the intended changes:

```bash
git add <files>
```

Review the staged changes:

```bash
git diff --staged
```

Commit using the Jira-linked commit convention:

```bash
git commit -m "GKQA-30: add checkout Playwright tests"
```

### Step 7 — Push the Feature Branch

Push the feature branch to the remote repository:

```bash
git push -u origin feature/GKQA-30-checkout-playwright-tests
```

### Step 8 — Create a Pull Request

Create a pull request with:

```text
Source: feature/GKQA-30-checkout-playwright-tests
Target: develop
```

The pull request should reference the Jira work item and clearly describe the proposed change.

### Step 9 — Review the Pull Request

Before merging:

- Review the `Files changed` view.
- Confirm that the changes match the Jira scope.
- Check for unintended changes.
- Verify relevant tests and automated checks.
- Check for exposed secrets or sensitive information.
- Address review comments.
- Confirm that the work is ready for integration.

Technical mergeability alone does not constitute approval.

### Step 10 — Merge into `develop`

Once the pull request has satisfied the required review and validation criteria, merge the feature branch into `develop`.

### Step 11 — Synchronize Local `develop`

After the successful merge:

```bash
git switch develop
git pull origin develop
git status
```

Confirm that the merged changes are present locally.

### Step 12 — Clean Up the Feature Branch

After confirming successful integration, delete the temporary feature branch when it is no longer required.

Local cleanup:

```bash
git branch -d feature/GKQA-30-checkout-playwright-tests
```

Remote cleanup where required:

```bash
git push origin --delete feature/GKQA-30-checkout-playwright-tests
```

### Step 13 — Begin the Next Work Item

Select the next Jira work item and repeat the workflow from the latest `develop` baseline.

The standard Gatekeeper QA workflow is:

```text
Jira
  ↓
Updated develop
  ↓
Feature Branch
  ↓
Work
  ↓
Local Review / Testing
  ↓
Stage
  ↓
Commit
  ↓
Push
  ↓
Pull Request
  ↓
Review / Automated Checks
  ↓
Merge to develop
  ↓
Synchronize Local develop
  ↓
Branch Cleanup
  ↓
Next Jira Work Item
```

Production releases follow a separate controlled integration from `develop` to `main` after the required release validation.
