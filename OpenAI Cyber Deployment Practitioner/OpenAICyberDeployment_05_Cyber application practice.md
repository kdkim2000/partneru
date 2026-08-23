# Cyber application practice

## Slide 1/46 - Title

Created July 2026

## Slide 2/46 - Introduction

In this application course, you'll work through a realistic Cyber / Daybreak customer example from first signal to partner-safe recommendation.

You'll practice diagnosing the customer's security workflow, identifying stakeholders, choosing a responsible Codex Security path, scoping a bounded evaluation, reviewing evidence carefully, and preparing a concise next-step recommendation.

Keep one principle in mind: Daybreak is a defensive cyber workflow motion. It is not a model-access pitch, an offensive cyber training course, or a promise of automatic remediation.

Your role is to help the customer move from a broad security signal to a bounded, authorized, evidence-led next step.

## Slide 3/46 - What you'll learn

By the end of this course, you'll be able to:

- Diagnose a customer's cyber personas, security inputs, and workflow bottlenecks.
- Route a Cyber / Daybreak use case based on scope, access, risk, and escalation needs.
- Select and scope a bounded Codex Security evaluation.
- Define reviewers, success metrics, evidence expectations, and governance guardrails.
- Interpret technical evidence, dispositions, and proof gaps.
- Prepare a concise, partner-safe recommendation with a clear next action and owner.

Let's get started!

## Slide 4/46 - How this course works

You'll use one fictional customer case throughout the course: Harborline Bank.

Each core module moves you one step closer to your final recommendation.

| Module | What you will build |
|---|---|
| Module 1 | Initial customer signal summary |
| Module 2 | Persona, bottleneck, and use-case diagnosis |
| Module 3 | Responsible route and Codex Security workflow pattern |
| Module 4 | Bounded evaluation plan |
| Module 5 | Evidence review note |
| Module 6 | Partner-safe recommendation |

As you work through the case, you'll need to balance customer conversation judgment with technical evidence judgment.

That means you'll practice both sides of the partner motion:

Understanding the customer's business pressure, stakeholder priorities, and opportunity signals.

Preserving technical accuracy around scope, evidence, workflow fit, proof gaps, and review ownership.

The aim is a clear, defensible recommendation that can support a real customer next step without overstating what Daybreak, Codex Security, or a bounded evaluation can prove.

## Slide 5/46 - Introduction (Module: Customer Context and Case Setup)

In this module, you'll meet the customer case you'll use throughout the course.

Your first task is not to recommend a product path. It is to understand what the customer is asking for, what pressure sits underneath that ask, and what still needs clarification.

## Slide 6/46 - How to use the Customer Case File

The Customer Case File is your working source for this course.

You'll refer to it to identify personas, diagnose workflow bottlenecks, classify the use case, choose a responsible workflow pattern, scope a bounded evaluation, review fictional evidence, and draft a partner-safe recommendation.

As you read the case, separate three things:

- **Known facts:** What the customer has said or provided.
- **Reasonable assumptions:** What may be true, but still needs confirmation.
- **Open questions:** What you need to clarify before recommending a next step.

This distinction matters because Cyber / Daybreak recommendations must be evidence-led.

A strong recommendation does not pretend all uncertainty has been resolved. It states the known scope, names the proof gaps, and recommends the next decision point.

## Slide 7/46 - Customer Case File: Harborline Bank

Harborline Bank is a fictional regional financial services company modernizing its digital customer portal.

The case includes a noisy AppSec backlog, a pull request that changes authorization logic in a customer account service, and several stakeholders with different priorities around risk reduction, evidence quality, developer handoff, governance, and release velocity.

Before you continue, download the Customer Case File — Harborline Bank. You'll use it as your working source for the rest of the course.

*(Attachment: CY8-2.3 OpenAI Partner University _ Cyber Application Practice Course _ Customer Case File.pdf, 1.4 MB)*

As you read the case file, focus on four questions:

- What is the customer asking for?
- What security workflow pressure sits underneath the ask?
- Who needs to review, approve, or act on the output?
- What still needs to be clarified before recommending a Daybreak or Codex Security next step?

The case is not asking you to prove a vulnerability or design a full deployment. It is asking you to identify the responsible first step: a bounded, authorized, evidence-led recommendation that keeps AppSec and engineering in control of the final decision.

## Slide 8/46 - Customer context overview: Harborline Bank

Harborline Bank is a realistic customer context because it combines several common Cyber / Daybreak signals:

- A noisy AppSec backlog.
- A security-sensitive pull request.
- Limited reviewer capacity.
- Pressure to maintain release velocity.
- Governance concerns about AI-assisted security work.
- Interest in broad Daybreak adoption before the first workflow is scoped.
- A question about cyber access before the partner has confirmed the workflow.

The case is not asking you to solve a vulnerability. It is asking you to recommend the responsible first step.

A strong first step should help Harborline answer a bounded decision question, such as:

> Can Codex Security help AppSec and engineering review this authorization-related change with clearer evidence, defined scope, and human approval?

That is different from:

> Can Daybreak scan everything, prove all vulnerabilities, and automate remediation across the estate?

The first question is bounded and reviewable. The second is too broad for a first recommendation.

## Slide 9/46 - Your learning role and final deliverable

In this course, you are acting as a partner team preparing a customer-ready recommendation for Harborline Bank.

Your final deliverable is a concise recommendation that explains:

- The customer signal
- The relevant personas
- The workflow bottleneck
- The selected Codex Security workflow pattern
- The bounded evaluation scope
- The evidence limits
- The review process
- The success metrics
- The recommended next action

The recommendation should be partner-safe. That means it should be defensive, scoped, evidence-led, and clear about human review.

It should also avoid claims about cyber-specialized access, reduced refusals, pricing, production testing, automatic remediation, or guaranteed vulnerability discovery.

## Slide 10/46 - Recommended exercise: Extract the initial cyber signal

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose**

Help you identify the first meaningful customer signal without jumping directly to a product pitch.

**Task**

Review the Customer Case File: Harborline Bank. Identify the customer's stated ask, the underlying security workflow pressure, the key stakeholders involved, and what still needs clarification before recommending a Codex Security workflow or bounded evaluation.

As you complete the task, consider:

- What is the customer asking for?
- What security workflow pressure is underneath the ask?
- Which stakeholders appear to be involved?
- What questions still need to be clarified?
- What should the partner focus on next in discovery?

**Estimated time**

8 minutes

**Suggested output and reflection**

A short initial signal summary with the customer ask, likely security workflow, open questions, and recommended discovery focus.

## Slide 11/46 - Knowledge check

**Question:** Which statement best captures the initial Cyber / Daybreak signal in the Harborline Bank case?

- **Harborline has a broad security ask, but the first step should clarify the authorized workflow, reviewer, scope, and proof point.** ✓ Correct
- Harborline primarily needs cyber-specialized access because the customer mentioned access in the opening ask.
- Harborline has confirmed an authorization vulnerability and now needs a remediation plan.
- Harborline has already approved broad repository coverage and now needs a deployment timeline.

*Explanation: The case includes backlog pressure, a sensitive pull request, named reviewers, and access questions, but the partner still needs to clarify scope and proof before recommending a path.*

## Slide 12/46 - Summary

You now have the working case for the course. The important move in this module was to treat the customer's broad ask as a signal, not as a conclusion.

Before recommending a Daybreak or Codex Security path, you need to clarify the workflow, personas, scope, reviewer, and evidence standard.

## Slide 13/46 - Introduction (Module: Identify Persona, Bottleneck, and Use Case)

In this module, you'll diagnose the customer situation before choosing a solution path.

You'll identify who is involved, where the workflow is stuck, and which Cyber / Daybreak use case is the strongest bounded starting point.

## Slide 14/46 - Identify stakeholders and cyber personas

Cyber personas are not just job titles. In a customer conversation, a persona is a decision lens: what the person is responsible for, what evidence they trust, and what decision they need to make.

In the Harborline Bank case, four personas matter.

| Persona | Primary decision lens | What your recommendation must address |
|---|---|---|
| CISO | Risk, governance, executive confidence | The work is bounded, authorized, reviewable, and aligned to human accountability |
| AppSec lead | Finding validity and evidence quality | The workflow can help separate candidate findings, proof gaps, and reviewer decisions |
| DevSecOps manager | Repeatability and tool fit | The first step does not bypass systems of record or jump into premature CI/CD integration |
| Engineering director | Release readiness and developer handoff | The output supports review of the pull request without claiming automatic approval |

The strongest recommendation will connect each persona to a decision need.

For example, it is not enough to say,

> "The CISO cares about risk."

A stronger statement is:

> "The CISO needs confidence that the first evaluation is limited to an owned repository, excludes production testing, keeps AppSec and engineering as decision owners, and produces evidence that can be recorded."

This gives the recommendation a clearer path.

## Slide 15/46 - Diagnose the workflow bottleneck

To diagnose the workflow, use the defensive workflow lens:

**Find → Validate → Test → Remediate → Prove**

This lens is a simple way to locate where the customer's security work is slowing down.

It is used because customers often already have scanners, tickets, repositories, and review meetings.

The problem is usually not that no security signal exists. The problem is that the signal gets stuck before it becomes a validated, prioritized, reviewable action.

For Harborline Bank, likely bottlenecks include:

- Too many low-confidence findings
- Slow validation of whether findings are real
- Weak developer handoff
- Unclear evidence for prioritization
- Release pressure around a sensitive pull request
- Limited reviewer capacity

A good recommendation should focus on the bottleneck the first evaluation can actually test. For this case, the most immediate bottleneck is not "all AppSec work is slow." That is too broad.

A more precise bottleneck is:

> AppSec and engineering need a faster, evidence-led way to review whether an authorization-sensitive pull request needs additional security work before release.

That bottleneck is specific enough to route and scope.

## Slide 16/46 - Classify the use case

Use-case classification helps you avoid vague phrases like "AI for security." It names the job the workflow should perform.

In this case, possible Cyber / Daybreak use-case labels include:

- Review code changes for a sensitive pull request
- AppSec backlog validation
- Evidence generation for reviewer decision-making
- Bounded remediation support, if a finding is validated and remediation is approved

For the first evaluation, the strongest primary use case is likely:

> Review code changes for the authorization-related pull request.

This fits the immediate customer decision: whether the authorization-related change can move forward after AppSec and engineering review.

A reasonable expansion path could be:

> AppSec backlog validation for a bounded slice of findings in the same owned repository.

That expansion should come later, after the first review produces a clear decision, evidence quality is acceptable, and reviewer ownership is confirmed.

## Slide 17/46 - Recommended exercise: Complete the customer situation summary

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose**

Help you connect the customer's stakeholders, workflow pressure, and strongest first Cyber / Daybreak use case.

**Task**

Use the Customer Case File to complete a short situation summary that identifies who is involved, where the workflow is stuck, and what first use case would be safest and most relevant to the customer's immediate decision.

Complete these fields:

- **Personas:** Who is involved, and what do they need to decide?
- **Bottleneck:** Where is the security workflow getting stuck?
- **First use case:** What is the strongest bounded starting point?
- **Evidence need:** What would show that the first step helped the reviewers make a decision?
- **Expansion path:** What could come later if the first evaluation succeeds?

**Estimated time**

8–10 minutes

**Suggested output and reflection**

A short customer situation summary that identifies the key personas, main workflow bottleneck, recommended first use case, evidence need, and one possible expansion path.

## Slide 18/46 - Knowledge check

**Question:** Harborline's engineering director says, "We do not want another alert queue. We need to know whether this authorization-related pull request can move forward without creating avoidable release risk." Which diagnosis is strongest?

- The first use case should be broad backlog remediation because release pressure usually means engineering needs fixes immediately.
- The first use case should be cyber-specialized access because the pull request involves authorization logic.
- **The first use case should be to review code changes for the sensitive pull request, with AppSec and engineering reviewing evidence before any release decision.** ✓ Correct
- The first use case should be a full scan of every repository so Harborline can compare all sources of release risk.

*Explanation: The statement points to a specific decision about a security-sensitive pull request. The Codex Security "Review code changes" workflow fits that decision while preserving human review.*

## Slide 19/46 - Summary

You diagnosed the case by linking personas to decisions, locating the bottleneck in the defensive workflow, and selecting a primary use case.

The key progression was from a broad ask to a specific first decision: review an authorization-sensitive pull request with clear scope and human accountability.

## Slide 20/46 - Introduction (Module: Route the Opportunity and Select the Workflow Pattern)

In this module, you'll turn the use-case diagnosis into a responsible route.

The goal is to choose a first workflow pattern that matches the customer's decision point without turning the conversation into an access-first or automation-first pitch.

## Slide 21/46 - Make the routing decision

Harborline's broad ask includes:

> "Can we use Daybreak across all repositories?"

That is not the right starting point for a first recommendation. A responsible route starts with the authorized defensive workflow.

In Cyber / Daybreak customer work, routing means choosing the safest and most relevant next step for the customer's bounded workflow.

For Harborline, the partner should reframe the broad ask like this:

> "Before recommending broader coverage, let's start with the customer-account-service pull request because it is customer-owned, authorization-related, time-sensitive, and reviewable by named AppSec and engineering owners."

This route is stronger because it is grounded in a real workflow and a near-term decision.

The partner should not promise:

- Cyber-specialized access
- Reduced refusals
- Zero Data Retention
- Special availability
- Pricing
- Production testing
- Broad autonomous testing
- Automatic remediation
- Guaranteed vulnerability discovery

Those topics either require approved OpenAI guidance, customer-specific review, or SME escalation.

## Slide 22/46 - Choose the first workflow pattern

The first workflow pattern should match the customer's immediate decision point.

For Harborline, the likely first pattern is:

> Review code changes for the authorization-related pull request.

Choose this pattern when the customer needs to review a bounded code change, especially one connected to sensitive logic such as authentication, authorization, account access, payment, or customer-data handling.

A possible expansion pattern is:

> Triage a backlog for a bounded set of existing findings in the owned repository.

Choose this later if the customer's main problem becomes backlog validation rather than pull-request review.

Some workflow patterns are not good first choices in this case.

| Workflow pattern | Why it is not the first choice |
|---|---|
| Deep security scan | It may create more review burden before the customer has proven the first review loop. |
| Fix and verify findings | This workflow starts from an accepted finding, so it is premature until AppSec and engineering have accepted the finding and remediation is explicitly in scope. |
| Broad autonomous testing request | The scope is too broad and the case does not approve production testing, live targets, or all repositories. |
| Access-first route | The access path should follow the approved workflow, not lead the conversation. |

The decision standard is simple:

Match the workflow pattern to the first customer decision, not to the largest possible ambition.

## Slide 23/46 - Recommended exercise: Choose the responsible route and workflow pattern

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose**

Help you move from a broad customer ask to a safe, bounded Codex Security recommendation.

**Task**

Use the Customer Case File to decide the responsible first route and the Codex Security workflow pattern that best fits the customer's immediate decision point.

As you complete the task, consider:

- **Customer ask:** What is the customer asking for?
- **Responsible route:** What is the safest first step?
- **Workflow pattern:** Which Codex Security workflow fits best?
- **Reason:** Why does this pattern fit the target, timing, and evidence need?
- **Guardrails:** What should not be promised or should be escalated?

**Estimated time**

8–10 minutes

**Suggested output and reflection**

A short route and workflow decision that explains the recommended first step, selected workflow pattern, rationale, key guardrails, and any escalation needs.

## Slide 24/46 - Knowledge check

**Question:** Harborline asks whether Daybreak can be used across all repositories and whether cyber-specialized access will help. The case also includes a release-sensitive pull request in an owned repository, named AppSec and engineering reviewers, and constraints against production testing or automatic remediation. What is the strongest first route?

- Review only authorization-related repositories, exclude production testing, and ask AppSec to decide which outputs matter after the scan.
- **Start with the authorization-related pull request, define reviewer-owned evidence, and defer access-path discussion until the workflow is scoped.** ✓ Correct
- Begin with a bounded backlog slice in customer-account-service, then decide whether the pull request needs a separate review.
- Open with Trusted Access qualification, repository confirmation, named reviewer, and a success metric before selecting the Codex Security workflow.

*Explanation: This route starts with the most immediate, owned, bounded, and reviewable workflow. It also keeps access-path discussion sequenced behind scope, evidence, and reviewer ownership.*

## Slide 25/46 - Summary

You selected a responsible first route by matching the workflow pattern to the customer's first decision point.

The first step is not "Daybreak everywhere." It is a bounded Codex Security review of the authorization-related pull request, with clear scope, reviewers, and guardrails.

## Slide 26/46 - Introduction (Module: Scope the Bounded Evaluation)

In this module, you'll define the first evaluation Harborline should run.

The focus is not a full deployment plan. The focus is one bounded starting point, named reviewers, evidence limits, success measures, and guardrails.

## Slide 27/46 - Define the target, scope, and reviewers

A bounded evaluation should be narrow enough to govern and specific enough to measure.

For Harborline, a strong first evaluation target may be:

- The owned customer-account-service repository
- The authorization-related pull request or diff
- The related authorization files or tests needed to review the change

The scope should also state what is out of scope. This is not a small detail. Out-of-scope items protect the customer, the partner, and the evaluation from becoming broader than approved.

For Harborline, out-of-scope items include:

- Production testing
- Live exploit reproduction
- Third-party infrastructure
- Broad review across all repositories
- Customer data
- Automatic merge or release decisions
- Automatic vulnerability closure
- Remediation unless a finding is validated and remediation is explicitly approved

The evaluation should name decision owners:

**AppSec reviewer**

Reviews finding quality, evidence, and security relevance.

**Engineering owner**

Reviews code behavior, tests, and implementation impact.

**Decision owner**

Confirms whether the pull request can proceed, needs more evidence, or requires remediation work.

A partner-safe scope statement might read:

> Harborline should begin with the Codex Security "Review code changes" workflow, bounded to the authorization-related pull request in the customer-owned customer-account-service repository. The review should inspect the approved diff and related authorization context only. Production testing, live exploit reproduction, third-party infrastructure, customer data, automatic remediation, and merge decisions are out of scope. AppSec and engineering remain the reviewers and decision owners.

## Slide 28/46 - Define evidence limits and success measures

A bounded evaluation should define what it can and cannot prove.

For Harborline, the evaluation can help reviewers answer questions such as:

- Does the diff create a candidate authorization concern?
- What source facts support the concern?
- What assumptions or proof gaps remain?
- Which reviewer needs to decide the next step?
- What evidence should be recorded?

The evaluation cannot prove everything. In this case, it cannot prove runtime exploitability, production behavior, or enterprise-wide risk because those activities are not in scope.

This is where the context, agentic runtime, and observability planning check helps.

Use this check because AI-assisted security work is not only about the model output. It depends on what the workflow is allowed to know, where it is allowed to operate, and how the customer reviews and records what happened.

| Planning check | Plain-language meaning | Harborline example |
|---|---|---|
| Context | What the workflow is allowed to use | Approved repository, pull request diff, related authorization files, tests, stakeholder notes |
| Agentic runtime | Where and how the workflow does work | Bounded Codex Security review of an approved diff, without production testing or automatic changes |
| Observability | How the customer monitors, reviews, and records the work | AppSec and engineering review, evidence note, decision logged in the customer-approved system of record. |

Success should focus on decision quality, not raw finding volume.

Relevant success signals for Harborline include:

- Clearer evidence for the pull request review
- Stronger reviewer confidence
- Better prioritization of whether the candidate finding needs action
- More actionable developer handoff
- Reduced noise around unsupported claims
- A clearer next decision: proceed, seek more evidence, remediate, suppress, or escalate

A weak success measure would be:

> "Number of findings generated."

A stronger success measure would be:

> "AppSec and engineering can accept, reject, or request more evidence for the candidate finding using a concise evidence record."

## Slide 29/46 - Recommended exercise: Define the first evaluation plan

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose**

Help you turn the selected Codex Security workflow into a simple, bounded evaluation plan.

**Task**

Use the Customer Case File to outline the first evaluation Harborline Bank should run. Keep the plan focused on one safe, reviewable starting point.

As you complete the task, consider:

- **Target:** What asset or workflow should be evaluated first?
- **Scope:** What is included, and what is clearly out of scope?
- **Reviewers:** Who needs to review the output and make decisions?
- **Evidence:** What can the evaluation prove, and what remains a proof gap?
- **Success:** What would show that the evaluation supported the customer's decision?
- **Stop conditions:** What would make the evaluation pause?
- **Escalation triggers:** What access, production, data, exploit-heavy, or SME issues need review before proceeding?

**Estimated time**

8–10 minutes

**Suggested output and reflection**

A short evaluation plan that identifies the target, scope, reviewers, evidence limits, and success measures.

## Slide 30/46 - Knowledge check

**Question:** Which evaluation plan is strongest for Harborline's first step?

- Treat the candidate finding as proof that the pull request is unsafe and block the release immediately.
- **Review the authorization-related pull request in the owned repository, exclude production testing and automatic remediation, and have AppSec and engineering decide the next action from the evidence record.** ✓ Correct
- Scan all repositories, rank every finding by severity, and ask engineering to fix the highest-ranked issues first.
- Start with CI/CD integration so every future pull request is automatically reviewed before merge.

*Explanation: This plan is bounded, reviewable, tied to the immediate decision, and clear about human ownership.*

## Slide 31/46 - Summary

You scoped a first evaluation that is narrow, authorized, and measurable.

The key move was to define the target, out-of-scope items, reviewers, evidence ceiling, and success signals before discussing broader rollout or integration.

## Slide 32/46 - Introduction (Module: Technical Evidence Review Practice)

In this module, you'll review a fictional Codex Security-style output and decide how to describe it responsibly.

This evidence review matters in two ways. In a customer conversation, careful language helps you avoid overstating what a finding proves. In a technical review, careful evidence labeling helps AppSec and engineering decide what should be accepted, rejected, investigated further, or escalated.

The goal is not to prove a vulnerability from limited information. The goal is to describe the evidence accurately, name what remains unproven, and identify the right next reviewer action.

## Slide 33/46 - Review the finding within the approved scope

Start every evidence review by restating what was approved.

For Harborline, the approved review is limited to the authorization-related pull request in customer-account-service and the related source context needed to understand the change.

The fictional finding says:

> Authorization check may be bypassed in one account-update path after refactor.

That statement should not be accepted at face value. It should be challenged against the evidence.

Use these evidence labels:

| Evidence label | What it means | Example in this case |
|---|---|---|
| Source fact | Directly visible in the provided material | The diff changes the account update path |
| Supported inference | A reasonable conclusion based on source facts | The changed path may need AppSec review |
| Runtime proof | Evidence from approved runtime activity | None in this case |
| Unsupported claim | A statement that goes beyond the evidence | "Unauthorized access is proven" |
| Proof gap | Something unresolved that needs review or validation | It is unknown whether route-level controls already enforce authorization |

This labeling pattern keeps the recommendation accurate.

It helps you separate what the case file shows, what can be reasonably inferred, what has not been tested, and what a human reviewer still needs to decide.

## Slide 34/46 - Separate evidence, limits, and next action

A strong evidence review separates four questions:

1. **Evidence** — What facts are visible in the materials?
2. **Limits** — What remains unproven?
3. **Disposition** — How should the finding be described?
4. **Next action** — Who should review or validate it next?

For Harborline, the strongest disposition is:

> Candidate finding / needs further review.

It should not be labeled as a validated finding because there is no runtime proof, no approved test execution, and no reviewer decision.

It should not be labeled as a false positive because the source facts show a plausible reason for review.

The recommended next action is for AppSec and the engineering owner to review the changed path, confirm whether authorization is enforced elsewhere, decide whether additional tests are needed, and record the outcome.

A partner-safe evidence note might read:

> The bounded code-change review surfaced a candidate authorization concern in the account update path. The source evidence shows the pull request changed how the update path reaches role-checking logic, and the provided tests do not clearly cover delegated administrator behavior.
>
> No runtime validation was approved or performed, so this should not be presented as a validated vulnerability. AppSec and engineering should review the changed path, confirm whether authorization is enforced elsewhere, and decide whether additional tests or remediation are needed.

This note is careful because it states the evidence, the limit, the disposition, and the next action.

## Slide 35/46 - Recommended exercise: Review the evidence

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose**

Help you practice reviewing a fictional Codex Security-style finding without overstating what the evidence proves.

**Task**

Use the fictional evidence in the Customer Case File to decide how the finding should be described and what should happen next.

As you complete the task, consider:

- **Scope:** What was approved for review?
- **Evidence:** What facts are visible in the provided materials?
- **Limits:** What is still unproven?
- **Disposition:** Should this be treated as a candidate finding, validated finding, false positive, proof gap, or needs further review?
- **Next step:** What should the AppSec reviewer or engineering owner do next?

**Estimated time**

8–10 minutes

**Suggested output and reflection**

A short evidence review note that identifies the finding status, key evidence, proof gap, and recommended reviewer action.

## Slide 36/46 - Knowledge check

**Question:** The fictional output says the authorization check "may be bypassed," but the case file shows no approved runtime validation, no test execution, and no AppSec reviewer decision. What is the best disposition?

- False positive, because the finding has not been proven through runtime testing.
- Critical vulnerability, because authorization issues are always severe.
- Validated finding, because the output names a specific authorization concern.
- **Candidate finding that needs AppSec and engineering review before any remediation or release decision.** ✓ Correct

*Explanation: The evidence supports a candidate finding and proof gaps. Human reviewers should decide the next action.*

## Slide 37/46 - Summary

You practiced evidence calibration by separating source facts, supported inferences, runtime proof, unsupported claims, and proof gaps.

The key outcome is not to "prove" the finding. It is to describe the evidence accurately and route the next reviewer action responsibly.

## Slide 38/46 - Introduction (Module: Prepare the Partner-Safe Recommendation)

In this module, you'll bring the case together into one concise recommendation.

The recommendation should help Harborline decide the next step without overstating access, automation, remediation, or proof.

## Slide 39/46 - Use the recommendation structure

A partner-safe recommendation should fit into six concise sections.

| Section | What to include |
|---|---|
| Customer situation | Customer signal, primary persona, workflow bottleneck, and classified use case |
| Recommended route | Responsible opportunity route and selected Codex Security workflow pattern |
| Bounded evaluation | Approved target, scope, reviewers, review process, and out-of-scope items |
| Success and guardrails | Success metrics, expected artifacts, governance guardrails, access guardrails, and escalation conditions |
| Evidence position | Candidate finding status, source facts, supported inferences, runtime proof if any, unsupported claims, proof gaps, and disposition |
| Next action | Customer action, partner action, OpenAI SME action if needed, owner, timing, and decision point |

This structure keeps the recommendation practical. It gives you a way to explain the customer situation, route, value, and next action while also preserving the technical boundaries that make the recommendation defensible.

Use the structure to avoid two common mistakes:

A recommendation that is too vague to act on.

A recommendation that is too technical to support a customer decision.

The strongest version does both jobs: it gives the customer a clear next step and shows the evidence, scope, guardrails, and review process behind it.

## Slide 40/46 - Keep the language partner-safe

Partner-safe language is not cautious for its own sake. It protects trust.

A recommendation should be:

- Defensive and workflow-led.
- Grounded in the customer's authorized asset and review process.
- Clear about human review and customer-owned decisions.
- Clear about proof gaps and evidence limits.
- Careful not to promise cyber-specialized access, reduced refusals, Zero Data Retention, special availability, pricing, production testing, automatic remediation, or guaranteed vulnerability discovery.
- Clear about when OpenAI SME support is required.

Compare these two recommendation statements.

**Weak statement**

> "Daybreak can scan all Harborline repositories, reduce false positives, fix authorization issues, and help the customer get cyber-specialized access."

This is weak because it overpromises scope, outcomes, remediation, and access.

**Stronger statement**

> "For the first step, Harborline should use the Codex Security 'Review code changes' workflow on the authorization-related pull request in the customer-owned customer-account-service repository. The review should produce an evidence record for AppSec and engineering to decide whether the candidate finding should be accepted, suppressed, remediated, or investigated further. Broader repository coverage, CI/CD integration, production testing, and access-path questions should be handled only after the first review loop is complete and any sensitive items are routed appropriately."

This is stronger because it is scoped, evidence-led, and clear about what comes next.

## Slide 41/46 - Example partner-safe recommendation

Use this example as a model for the final exercise.

**Customer situation**

Harborline Bank has a growing AppSec backlog and an immediate release decision involving an authorization-related pull request in customer-account-service. The main stakeholders are the CISO, AppSec lead, DevSecOps manager, and engineering director. The immediate bottleneck is validation and reviewer confidence for a sensitive pull request, not broad estate-wide coverage.

**Recommended route**

Start with the Codex Security "Review code changes" workflow, bounded to the authorization-related pull request. This route fits the customer's immediate decision point because the target is customer-owned, reviewable, time-sensitive, and connected to a named AppSec and engineering review path.

**Bounded evaluation**

Limit the first evaluation to the approved pull request, related authorization files, and relevant tests in customer-account-service. Exclude production testing, live exploit reproduction, third-party infrastructure, customer data, automatic remediation, automatic merge, and broad review across all repositories. AppSec and engineering remain responsible for reviewer decisions.

**Success and guardrails**

Success should be measured by evidence quality, reviewer confidence, decision clarity, and developer handoff, not by raw finding count. Expected artifacts should include a short evidence record, proof gaps, reviewer disposition, and next action. Access-path questions, cyber-specialized access, production testing, and broader automation should be escalated or revisited only after the first evaluation is reviewed.

**Evidence position**

The fictional output should be treated as a candidate finding that needs further review. Source facts indicate that the pull request changes how one account-update path reaches role-checking logic. No runtime proof was collected, and it is not proven that unauthorized access is possible. AppSec and engineering should review whether authorization is enforced elsewhere and whether additional tests or remediation are needed.

**Next action**

Harborline should confirm the approved scope, name the AppSec and engineering reviewers, and agree where the evidence record will be logged. The partner should facilitate the bounded evaluation plan and route any cyber-specialized access, production testing, or advanced cyber questions to the appropriate OpenAI SME before making commitments.

## Slide 42/46 - Recommended exercise: Draft the partner-safe recommendation

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose**

Help you bring the course application together into one clear customer-ready recommendation.

**Task**

Use the decisions made throughout the course to draft a concise recommendation covering customer situation, recommended route, bounded evaluation, success metrics and guardrails, evidence position, and next action.

**Estimated time**

8–10 minutes

**Suggested output and reflection**

A concise partner-safe recommendation that explains the first step, why it fits, what evidence and proof gaps apply, what guardrails must be preserved, and what should happen next.

**Self-check**

Your recommendation should identify the customer's immediate decision point, define a bounded first step, name the relevant human decision owners, separate evidence from proof gaps, and avoid promises about cyber-specialized access, production testing, automatic remediation, or guaranteed vulnerability discovery.

## Slide 43/46 - Knowledge check

**Question:** Harborline needs a recommendation after reviewing the case context. The customer has a noisy AppSec backlog, an immediate authorization-related pull request, named AppSec and engineering reviewers, and an unresolved question about cyber-specialized access. Which recommendation is strongest?

- **Start with the authorization-related pull request, define AppSec and engineering reviewer responsibilities, record evidence and proof gaps, and revisit broader coverage or access questions after the first reviewer disposition.** ✓ Correct
- Use the pull request as the first target, but position the recommendation around faster release approval because the finding concerns authorization logic and the customer has release pressure.
- Run a security scan of customer-account-service, exclude production testing, have AppSec disposition the outputs, and use the results to decide whether broader Daybreak coverage is justified.
- Start with a bounded backlog validation slice in customer-account-service, use the evidence to identify recurring risk patterns, and review the pull request in a follow-up evaluation.

*Explanation: This recommendation matches the immediate decision point, preserves AppSec and engineering review, records evidence and proof gaps, and sequences broader coverage or access questions responsibly.*

## Slide 44/46 - Summary

You synthesized the case into a partner-safe recommendation.

The recommendation connects the customer signal, personas, workflow bottleneck, selected route, bounded evaluation, evidence limits, guardrails, and next action. It gives the customer a clear next step while preserving human accountability and responsible escalation.

## Slide 45/46 - Recap

In this course, you practiced turning a broad Cyber / Daybreak signal into a partner-safe recommendation for Harborline Bank.

You moved through the full decision path: diagnose the customer workflow, identify personas and bottlenecks, choose a responsible Codex Security pattern, scope a bounded evaluation, review evidence, and define the next action.

A strong recommendation helps the customer make the next responsible decision without trying to solve the entire security program at once.

## Slide 46/46 - Congratulations

Congratulations, you've completed this course!

You can now use the Cyber / Daybreak track concepts together in a realistic customer situation: diagnosing workflow pressure, routing responsibly, scoping a bounded evaluation, interpreting evidence carefully, and preparing a recommendation that customers, partners, and OpenAI teams can act on with confidence.

Course completed.

**Next up in OpenAI Cyber Deployment Practitioner: Cyber Lab - Northstar Financial** (Course, 3 min)

Step into the role of a security advisor for Northstar Financial and sharpen your ability to deliver actionable, evidence-based recommendations under real-world constraints. Analyze a focused customer scenario, review a targeted pull request, and translate broad security requests into clear, bounded next steps that balance risk, scope, and organizational priorities. Practice communicating findings with precision—without promising the impossible—while navigating limited access, strict review boundaries, and the need for human oversight. Perfect for anyone looking to master concise, high-impact security recommendations in fast-moving engineering environments.
