# API Security, Data Handling, and Access Controls

## Slide 1/41 - Design Use Cases for Activation (Title)
API Security, Data Handling, and Access Controls
Created July 2026

## Slide 2/41 - Introduction

The API lets companies build intelligence into products, operations, workflows, and customer experiences. These solutions may touch business data, internal systems, customer context, tools, logs, credentials, permissions, and approvals.

Before an enterprise API workflow is trusted, teams must clarify what data it touches, who or what can access it, how secrets are protected, which actions need approval, and what evidence reviewers need before launch.

This course builds practical security-review judgment. It does not cover full security architecture, identity implementation, monitoring configuration, or legal, privacy, regulatory, or compliance advice.

## Slide 3/41 - What you'll learn

By the end of this course, you'll be able to:

- Map API data flows and explain how sensitivity, ownership, minimization, logging, and retention shape deployment review.
- Distinguish authentication, authorization, least privilege, and secrets handling.
- Identify issues involving access controls, tool and system permissions, and action boundaries that require approval, remediation, or escalation.
- Define approval, auditability, logging, and security validation questions, and identify evidence gaps and handoff owners.
- Use an API Security and Data Handling Review to document remediation actions and make a deployment-readiness recommendation.

## Slide 4/41 - What you'll produce

You will learn how to use an API Security and Data Handling Review — a practical job aid for evaluating API workflows before pilot, production review, or customer handoff.

In this course, you'll use focused exercises to practice the decision-making process rather than complete a full review. In real projects, you would apply the review using approved, sanitized information from a customer opportunity, implementation project, pilot, or internal API workflow.

The review helps you evaluate five areas:

- Data boundary
- Access and secrets boundary
- Action and approval boundary
- Evidence gap and remediation
- Readiness recommendation

Let's get started!

## Slide 5/41 - Introduction (Module: Map data movement and sensitivity)

Security review starts with data movement.

If you cannot explain what data enters the workflow, where it travels, what is stored, what is logged, and what exits the system, you cannot reliably assess access control, approval needs, logging risk, retention, or downstream review needs.

In this module, you will map the data that an API receives, processes, stores, logs, and sends. You will also classify likely sensitivity and apply data minimization so the workflow does not collect, expose, store, return, or log more information than it needs.

## Slide 6/41 - Key definitions

Before reviewing an API workflow, use these definitions.

- **Data movement** — Where data enters, travels, is transformed, stored, logged, and exits an API workflow.
- **Data classification** — Labeling data by sensitivity and handling expectations.
- **Sensitive data** — Data that may require extra protection because it is confidential, personal, regulated, customer-specific, or security-related.
- **Data owner or system owner** — The team or person accountable for the source system, data use, access permissions, and approval expectations.
- **Logged data** — Data captured in system or application records for troubleshooting, monitoring, audit, or support.
- **Data minimization** — Collecting, sending, storing, returning, and logging only the data the workflow actually needs.
- **Abuse monitoring logs** — OpenAI platform logs generated to enforce usage policies and agreements and mitigate harmful use. By default, these logs may include customer content and derived metadata and are retained for up to 30 days, subject to documented exceptions.
- **Application state** — Customer data retained by some API features to complete or maintain the requested workflow. Its retention depends on the endpoint, capability, request settings, and object lifecycle.
- **OpenAI data retention controls** — Approved organization- or project-level controls such as Modified Abuse Monitoring and Zero Data Retention. Eligibility and configuration must be confirmed; Zero Data Retention does not make every endpoint or capability eligible or stateless.

Note: Confirm the current Data controls in the OpenAI platform guidance before using these definitions in implementation or customer guidance.

These terms are deliberately practical. You do not need to produce a complete data-protection impact assessment in this course. You do need to make enough information visible that the right customer, platform, security, privacy, or system-owner stakeholders can review it.

## Slide 7/41 - Identify data movement

Start by describing the workflow as a sequence of data events. Avoid starting only with the model call. The model call is one part of the workflow, but the security review needs the full path.

For each workflow step, ask: What data enters the API? Where does the data come from? Who or what sends it? What data is processed or transformed? What output is generated? Is anything stored temporarily or persistently? Is anything logged for troubleshooting, monitoring, audit, or support? Is anything sent to another internal system? Is anything transferred outside the workflow boundary or customer-controlled environment? Who owns each source or destination? What access or permission assumptions are being made?

A useful data-movement statement is specific enough to test.

- Weak statement: "The API uses support data and returns a summary."
- Stronger statement: "The API receives support ticket title, description, requester role, priority, product area, and internal notes from the helpdesk system. It generates an internal triage summary and recommended next action. It writes the generated summary back to the ticket record only after staff confirmation. It logs request ID, timestamp, endpoint, status code, latency, and error category. It excludes ticket body, requester details, secrets, and generated narrative from application logs."

The stronger statement helps reviewers see what data is used, what is returned, what is stored, what is logged, and what must be validated before launch.

## Slide 8/41 - Classify sensitivity

After mapping where data moves, classify the sensitivity of the data the API receives, processes, stores, logs, or sends.

Common sensitivity categories include:

- **Public data** — Information approved for broad public use.
- **Internal data** — Business information intended for internal users but not necessarily confidential.
- **Customer-confidential data** — Customer-specific records, communications, documents, account context, or operational details.
- **Personal or regulated data** — Information that may be personal, protected, regulated, or subject to customer, jurisdictional, contractual, or industry-specific rules.
- **Secrets, credentials, or tokens** — API keys, passwords, certificates, tokens, private keys, connection strings, or other credentials that could enable unauthorized access.
- **Customer-specific or jurisdiction-specific classification** — Any classification that must be confirmed with the customer's security, privacy, legal, compliance, platform, or system-owner teams.

Do not guess when classification is uncertain. If a field may be regulated, personal, customer-confidential, or jurisdiction-specific, mark it as unresolved and route it to the right owner. Use the highest sensitivity level that reasonably applies until an accountable owner confirms otherwise.

For example, a support request may look routine, but it could contain customer names, employee details, internal issue notes, account information, health-related context, payment details, or other sensitive content entered by the requester.

## Slide 9/41 - Apply data minimization

Data minimization reduces risk before the workflow moves toward broader use. The principle is simple: the API should collect, send, store, return, and log only what the workflow needs.

Check whether the workflow can: collect only the fields needed for the task; exclude sensitive fields where possible; mask, redact, or omit sensitive values where appropriate; avoid passing full records when a subset is enough; avoid unnecessary logging; store only the minimum needed output or metadata; limit generated outputs so they do not expose unnecessary sensitive details, internal context, or source data; use identifiers instead of raw content where possible; name unresolved data questions before launch.

Data minimization applies to both inputs and outputs. A design can minimize input data but still expose too much in a generated response. For example, an internal account briefing API may only need to say "one unresolved billing escalation exists" rather than reproducing the full customer complaint, internal notes, and employee names.

Logs need special care. Logs are useful for troubleshooting and audit, but they can become a new data exposure surface if they capture raw prompts, sensitive retrieved context, secrets, credentials, customer-confidential data, personal data, regulated data, or sensitive generated outputs.

**Check OpenAI platform data handling**

OpenAI API data is not used to train or improve OpenAI models unless the organization explicitly opts in to share it.

Separate two storage questions. Abuse monitoring logs are generated by default and may contain prompts, responses, and derived metadata; they are retained for up to 30 days, subject to documented exceptions. Application state is retained by some API features to complete or maintain a workflow, and its duration depends on the endpoint, capability, request settings, and object lifecycle.

Modified Abuse Monitoring and Zero Data Retention are approval-based controls that eligible customers can configure at the organization or project level. Do not assume either control is enabled. Verify the customer's approved configuration and the current endpoint/capability table.

With Zero Data Retention, the "store" parameter for Responses and Chat Completions is treated as false, while endpoints or capabilities marked ineligible may still retain application state.

Note: Data-control eligibility, endpoint behavior, and retention details can change. Confirm the current Data controls in the OpenAI platform guidance before implementation.

## Slide 10/41 - Review pattern: data boundary

When you review data movement, avoid broad labels. Labels like "support data," "account data," or "internal notes" are not specific enough for a technical security review.

A stronger data-boundary review should answer four questions:

**What data does the API touch?** Name the fields, records, attachments, generated outputs, logs, and system destinations where known. If the workflow receives ticket text, internal notes, requester role, region, and generated summaries, name those items directly.

**What is the highest likely sensitivity?** Classify the data at the highest level that reasonably applies until an accountable owner confirms otherwise. A support ticket may be internal in some cases, but customer-confidential, personal, regulated, or security-related in others.

**What should be minimized?** Identify data that should be excluded, masked, redacted, or replaced with identifiers. Pay special attention to raw free-text fields, internal notes, attachments, credentials, and generated outputs that could expose source content.

**What classification question is unresolved?** Name the owner who should confirm data classification, source approval, retention, logging policy, or allowed use. The reviewer should not invent the answer.

A strong data-boundary statement is short, but it is precise. It does not need to complete the entire security review. It should make the data risk visible enough that the right owner can validate it.

## Slide 11/41 - Recommended exercise: Spot the data boundary

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice identifying the data boundary in an API workflow.

**Task:** Review the API details below and identify the data boundary. Focus only on the data touched, likely sensitivity, minimization concern, and unresolved classification question.

**API details:** A support team is prototyping an API that triages product-support tickets before staff review. The workflow works like this: a support ticket is created in the helpdesk system; the helpdesk system sends ticket_id, requester_role, product_area, subject, description, priority, region, and internal_notes to the triage API; the API generates an internal summary, a category, a risk flag, and a recommended next action; the prototype stores the generated summary and category in the ticket record; the prototype currently logs the full request and response body to simplify debugging; the team has not confirmed whether production tickets may contain customer-confidential, personal, or regulated content; the backend calls the Responses API through an OpenAI project using the default data-retention setting; the team has not confirmed whether Modified Abuse Monitoring or Zero Data Retention is approved, whether response storage is enabled, or what application state the selected endpoint retains.

Answer these six prompts: Data touched / Highest likely sensitivity / Data that should be excluded, masked, redacted, or minimized / Unresolved data owner or classification question / OpenAI platform storage or retention fact to verify / OpenAI organization/project control or endpoint limitation to confirm.

**Estimated time:** 7-9 minutes.

**Suggested output and reflection:** A concise data-boundary note that names the specific data fields, not just "ticket data"; recognizes that support-ticket text and internal notes may contain sensitive content; flags full request and response logging as a potential exposure risk; identifies the helpdesk owner, customer security reviewer, privacy reviewer, or another accountable owner as needed; avoids making unsupported claims about whether the data is legally regulated; separates abuse monitoring retention from endpoint-specific application state; does not assume Modified Abuse Monitoring or Zero Data Retention is enabled, eligible, or sufficient for every endpoint.

**Optional stretch:** Add one field that should be excluded from logs or redacted before broader use, and one official platform setting or endpoint fact to verify before pilot.

## Slide 12/41 - Knowledge check

**A prototype support API receives ticket text, sends it to the model, stores a summary, and logs the full request and response. The team says, "No security review is needed because we only use support tickets." What is the best response?**

- Accept the claim because support tickets are usually low risk.
- **Map data movement, sensitivity, ownership, and minimization before deployment.** ✓ Correct
- Approve the workflow once it works in testing.
- Focus only on model selection because data handling comes later.

Correct! Support tickets can contain sensitive, customer-confidential, personal, regulated, or security-related data. The team needs a data movement and sensitivity review before deployment.

## Slide 13/41 - Summary

In this module, you mapped where data enters, travels, is stored, is logged, and exits an API workflow. You classified likely sensitivity, identified ownership and access assumptions, and used data minimization to reduce unnecessary exposure.

The next security question is access: who or what can call the API, what can they do, and how are credentials protected?

## Slide 14/41 - Introduction (Module: Define authentication, authorization, and secrets handling)

After mapping data movement, the next step is to make access-control assumptions explicit.

In enterprise API workflows, "the API works" is not enough. Reviewers need to know who or what can call the API, what access that caller has, how credentials are protected, and whether the workflow follows least privilege.

This module focuses on authentication, authorization, secrets handling, and least privilege at a review and planning level. You are not designing a complete identity architecture. You are making access assumptions visible so the right technical, platform, security, and system-owner teams can validate them.

## Slide 15/41 - Key definitions

Use these definitions when reviewing access controls.

- **Authentication** confirms who or what is calling the API.
- **Authorization** defines what that caller is allowed to access or do.
- **Secrets** are credentials, keys, tokens, passwords, certificates, private keys, connection strings, or similar values that must be protected.
- **Least privilege** means giving the caller only the access needed for the workflow and no more.
- **Auditability** means there is enough reviewable evidence to understand what happened, who or what acted, and what decision or approval occurred.

A common failure pattern is treating authentication as if it proves the workflow is safe. Authentication only tells you the caller is recognized. Authorization determines what that caller can access or do.

## Slide 16/41 - Distinguish authentication and authorization

Authentication answers: "Who or what is making the request?" Authorization answers: "What is that caller allowed to access or do?"

Both must be clear before enterprise deployment. A workflow may successfully authenticate a caller but still authorize too much access. For example, a service account may be valid, but it should not automatically have permission to read sensitive records, update production systems, or perform admin-level actions unless the workflow truly requires that access and the right approval is in place.

When reviewing an API design, identify whether the caller is a: user, application, service account, internal system, external system, or another API or workflow component.

Then capture the assumptions that need validation: How is the caller authenticated? What permissions does the caller have? Are permissions scoped to the workflow? Are sensitive actions separated from routine actions? Can permissions vary by role, system, region, customer, environment, or workflow? Who approves access for production use? What evidence would show that access is controlled appropriately?

It can help to think in request terms. A request may include a valid token, but the backend still needs to evaluate whether that caller can read this source, write to that system, access this customer record, or perform this action in this environment.

## Slide 17/41 - Handle secrets safely

Secrets are high-risk because they can allow unauthorized access if exposed. An API design should make secrets handling explicit before broader use.

Safe secrets-handling assumptions include: use environment variables or managed secret stores; avoid hardcoded keys; do not paste real credentials, customer secrets, or production tokens into prompts, examples, screenshots, demos, generated code samples, logs, or learner artifacts; identify who owns each credential, key, or token; identify rotation and revocation assumptions; confirm whether separate credentials are needed for development, testing, staging, and production; name any secrets-handling questions that require customer security, platform-team, or system-owner review.

A design that works locally with a copied token may be useful for early testing, but it is not enterprise-ready if the secret is hardcoded, shared broadly, stored in a repository, logged, pasted into a prompt, or used outside its approved environment.

For the OpenAI API, never deploy a key in browser or mobile client code. Route requests through an approved backend or server-side component that can protect the key.

Do not share a team member's API key. Use individual access and permissions for people, and use an approved project-scoped service account or other non-human identity for application workloads. Grant only the permissions the workload needs.

Monitor project or organization usage for unexpected activity. Rotate or revoke a key immediately when exposure is suspected, update dependent applications, and keep experimentation, staging, and production credentials separate.

Note: Confirm the current Best Practices for API Key Safety before implementation.

Use placeholders in examples, such as: `OPENAI_API_KEY` stored as an environment variable; `HELPDESK_API_TOKEN` stored in a managed secret store; `CRM_SERVICE_ACCOUNT_TOKEN` retrieved at runtime by the application.

Do not include real values. Do not include screenshot evidence that reveals real values. If a learning artifact needs to show a credential pattern, use clearly fake placeholders.

## Slide 18/41 - Apply least privilege

Least privilege means the API caller should receive only the access needed for the workflow and no more.

Apply least privilege by checking whether the design can: grant only the access needed for the workflow; separate read-only, write, and admin-level access; limit access by role, system, environment, customer, region, team, or workflow where appropriate; name approval requirements for sensitive actions; separate development, testing, staging, and production access assumptions where relevant; identify where human approval is required before the API changes a system, exposes sensitive data, or affects a customer-facing decision; document access-control questions that must be validated with the customer's security, privacy, legal, platform, or system-owner teams.

Least privilege is especially important for service accounts. A shared service account with broad read/write access can make a prototype easy to build but difficult to approve. If the workflow only needs to read a ticket category and write a routing label, it should not have permission to read every record, export attachments, modify user profiles, delete records, or update unrelated systems.

The goal in this course is not to design a complete enterprise identity architecture. The goal is to make access assumptions visible enough that the right teams can review them before deployment.

**Apply least privilege in the OpenAI platform**

OpenAI role-based access control (RBAC) applies across the Dashboard and API. An organization is the top-level account; a project is a boundary for keys, files, and resources. Organization roles can apply across all projects, while project roles apply only within one project.

Prefer project-level access when organization-wide access is not required. Use roles that include only the permissions needed for the task. Remember that a user's effective access is the union of all assigned roles.

Separate experiments, staging, and production into different projects. Scope service accounts and API keys to the project and operation they support; verify both key permissions and the applicable project role where required. Test with a non-owner account, and review unused roles and keys regularly.

Note: Confirm the current Manage permissions in the OpenAI platform guidance before implementation.

## Slide 19/41 - Review pattern: access and secrets boundary

When you review access and secrets, use these questions.

**Who or what is acting?** Name the caller or service identity — user, application, service account, internal system, external system, or workflow component.

**What OpenAI organization and project boundary applies?** Name the organization, project, and environment. Confirm whether the caller is a user, project service account, or another approved identity, and whether a human API key is being reused for a workload.

**What permissions are actually required?** Identify the minimum permissions the workflow needs. Separate read access from write access. Separate draft actions from system-changing actions. Separate development, testing, staging, and production access assumptions where relevant.

**Which RBAC roles and API key permissions grant that access?** Record the minimum project role, role permissions, and API key permissions. Check for unintended access created by organization-level roles or by multiple roles whose permissions combine.

**Where is current access too broad?** Look for shared service accounts, broad read/write access, admin-level permissions, access to all records when only pilot records are needed, or production access that has not been approved.

**How are secrets protected?** Identify whether tokens, API keys, credentials, certificates, or connection strings are stored safely. Hardcoded credentials, tokens in local files planned for production use, credentials in logs, or reused testing-to-production secrets should be flagged for remediation.

**Can the OpenAI API key be reached from a client?** Confirm that no OpenAI API key is embedded in browser or mobile code. A suspected exposure should trigger usage review, rotation or revocation, and an update to dependent applications.

A strong access-and-secrets boundary does not need to design the full identity system. It should make the risk visible enough that the system owner, platform owner, or security team can validate the next step.

## Slide 20/41 - Recommended exercise: Spot the access and secrets boundary

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice identifying access, permission, and secrets-handling risks in an API workflow.

**Task:** Review the API details below and identify the access and secrets boundary. Focus only on caller identity, required permissions, excessive access, secrets handling, and required remediation.

**API details:** The support-ticket triage API now has more implementation detail. The prototype uses: one shared service account for helpdesk access; broad read access to all support tickets; broad write access to update support tickets; a helpdesk API token stored in a local configuration file on a developer laptop; the same token for testing and the planned production pilot; full request and response logging for debugging; no named owner for approving production write access. A browser-based demo calls the OpenAI API directly with one developer's personal API key embedded in the client. The same OpenAI project and key are planned for testing and the pilot. No OpenAI project-role or API key-permission review has been completed, and no usage-monitoring or rotation owner is named. The workflow only needs to read approved pilot tickets and write a draft triage summary or category after staff review.

Answer these eight prompts: Caller or service identity / Required permissions / Permission or access concern / Secrets-handling concern / Required remediation / OpenAI organization/project boundary / OpenAI caller identity and client-side key exposure concern / Usage monitoring, rotation, or revocation action.

**Estimated time:** 8-10 minutes.

**Suggested output or reflection:** A concise access-and-secrets note that identifies the service account as the caller or service identity; separates what the workflow needs from what the current permissions allow; flags broad read/write access as a least-privilege concern; flags local token storage and test-to-production token reuse as secrets-handling concerns; names a concrete remediation, such as scoping permissions, separating environments, moving secrets to approved storage, or naming the production access owner; flags the client-side personal OpenAI API key as a blocker and routes API calls through a protected backend; recommends a project-scoped non-human identity, least-privilege role and key permissions, separate environment projects or credentials, usage review, and key rotation.

**Optional stretch:** Add one least-privilege rule for the ticket-update action.

## Slide 21/41 - Knowledge check

**An API authenticates successfully using a valid service account. Which question is still required before deployment?**

- Can the API return a useful summary?
- What model will generate the response?
- **What is the service account authorized to access or do?** ✓ Correct
- Is the prototype fast enough in local testing?

Correct! Authentication confirms who or what is calling. Authorization defines what that caller can access or do. A valid service account can still be over-permissioned.

## Slide 22/41 - Summary

In this module, you distinguished authentication from authorization, identified caller types, reviewed secrets-handling assumptions, and applied least privilege.

A secure API review should show who or what can call the workflow, what that caller can access or do, how credentials are protected, and which access questions need approval before deployment.

## Slide 23/41 - Introduction (Module: Add controls, approvals, and auditability)

A security review is not complete until the workflow is reviewable and governable. That means the team needs to define controls, approval gates, auditability expectations, and remediation actions before deployment.

This module helps you define what can proceed automatically, what requires approval, what evidence should be captured, what should never be logged, and what must be fixed before launch.

This module stays at the review level. It does not teach full compliance design, production monitoring implementation, incident response, or detailed eval and guardrail configuration.

## Slide 24/41 - Key definitions

Use these definitions when adding controls.

- **Control** means a rule, check, approval, technical setting, monitoring signal, or process step that reduces risk or makes the workflow safer to operate.
- **Approval gate** means a defined point where a person, team, or system owner must review and approve an output, action, access request, or deployment decision before it proceeds.
- **Human review** means a qualified person reviews an output, action, exception, or recommendation before it affects a customer, system, business process, or sensitive decision.
- **Logging** means recording selected events, requests, responses, errors, actions, approvals, or system activity so the workflow can be monitored, supported, and reviewed.
- **Retention** means how long logs, outputs, review evidence, or related records are kept, and when they are deleted or archived according to customer policy and official guidance.
- **Auditability** means there is enough reviewable evidence to understand what happened, who or what acted, what data or system was involved, and what decision or approval occurred.
- **Remediation** means the fix, control, validation, or process change required to resolve a security, data-handling, access-control, logging, or approval gap.
- **Escalation** means routing a risk, unresolved question, exception, or high-impact decision to the appropriate security, privacy, legal, platform, system-owner, or customer team.

## Slide 25/41 - Define approval gates

Approval gates make clear which outputs, actions, access requests, or deployment decisions can proceed automatically and which require review before launch or use.

When reviewing an API workflow, identify: human review for sensitive outputs; human approval for system-changing actions; escalation when risk or uncertainty appears; who approves the action, output, access request, or deployment decision; which actions are blocked until approval occurs; what evidence confirms that approval happened; which approval questions must be resolved with the customer, platform team, security team, privacy team, legal team, or system owner.

Examples of approval gates may include review before: sending a customer-facing response; changing a customer record; creating, updating, or closing a ticket; triggering an operational workflow; exposing sensitive data; expanding access to a broader user group; launching the API beyond a pilot environment.

For technical workflows, an approval gate should be specific enough to implement later. "Human review required" is a useful start, but the review should also identify who reviews, what they review, what they can approve or reject, what evidence is captured, and what happens if approval is missing.

## Slide 26/41 - Define auditability

Auditability helps security, compliance, platform, and support teams understand what happened after an API workflow runs. It is not just "having logs." It is having the right evidence, protected in the right way, for the right reviewers.

When defining auditability, capture: What operational event should be logged? Who or what initiated the workflow? What source record, action, approval, status, or error category should be visible? Who can review the evidence? What must never be logged? What evidence shows that approval occurred? What evidence shows that access was controlled? What evidence shows that sensitive data, secrets, or restricted fields were not exposed unnecessarily? How long should logs or review evidence be retained, pending customer policy and official guidance? What issue or signal should trigger review, escalation, correction, or pause?

Do not assume more logging is always better. Logs can create risk if they capture secrets, credentials, tokens, personal data, regulated data, customer-confidential data, unnecessary prompt content, sensitive retrieved context, or sensitive generated outputs.

A practical auditability approach separates operational evidence from sensitive content. For example, a workflow may log request ID, caller or service identity, timestamp, endpoint, status code, error category, approval status, and source record ID, while excluding raw prompts, full source documents, credentials, and generated customer-facing text.

**Example: Safer audit event**

```json
{
  "request_id": "req_12345",
  "caller_id": "svc_support_triage",
  "environment": "staging",
  "endpoint": "/triage",
  "source_record_id": "ticket_67890",
  "action": "draft_summary_created",
  "approval_status": "pending",
  "status_code": 200,
  "latency_ms": 842,
  "error_category": null,
  "timestamp": "2026-06-30T15:00:00Z"
}
```

**Example: Unsafe audit event (what to avoid)**

```json
{
  "prompt": "[REDACTED_FULL_TICKET_TEXT_AND_INTERNAL_NOTES]",
  "api_key": "[REDACTED_API_KEY]",
  "customer_email": "[REDACTED_EMAIL]",
  "generated_customer_response": "[REDACTED_GENERATED_RESPONSE]"
}
```

The safe event supports troubleshooting and review without exposing raw prompts, credentials, customer content, or generated narrative that may contain sensitive source data.

## Slide 27/41 - Define remediation

Remediation turns review findings into action. A security review is only useful if it identifies what needs to change, who owns the change, and what evidence will prove the issue has been resolved.

For each issue, capture: What must change before launch? Who owns the fix? What proof is needed after remediation? What validation should happen after the fix? Can the issue be accepted with conditions, must it be remediated before launch, or does it require pause or escalation?

Use the recommendation level that matches the risk:

- **Ready** — No blocking security or data-handling gaps identified at this level of review.
- **Ready with conditions** — Limited issues need documented controls, ownership, or validation.
- **Remediate before launch** — A blocking issue must be fixed before deployment.
- **Pause or escalate** — The risk exceeds course-level review and needs a security, privacy, legal, platform-team, system-owner, or customer decision.

The remediation should be concrete. "Improve logging" is too vague. "Remove raw ticket body from application logs; retain request ID, timestamp, endpoint, status, latency, and error category; validate redaction in staging; assign log-access owner" is actionable.

## Slide 28/41 - Reference pattern: action and approval boundary

Use this reference pattern when you need to decide what an API workflow can do automatically, what requires approval, and what should be blocked.

In many API workflows, the risk changes when the API moves from generating information to changing a system. An internal draft, summary, label, or recommendation may be acceptable within a controlled review flow. A system-changing action usually needs clearer boundaries.

**Allowed action** — Something the API can perform within the approved workflow boundary without additional approval. Common examples: generate an internal draft summary; classify an item for staff review; suggest a next step; return structured output to an internal reviewer; flag an item for review without changing the source system.

**Approval-only action** — May be useful, but should require human approval, system-owner approval, or workflow-owner approval before it proceeds. Common examples: write a generated summary back to a source record; change priority, status, owner, or category; route work to another queue; trigger an escalation; prepare customer-facing language; expand access beyond an approved pilot group.

**Disallowed action** — Should be blocked for the current release because it creates too much risk, lacks approval, or exceeds the intended workflow boundary. Common examples: send customer-facing messages automatically; close tickets automatically; delete or overwrite source content; change account status; trigger external escalation without approval; use data sources that have not been approved for the workflow.

**Approval or escalation owner** — Every approval-only action needs an owner: the system owner, the data owner, the workflow owner, a security reviewer, a privacy reviewer, a platform owner, or a customer decision-maker.

**Audit evidence** — For actions that require approval, define what evidence should exist after the workflow runs: request ID, source record ID, caller or service identity, reviewer identity, approval decision, timestamp, action taken, error state, escalation route (where relevant).

**Logging boundary** — Auditability does not mean logging everything. Avoid logging: raw sensitive content; full prompts or source records where not approved; credentials, tokens, or secrets; personal or regulated data where not approved; customer-confidential details where not approved; generated content that could expose sensitive source data.

Action boundaries help technical teams separate safe automation from actions that require control. The API may be allowed to draft, summarize, classify, or recommend, but that does not automatically mean it should update records, route work, or communicate externally without approval.

## Slide 29/41 - Where controls may be enforced later

In a security review, it is not enough to say, "add a control." The review should also help the next owner understand where that control may need to live later.

You are not expected to design or configure these controls in this course. Your role is to make the control need visible, name the likely owner, and capture what evidence would be needed before pilot, production review, or handoff.

| Control need | Where it may be enforced later | What to capture in the review |
|---|---|---|
| Caller authentication | API gateway, application backend, identity provider, or service layer | Who or what can call the workflow, and who owns the authentication pattern. |
| Authorization | Application logic, downstream system permissions, IAM, RBAC, or policy rules | What access is required, what current access is too broad, and who approves the production scope. |
| Secrets protection | Managed secret storage, runtime configuration, or approved CI/CD secret injection | What secrets are used, where they are stored, whether environments are separated, and who owns rotation or revocation. |
| Logging boundary | Application logging rules, middleware, gateway logging configuration, SDK/client settings, or log pipeline filters | What should be logged, what must not be logged, and who can validate the logging approach. |
| Approval gate | Workflow orchestration, ticketing system, reviewer UI, internal queue, or business process step | What action requires approval, who approves it, what they review, and what evidence proves approval occurred. |
| Disallowed action | Application allowlist, tool/action registry, downstream permission denial, or business rules | What is blocked for the current release and what owner would need to revisit the decision later. |
| Escalation path | Security, privacy, legal, platform, system-owner, workflow-owner, or customer review process | What issue triggers escalation, who receives it, and whether the workflow pauses, continues with conditions, or degrades safely. |

For example, instead of writing "Human approval is required before ticket updates," write: "The API may generate a draft ticket summary, but it must not write that summary back to the ticket until staff approval occurs. The approval gate may need to live in the helpdesk workflow, reviewer UI, or application layer. The workflow owner must confirm the final approach before pilot."

## Slide 30/41 - Knowledge check

**An API can generate an internal summary and automatically update a customer record. The team has not defined who approves record changes or what evidence confirms approval. What is the safest next step?**

- Remove all logging so sensitive data cannot be exposed.
- **Block automatic updates until approval owner and evidence are defined.** ✓ Correct
- Allow automatic updates as long as logs exist.
- Proceed because the API output is useful.

Correct! System-changing actions require clear approval ownership and review evidence. Logging alone does not make an action safe.

## Slide 31/41 - Summary

In this module, you defined approval gates, auditability expectations, logging boundaries, retention questions, escalation triggers, and remediation actions.

The key habit is to make control decisions concrete. A strong review names what is allowed, what is approval-only, what is disallowed, what evidence is captured, what must not be logged, and what must be remediated before launch.

## Slide 32/41 - Introduction (Module: Use the API Security and Data Handling Review)

You have now reviewed the three boundaries that shape API security and data-handling readiness: the data boundary, the access and secrets boundary, and the action and approval boundary.

In this module, you'll bring those boundaries together in the API Security and Data Handling Review.

This review is a take-forward job aid for real API deployment work. Use it when reviewing a customer workflow, internal prototype, pilot candidate, or implementation handoff.

The goal is to make the most important readiness questions visible: what data the API touches, who or what can access it, what actions it can take, what evidence or approval is missing, and what the safest next step should be.

## Slide 33/41 - Key concepts

Use these terms when working with the review.

- **API Security and Data Handling Review** means a first-pass review snapshot that helps technical teams identify security and data-handling assumptions before an API workflow moves toward pilot, production review, or customer handoff.
- **Data boundary** means the data the API receives, processes, stores, logs, sends, or exposes.
- **Access and secrets boundary** means who or what can access the workflow, what permissions are required, and how credentials, tokens, API keys, or other secrets are protected.
- **Action and approval boundary** means what the API can do automatically, what requires approval, and what should be blocked.
- **Evidence gap** means something that must be confirmed before the readiness recommendation can be trusted.
- **Remediation** means the fix, control, validation, or process change needed to address a blocker or risk.
- **Readiness recommendation** means the next-step judgment: ready, ready with conditions, remediate before launch, or pause/escalate.

The review is not a substitute for customer security, privacy, legal, compliance, platform, or system-owner review. It helps prepare for those conversations by making assumptions and gaps visible.

## Slide 34/41 - What the review is used for

Use the API Security and Data Handling Review when a real API workflow is moving from idea or prototype toward a more serious review point.

That review point might be: a customer technical design discussion; a pilot-readiness discussion; a production-readiness review; a handoff to security, privacy, platform, or system-owner teams; a decision about whether a workflow should proceed, proceed with conditions, remediate, or pause.

The review is useful when the API workflow touches any of these: customer-confidential, personal, regulated, internal, or security-related data; internal systems or customer systems; service accounts, tokens, API keys, connectors, tools, or system integrations; logs, audit trails, retained outputs, or monitoring evidence; actions that update records, route work, trigger workflows, or affect customer-facing decisions.

Do not use the course exercise details to complete the take-forward review. In real work, complete the review with approved and sanitized information from the actual workflow being reviewed.

Also avoid using: customer-confidential information unless approved for that review context; production credentials or tokens; sensitive regulated data; proprietary architecture diagrams that are not approved for training or sharing; raw logs that contain secrets, personal data, or customer-confidential content.

When information is missing, write "unknown," "not confirmed," or "requires owner review." That is better than guessing.

## Slide 35/41 - API Security and Data Handling Review snapshot

The API Security and Data Handling Review is organized into five review lenses. Use these lenses after the course when you are reviewing a real API workflow with approved project information.

**Data boundary** — This section identifies what data the API touches and whether that data creates security, privacy, customer-policy, or minimization questions.

Fields: Data touched; Highest likely sensitivity; Data that should be excluded, masked, redacted, or minimized; Logging or retention consideration; OpenAI API endpoint or capability; Default training and abuse-monitoring treatment verified; Application-state retention and "store" behavior; Modified Abuse Monitoring or Zero Data Retention status, eligibility, and endpoint limitations; Official guidance verified as of; Unresolved data owner or classification question; Security validation question.

Quality check: This section is strong when it names specific data fields or data categories, not broad labels. It separates abuse monitoring from endpoint-specific application state, records the endpoint or capability, does not assume Modified Abuse Monitoring or Zero Data Retention is enabled, and identifies the owner and current official guidance needed to validate any sensitive-data, logging, retention, or classification uncertainty.

**Access and secrets boundary** — This section identifies who or what can access the workflow, what permissions are required, and whether credentials are protected appropriately.

Fields: Caller or service identity; OpenAI organization, project, and environment; Caller identity type (user, service account, or other approved workload identity); Required permissions; RBAC role and API key permissions; Permission or access concern; Secrets-handling concern; Client-side key exposure check; Usage monitoring and rotation/revocation owner; Environment-separation assumption; Security validation question.

Quality check: This section is strong when it separates authentication from authorization, identifies the OpenAI organization and project boundary, states the caller identity type, records the minimum RBAC role and key permissions, confirms that keys are not exposed client-side, separates experimentation, staging, and production, and names the usage-monitoring and rotation or revocation owner.

**Action and approval boundary** — This section identifies what the API can do automatically, what requires approval, and what should be blocked.

Fields: Allowed action; Approval-only action; Disallowed action; Approval or escalation owner; Audit evidence required; Security validation question.

Quality check: This section is strong when it draws a clear line between generating information and changing a system. System-changing actions, customer-facing actions, and sensitive workflow changes should have explicit approval ownership and evidence.

**Evidence gap and remediation** — This section identifies what evidence is missing and what must change before the workflow can move forward.

Fields: Evidence available; Evidence missing; Required remediation; Owner; Validation evidence required after remediation.

Quality check: This section is strong when each gap has a named owner, a concrete remediation, and a way to prove the issue has been resolved. Avoid vague statements such as "improve security" or "review later."

**Readiness recommendation** — This section makes the review actionable.

Fields: Recommendation; Reason; Top blocker or condition; Next safe step; Handoff owner; Evidence that would change the recommendation.

Quality check: This section is strong when the recommendation follows directly from the evidence. Another stakeholder should be able to understand why the workflow is ready, conditionally ready, blocked, or needs escalation, who owns the next action, and what evidence would change the recommendation.

Before using this review for implementation or customer guidance, confirm the current OpenAI data controls, API key safety, and permissions guidance. Record the verification date and any account- or project-specific owner confirmation.

## Slide 36/41 - Recommendation levels

Use the review findings to recommend the safest next step.

**Ready** — Use this when no blocking security or data-handling gaps are identified at this level of review. A workflow may be ready when the data boundary is clear, access is scoped, secrets handling is approved, action boundaries are defined, logs exclude sensitive content, and approval evidence is available where needed.

**Ready with conditions** — Use this when the API can continue only if specific controls, owners, or validation steps are documented. A workflow may be ready with conditions if it is internal and limited in scope, but a specific item such as log-review ownership, retention policy, or final approval ownership still needs confirmation before broader rollout.

**Remediate before launch** — Use this when a blocking issue must be fixed before deployment. Typical blockers include: sensitive data in logs; excessive permissions; unsafe secret handling; missing approval gates for system-changing actions; unclear production access; unresolved data ownership.

**Pause or escalate** — Use this when the risk or uncertainty exceeds this course-level review and needs a decision from the appropriate security, privacy, legal, platform, system-owner, or customer team. Typical escalation points include: jurisdiction-specific data questions; unclear customer policy; regulated data uncertainty; sensitive automated actions; uncertainty about whether the workflow should be allowed at all.

## Slide 37/41 - Recommended exercise: Complete a security and data-handling review correction

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice turning a vague security review into a specific, evidence-based API Security and Data Handling Review.

**Task:** Review the API details below and rewrite the weak review statement so another technical, security, privacy, platform, or system-owner stakeholder could understand the evidence and the safest next step. Do not make legal or compliance conclusions. Mark unresolved questions as "not confirmed" or "requires owner review."

**API details:** A support-ticket triage API is moving toward a limited pilot. The API receives ticket_id, requester_role, product_area, subject, description, priority, region, and internal_notes from the helpdesk system. Production tickets may contain customer-confidential or personal data, but classification has not been confirmed. The API generates an internal summary, category, risk flag, and recommended next action. Full request and response bodies are currently logged. A shared service account can read and write all tickets in the test environment. Production access scope has not been approved. The API token is stored in a local configuration file. No approval owner has been named for applying recommended next actions. The team wants to start a limited pilot next week. The backend uses the Responses API in an OpenAI project with default data controls. The team has not verified abuse-monitoring retention, application-state behavior, or whether Modified Abuse Monitoring or Zero Data Retention is approved. A browser demo calls the OpenAI API with one developer's personal API key embedded in client code. OpenAI project roles, API key permissions, usage monitoring, and rotation or revocation ownership have not been reviewed.

Weak review statement: "The API uses support-ticket data. Access is controlled by a service account. Logs are enabled. Human review is required. Ready for pilot."

In your correction, include: Data boundary; Access and secrets boundary; OpenAI platform data-control and endpoint check; OpenAI project, RBAC, and key-safety remediation; Official guidance verified as of; Action and approval boundary; Evidence gap and remediation; Readiness recommendation; Handoff owner or required reviewer; Evidence that would change the recommendation.

**Estimated time:** 10-12 minutes.

**Suggested output or reflection:** A concise review correction that replaces vague claims with specific evidence; connects each concern to the API details provided; names at least one required owner or reviewer; identifies the top blocker or condition; gives a next safe step that does not ignore unresolved security or data-handling risks; separates default abuse monitoring from endpoint-specific application state, does not assume Modified Abuse Monitoring or Zero Data Retention, and names the current official documentation to verify; treats a client-side or shared OpenAI API key as a blocker requiring protected backend routing, a scoped project identity, role and key-permission review, usage review, and rotation.

**Optional stretch:** Add two remediation validation tests: one staging log check that proves raw ticket bodies and tokens are not captured, and one access check that confirms the pilot uses the intended OpenAI project, scoped identity, role, and key permissions.

## Slide 38/41 - Knowledge check

**A support-triage API is proposed for a limited internal pilot. The team will use approved test tickets, store credentials securely, separate test and pilot access, require staff approval before ticket updates, and exclude sensitive content from logs. The audit-event retention period and weekly log-review owner are still unconfirmed. What is the most appropriate recommendation?**

- Remediate before launch because every missing detail is always blocking.
- **Ready with conditions.** ✓ Correct
- Ready with no conditions.
- Pause or escalate because no API can launch without a full legal review.

Correct! "Ready with conditions" may be appropriate when the remaining issues are limited, explicit, owned, and resolvable before broader rollout. The condition should name the missing retention decision and log-review owner. If sensitive content were still logged, production access were too broad, secrets were unsafe, or automatic system-changing actions were unapproved, the safer recommendation would be remediate before launch or pause/escalate.

## Slide 39/41 - Summary

In this module, you brought together data, access, secrets, controls, logging, auditability, and remediation considerations into a concise API Security and Data Handling Review snapshot.

The review is a take-forward job aid, not a course submission. It helps implementation teams avoid vague security claims and gives reviewers a clear path to approve, condition, remediate, or escalate.

## Slide 40/41 - Recap

In this course, you learned how to identify the security and data-handling assumptions that can block or reshape an API workflow.

You reviewed five areas:

- **Data boundary** — What data the API touches and its sensitivity.
- **Access and secrets boundary** — Who can access the workflow, required permissions, and credential protection.
- **Action and approval boundary** — What can happen automatically, what needs approval, and what must be blocked.
- **Evidence gaps and remediation** — What is missing, what must change, and who owns the next action.
- **Readiness recommendation** — Whether to proceed, proceed with conditions, remediate, or pause and escalate.

The key takeaway is to make these boundaries and risks visible before pilot, production review, or customer handoff.

## Slide 41/41 - Congratulations

Congratulations, you've completed the course!

Use the API Security and Data Handling Review with approved project information when assessing a real API workflow. Do not reuse course exercise details as a real review or include unapproved confidential data, credentials, regulated information, raw logs, or proprietary materials.

The review does not provide final approval. It helps reviewers see the data, access, and action boundaries; evidence gaps; remediation needs; and safest next step. These findings also inform later context, data, retrieval, and deployment decisions.
