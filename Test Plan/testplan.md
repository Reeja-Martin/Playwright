VWO Staging Authentication — Functional Test Plan
Proposed Test Plan ID: TP-VWO-AUTH-001
Status: Draft for review
Execution status: Not executedS
Basis: Prepared using the generic RICE POT QA template

1. Test Plan ID and Title
TP-VWO-AUTH-001 — VWO Staging Authentication: Functional Test Plan

2. Objective and References
Validate the agreed email-and-password login, logout, and password-reset workflows in a VWO staging environment using desktop Chrome.

No formal requirements or acceptance criteria were provided. The coverage IDs below are proposed local identifiers—not VWO requirement IDs—and must be reconciled with authoritative requirements before execution.

The exact staging URL and build/version are Not provided. Although app.vwo.com was identified, the selected target is a staging environment; confirm its URL before testing.

3. In Scope and Out of Scope
In scope

Sign in with valid email and password.
Denial of sign-in for invalid credentials and applicable invalid or missing inputs.
Logout and checking that protected content requires sign-in afterward.
Password-reset request and completion, subject to confirmed product behavior.
Focused functional regression of the above workflows.
Desktop Chrome.
Out of scope

SSO, MFA, account registration, security or penetration testing, performance/load testing, accessibility testing, mobile/responsive testing, and other browsers.
Authorization or role-permission testing beyond confirming the user’s signed-in or signed-out state.
4. Requirements and Planned Coverage
Proposed local ID	Planned coverage	Basis and gap
VWO-AUTH-01	Valid email/password sign-in reaches the agreed authenticated state	Proposed; confirm success condition and provide a test account
VWO-AUTH-02	Invalid credentials and applicable invalid or missing inputs do not sign in	Proposed; confirm validation rules and observable outcomes
VWO-AUTH-03	Logout ends the user-visible authenticated session; protected content requires sign-in	Proposed; confirm expected logout behavior
VWO-AUTH-04	Password-reset request and completion follow the approved reset flow	Proposed; confirm account eligibility, email access, token behavior, and password rules
These identifiers are for planning only. Update the mapping when official requirements are supplied.

5. Test Approach, Levels, and Types
Use risk-based, primarily manual functional testing of the staging UI. Cover the sign-in, logout, and password-reset workflows at the system/UI level. Check dependent integrations, such as reset-email delivery, only where they are observable and approved test access is available.

Design positive, negative, boundary, and state-transition scenarios where product rules are known. Do not invent exact error messages, password rules, lockout behavior, reset-token lifetime, or delivery behavior. Automation is not included in this plan.

6. Environment, Tools, Access, and Test Data
Environment: VWO staging; URL and build/version are Not provided.
Target: Desktop Chrome; browser version and operating system are Not provided.
Access: Test accounts and reset-mailbox access are not available yet.
Test data: Use approved, dedicated synthetic accounts: a valid account, invalid-credential inputs, and an account/mailbox suitable for password-reset testing. Account provisioning and mailbox setup are prerequisites. Do not use real customer data or production credentials.
Tools: Chrome and an approved defect tracker or test repository. Specific tools and versions are Not provided. Capture sanitized evidence where permitted; do not record passwords or reset tokens.
7. Entry and Exit Criteria
Proposed entry criteria — confirm before execution

The staging URL and build are identified and reachable.
Acceptance behavior for the four coverage IDs is documented or confirmed by the product owner.
A dedicated valid test account and reset-mailbox path are provisioned.
Invalid-input test data is approved.
Chrome and operating-system targets are agreed.
Test cases and the defect reporting channel are reviewed.
Proposed exit criteria — for review

100% of approved P1 cases are executed, and all pass.
At least 95% of all approved cases are executed.
No Severity 1 or Severity 2 defects remain open.
Remaining failures or waivers are documented with an owner and disposition.
Coverage and execution status are reported against each approved requirement.
These thresholds are proposals, not agreed VWO release criteria. Blocked tests must be reported as blocked, not passed.

8. Roles, Responsibilities, Estimates, and Schedule
Role	Responsibility	Owner / estimate
Product or requirement owner	Confirm acceptance behavior and scope	Not provided
QA engineer or test lead	Design cases, prepare data, execute, and report coverage and defects	Not provided
Staging/environment owner	Provide stable build, URL, access, and reset-mailbox integration	Not provided
Developer and defect triage participants	Diagnose defects, prioritize them, and support retesting	Not provided
Staffing, effort estimates, and schedule are Not provided. Set these after requirements and access are confirmed. No execution date is assumed.

9. Defect Management and Reporting
Log defects in the approved tracker with the environment/build, browser/version, preconditions, sanitized data, reproducible steps, expected and observed results, evidence, proposed severity/priority, and linked coverage ID.

Agree on severity and priority with product and engineering; proposed values are not final until confirmed. Report execution status, pass/fail/blocked counts, defects by severity, coverage gaps, and risks at an agreed cadence.

The tracker, severity definitions, triage owner, and reporting cadence are Not provided.

10. Risks, Dependencies, Assumptions, and Open Questions
Risks and dependencies

The staging URL, build, and stable access are unknown.
Test accounts and reset-mailbox access are unavailable.
Authoritative requirements and expected outcomes were not supplied.
Reset-email delivery may depend on an unconfirmed staging integration.
Browser/OS versions, defect workflow, ownership, and schedule are unspecified.
Assumptions to validate

Email and password are the only sign-in method in scope.
Expected behavior will be confirmed against approved VWO requirements.
Dedicated synthetic accounts can be provisioned.
Reset requests can be tested without contacting real users.
No exact UI messages, password policy, lockout behavior, reset-token lifetime, or success destination is assumed.

Open questions

What are the staging URL and build?
What are the approved login, logout, and password-reset acceptance criteria?
Who provides test accounts and mailbox access?
Which Chrome and operating-system versions are supported?
What defect severity definitions, reporting cadence, schedule, and approvers should be used?
11. Suspension and Resumption Criteria
Suspend affected testing if staging is unavailable or unstable, access or data is missing or unsafe, reset-email integration is unavailable, results cannot be reproduced because of an environment issue, or a critical defect blocks reliable continuation. Record the blocker, impacted cases, evidence, and owner. Do not count blocked work as passed.

Resume when the environment is stable, required access and dependencies are restored, the blocker is resolved or an approved workaround is documented, and QA confirms the setup with a smoke check. Re-run affected cases and relevant regression, then update status and coverage.

12. Test Deliverables and Approval
Deliverables

This test plan.
Reviewed test cases mapped to approved requirements.
Test-data and setup checklist.
Execution and defect summary after future execution.
Unresolved risks and coverage gaps.
No tests have been executed as part of this plan.

Approval required before execution

Product/requirement owner: confirm scope and acceptance behavior.
QA lead: approve coverage and proposed criteria.
Staging owner: confirm environment and access.
Approver names and approval dates are Not provided.