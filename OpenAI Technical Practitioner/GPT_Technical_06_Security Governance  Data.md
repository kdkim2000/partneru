# Security, Governance & Data

## Slide 1/53 - Title

Security, Governance & Data

Created July 2026

## Slide 2/53 - Introduction

Security, governance, and data decisions shape whether AI solutions can be trusted, adopted, scaled, and operated responsibly in the business.

This course helps you recognize practical risk signals, frame governance needs clearly, and identify when specialist validation is required.

You will focus on early readiness questions: what needs protection, who can access what, what the system can do, how outputs are reviewed, how activity is monitored, and which assumptions need validation.

You will also start a lightweight Security, Governance & Data Readiness Recommendation to capture assumptions, safeguards, risks, validation needs, escalation points, and the next responsible step.

## Slide 3/53 - What you'll learn

By the end of this course, you'll be able to:

- Identify common security, governance, and data-readiness considerations in OpenAI-powered solutions.
- Classify data, access, tool use, and workflow actions by practical risk level.
- Recognize where permissions, approvals, review, auditability, evals, guardrails, and observability may be needed.
- Ask stronger technical discovery questions about data handling, access controls, compliance, and escalation.
- Distinguish implementation-ready assumptions from issues requiring specialist validation.
- Produce a Security, Governance & Data Readiness Recommendation for a sanitized workflow.

## Slide 4/53 - What you'll produce

You will start a lightweight Security, Governance & Data Readiness Recommendation with four sections:

- Data sensitivity, source, ownership, and access notes
- Permissions, role boundaries, tool/action risks, and approval needs
- Evals, guardrails, observability, auditability, and review signals
- Compliance, residency, privacy, security validation needs, escalation points, and next responsible step

This recommendation is not a compliance review, legal opinion, security architecture, privacy assessment, or policy implementation plan. It is a practical readiness artifact that helps a team see what is known, what is assumed, what needs validation, and who should own the next step.

Let's get started!

## Slide 5/53 - Introduction (Module: Treat governance as a trust enabler)

Trustworthy AI work needs more than a strong prompt. It needs a clear operating model for how the workflow runs, who owns it, and what the AI-supported system is allowed to do.

Governance makes those decisions visible early. It names the workflow owner, data and access boundaries, review points, approval needs, monitoring signals, and escalation paths before the solution moves into pilot, release, or scale.

In this module, you'll learn to treat governance as a trust enabler, not a late-stage blocker.

The goal is to help teams move faster with clearer ownership, safer boundaries, stronger review paths, and better evidence for what still needs validation.

## Slide 6/53 - What governance means in technical solution work

Governance is the way AI-supported work is controlled, reviewed, monitored, and improved.

In technical solution work, it helps teams define how the workflow should operate safely and responsibly before it moves into pilot, release, or scale.

A useful governance conversation makes the operating boundaries visible.

It clarifies who owns the workflow, who can access the data, what the AI-supported system is allowed to do, which outputs need review, what activity should be logged, and when issues need to be escalated.

Governance may include ownership, permissions, data boundaries, tool boundaries, approval rules, review standards, evals, guardrails, logs, auditability, escalation paths, and operational monitoring.

**Quick definitions**

- **Evals:** Tests that check whether the AI-supported workflow behaves as expected.
- **Guardrails:** Controls that guide, restrict, or check behavior against the workflow's rules, risk level, and escalation needs.
- **Auditability:** The team can reconstruct what happened: what was requested, what context or source material was used, what output was produced, who reviewed it, and what action followed.
- **Observability:** The team can monitor activity, performance, quality, errors, escalations, and other signals after the workflow is in use.

You do not need to configure these here. Your role in this course is to recognize when they matter, ask the right readiness questions, and know when specialist validation is needed.

For example, an AI assistant that drafts customer-facing service responses needs more than a good prompt.

The team needs to know which customer data the assistant can use, who reviews responses before they are sent, which topics require escalation, what the assistant should avoid or refuse, how output quality will be tested, and who owns updates to approved sources or instructions.

Design governance as part of the workflow from the beginning. When governance is visible early, teams can move faster with clearer ownership, safer boundaries, stronger review paths, and better evidence for what still needs validation.

## Slide 7/53 - Governance is not the same as bureaucracy

Clear governance helps teams move faster because the important decisions are visible early. When owners, boundaries, review points, escalation paths, and operating rules are defined, teams spend less time resolving ambiguity later.

Weak governance creates friction because people are unsure who owns the workflow, which data can be used, what the AI-supported system can do, who reviews outputs, and what must be escalated.

Those gaps can delay pilots, create avoidable risk, or force late-stage rework.

Strong governance supports safer adoption, better handoff, faster review, clearer accountability, more confident scaling, and stronger operational trust.

**For example**

A customer-facing response assistant can move faster when the team has already defined which support sources are approved, who reviews sensitive drafts, which topics require escalation, what should be logged, and who owns updates to instructions or templates.

Treat governance as a trust enabler from the start.

The goal is to give the team enough clarity to move responsibly, validate what remains uncertain, and involve the right specialists before risk increases.

## Slide 8/53 - Practical governance questions

Governance becomes practical when you can turn it into clear questions.

These questions help you identify who owns the workflow, what boundaries are needed, how outputs should be reviewed, and what evidence is required before the solution moves from exploration to pilot, release, or scale.

Ask:

- Who owns the workflow?
- Who owns the data?
- Where did the data come from, who owns it, and is it approved for this workflow?
- Who owns the AI-supported output?
- Who approves changes?
- Who reviews high-risk outputs?
- What actions are restricted?
- What should be logged?
- What must be escalated?
- What evidence is needed before expansion?

**Who may need to validate what?**

- **Workflow owner:** Confirms the business process, users, review points, and operating owner.
- **Data owner:** Confirms source quality, approved use, access boundaries, and data maintenance.
- **Security lead:** Reviews access controls, tool permissions, logging, auditability, and incident concerns.
- **Privacy or legal reviewer:** Validates personal data, regulated data, retention, regional requirements, and contractual constraints.
- **Implementation owner:** Confirms environment, release path, monitoring, support, and rollback readiness.
- **Partner technical lead:** Captures assumptions, frames the next responsible step, and routes unresolved issues to the right specialist.

For example, if a customer wants an AI assistant to draft customer-facing service responses, these questions help clarify whether support operations, legal, compliance, data owners, or security teams need to be involved.

They also help identify which response types need review, which topics require escalation, and what evidence would be needed before the assistant is used more broadly.

Use these questions in early technical conversations. The goal is to capture assumptions, surface missing owners or controls, and identify the next responsible validation step before risk increases.

## Slide 9/53 - Governance across solution types

Governance needs change depending on where the AI-supported workflow runs, who uses it, what data it touches, what actions it can take, and how the work is monitored.

The same governance principle may show up differently across employee-facing workflows, API-led applications, agentic workflows, developer workflows, and open model or self-hosted patterns.

**Quick definition:** In this course, an agentic workflow means a workflow where AI can work through multiple steps, use tools or systems, follow guardrails, and move work toward an output. You do not need to build or configure the agent here. Your job is to recognize how the ability to use tools or take steps changes readiness questions.

**Examples**

ChatGPT workspace workflows may need administrator enablement, role- and group-based access, approved apps, plugins, or Workspace Agents, action permissions, review expectations, compliance visibility, and checks for plan, regional, and workspace availability.

API-led applications may need authentication and authorization, a clear data-flow map, applicable storage, retention, and logging controls, evals, monitoring, release gates, and validation of whether any Zero Data Retention requirement changes the viable endpoint, tool, or feature set.

Agent- or tool-enabled workflows may need least-privilege connections, clear read and write boundaries, approval rules, action constraints, logs or traces, escalation and rollback plans, and safeguards against prompt injection or unintended data exposure from untrusted content.

Codex workflows may need repository trust boundaries, sandbox and workspace limits, network controls, an approval policy, review rules, and auditability. Do not assume every edit or command requires approval—the active sandbox and policy determine what can proceed within the permitted boundary.

Open model or self-hosted patterns may need infrastructure, patching, monitoring, and operational ownership review.

The specific controls may differ, but the readiness habit is the same: connect governance to the workflow. Ask what the AI can access, what it can do, who reviews the result, how activity is monitored, and who owns improvement.

## Slide 10/53 - Real-world example

**Example context: Governing customer-facing response drafts**

A partner implementation lead is working with a customer product owner and support operations team on a workflow that drafts customer-facing service responses.

The workflow uses approved support articles, recent case notes, and response templates. The customer wants faster response drafting without reducing quality or exposing sensitive customer information.

The partner must decide what governance questions need to be visible before the workflow can be considered for a limited pilot.

The work may look simple because the AI is only drafting text, but governance still matters because the output could affect customers.

The team should clarify:

- Which support sources are approved for use
- Whether recent case notes can be used for response drafting
- Who reviews the draft before it is sent
- Which topics require escalation, such as refunds, account closures, legal complaints, unresolved incidents, or sensitive customer-impacting issues
- What the assistant should refuse, avoid, or route to a human
- What should be logged for quality review or auditability
- Who owns updates to source content, instructions, templates, and escalation rules

**Why this helps:** This example shows that governance belongs inside the workflow design, not in a separate checklist at the end. It also shows how partner implementation leads can move a customer conversation forward without pretending to approve security, legal, privacy, or compliance questions themselves.

## Slide 11/53 - Recommended exercise: Spot the governance gaps

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Practice identifying the ownership, boundaries, review points, and escalation needs that make governance a trust enabler.

**Task:** Review this workflow need: "A customer wants AI support for drafting customer-facing service responses from approved support knowledge and recent case notes." Pause before thinking about tools or implementation. Reflect on three questions:

1. Who owns the workflow? Who should be accountable for the process, source content, review standards, and updates?
2. Where are the boundaries? What should the AI-supported workflow be allowed to use, draft, avoid, refuse, or route to a human?
3. What needs review or escalation? Which topics, outputs, or uncertain cases should require a reviewer or specialist before use?

**Estimated time:** 3–4 minutes

Suggested output or reflection: Write three short bullets. End with one sentence: "The governance question I would clarify first is…"

## Slide 12/53 - Knowledge check

**Question:** Which statement best reflects strong governance? (Select all that apply)

- Governance is only a legal function.
- Governance means saying no to all automation.
- Governance should wait until after the pilot proves value.
- **Governance defines owners, boundaries, review points, evidence, and escalation so teams can move faster with trust.** ✓ Correct

Strong governance supports trustworthy adoption and scaling by making the operating boundaries visible early.

## Slide 13/53 - Summary

Clear governance makes important decisions visible before risk increases. It helps the team understand who owns the workflow, who owns the data, what the AI-supported system is allowed to do, where review is required, and what must be escalated before the workflow moves toward pilot, release, or scale.

Governance is not just a late-stage approval step. When it is built into the conversation early, it can help teams move faster with clearer ownership, safer boundaries, stronger review paths, and better evidence for what still needs validation.

## Slide 14/53 - Introduction (Module: Map data sensitivity, access, ownership, and movement)

Data readiness starts by separating what a system can reach from what the customer has approved for use. Technical access does not automatically make data appropriate, permitted, or safe for the workflow.

Before recommending a source, map what it contains, who owns it, who can access it, how sensitive it is, and where it may move. This surfaces permission gaps, unclear ownership, and exposure risks early.

In this module, you'll learn to judge data readiness before build, pilot, or scale, so teams can use the right data within the right boundaries and flag what still needs validation.

## Slide 15/53 - Data categories that matter

Not all data creates the same readiness questions. A workflow that uses public information has a different risk profile from one that uses customer records, personal data, source code, or regulated information.

At a practical level, common categories may include:

- Public information
- Internal business information
- Confidential company information
- Customer data
- Personal data
- Regulated data
- Credentials, secrets, and keys
- Source code or proprietary technical information
- Financial, legal, health, employment, or security-sensitive data

Higher-sensitivity data usually requires stronger access controls, review, logging, and specialist validation.

**For example**

A customer support article may be approved for broad use, while a case note may include personal information, unresolved complaints, or internal-only comments.

A readiness recommendation should not simply say "data is available." It should name the data type, sensitivity level, source, owner, access boundary, and any validation needed before the data is used in the workflow.

## Slide 16/53 - Source and ownership questions

Data readiness depends on source and ownership. The team needs to know where information comes from, who maintains it, who approves its use, and whether it can be used for the specific AI-supported workflow.

Ask:

- Where does the data live?
- Who owns it?
- Who maintains it?
- Who can access it?
- How current is it?
- Is it approved for this workflow?
- Can it be used in AI-supported processing?
- Can outputs include or expose it?

The key distinction is that available data is not always approved data.

A system may technically contain useful information, but that does not mean the information is approved for AI processing, retrieval, response drafting, sharing, storage, logging, or reuse.

**For example**

A support platform may include both approved support articles and internal escalation comments. Both are available to some users. Only one may be appropriate as source content for a customer-facing response draft.

## Slide 17/53 - Access control basics

Access control is about who can see, use, update, or act on information. It becomes especially important when retrieval, tools, agents, or connected systems are involved because outputs can cross boundaries if permissions are not clearly understood.

Ask:

- Which users need access?
- Which users should be excluded?
- Are permissions role-based?
- Are permissions inherited from source systems?
- Does the AI-supported system need user-specific context?
- Could outputs expose information across access boundaries?
- Who approves access changes?

**For example**

A support agent may be allowed to see case notes for accounts they support, but not notes for every account in the company.

If an AI assistant retrieves notes without respecting the right access boundaries, it could expose information to users who should not see it.

A strong readiness recommendation names access assumptions plainly. It should say what the workflow appears to require and what needs validation before the team treats access as ready.

## Slide 18/53 - Data movement and retention considerations

Data readiness also depends on how information moves through the solution. A workflow may start with approved data in one system, but the risk profile can change when that data is sent to a model or API, combined with other sources, used to generate outputs, stored in another place, or retained in logs.

Map the data flow from start to finish.

Ask:

- What data enters the workflow?
- What data is sent to a model or API?
- What data is retrieved from connected systems?
- What outputs are generated?
- Where are outputs stored?
- What logs are retained?
- What data should not be stored or reused?
- What customer policy governs retention?

**For example**

A customer-service response assistant may use approved support articles and recent case notes.

The support articles may be lower risk and reusable, while the case notes may include customer details, internal comments, or sensitive issue history.

If the assistant generates a draft response, the team also needs to know whether that draft is stored in the ticketing system, included in logs, reviewed by a human, or retained for quality monitoring.

Capture movement and retention assumptions clearly in the readiness recommendation. Do not assume that one retention or deletion setting covers every product surface, API endpoint, tool, connected system, or log.

For API-led workflows, validate the applicable storage and retention controls and whether any Zero Data Retention requirement changes the viable endpoint, tool, or feature choice.

Exact retention, privacy, residency, and contractual claims should be validated against approved sources and the appropriate security, privacy, legal, compliance, data, or customer-policy stakeholders before the workflow is treated as ready.

Use this map to trace what data enters the workflow, where it moves, who can access it, what may be stored or logged, and what needs validation before the data is treated as ready.

Visual diagram: a data-flow map inside an "Access boundary" box — Source data (with Data sensitivity) → AI-supported processing → Generated output (with Output exposure) → Review / storage / logging (with Retention question and Validation owner).

## Slide 19/53 - Data-to-validation transition

Once you have mapped data sensitivity, source, ownership, access, movement, and retention, convert those notes into validation questions.

The goal is to identify which assumptions can move forward, which need evidence, and which require review by the right specialist or customer owner.

Data notes often create validation questions for compliance, privacy, residency, security, and customer policy review.

Use this pattern:

- **Data note:** Recent case notes may include personal or sensitive customer information.
- **Validation question:** Can this data be used for AI-supported response drafting?
- **Risk area:** Privacy, customer policy, access control, and retention.
- **Validation owner:** Data owner, privacy/legal reviewer, security lead, or customer policy stakeholder.
- **Next responsible step:** Confirm approved use, access limits, review needs, and retention or logging expectations before pilot.

Avoid turning uncertainty into assurance. Capture the assumption, explain why it matters, name the risk area, and route it for validation. This keeps the readiness recommendation credible and makes the next responsible step clear.

## Slide 20/53 - Real-world example

**Example context: Distinguishing available data from approved data**

A partner implementation lead is working with a customer-service team on response drafting.

The customer support platform contains approved support articles, recent case notes, refund decisions, account history, and internal escalation comments.

The partner can technically access several of these sources, but that does not mean all of them are approved for AI-supported response drafting.

Approved support articles may be safe to use as source content.

Recent case notes may include personal information, unresolved complaints, or internal notes that should not appear in a customer-facing response.

Refund decisions and legal complaints may require stricter review and escalation.

Internal escalation comments may be useful for support operations but inappropriate for direct customer-facing output.

The partner should not decide alone that the data is approved. The readiness recommendation should separate technical access from approved use by capturing:

- Which sources are proposed for the workflow
- Which sources are approved support content
- Which sources include personal, confidential, regulated, or internal-only information
- Who owns and maintains each source
- Which outputs could expose sensitive information
- What requires validation by data, security, privacy, legal, compliance, or customer-policy owners

**Why this helps:** This example makes the principle "available data is not automatically approved data" concrete. It helps you separate technical access from approved use before recommending a pilot or expansion.

## Slide 21/53 - Recommended exercise: Separate available data from approved data

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Practice recognizing that technical access to data does not automatically mean the data is approved, appropriate, or safe for the workflow.

**Task:** Review this workflow example: "A customer-service platform contains approved support articles, recent case notes, refund decisions, account history, and internal escalation comments. A team wants AI to use this information to draft customer-facing responses."

Reflect on three questions:

1. What seems safest to start with? Which source or data type seems most likely to be appropriate for response drafting?
2. What needs validation first? Which source or data type may include personal, sensitive, confidential, regulated, or internal-only information?
3. What could be exposed? What output risk might appear if the AI used the wrong source or included the wrong detail?

**Estimated time:** 3–4 minutes

Suggested output or reflection: Write three short bullets. End with one sentence: "The data assumption I would validate first is…"

## Slide 22/53 - Knowledge check

**Question:** A source system contains customer data. The team says the AI workflow can use it because the data is available. What is the strongest response?

- Avoid using any customer data in all cases.
- Only the model choice matters.
- Available data is automatically approved for AI use.
- **Confirm ownership, approved use, and access first.** ✓ Correct

Data availability is not the same as approved data use. The team should validate source ownership, access boundaries, and whether the data is approved for the specific workflow.

## Slide 23/53 - Summary

Treat every data source as a readiness question. Just because a system can technically access data does not mean that data is approved, appropriate, or safe for an AI-supported workflow.

Before recommending a source for pilot or expansion, clarify what the data contains, how sensitive it is, where it comes from, who owns it, who can access it, where it may move, and what could be exposed in the output. This helps the team separate available data from approved data.

A useful data-readiness judgment turns uncertainty into validation questions. Capture the data assumption, name the risk area, and identify who should validate approved use, access boundaries, movement, retention, privacy, security, residency, or customer-policy requirements.

## Slide 24/53 - Introduction (Module: Define permissions, roles, tool risks, and approval boundaries)

Once data is mapped, the next question is what each person or system may do with it. Permissions and roles turn data boundaries into practical operating rules. Define who can view, edit, approve, send, trigger, or override actions, and where human review is required.

This keeps helpful AI support from becoming uncontrolled access, unsupported decisions, or unintended system changes.

In this module, you'll learn to judge role, tool, and action risk before build, pilot, or scale, so teams can set clear approval boundaries and flag what still needs specialist validation.

## Slide 25/53 - Role and permission boundaries

Role and permission boundaries define who participates in the workflow and what each role should be allowed to see, draft, approve, trigger, or change.

Common roles may include end users, reviewers, approvers, administrators, system owners, data owners, security reviewers, legal or compliance reviewers, privacy reviewers, implementation owners, and support owners.

A workflow may be risky if the roles are unclear. For example, an AI assistant may draft a customer response, but someone still needs to own review criteria, escalation categories, and final sending authority. Another person may own source content updates. A different team may own access controls or logging.

The readiness recommendation should make role assumptions visible before a workflow is treated as ready.

Useful notes include:

- Who uses the workflow
- Who reviews outputs
- Who approves sensitive actions
- Who owns data sources
- Who owns system access
- Who owns support, monitoring, and improvement
- Which specialist validates unresolved risk areas

## Slide 26/53 - Action-risk levels

AI-supported workflows can create different levels of operational risk depending on what the system is allowed to do.

A useful ladder is:

- **Read-only:** Retrieves or summarizes information.
- **Draft:** Creates content for a human to review.
- **Recommend:** Suggests next steps without taking action.
- **Act with approval:** Performs an action only after human approval.
- **Restricted:** Should not be automated or should require specialist validation.

This ladder helps you avoid moving too quickly from "AI can help" to "AI can act." The same workflow can also move up the ladder over time. A first phase may be draft-only, while a later phase may update systems, send messages, or trigger downstream work.

**Why action-risk levels matter**

A read-only workflow may still require access controls, but it usually creates less operational risk than a workflow that updates records, sends messages, changes status, approves requests, or triggers downstream systems.

Before recommending action-taking behavior, validate permissions, approval gates, logs, auditability, failure handling, and ownership.

For customer-facing or high-impact workflows, also confirm who reviews the output, what counts as an exception, and what must be escalated before any action affects customers, systems, or business decisions.

## Slide 27/53 - Tool and agent boundaries

Tool or agent permissions can change the risk profile because the workflow may interact with other systems, retrieve context, trigger actions, or continue work over multiple steps.

**Quick definition:** In this course, a tool boundary means a clear limit on what an AI-supported workflow can access or do through connected systems.

You do not need to configure the tool. Your job is to identify what the tool can read, write, trigger, or expose, and what must be validated before use.

Questions can be split into three areas:

**Access and identity**

- Which tools or systems are involved?
- Which identity does each tool use?
- What can each tool read?
- Is access limited to the workflow's needs?

**Actions and safeguards**

- What can each tool write or trigger?
- Which actions require confirmation?
- What actions are prohibited?
- Could connected content contain untrusted instructions?
- How are access, actions, and data protected from them?

**Operations and ownership**

- What happens when a tool fails?
- What should be logged?
- Who owns the integration?
- What must be escalated?

Approval settings and action constraints can narrow how a tool is used, but they do not replace the connected system's own permissions or guarantee that returned content is safe.

Treat external or retrieved content as untrusted when it may contain hidden instructions, and validate how the workflow limits unauthorized actions and unintended data exposure.

**For example**

A response-drafting assistant that only reads approved support articles has a different readiness profile from one that can update ticket status, issue credits, send emails, or trigger escalation workflows.

The second pattern needs clearer approval gates, failure handling, logs, auditability, and owner validation.

## Slide 28/53 - Approval gates

Approval gates define where human permission is required before work continues. They should be specific enough to operate in practice.

Approval gates may be needed for sensitive outputs, external communication, system write-backs, high-impact decisions, tool use with side effects, production changes, security-sensitive actions, exceptions, or low-confidence results.

Avoid writing only "human in the loop."

A useful approval gate names:

- The reviewer or approver
- The trigger for review
- The criteria the reviewer uses
- The next action after approval, rejection, or escalation

**For example:** "A support manager reviews any recommendation involving refunds, account closure, legal language, unresolved incidents, or sensitive customer-impacting issues before the response is sent."

That statement is more useful than "human review is required" because it tells the team who reviews, when review happens, and which cases require escalation.

## Slide 29/53 - Real-world example

**Example context: Setting boundaries for vendor-risk updates**

A partner solution architect is working with a customer procurement team on a workflow that reviews vendor-risk information. The customer wants AI to summarize vendor records, flag risk signals, recommend next steps, and eventually update the procurement system.

A lower-risk starting pattern may allow read-only retrieval and draft recommendations. A higher-risk pattern may update vendor records, trigger approval workflows, or change vendor status.

The readiness recommendation should clarify what the system can read, what it can draft, what requires approval, and what actions are prohibited.

The partner should help the team distinguish:

- Read-only access to approved vendor-risk information
- Draft risk summaries for a procurement analyst to review
- Recommendations that require human approval before action
- System write-backs that change records or trigger downstream workflows
- Restricted actions that should not be automated without specialist validation

The key readiness question is whether the workflow is only helping a human review vendor risk or whether it can change records or trigger procurement actions.

As the workflow moves closer to action-taking behavior, the recommendation needs stronger approval gates, auditability, failure handling, ownership, and specialist validation.

## Slide 30/53 - Recommended exercise: Draw the line between help and action

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Practice using the action-risk ladder to decide when permissions, approval gates, logging, auditability, or specialist validation may be needed.

**Task:** Review this workflow example: A customer wants AI to help a support team handle service cases. The first version may summarize case details and draft responses. A later version may update ticket status, issue credits, or send customer emails.

Reflect on these actions below:
- Summarize approved support information
- Draft a response for an agent to review
- Recommend that a case be escalated
- Update ticket status
- Send a customer-facing email or issue a credit

For each group below, choose one action from the list:
1. Low-risk starting point — Which action seems closest to read-only, draft, or recommend behavior?
2. Approval-required action — Which action should require a human approval gate before it happens?
3. Restricted or specialist-validation action — Which action should not move forward without clearer permissions, logging, auditability, failure handling, and owner validation?

**Estimated time:** 3-4 minutes

Suggested output and reflection: Write three short bullets. End with one sentence: "I would not allow the workflow to ___ until…"

## Slide 31/53 - Knowledge check

**Question:** Which workflow behavior usually requires the strongest approval, logging, auditability, and specialist validation?

- Drafting a customer response for human review.
- **Automatically updating a customer record and sending a customer-facing message** ✓ Correct
- Summarizing an approved internal support article.
- Suggesting that a complaint should be reviewed by a manager.

Action-taking behavior that updates records and sends external communication creates higher operational risk and needs stronger controls before it is recommended.

## Slide 32/53 - Summary

Permissions and action boundaries define what people, systems, tools, and AI-supported workflows are allowed to see, draft, recommend, trigger, or change. The closer a workflow gets to changing systems or affecting customers, the stronger its controls must be.

Remember that a useful readiness conversation names the role, the permission, the action, and the boundary. It should be clear who reviews, who approves, what actions are restricted, what happens when something fails, and what must be validated by a specialist before the workflow moves forward.

## Slide 33/53 - Introduction

**Use evals, guardrails, observability, and auditability to control and improve behavior**

A promising demo is not readiness evidence. Teams need to know how the workflow was tested, what controls shape its behavior, and what signals show whether it keeps working as intended.

Use evals, guardrails, observability, and auditability to turn trust into an operating practice. Evals test behavior, guardrails set boundaries, observability shows what is happening in use, and auditability helps reconstruct what happened when questions arise.

In this module, you'll learn to identify the controls, evidence, and ownership needed before pilot, release, or scale, so teams can monitor behavior, improve it over time, and escalate issues responsibly.

## Slide 34/53 - Evals as governance evidence

Evals are tests that check whether the AI-supported workflow behaves as expected. They provide evidence for readiness by testing known requirements, edge cases, failure modes, and changes over time.

Evals may test accuracy, groundedness, completeness, format compliance, refusal behavior, tool-use behavior, escalation behavior, safety-sensitive cases, and regression after changes.

For example: A customer-service response assistant should be tested against normal questions, ambiguous cases, sensitive complaints, refund requests, account-closure requests, unresolved incidents, and questions outside the approved support sources.

The team should know whether the assistant grounds responses in approved content, escalates the right cases, avoids prohibited language, and follows the expected output format.

For higher-risk workflows, eval evidence is part of readiness, not an optional enhancement. It helps the team see whether the workflow is reliable enough to move forward and what still needs validation.

## Slide 35/53 - Guardrails, moderation, and structured outputs as controls

Guardrails are controls that guide, restrict, check, and maintain proven successful AI-supported behavior. Moderation checks can help identify certain unsafe or policy-sensitive content. Structured outputs help produce predictable fields or formats for downstream workflows.

Controls may include input filters, output checks, moderation checks, structured outputs, tool-use limits, retrieval requirements, human approval gates, restricted topics, escalation rules, logging, and monitoring.

Structured outputs can reduce ambiguity when downstream systems require predictable fields or formats, but they do not guarantee correctness. They still need to be evaluated.

For example, a complaint-classification workflow may require structured categories such as "billing issue," "technical support," "refund request," "legal complaint," or "urgent safety concern."

Structured categories make review and routing easier, but the team still needs evals to test whether complaints are classified correctly and whether sensitive cases are escalated.

## Slide 36/53 - Observability as operational visibility

Observability is how the organization monitors, controls, and improves AI activity. In practical terms, it means visibility into what the workflow is doing, what it can access, how it is performing, and whether it is following policies and governance rules.

Useful signals may include usage volume, user feedback, output quality, latency, cost, error rates, tool calls, retrieval performance, escalations, approval requests, refusals, and high-risk cases.

The right signals depend on the workflow and risk level. A low-risk internal summarization workflow may need basic usage, feedback, and quality signals.

A customer-facing or action-taking workflow may need stronger visibility into approvals, escalations, tool calls, override rates, repeated failure modes, and incidents.

Observability is not only a technical dashboard idea. It is an operating question: what evidence will show that the workflow is working, where it is failing, and who is responsible for improvement?

## Slide 37/53 - Auditability basics

Auditability is the ability to reconstruct what happened. It matters when a team needs to understand how an output was produced, why an action was taken, who reviewed it, and what control applied.

Auditability questions may include:
- What was requested?
- What context was used?
- What tools were called?
- What output was produced?
- Who reviewed or approved it?
- What action was taken?
- What was escalated?
- What policy or control applied?

Auditability expectations are especially important for regulated, high-risk, customer-facing, or action-taking workflows.

For example, if an AI-supported workflow recommends an escalation or updates a case status, the team may need evidence of the input, the generated output, the reviewer, the approval decision, and the final action.

Your readiness recommendation should identify what may need to be logged or reconstructable without making unsupported claims about audit compliance.

## Slide 38/53 - Improvement loops and ownership

AI-supported workflows should improve based on evidence. Evals, feedback, logs, review outcomes, and observed failure modes should feed into a clear improvement loop.

Improvement loops may include reviewing failed cases, updating instructions, improving source content, adjusting retrieval, updating guardrails, expanding eval sets, revising escalation rules, training users, and monitoring drift.

The readiness recommendation should identify who owns improvement, not just what should improve.

For example, source content updates may belong to a knowledge owner, escalation rules may belong to the workflow owner, access controls may belong to security, and release or rollback decisions may belong to the implementation owner.

Without ownership, issues can be observed but not fixed. A useful readiness recommendation makes the improvement path visible before the workflow scales.

## Slide 39/53 - Real-world example

Example context: Controlling complaint classification

A partner implementation lead is working with a customer support team on a workflow that classifies customer complaints and recommends next steps.

The workflow uses incoming complaint text, approved support categories, escalation rules, and reviewer feedback. The customer wants faster routing and more consistent escalation.

The readiness recommendation should identify eval cases for normal, urgent, ambiguous, unsafe, and escalation-required complaints.

It should also identify guardrails such as structured categories, moderation checks, restricted topics, and human review.

Useful observability signals may include escalation frequency, reviewer overrides, error patterns, repeated failure modes, low-confidence cases, and cases that require policy or legal review.

Useful auditability notes may include what complaint text was received, which category was assigned, what recommendation was made, who reviewed it, and what action followed.

**Why this helps:** This example shows how evals, guardrails, observability, auditability, and improvement ownership work together. The team is not only asking whether AI can classify complaints. It is asking how classification will be tested, controlled, monitored, reconstructed when needed, and improved after real use.

## Slide 40/53 - Recommended exercise: Choose the first controls

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Practice identifying the basic evidence, boundaries, monitoring signals, and review needs that help a team control and improve AI-supported behavior.

**Task:** Review this workflow example: "A customer support team wants AI to classify incoming complaints, recommend next steps, and route urgent or sensitive cases for review."

Choose one item for each prompt:
- One eval to run — What should the team test before broader use?
- One guardrail or review point — What should prevent unsafe, unsupported, or sensitive outputs from moving forward unchecked?
- One observability signal — What should the team watch after use begins?
- One auditability question — What might the team need to reconstruct later?

**Estimated time:** 4-5 minutes

Suggested output and reflection: Write four short bullets. End with one sentence: "The control I would prioritize first is…"

## Slide 41/53 - Knowledge check

**Question:** Match each need to the right concept.

- Track escalations, reviewer overrides, refusals, and error patterns after launch → **Observability** ✓ Correct
- Prevent the workflow from producing restricted content or taking prohibited actions → **Guardrail** ✓ Correct
- Test whether answers are grounded in approved sources → **Eval** ✓ Correct
- Produce predictable fields for downstream review or routing → **Structured output** ✓ Correct
- Reconstruct what was requested, produced, reviewed, approved, or acted on → **Auditability** ✓ Correct

All pairs matched correctly!

## Slide 42/53 - Summary

Controls work best together. Evals test expected behavior; guardrails, moderation, and structured outputs reduce risk and support consistent review.

Observability shows performance, failures, overrides, and escalations, while auditability records what happened and who approved or acted.

No single control is sufficient. Strong readiness connects testing, prevention, monitoring, evidence, review, and ownership so teams can improve the workflow and escalate issues responsibly.

## Slide 43/53 - Introduction

**Recognize validation needs and complete the readiness recommendation**

A useful readiness recommendation turns uncertainty into responsible next steps. It shows what is known, what is assumed, what still needs validation, and who should own each follow-up.

Some questions require security, privacy, legal, compliance, residency, data, product, or implementation review. Your role is to recognize those signals, route them to the right owner, and avoid treating unvalidated assumptions as implementation ready.

In this module, you'll complete a lightweight Security, Governance & Data Readiness Recommendation covering key boundaries, safeguards, risks, validation needs, escalation points, and the next responsible step.

## Slide 44/53 - Validation needs, not assurances

Identifying a validation need is not the same as answering it. You should not make unsupported claims about legal, compliance, privacy, residency, security, product availability, or implementation readiness.

Instead, capture the assumption, identify the risk area, name the relevant approved source or specialist, and recommend the next responsible step.

Use careful technical language: "This appears to be a plausible starting path, but we need to validate the data, source, access, review, eval, and governance assumptions before treating it as a recommendation."

That language is not evasive. It is responsible. It keeps the work moving while making clear which assumptions still need evidence or specialist review.

## Slide 45/53 - Common validation tripwires

Some topics should immediately prompt a validation question because they can affect privacy, security, compliance, residency, contract terms, implementation readiness, or customer policy.

Common tripwires include:
- Data residency
- Inference residency
- Data retention, storage, or Zero Data Retention requirements
- Data processing terms
- Regulated data use
- Industry-specific compliance
- Cross-border data movement
- Audit and logging requirements
- Customer contractual restrictions
- Security architecture, prompt-injection boundaries, or untrusted-content handling
- Workspace, app, agent, API, or developer-tool access-control implementation
- Sandbox, network, repository, or tool-action boundaries
- Incident response expectations
- Customer internal policy constraints

These tripwires do not automatically mean the work must stop. They mean the recommendation should route uncertainty responsibly instead of converting it into unsupported assurance language.

For example: If a workflow uses customer data and may store outputs in a ticketing system, the readiness recommendation should not claim that retention requirements are satisfied. It should identify retention as a validation need, name the relevant risk area, and route the question to the appropriate data, privacy, legal, security, compliance, or implementation owner.

## Slide 46/53 - Convert uncertainty into escalation questions

A good escalation question gives the right person enough context to respond. It should explain what assumption needs validation, why it matters, which risk area it affects, who should validate it, what source or specialist input may be needed, and what next step is recommended.

Use this structure:
- Assumption: What are we assuming?
- Why it matters: What could go wrong, be exposed, fail, or be misunderstood?
- Risk area: Which area is affected?
- Who validates: Which owner or specialist should review it?
- Next step: What should happen before pilot, release, or expansion?

For example:
- **Assumption:** The AI workflow can use recent case notes for customer-response drafting.
- **Why it matters:** Case notes may include personal information, sensitive customer details, unresolved issues, or internal comments.
- **Risk area:** Data use, privacy, access control, retention, and customer policy.
- **Who validates:** Data owner, privacy or legal reviewer, security lead, and implementation owner.
- **Next step:** Validate approved use, access boundaries, retention, logging, and review requirements before pilot.

You can use the same structure for other readiness questions. If the workflow may later update ticket status, the escalation question should focus on write-back permissions, approval gates, logging, failure handling, auditability, and system ownership.

## Slide 47/53 - What the readiness recommendation includes

Your readiness recommendation brings together the notes you have built across the course. It should make clear what is known, what is assumed, which safeguards or controls may be needed, what requires validation, and what next step should happen before pilot, release, or expansion.

Your recommendation should include four sections (all four clicked to complete):

1. **Data sensitivity, source, ownership, and access notes** ✓ — Capture what data the workflow uses, where it comes from, who owns it, who can access it, and which data-use assumptions need validation.
2. **Permissions, role boundaries, tool/action risks, and approval needs** ✓ — Capture who participates in the workflow, what each role can see or do, which actions are read-only, draft, recommend, approval-required, or restricted, and where approval gates are needed.
3. **Evals, guardrails, observability, auditability, and review signals** ✓ — Capture the main failure modes, controls, review points, monitoring signals, auditability needs, and improvement owners.
4. **Compliance, residency, privacy, security validation needs, escalation points, and next responsible step** ✓ — Capture unresolved assumptions, the risk areas they affect, who should validate them, and what should happen next.

The recommendation should help the team see the readiness picture clearly: the workflow value, the operating boundaries, the open risks, and the validation path needed to move forward responsibly.

Optional offline crib sheet: You may copy your selected matches or choices into your Security, Governance & Data Readiness Recommendation for your own use. Do not submit it. It is not graded and it does not unlock progress.

## Slide 48/53 - Recommendation quality check

Before you use or share your readiness recommendation, check whether it gives the team enough information to make a responsible next-step decision.

A strong recommendation should make the workflow's assumptions, boundaries, controls, validation needs, and escalation points clear.

Check whether your recommendation:
- Identifies data sensitivity clearly
- Names source systems, data owners, and access assumptions
- Distinguishes read-only from action-taking behavior
- Includes review and approval points
- Includes evals and guardrails
- Includes observability and auditability signals
- Avoids unsupported compliance or security claims
- Identifies what must be validated
- States the next responsible step

If any item is unclear, capture it as an assumption, validation question, escalation point, or next responsible step. The goal is not to make the recommendation look complete. The goal is to make the readiness picture honest enough for responsible follow-up.

## Slide 49/53 - Recommended exercise: Complete your Security, Governance & Data Readiness Recommendation

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Practice creating one lightweight readiness recommendation that brings together data, access, action boundaries, controls, validation needs, escalation points, and the next responsible step.

**Task:** Review this sanitized workflow brief: "A customer-service team wants AI to draft customer responses using approved support articles and recent case notes. The first phase is draft-only. Some cases involve refund requests, account closures, legal complaints, unresolved incidents, or sensitive customer details. The customer may later want the assistant to update ticket status automatically."

Create a short Security, Governance & Data Readiness Recommendation with four sections:

1. Data sensitivity, source, ownership, and access — What data is involved, where does it come from, who owns it, who can access it, and what data-use assumptions need validation?
2. Permissions, role boundaries, tool/action risks, and approval needs — What can the assistant see, draft, recommend, or change? What should stay draft-only, require approval, or be treated as restricted?
3. Evals, guardrails, observability, auditability, and review signals — What should be tested, reviewed, monitored, logged, or made reconstructable before broader use?
4. Validation needs, escalation points, and next responsible step — What assumptions require data, security, legal, privacy, compliance, product, or implementation validation? What should happen next?

Then choose one final decision: Ready for limited pilot / Not ready / Needs specialist validation before pilot.

**Estimated time:** 6-8 minutes

Suggested output and reflection: Write one or two bullets for each section, then add a final decision and one-sentence rationale.

Use this format for your final decision and rationale:

Decision: Needs specialist validation before pilot.
Rationale: The workflow may be draft-only at first, but it uses customer data and includes sensitive case types. Before pilot, the team should validate approved data use, access boundaries, human review, escalation rules, logging, auditability, and whether any future ticket updates require stronger approval and failure-handling controls.

## Slide 50/53 - Knowledge check

**Question:** Match each platform or workflow signal to the control area that should be validated first.

- Agent- or tool-enabled workflow → **Connection identity; least-privilege access; read/write boundaries; approvals and action limits** ✓ Correct
- ChatGPT workspace workflow → **Admin enablement; role and group access; approved apps, plugins, or Workspace Agents; action permissions and review** ✓ Correct
- API-led application → **Authentication; data flows; logging; storage and retention; Zero Data Retention implications for endpoint, tool, or feature choice** ✓ Correct
- Codex workflow → **Repository trust; sandbox and workspace boundaries; network access; approval policy; review; auditability** ✓ Correct

All pairs matched correctly!

## Slide 51/53 - Summary

A strong readiness recommendation does not turn uncertainty into assurance. It makes assumptions, safeguards, validation needs, escalation points, and the next responsible step visible.

In this module, you practiced identifying validation tripwires, converting uncertainty into escalation questions, and completing a lightweight Security, Governance & Data Readiness Recommendation.

Use the recommendation to help the right specialists review data, access, compliance, privacy, security, product, and implementation assumptions before the workflow moves toward pilot, release, or expansion.

## Slide 52/53 - Recap

Security, governance, and data-readiness judgment is about making assumptions, boundaries, risks, validation needs, escalation points, and next responsible steps visible.

You should now be able to treat governance as a trust enabler in technical solution work, and ask practical governance questions about ownership, boundaries, review, monitoring, and escalation. You've also learned how to distinguish available data from approved data, and escalate responsibly instead of making unsupported assurance claims.

The main habit to take forward is careful readiness language: this may be a plausible starting path, and these are the assumptions we need to validate before treating it as a recommendation.

## Slide 53/53 - Congratulations

Congratulations, you've completed this course!

Before your next technical customer conversation, solution review, discovery prep, implementation handoff, pilot discussion, or readiness review, remember to use your readiness recommendation.

Use it to clarify what needs protection, what data is involved, who owns review and approval, and which assumptions need specialist validation before the workflow moves forward.

Course completed. Next up in OpenAI Technical Practitioner: **OpenAI Technical Practitioner - Final Exam** (Course, 2 min) — Codex Deployment Practitioner - Final Exam.
