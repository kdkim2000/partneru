# Cyber Governance And Operating Model

## Slide 1/55 - Title

Created July 2026

## Slide 2/55 - Introduction

Daybreak helps customers move from security signals to reviewable actions, but that work only scales with governance. Defensive cyber workflows can touch sensitive code, repositories, credentials, findings, test environments, risk decisions, and remediation paths. Before work begins, customers need clear boundaries for access, review, and decision records.

In this course, you'll learn to assess whether a customer has the operating model to use Daybreak and Codex Security in a governed, repeatable workflow. You'll practice asking readiness questions, spotting risky scope, preserving human accountability, and deciding whether to proceed, pause, escalate, or expand.

## Slide 3/55 - What you'll learn

By the end of this course, you'll be able to:

- Explain why governance is built into the Daybreak operating model.
- Use an operating model lens to assess workflow readiness.
- Confirm minimum readiness conditions: authorized defensive workflow, customer-owned asset, approved environment, and named reviewers.
- Identify key governance decisions for access, permissions, data handling, monitoring, auditability, evidence retention, and records.
- Clarify what Codex Security can support and which decisions remain customer-owned.
- Decide whether to proceed, pause, escalate, or expand based on readiness, risk, and escalation triggers.

Let's get started!

## Slide 4/55 - Introduction (Module: Why governance is Daybreak's operating model)

Daybreak should be understood as a governed defensive cyber workflow motion, not simply a model-access conversation or unmanaged automation.

In this module, you'll learn why governance is the working structure that helps customers define what is allowed, what is in scope, who reviews output, where evidence goes, and when a partner should pause or escalate.

## Slide 5/55 - Why Daybreak needs governance

Daybreak and Codex Security can help customers move faster through defensive security work, but the work itself is sensitive.

It may touch source code, internal systems, vulnerability findings, security tools, approval processes, remediation decisions, and records used by security, engineering, risk, and compliance teams.

That is why governance is not an afterthought. It is part of how Daybreak creates durable customer value.

Without governance, a customer may ask for something broad, such as "scan everything," "test all internet-facing systems," or "automate all fixes."

Those requests may reflect real urgency, but they are not yet safe or specific enough to act on.

They do not clarify ownership, authorization, environment, access, data handling, review gates, evidence standards, or escalation paths.

A strong operating model helps partners turn broad interest into a responsible next step. It helps you ask:

- What defensive workflow is the customer trying to improve?
- What asset or environment is approved?
- Who will review the output?
- What can Codex-supported execution access and do?
- What evidence will be retained?
- Which decisions remain with the customer?

In customer discovery, use this lens to strengthen opportunity documentation and avoid vague or unsupported cyber notes. In technical validation, use it to confirm the readiness conditions that must be true before workflow execution, testing, remediation support, or expansion.

Use this operating model lens to check whether a Daybreak workflow is ready to proceed, needs clarification, requires escalation, or may be ready to expand.

## Slide 6/55 - What an operating model means in this course

In this course, an operating model means the practical working pattern that defines:

- Who can do the work
- What they can do
- Which assets are in scope
- Which environment is approved
- Which tools and data may be used
- Which approvals are required
- What evidence is produced
- Who reviews the output
- How long evidence is retained
- Where final decisions are recorded

This course uses an operating model lens because customers need more than advanced AI capability.

They need a governed way to bring that capability into existing security and engineering workflows without losing control of scope, access, evidence, review, or accountability.

In customer conversations, this lens turns broad interest in cyber AI into concrete readiness questions.

In technical validation, it clarifies the conditions that must be true before workflow execution, testing, remediation support, or expansion.

A simple way to think about it:

Daybreak creates value when it helps the customer move from security signal to reviewable action. Governance is what makes that movement authorized, observable, accountable, and repeatable.

## Slide 7/55 - The six operating model questions

You will use six operating model questions throughout this course.

This framework is introduced because Daybreak conversations can become complex quickly. A customer may mention model access, repositories, scanners, production testing, remediation automation, or special cyber capability in the same conversation.

The six questions give you a stable way to slow the conversation down and check whether the workflow is ready.

| Operating model question | What it helps clarify |
|---|---|
| Are we allowed to do this work? | Authorization, defensive purpose, customer permission, and scope. |
| Is the asset customer-owned and the environment approved? | Whether the target and environment are appropriate for the workflow. |
| What can the workflow access and do? | People, systems, tool permissions, and allowed actions. |
| What evidence will be produced, reviewed, retained, and recorded? | Auditability, evidence quality, review process, and systems of record. |
| Which decisions remain customer-owned? | Human accountability for risk, severity, remediation, release, retention, and closure. |
| Should we proceed, pause, escalate, or expand? | The responsible next step based on operating model readiness. |

These questions are intentionally simple. They create a shared standard for sales, pre-sales, and technical conversations, keeping the focus on governance readiness rather than deployment design, cyber lab work, or product setup.

## Slide 8/55 - Context, agentic runtime, and observability

Use three enterprise operating-model layers to discuss a governed Daybreak workflow: context, agentic runtime, and observability.

These terms help commercial and technical teams describe the operating model in the same language.

**Context** is what the AI is allowed to know or use. In a Daybreak workflow, context may include an approved repository, branch, commit, scanner finding, ticket, security policy, architecture note, test output, or review record.

The key question is: What information is approved for this workflow, and what must stay out of scope?

**Agentic runtime** is where and how Codex or Codex Security does work. This may be a local checkout, an approved sandbox, a lower-level test environment, a Codex workflow surface, a CI-style worker, or another approved execution environment.

The key question is: Where can the workflow run, which tools can it use, and what actions are permitted?

**Observability** is how the customer monitors, controls, and improves the workflow. It includes approval records, run logs, tool activity, generated artifacts, evidence packets, reviewer dispositions, and system-of-record updates.

The key question is: Can the customer trace what happened and decide whether the output is ready for human review?

In customer conversations, these layers keep the discussion workflow-first rather than access-first. In technical validation, they identify the operating facts that must be confirmed before remediation support, integration, automation, or expansion.

## Slide 9/55 - Real-world example

A customer has a large backlog of scanner findings. The security team says they are spending too much time validating which findings are real, assigning ownership, testing safely, and documenting closure. Engineering teams also push back on tickets that do not include enough evidence or remediation context.

Daybreak and Codex Security may help accelerate validation and evidence generation.

But the first question is not "Which model should they use?" The first question is whether the workflow can be governed.

A stronger first step would define one bounded backlog slice, one customer-owned repository, one approved environment, a named AppSec reviewer, evidence expectations, and a stop condition.

The point is not to create more alerts. The point is to help the customer move from security signal to reviewable action without removing human accountability.

## Slide 10/55 - Knowledge check

**Question:** A customer says: "We want Daybreak to validate security findings automatically across our whole backlog. We need to move faster." What is the strongest reason to introduce an operating model before recommending the work?

- It is mainly needed when the customer asks for an executive presentation.
- It lets the partner avoid discussing the customer's current security tools.
- **It helps confirm the authorized workflow, approved assets, runtime boundaries, evidence path, and customer-owned decisions before work begins** ✓ Correct
- It proves Codex Security can replace manual risk decisions once the output looks accurate.

*Explanation: Governance is part of the Daybreak operating model because it clarifies what is allowed, what is in scope, what the workflow can access, how output will be reviewed, and which decisions remain with the customer.*

## Slide 11/55 - Summary

In this module, you learned why governance is part of the Daybreak operating model. Daybreak work touches sensitive assets, tools, evidence, and risk decisions, so customers need a governed way to use AI-assisted security workflows.

You also learned the six operating model questions you'll use throughout the course. These questions help you move from broad cyber interest to concrete readiness: authorization, approved assets, access boundaries, evidence, customer-owned decisions, and the right next step.

## Slide 12/55 - Introduction (Module: Authorized scope, customer-owned assets, and defensive environments)

The first governance question is simple: Are we allowed to do this work?

In this module, you'll learn how to check whether a Daybreak or Codex Security workflow is authorized, defensive, customer-owned, and bounded before recommending a next step.

## Slide 13/55 - Are we allowed to do this work?

In this course, authorized means the customer has explicit permission to work on named assets, in approved environments, for a defined defensive purpose.

Defensive means the work is intended to protect the customer's own systems.

Examples include validating findings, prioritizing risk, proposing remediation for review, or creating evidence for a security decision.

A strong example of a customer-safe question is:

> "What are we allowed to inspect, for what defensive purpose, and under whose authority?"

This question helps avoid vague or risky assumptions.

**For example**

"Our team wants to review internet-facing systems" is not enough.

Which systems? Owned by whom? In which environment? With what permission? For what purpose? Who will review the output?

If the customer cannot answer those questions, the workflow is not ready to proceed. That does not mean the opportunity is weak. It means the next step is to clarify authorization and scope.

## Slide 14/55 - The four-part scope statement

A good first Daybreak workflow should be summarized in a short scope statement. This statement does not need to be a full deployment plan. It is a minimum operating model package that makes the next step concrete.

| Scope element | Question to answer |
|---|---|
| Customer-owned asset | Which repository, application, backlog slice, workflow, or environment is in scope? |
| Approved environment and access path | Where will the work happen, and how will access be approved? |
| Named owner and reviewer | Who owns the workflow, and who reviews the output? |
| Evidence expectation and stop condition | What evidence should be produced, and when should the workflow stop or escalate? |

Use the four-part scope statement to turn a broad cyber request into a clear next step.

By naming the approved asset, environment, owner, reviewer, evidence expectation, and stop condition, you can document the opportunity clearly and give technical counterparts the boundaries they need before validation begins.

## Slide 15/55 - What a good first workflow looks like

A good first workflow is narrow enough to govern and meaningful enough to produce evidence.

Strong starting points often include one:

- Customer-owned repository.
- Approved application or service.
- Vulnerability backlog slice.
- Vulnerability class.
- Pull request or diff pattern.
- Approved lower-level environment.

A weak first workflow is usually too broad, too sensitive, or too unclear. Examples include:

- "Scan everything."
- "Test all internet-facing systems."
- "Automate all remediation."
- "Run this against production first."
- "Use AI to test external targets."
- "Let's decide reviewers after we see the output."

These requests may signal real customer urgency, but they are not ready as written. You should narrow the workflow before recommending a Daybreak or Codex Security next step.

Production and live testing require explicit authorization and should not be treated as the default starting point.

## Slide 16/55 - Real-world example

A customer asks to apply Daybreak across all internet-facing applications.

The request may be directionally useful because it suggests the customer wants broader security coverage. But it is too broad to govern as a first step unless ownership, environment boundaries, access controls, and review gates are already clear.

A better starting point would be one customer-owned repository, one approved lower-level environment, or one high-priority backlog slice.

The customer should also name the human reviewer and agree what evidence is expected.

The partner should not reject the customer's ambition. The partner should help turn it into a defensible first workflow.

## Slide 17/55 - Recommended exercise: Scope the first safe workflow

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Practice narrowing a broad cyber ask into an authorized, defensible starting point.

Suggested learner task:

Review this customer context:

> A customer says, "We want to use Daybreak across all internet-facing applications because our security backlog is growing. We also want to know whether Codex Security can help propose fixes."

Write a four-part scope statement that covers:

- The customer-owned asset or workflow in scope.
- The approved environment and access path.
- The owner or reviewer.
- The evidence expectation and stop condition.

**Estimated time:** 7 minutes

**Suggested output and reflection:** A 5–7 line scope package that states what is allowed, what is not allowed, who owns review, and what should happen if the workflow reaches a stop condition.

## Slide 18/55 - Knowledge check

**Question:** Which proposed first workflow is ready enough to discuss as a bounded Daybreak next step?

- Run the workflow across all internet-facing applications and use the output to close security tickets automatically.
- **Use the customer's owned repository in an approved lower-level environment, with named AppSec and engineering reviewers, agreed evidence expectations, and a stop condition.** ✓ Correct
- Review a third-party target because the customer believes they probably have permission.
- Test the customer's production environment first, then decide who should review the findings.

*Explanation: This option is bounded, customer-owned, approved, reviewed, evidence-led, and clear about when the workflow should stop or escalate.*

## Slide 19/55 - Summary

In this module, you learned how to check whether a Daybreak workflow is authorized, defensive, customer-owned, and appropriately bounded. A strong first workflow should name the asset, environment, owner, reviewer, evidence expectation, and stop condition.

The key move is to narrow broad cyber interest into one safe starting point. That helps the customer learn from a real workflow while preserving governance and human accountability.

## Slide 20/55 - Introduction (Module: Access controls, tool permissions, and data handling)

Once scope is clear, the next question is: What can the workflow access and do?

This module focuses on access controls, tool permissions, and data handling. These topics can sound technical, but they are also part of responsible selling and qualification. A Daybreak opportunity is not ready if you cannot explain, even at a high level, what access is needed and what action boundaries should be preserved.

You do not need to design the full implementation in this course. You do need to recognize whether access is proportionate to the approved workflow.

## Slide 21/55 - What can the workflow access and do?

Access is part of solution design, not an administrative detail.

Before work begins, the customer should confirm what the workflow can see, which tools it can use, and what actions it can take.

The same technical task can carry different risk depending on its permissions.

For example, a review workflow may be relatively narrow if it is read-only against one approved repository slice.

The risk changes if it can create branches, connect to internal systems, run tests, trigger follow-up actions, access logs, or update tickets.

Access clarity strengthens customer discovery by making the opportunity specific: the note should identify the workflow, asset, reviewer, and next step rather than simply saying "customer wants to run Codex Security on their environment."

In technical validation, the same clarity helps keep permissions proportionate, so the workflow only receives the access needed for the approved scope.

## Slide 22/55 - People, systems, and actions

Access conversations can become scattered quickly. A customer may mention users, repositories, scanners, test environments, ticketing systems, logs, CI/CD, and remediation in the same discussion.

Use three access categories to keep the conversation precise: people, systems, and actions.

This model is not a new compliance framework. It is a practical way to confirm whether the workflow's permissions match the approved scope.

| Access category | Sales / GTM should listen for | Technical / deployment should confirm |
|---|---|---|
| People | Who owns, approves, runs, reviews, and requests expansion. | Identity model, role assignment, approval path, reviewer queue, and escalation owner. |
| Systems | Which repositories, branches, scanner findings, logs, tickets, policies, or environments are in scope. | Repository boundary, branch or commit scope, environment boundary, tool connections, and system-of-record location. |
| Actions | What the workflow is allowed to do. | Which customer-selected action boundary applies, using the course checklist in Card 4.4—for example, review-only, approved testing, proposed change preparation, reviewable pull request preparation, evidence export, a recurring run, or downstream action. |

A strong access boundary is proportionate. A review of one approved repository slice should not require broad access to unrelated repositories, live systems, production data, or downstream tools.

The most important technical check is not "Can the tool do this?" It is: "Does the customer's approved operating model allow this workflow to do this action, in this environment, with this data, under this review path?"

## Slide 23/55 - Action boundaries: a course operating checklist

Use this course-created operating checklist to state customer-selected action boundaries in plain language before a workflow begins. It is not a set of published Codex Security product modes or UI settings. It helps commercial and technical teams distinguish reviewing evidence, running approved checks, preparing proposed changes, and taking actions that affect customer systems.

Confirm each customer-selected action boundary before the workflow begins:

**Read-only**

The workflow reviews approved artifacts and produces a report or evidence summary.

**Approved testing**

The workflow can run approved checks or tests in an approved environment.

**Proposed change preparation**

The workflow can prepare a separate branch or proposed change for review.

**Reviewable pull request preparation**

The workflow can prepare a pull request for human review, subject to the customer's normal controls.

**Evidence export**

The workflow can send evidence or summaries into a vulnerability management, ticketing, or tracking system.

**Recurring run**

The workflow runs on an agreed schedule or event, such as a pull request or CI/CD signal.

**Downstream action**

The workflow can affect downstream systems, code paths, release processes, or operational records.

The first workflow should usually start with the least-privileged customer-selected action boundary that can answer the evaluation question. For example, if the customer only needs to know whether Codex Security can improve finding validation, a review-only workflow may be enough. If the customer wants remediation support, proposed change or pull request preparation may be considered later—but only after review gates, test expectations, and rollback assumptions are clear.

Do not imply that Codex Security automatically commits, merges, ships, closes tickets, or accepts risk. Those are customer-owned decisions.

Before expanding the action boundary, confirm:

- Who approves the permission change?
- Which environment is approved?
- Which identity or role will run the workflow?
- Which tools or systems can be accessed?
- What logs and evidence will be retained?
- Who reviews the output before it affects code, tickets, release decisions, or risk records

## Slide 24/55 - Data handling, secrets, and retention

Data handling decisions should be made before work begins. In cyber workflows, data handling applies to more than the initial prompt or repository.

It may include source code, scanner findings, dependency data, tickets, logs, test output, generated reports, temporary files, repository clones, proof artifacts, and exported evidence.

Before work begins, the customer and appropriate account or technical owners should confirm items such as:

- Which data types are allowed in the workflow.
- Which data types are prohibited.
- Whether secrets, credentials, tokens, keys, or production data may appear in scope.
- How secrets or sensitive values should be redacted, excluded, or handled.
- Whether repository clones, generated files, logs, or temporary outputs may be retained.
- Where final evidence can be stored.
- Who can access the evidence.
- How long evidence should be retained.
- What must be deleted after the workflow.

In technical validation, pay close attention to temporary artifacts. A workflow may create intermediate files, local reports, test outputs, logs, cloned repositories, or exported summaries.

Those artifacts can carry sensitive information even when the final report looks safe.

A good follow-up conversation should use the approved review record, not unapproved repository content, disposable clones, raw customer data, or temporary lab outputs.

Avoid making unsupported data-handling claims. Do not promise special retention terms, Zero Data Retention, special workspace behavior, or access exceptions unless those details are confirmed through the appropriate OpenAI and customer channels.

## Slide 25/55 - Customer-safe access language

Use careful access language in customer conversations. The goal is to keep the conversation workflow-first, governed, and accurate.

| Use language such as | Avoid language such as |
|---|---|
| "The first step is to scope the workflow and confirm the required access path with the customer's security owners and the OpenAI account team." | "We can get you the cyber model." |
| "Most defensive AppSec evaluations should begin with a bounded workflow and approved access assumptions." | "This removes refusals." |
| "We should confirm data handling, reviewer ownership, and escalation paths before moving toward automation or broader coverage." | "Trusted Access is automatic." |
| "The workflow should only access the systems and artifacts needed for the approved scope." | "This includes special data handling or deployment terms." |
| "Any remediation proposal still needs customer review and approval." | "Codex Security can automatically fix and ship these issues." |

This language helps you stay credible with both security and engineering stakeholders. It also helps prevent early conversations from turning into unsupported access, availability, or automation claims.

## Slide 26/55 - Knowledge check

**Question:** Match each access decision to the correct category.

- Who can request broader or recurring coverage after the first workflow → **People** ✓ Correct
- Who can approve, run, and review the workflow → **People** ✓ Correct
- Whether logs, policies, or review records may be used as context → **Systems** ✓ Correct
- Which repository, scanner output, ticketing system, or lower-level environment is in scope → **Systems** ✓ Correct
- Whether the workflow can read, report, branch, test, propose remediation, or trigger a follow-up step → **Actions** ✓ Correct

## Slide 27/55 - Summary

In this module, you learned that access is part of solution design. A governed Daybreak workflow should clarify people, systems, and actions before work begins.

You also learned why tool permissions, data handling, retention, and safe access language matter. Access should be proportionate to the approved workflow, and partners should avoid promises about special model access, refusal behavior, data handling, or automatic remediation.

## Slide 28/55 - Introduction (Module: Monitoring, auditability, evidence retention, and systems of record)

After scope and access come the evidence questions: Can the output be reviewed, trusted, retained, and recorded?

This module moves from permission to proof. You'll learn how Daybreak and Codex Security outputs become evidence for human review, not automatic decisions. In customer conversations and technical validation, the value story should focus on decision quality: clearer evidence, stronger reviewer confidence, and records the customer can use in its existing security process, not raw finding volume.

## Slide 29/55 - Can the output be reviewed?

Any output from a Codex-supported security workflow should be treated as evidence for human review, not as an automatic ticket queue, closure decision, production fix, or risk acceptance.

Strong evidence helps the customer decide whether a candidate finding should be confirmed, investigated, suppressed, deferred, remediated, or escalated.

Weak evidence creates uncertainty. It may cause engineering pushback, delayed closure, duplicated review, or overclaiming.

Preserve the difference between technical output and accountable decision-making. Technical output may summarize findings, propose remediation, or organize evidence.

The customer still decides whether the finding is real, whether the risk is material, whether remediation is accepted, and where the decision is recorded.

This distinction is useful in selling. The strongest message is not "we generated more findings." The stronger message is "the workflow helped reviewers make better, faster, better-evidenced decisions."

## Slide 30/55 - The decision-grade evidence record

A Codex Security output becomes stronger when it is turned into a decision-grade evidence record. This record helps security, engineering, and governance stakeholders see what happened, what the evidence supports, what remains unproven, and what decision the customer needs to make.

This structure is introduced because cyber outputs need provenance. A reviewer should not have to guess which repository was reviewed, which environment was used, whether testing was authorized, or where the final decision was recorded.

You do not need to collect every element in every first workflow; use this as a completeness check when the workflow becomes sensitive, repeated, or expansion-ready.

| Evidence element | What it should capture |
|---|---|
| Workflow or run identifier | The run, scan, review, or workflow instance being discussed. |
| Scope boundary | What was reviewed and what was out of scope. |
| Approved artifact | Repository, branch, commit, path, ticket, scanner finding, or code slice. |
| Environment | Local checkout, sandbox, lower-level environment, CI-style worker, or other approved runtime. |
| Source fact | What the code, finding, log, diff, test output, or artifact directly shows. |
| Validation method | How the claim was checked, such as source review, approved test, scanner comparison, or human review. |
| Supported inference | A reasonable conclusion drawn from the available evidence. |
| Proof gap | What has not been tested, reviewed, reproduced, or approved. |
| Proposed action | Investigate, suppress, defer, remediate, re-test, escalate, or record. |
| Reviewer disposition | The human reviewer's decision or required next review. |
| System-of-record entry | Where the decision, owner, status, and next action are recorded. |
| Retention and cleanup status | What evidence is retained and what temporary artifacts must be removed. |

In customer-facing value conversations, this record helps explain what was actually proven. In technical validation, it preserves the operating facts needed to check the workflow, reproduce the review path, and avoid overstating the output.

## Slide 31/55 - Monitoring and auditability

The customer should be able to trace what happened in a Daybreak workflow.

That includes:

- What workflow was run
- Who approved it
- What asset was in scope
- What environment was used
- What tools and permissions were used
- What evidence was produced
- Who reviewed it
- What decision was made
- Where the decision was recorded

This is observability in practice. Observability should support operational control, not just reporting after the fact.

As workflows expand, monitoring helps customers confirm that AI-assisted security work is following policy, preserving review gates, and producing usable evidence. It also supports your judgment. If the customer cannot monitor or audit the workflow, you may need to pause, narrow scope, or escalate before recommending expansion.

## Slide 32/55 - Systems of record stay customer-owned

Daybreak and Codex Security should complement the customer's existing security and engineering processes.

They should not be positioned as replacing the customer's scanners, ticketing systems, policy systems, risk registers, CI systems, approval workflows, or audit processes by default.

The customer decides what becomes an official:

- Finding
- Ticket
- Accepted fix
- Exception
- Risk acceptance
- Backlog item
- Audit record
- Closure note

This matters because many security teams already have tools and systems of record.

Their problem is often not lack of signal. Their problem is turning signal into validated, prioritized, reviewable action with enough evidence to support a decision.

You should help the customer decide where outputs belong in the existing workflow, not assume Daybreak replaces the workflow.

## Slide 33/55 - Real-world example

Codex Security produces a finding summary that appears credible. It identifies an approved repository slice, points to relevant source facts, and suggests a bounded remediation path.

That output is useful, but it is not enough by itself. The customer still needs to know:

- What was reviewed
- What was out of scope
- Which claims are source facts
- Which conclusions are supported inferences
- What was not tested
- Who must review the finding
- Where the decision will be recorded

A better follow-up is to convert the output into an evidence record. The AppSec reviewer can then decide whether the finding should be confirmed, investigated further, suppressed, remediated, or escalated.

## Slide 34/55 - Recommended exercise: Build a decision-grade evidence record

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Practice turning technical output into a reviewable governance artifact with enough provenance for security and engineering review.

Suggested learner task:

Review this sample workflow note:

> "Codex Security reviewed the approved payments-service repository slice on branch feature-auth-checks in a lower-level environment. The workflow compared two authorization code paths and referenced scanner finding APPSEC-1842. It noted that one path checks account ownership before returning customer data, while the newer path appears to rely on a caller-provided account ID. No production testing was authorized. A targeted unit test was suggested, but no remediation branch has been approved yet. The AppSec reviewer needs to decide whether this should become a confirmed finding, a proof gap, or a suppressed candidate."

Create a decision-grade evidence record that includes scope, source fact, supported inference, proof gap, reviewer decision, and system-of-record entry; make run identifier, environment, validation method, proposed action and as an optional stretch, retention.

**Estimated time:** 8 minutes

**Suggested output and reflection:** A brief evidence record that separates what is known, what is inferred, what has not been proven, what action is proposed, and what decision remains customer-owned.

## Slide 35/55 - Knowledge check

**Question:** Match each evidence element to its meaning.

- A reasonable conclusion drawn from available evidence → **Supported inference** ✓ Correct
- What a human reviewer must accept, reject, suppress, remediate, or escalate → **Reviewer disposition** ✓ Correct
- What has not been proven, tested, or reviewed → **Proof gap** ✓ Correct
- Where the decision, owner, and next action are recorded → **System-of-record entry** ✓ Correct
- What was reviewed and what was out of scope → **Scope** ✓ Correct
- What the code, finding, log, diff, or artifact directly shows → **Source fact** ✓ Correct

## Slide 36/55 - Summary

In this module, you learned how monitoring, auditability, evidence retention, and systems of record make Daybreak outputs reviewable.

The key distinction is that Codex Security output is evidence for human review, not an automatic decision. Customers need a clear evidence record, an agreed retention path, and a system-of-record entry that preserves ownership and accountability.

## Slide 37/55 - Introduction (Module: Human review, customer responsibility, and remediation acceptance)

The next governance question is: Which decisions remain customer-owned?

This module helps you avoid overclaiming what Daybreak or Codex Security does. Codex-supported workflow execution may help customers move faster, but the customer remains accountable for scope, risk, severity, remediation, release, records, and governance decisions.

This responsibility split is not a weakness in the value story. It is what makes defensive cyber work trustworthy.

## Slide 38/55 - Who decides?

Codex-supported workflow execution can help inspect assets, organize evidence, generate structured reports, suggest remediation, run approved checks, and prepare reviewable outputs.

The customer remains responsible for:

- Scope
- Authorization
- Risk decisions
- Severity judgment
- Remediation acceptance
- Production approval
- Data handling
- Evidence retention
- Systems-of-record updates

You should be able to explain this split clearly. The message is not "Codex does less than expected."

The message is "Daybreak helps the customer move faster through governed workflows while preserving customer accountability."

That matters to CISOs, AppSec leads, engineering leaders, compliance teams, and technical reviewers. Each group may have a different concern, but all of them need to know that human review remains the control point.

## Slide 39/55 - Codex-supported execution vs. customer-owned decisions

Use this distinction when explaining what the workflow can support and what the customer must decide.

| Codex-supported workflow execution can help with | Customer-owned decisions include |
|---|---|
| Reviewing scoped artifacts | What is in scope |
| Structuring findings and evidence | Whether the asset and environment are approved |
| Suggesting bounded remediation | Whether the risk is real and material |
| Preparing reports or review materials | Whether severity is justified |
| Running approved checks where authorized | Whether data handling is permitted |
| Summarizing residual risks or follow-up items | Whether remediation is accepted |
| Organizing evidence for review | Whether a change can be merged, released, deferred, or closed |
| Preparing output for a human reviewer | What must be retained in official systems of record |

This distinction should appear in both customer-facing language and internal opportunity notes. It helps you avoid unsupported automation claims and helps customers understand the role of human review.

## Slide 40/55 - Review gates across security and engineering

A governed Daybreak workflow should identify review gates before output is produced, not after the customer is already debating whether to accept a finding or patch.

Different reviewers answer different questions.

**Security reviewers**

Validate risk, severity, evidence quality, policy alignment, and escalation needs.

**Engineering reviewers**

Validate code impact, test coverage, maintainability, dependency effects, and operational risk.

**Business, risk, legal, compliance, or architecture owners**

May be needed when the workflow involves residual risk, exceptions, regulated data, critical systems, production activity, or sensitive access.

To make the review path explicit, ask:

> "Who needs to review this output before it can affect a ticket, risk record, code change, or business decision?"

## Slide 41/55 - Real-world example

Codex Security proposes a bounded patch for a validated issue. The proposal may help the customer move faster, but it is not automatically safe to merge or sufficient to close the issue.

Engineering still needs to review technical safety, test coverage, maintainability, and operational risk. Security still needs to confirm whether the evidence supports the finding and whether the remediation addresses the risk.

If the workflow touches a regulated system or production release, additional review may be required.

Codex can accelerate reviewable work. The customer remains accountable for the decision.

## Slide 42/55 - Knowledge check

**Question:** Match each task or decision to the correct owner type.

- Decide whether the risk is material enough to require remediation → **Customer-owned decision** ✓ Correct
- Run an approved targeted check where authorized → **Codex-supported workflow execution** ✓ Correct
- Record official closure in the customer's risk or ticketing system → **Customer-owned decision** ✓ Correct
- Approve whether a change can be merged or released → **Customer-owned decision** ✓ Correct
- Prepare a structured finding summary from approved artifacts → **Codex-supported workflow execution** ✓ Correct
- Organize evidence into a reviewable format → **Codex-supported workflow execution** ✓ Correct

## Slide 43/55 - Summary

In this module, you learned how to clarify the split between Codex-supported workflow execution and customer-owned decisions.

Codex can help inspect, structure, summarize, and prepare evidence or remediation suggestions.

The customer still owns authorization, risk, severity, remediation acceptance, production approval, data handling, retention, and official records. That split preserves governance and keeps human accountability in place.

## Slide 44/55 - Introduction (Module: Proceed, pause, escalate, or expand)

At this point in the course, you have worked through the operating model conditions: authorization, scope, approved environment, access, data handling, evidence, review, retention, records, and customer-owned decisions.

Now you need to turn that information into a next-step judgment.

This module introduces four possible actions: proceed, pause, escalate, or expand. This decision model is introduced because cyber conversations are often ambiguous. A customer may have a strong opportunity, an unclear operating condition, a sensitive request, or a successful first workflow that is ready to scale. The four options help you respond consistently without overpromising or slowing down good opportunities unnecessarily.

## Slide 45/55 - The four next-step options

Use these four actions when deciding what should happen next.

| Next step | Use when | What it means |
|---|---|---|
| Proceed | The workflow is authorized, bounded, reviewed, evidenced, and customer-owned. | Move to a clear bounded next action. |
| Pause | A required operating model condition is unclear. | Identify the missing condition and who can resolve it. |
| Escalate | The request is sensitive, advanced, or requires OpenAI confirmation. | Bring in OpenAI or partner subject matter expertise before making claims or recommendations. |
| Expand | The bounded workflow has proven evidence quality, reviewability, and governance control. | Broaden repeatability without removing review gates or customer-owned decisions. |

This decision standard supports both sales and technical enablement. It gives you a way to move good opportunities forward while protecting customers, partners, and OpenAI from unsupported claims or poorly governed workflows.

## Slide 46/55 - When to proceed

Proceed when the customer has confirmed the core operating model conditions:

- Owned asset
- Approved environment
- Access path
- Allowed data
- Tool permissions
- Reviewer ownership
- Evidence expectations
- Stop condition
- System-of-record path

Proceed does not mean "automate everything." It means the workflow is clear enough to support a bounded, reviewed next step.

A good proceed decision should produce a concrete next action, such as confirming the scope package, preparing the evidence expectations, aligning customer reviewers, or routing the opportunity to the right OpenAI or partner support.

Use this option when the workflow is specific, authorized, and governed enough to move forward.

## Slide 47/55 - When to pause

Pause when a required operating model condition is unclear.

Common reasons to pause include unclear:

- Scope
- Asset ownership
- Authorization
- Environment
- Access path
- Data handling
- Reviewer ownership
- Evidence expectations
- Stop condition
- System-of-record path

You should also pause when the customer wants to skip human review or treat Codex Security output as an automatic closure decision.

Pause when the customer wants production testing, automated remediation, or recurring coverage before manual evidence quality has been proven.

A pause should not stall the opportunity indefinitely. It should name the missing condition and identify the customer owner who can resolve it.

For example:

> "We should pause until the customer confirms the approved environment and names the AppSec reviewer. Once those are clear, we can revisit the bounded workflow."

## Slide 48/55 - When to escalate

Escalate when the request is sensitive, advanced, unclear, or requires OpenAI confirmation.

Escalation is not only a sales-routing step. In technical validation, escalation may also mean the workflow needs deeper review before anyone recommends access, integration, runtime, or automation.

Common escalation triggers include:

- Unclear authorization, third-party targets, or uncertain asset ownership.
- Production testing, live-target activity, destructive testing, or activity outside an approved environment
- Exploit-heavy workflows, red-team activity, malware-adjacent analysis, reverse engineering, or advanced validation requests.
- Cyber-specialized access, Trusted Access uncertainty, refusal-friction claims, or special model availability questions.
- Custom harnesses, API / headless workflows, MCP or external tool connections, CI/CD automation, or integrations that act across multiple systems.
- Workflows involving critical infrastructure, regulated environments, sensitive data, privileged access, or high-risk customer contexts.
- Requests involving pricing, commercial terms, special data handling, ZDR, downstream access, resale, proxying, or external user access.

Not every trigger requires the same escalation path. The key is to name the risk, avoid making claims, and bring in the right OpenAI or partner expert before recommending access, integration, automation, or commercial terms.

Escalation should be specific. Do not say only "we need to escalate." Name the reason:

> "This request includes production testing and custom tool integration, so we should confirm the authorized scope, runtime boundaries, data handling, and review controls with the right OpenAI or technical support before recommending a route."

Avoid promising cyber-specialized access, all-refusal removal, special data handling, pricing, or availability. Keep the next step grounded in the approved workflow and the missing operating-model facts.

## Slide 49/55 - When to expand

Expand only when the bounded workflow consistently produces useful evidence and human reviewers can reliably accept, reject, suppress, escalate, or record outputs.

Expansion should make the governed workflow more repeatable. It should not remove review gates or customer-owned decisions.

A safe maturity path may move from:

1. Manual bounded workflow.
2. Repeated repository coverage.
3. System-of-record integration.
4. Controlled CI/CD or triggered review.

Expansion should be based on evidence quality, reviewer confidence, data handling readiness, system-of-record fit, and escalation clarity.

It should not happen just because the first workflow produced output.

This course is not about building the executive value story for expansion. That comes later in the Cyber / Daybreak pathway. Here, the focus is operating model readiness: can the customer govern the broader workflow safely and repeatably?

## Slide 50/55 - Real-world example

A customer completes a successful bounded Daybreak pilot and wants to expand across more applications.

Before expanding, the partner should confirm that the customer can consistently review outputs, handle false positives, retain evidence, record decisions in the right system of record, and escalate sensitive cases.

If those conditions are clear, expansion may be appropriate. If they are not clear, the partner should pause or narrow the expansion plan.

Expansion should make the governed workflow more repeatable. It should not remove review gates or customer-owned decisions.

## Slide 51/55 - Recommended exercise: Decide whether to proceed, pause, escalate, or expand

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Practice operating-model judgment in ambiguous customer situations, including technical readiness and escalation triggers.

**Suggested learner task**

Review the six customer asks below. Classify each as proceed, pause, escalate, or expand. For each ask, name the missing condition, escalation trigger, or expansion requirement.

- The customer has one owned repository, an approved lower-level environment, named AppSec and engineering reviewers, agreed evidence expectations, read-only access, and a system-of-record path.
- The customer has a promising backlog validation workflow, but no named reviewer and no evidence-retention rule.
- The customer asks for cyber-specialized access to support exploit-heavy testing in production.
- A bounded workflow has produced accepted evidence over several review cycles. The customer wants recurring review for the same repository while preserving the same review gates.
- The customer asks Codex Security to close tickets automatically whenever confidence is high.
- The customer wants to connect the workflow to CI/CD, create remediation branches, and export evidence to a vulnerability management system, but has not confirmed the service identity, branch permissions, export rules, or audit logging.

**Estimated time:** 8 minutes

**Suggested output and reflection:** A short decision log with the classification, reason, missing condition or escalation trigger, and recommended next action for each ask.

## Slide 52/55 - Knowledge check

**Question:** A customer completed one bounded manual workflow. Reviewers accepted the evidence format, false positives were recorded, and decisions were documented in the ticketing system. The customer now asks to add recurring review for the same repository with the same review gates. What is the best next step?

- Escalate because any recurring workflow is automatically sensitive
- Pause until the customer asks for cyber-specialized access
- Proceed by removing manual review to reduce cycle time
- **Expand** ✓ Correct

*Explanation: Expansion can be appropriate when the bounded workflow has proven evidence quality, reviewability, governance control, and a system-of-record path. The expansion should preserve review gates and customer-owned decisions.*

## Slide 53/55 - Summary

In this module, you learned how to decide whether to proceed, pause, escalate, or expand.

Proceed when the workflow is clear enough for a bounded, reviewed next step. Pause when a required condition is missing. Escalate when the request is sensitive, advanced, or requires OpenAI confirmation. Expand only when the workflow has proven evidence quality, reviewability, and governance control.

This decision model helps you move opportunities forward responsibly without turning Daybreak into unmanaged automation, unsupported access promises, or a replacement for customer governance.

## Slide 54/55 - Recap

Daybreak workflows scale when customers can govern how defensive cyber work is scoped, executed, reviewed, recorded, retained, and escalated.

Across this course, you used an operating model lens to evaluate whether a Daybreak workflow is authorized, bounded, observable, evidence-led, and customer-owned. You also clarified the split between Codex-supported workflow execution and customer-owned decisions around risk, approval, remediation acceptance, retention, and records.

The core behavior change is simple: Move from "Can we use AI for cyber?" to "What approved defensive workflow can we govern, review, evidence, and improve?"

## Slide 55/55 - Congratulations

Congratulations, you've completed this course!

Use the six operating model questions as a field check before recommending a Daybreak next step:

- Are we allowed to do this work?
- Is the asset customer-owned and the environment approved?
- What can the workflow access and do?
- What evidence will be produced, reviewed, retained, and recorded?
- Which decisions remain customer-owned?
- Should we proceed, pause, escalate, or expand?

Together, these questions help you keep Daybreak conversations workflow-first, defensive, governance-aware, evidence-led, and customer-owned.
