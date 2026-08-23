# Codex Security Workflow Patterns

## Slide 1/58 - Title

Codex Security Workflow Patterns

Created July 2026

## Slide 2/58 - Introduction

Security teams often do not need another alert queue. They need a repeatable way to turn repository context and security signal into validated evidence and reviewable remediation.

Codex Security supports that work as part of Daybreak. It helps authorized security and engineering teams analyze scoped code, validate findings, prepare evidence, and support bounded remediation.

In this course, you'll learn how to explain Codex Security workflow patterns responsibly while keeping human review, customer governance, and final decisions in place.

## Slide 3/58 - What you'll learn

You do not need to run scans or debug code. The goal is to recognize the customer workflow, choose the right Codex Security pattern, set safe evidence expectations, and involve technical or AppSec support when needed.

By the end of this course, you'll be able to:

- Explain Codex Security's role in Daybreak workflows.
- Identify required scope, context, authorization, and evidence boundaries.
- Describe the lifecycle from threat modeling to revalidation.
- Choose among the Codex Security plugin workflows taught in this course: run a security scan, run a deep security scan, review code changes for security, and fix and verify findings.
- Explain remediation support without overpromising automation, approval, or closure.

Let's get started!

## Slide 4/58 - Introduction (Module: What Codex security does in defensive workflows)

A customer may ask whether Codex Security can scan repositories, fix a backlog, or unlock cyber-model access.

Treat that as a signal, not a workflow decision. First clarify the authorized defensive workflow: what work needs support, what is in scope, who reviews outputs, what evidence is needed, and what is out of scope.

**Core rule:** Start with the authorized workflow, then choose the Codex Security pattern that fits.

## Slide 5/58 - Codex Security as a workflow-native layer

Codex Security is part of Daybreak and supports defensive application security and secure software development through two distinct surfaces: the Codex Security plugin, which runs in a local Codex task, and Codex Security cloud, which scans connected GitHub repositories through Codex cloud.

A useful way to explain it is:

Codex Security helps authorized security and engineering teams use repository context and model reasoning to support structured security analysis, evidence generation, and reviewable remediation across local and cloud-based workflows.

For a customer conversation, think of these as four jobs: understand the code context, test whether the evidence supports the finding, package the decision for review, and support a reviewable fix when the finding is ready.

That means Codex Security is not just "a model answering security questions." It is closer to a repeatable security workflow surface.

It can help teams work through tasks such as:

- Understanding repository structure and relevant system context.
- Building or reviewing a threat model.
- Discovering candidate findings.
- Validating whether a finding appears relevant in context.
- Explaining an attack path at the right level of evidence.
- Preparing reports that support human review.
- Supporting bounded remediation, tests, and revalidation when the finding is ready for that step.

This matters because security work rarely ends at detection. A finding only creates value if the team can decide whether it is real, understand why it matters, route it to the right owner, remediate safely, and record evidence that the decision was made.

## Slide 6/58 - From alerts to decisions

A security alert is a signal that something may need review. It is not the same as a decision.

Many AppSec teams face large queues of scanner findings, dependency alerts, bug-bounty reports, code review concerns, or audit issues. More signal can help, but it can also create more work when teams cannot validate, prioritize, and remediate quickly enough.

Codex Security is most valuable when it helps move from alert volume to decision quality.

**Alert volume means:**
- More potential issues to review.
- More tickets, scanner outputs, or backlog items.
- More pressure on security and engineering teams.

**Decision quality means:**
- Clearer evidence about whether the finding applies.
- Stronger validation of what is real, reachable, or relevant.
- Better prioritization based on impact and context.
- Reviewable remediation guidance.
- Clear proof gaps where the evidence is not yet enough.
- A better handoff between AppSec, engineering, and governance processes.

Weak positioning sounds like:

"Codex Security will find more vulnerabilities."

Stronger positioning sounds like:

"Codex Security can help the team reason over repository context, validate which findings are supported by evidence, and prepare reviewable next steps while keeping security and engineering reviewers in control."

## Slide 7/58 - Human control points remain essential

Codex Security can support analysis, evidence generation, and patch preparation. It does not replace customer judgment.

Human security and engineering teams remain responsible for:

- Confirming scope and authorization.
- Calibrating severity.
- Deciding whether a candidate finding is real and material.
- Accepting, changing, or rejecting remediation suggestions.
- Determining whether tests and review are sufficient.
- Approving pull requests.
- Making release decisions.
- Updating the customer's system of record.
- Deciding whether to expand, pause, or escalate.

For commercial roles, the key point is not how each control point works; it is that the customer must have review gates before findings become fixes or records.

Treat pull requests, tests, CI checks, security review, engineering approval, and systems of record as control points in the workflow.

A customer-ready explanation is:

"Codex Security can help prepare evidence and reviewable remediation support. Your security and engineering teams still decide what is accepted, merged, released, and recorded."

That language helps protect the customer's governance process and keeps the partner from overclaiming automation.

## Slide 8/58 - What Codex Security is not

Codex Security should not be positioned as:

- A replacement for scanners.
- A replacement for AppSec or engineering teams.
- A guarantee that every vulnerability will be found.
- A guarantee that every reported issue is exploitable.
- A system that automatically merges, ships, or closes fixes.
- A shortcut around customer authorization, access controls, or review gates.
- A default path to cyber-specialized model access.
- A license to test production systems or third-party targets without explicit authorization.

The right positioning is narrower and stronger:

Codex Security helps authorized defenders structure security analysis and remediation support around approved assets, evidence, and human review.

## Slide 9/58 - Real-world example: Scanner backlog to reviewable decisions

A regional financial services company has a growing AppSec backlog. The team already uses SAST and dependency scanners, but developers often push back on tickets because many findings are not clearly exploitable in the application's actual context.

The customer does not need a pitch about replacing its scanners. The better conversation is about the decision bottleneck:

- Which findings are real?
- Which are reachable?
- Which affect high-impact code paths?
- Which need more proof?
- Which can be suppressed with evidence?
- Which are ready for remediation?
- Who reviews and accepts the decision?

A Codex Security workflow may help by using repository context and existing scanner output to support validation, evidence packaging, and remediation guidance. The value is not "more findings", it is helping the customer move from raw signal to reviewable decisions.

## Slide 10/58 - Knowledge check

**Question:** A customer says, "We already have scanners. The issue is that AppSec spends days validating which findings are real, and engineering does not trust the tickets." Which response best explains Codex Security's role?

- The customer should focus on access to a cyber-specialized model before discussing repository scope or reviewer ownership.
- **Codex Security can help the team reason across repository context and scanner output to support validation, evidence generation, prioritization, and reviewable remediation while keeping human reviewers accountable.** ✓ Correct
- Codex Security replaces the customer's scanners by producing a more accurate list of vulnerabilities that engineering can use directly.
- Codex Security should be used to automatically patch all critical findings so the backlog does not keep growing.

*Explanation: This works because it positions Codex Security as a workflow-native layer for evidence-backed security decisions, not as a scanner replacement, automatic remediation system, or access-first conversation. Human security and engineering reviewers remain responsible for validation, severity, acceptance, and release decisions.*

## Slide 11/58 - Summary

Codex Security is strongest when positioned as part of the customer's defensive workflow. It helps turn repository context and security signal into evidence, validation, and reviewable next steps.

The core distinction to remember is simple: alerts create work, but evidence supports decisions. Codex Security can help improve decision quality, but human teams still own scope, severity, remediation acceptance, final approval, and systems-of-record updates.

## Slide 12/58 - Introduction (Module: Repository context and evidence boundaries)

Codex Security workflows depend on the right context and clear boundaries.

An evidence boundary defines what the workflow is allowed to inspect, test, and claim based on the approved scope and permitted activity. An evidence ceiling is the highest level of proof the workflow can honestly claim. For example, if runtime testing is not approved, the workflow can provide source-supported evidence and proof gaps, but it should not claim runtime proof.

The goal here is to identify what must be known before a Codex Security workflow is ready, and how to avoid overstating what the evidence proves.

## Slide 13/58 - Context for security reasoning

Security analysis needs context. A code snippet alone rarely tells the full story.

Repository context is the code, tests, dependencies, scanner outputs, architecture notes, and related materials Codex Security uses to reason about a codebase.

Useful repository context may include:

- In-scope repository, service, code slice, pull request, or specific change
- Authentication and authorization model
- Relevant logs
- API contracts
- Test coverage
- Architecture overview or service map
- Data flows and sensitive data locations
- Existing scanner outputs
- Trust boundaries
- Dependency information
- Known security policies or coding standards
- Deployment context
- Relevant tickets, prior review notes, or accepted risk records

Context does not mean unlimited access. It means the workflow has the right materials for the approved task.

**For example**

A security review of a pull request may need the changed files, related authorization helpers, relevant tests, and expected behavior. It does not automatically need access to every repository, production data, or unrelated internal systems.

## Slide 14/58 - Context, runtime, and observability

A useful operating-model lens is:

**Context** — What the workflow is allowed to know or use.

**Agentic runtime** — Where and how the workflow does work.

**Observability** — How the customer monitors, reviews, records, and improves the work.

For a Codex Security workflow, that might look like this:

**Context:** The approved repository, branch, scanner findings, architecture notes, test results, and relevant security policy.

**Agentic runtime:** For the Codex Security plugin, the workflow runs in a local Codex task against the authorized project. For Codex Security cloud, the research-preview workflow scans connected GitHub repositories through Codex cloud. Confirm the surface, repository scope, permitted actions, and approval boundaries before work begins.

**Observability:** The report, validation notes, reviewer decision, pull request discussion, CI output, ticket update, or system-of-record entry that shows what happened and what was decided.

These layers help partners ask better questions:

- What materials are in scope?
- Where will the workflow run?
- What actions are permitted?
- What evidence will be produced?
- Who reviews that evidence?
- Where will the decision be recorded?

When these answers are unclear, the workflow is not ready.

## Slide 15/58 - Authorization and scope before analysis

Before proposing or running a Codex Security workflow, confirm that the target is owned, authorized, and appropriate for defensive review.

At minimum, clarify:

- Approved repository, code slice, backlog slice, branch, commit, pull request, or environment.
- Security or engineering owner.
- Named human reviewer.
- Data-handling boundaries.
- In-scope and out-of-scope targets.
- Permitted runtime activity.
- Whether tests, local execution, dependency installation, network access, or runtime validation are allowed.
- Escalation path if scope or authorization is unclear.

> A customer may say, "Can you scan our customer portal?" That is not enough.

A better scoped statement is:

> "The approved scope is the customer-owned account-service repository, specifically the authentication and authorization modules on the staging branch. The AppSec lead owns the review, an engineering lead will review any proposed fixes, and production testing is out of scope."

That statement gives enough shape to begin choosing a workflow pattern.

## Slide 16/58 - Evidence levels and proof gaps

Not every security statement carries the same evidentiary weight.

Use these evidence levels when interpreting or communicating Codex Security outputs.

**Source fact** — Something directly visible in code, configuration, logs, test output, scanner output, or provided materials.

Example: "The pull request removes a role-checking helper from the account export route."

**Supported inference** — A reasonable conclusion drawn from available source facts.

Example: "Because the route previously called the role-checking helper and now does not, authorization behavior may have changed for this action."

**Runtime proof** — Evidence observed from approved runtime testing.

Example: "In the approved staging environment, a user without the export role successfully triggered the export endpoint."

Only use this label when runtime activity was explicitly authorized and observed.

**Unsupported claim** — A statement that goes beyond available evidence.

Example: "This issue allows any attacker to export all customer accounts" when no runtime test, access path, or data exposure proof has been established.

**Proof gap** — Something that remains unproven and needs more evidence or human review.

Example: "The review does not confirm whether upstream middleware still blocks this route at runtime."

This distinction protects credibility. It also helps customers understand what they can decide now and what still needs validation.

## Slide 17/58 - Candidate, validated, suppressed, and unresolved findings

Codex Security outputs should separate finding status clearly.

A **candidate finding** is a potential issue surfaced by analysis. It may be plausible, but it still needs review.

A **validated finding** has enough evidence for a human reviewer to treat it as real, relevant, and actionable within the approved scope.

A **false positive** is a finding the reviewer determines does not apply.

A **suppressed finding** may be technically detectable but is not relevant within the customer's context, often because of an existing control, unreachable path, or accepted exception.

An **unresolved proof gap** is not a confirmed issue or a false positive. It is a statement that more evidence is needed before the team can decide.

Avoid language that collapses these categories. For example, do not say "Codex Security found a vulnerability" when the output is still a candidate finding. Say:

> "Codex Security surfaced a candidate finding. The evidence suggests a possible authorization regression, but runtime behavior still needs approved validation before it can be treated as confirmed."

## Slide 18/58 - Real-world example: Evidence ceiling in a pull request review

A fintech engineering team asks for help reviewing a pull request that changes authorization logic in a customer-account service.

The approved scope is limited to:

- The pull request, including the changed files and related code
- Related authorization helper files
- Existing unit tests
- Security review notes from the AppSec team

The approved scope does not include:

- Production testing
- Live customer data
- Network requests
- Testing unrelated services
- Making code changes

A Codex Security review of the code changes can support the team by identifying source facts, supported inferences, and proof gaps.

For example, it may state:

- **Source fact:** The pull request removes a call to `requireExportRole()` from the account export route.
- **Supported inference:** Export authorization may now rely only on general session validation.
- **Proof gap:** The review does not confirm whether upstream middleware still enforces export-specific authorization at runtime.
- **Recommended next action:** AppSec should review the authorization design and approve a lower-level test if runtime validation is needed.

That output is useful because it respects the evidence ceiling. It does not claim runtime proof that was never observed.

## Slide 19/58 - Recommended exercise: Build a context and evidence boundary checklist

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Help you reinforce what must be known before a Codex Security workflow is treated as ready.

**Task:** Review the short sample request below for a security review of a repository change. Identify what context is present, what context is missing, what the evidence ceiling should be, and whether the work is ready to proceed.

Fictional customer excerpt:

> "Can you use Codex Security to review a pull request in our payment portal? The PR changes how refunds are approved. We can share the changed files in the pull request and a short architecture note. The AppSec manager asked for a quick review before tomorrow's release meeting. We do not yet know whether you can run the app locally, and production testing is not allowed. Engineering has not confirmed who will review proposed fixes."

**Estimated time:** 8–10 minutes

**Suggested output and reflection:** A brief "ready / not ready" note with missing context, required owner or reviewer, evidence boundary, and next action.

**Optional stretch:** Add one customer-safe clarification question that would move the request closer to ready.

## Slide 20/58 - Knowledge check

**Question:** A customer asks for a Codex Security review of a pull request that changes login behavior. The customer provides the diff and related files, but says no runtime testing is approved. Which statement is the safest evidence boundary?

- Codex Security can confirm whether the login change is exploitable because it can reason from the code.
- Codex Security should treat every authentication-related finding as validated because login changes are always high risk.
- Codex Security should automatically run the application locally to prove whether the login change is exploitable.
- **Codex Security can provide source-supported findings and supported inferences, but it should not claim runtime proof unless approved runtime testing is performed.** ✓ Correct

*Explanation: This works because it separates source facts and supported inferences from runtime proof. Without approved runtime testing, the workflow can support review, identify proof gaps, and recommend next validation steps, but it should not claim observed exploitability or confirmed runtime behavior.*

## Slide 21/58 - Summary

Good Codex Security work starts before analysis begins. The target, owner, reviewer, scope, permitted activity, data boundary, and evidence ceiling need to be clear enough to support a defensible review.

The most important habit is evidence calibration. Separate what is directly visible, what is reasonably inferred, what was observed through approved testing, and what remains unproven.

## Slide 22/58 - Introduction (Module: The Codex security assessment lifecycle)

Codex Security workflows follow a structured path from repository context to reviewable action. The lifecycle helps teams avoid jumping from "the tool found something" to "the issue is fixed."

Each step has a different purpose: understanding the system, discovering possible issues, validating evidence, explaining attack paths, packaging findings, supporting remediation, and revalidating the result.

## Slide 23/58 - The lifecycle at a glance

A practical Codex Security assessment lifecycle includes six connected stages:

1. Threat model
2. Finding discovery
3. Validation and attack-path analysis
4. Reporting as an evidence package
5. Reviewable remediation support
6. Revalidation and disposition

This lifecycle supports the broader defensive workflow: **Find → validate → test → remediate → prove**

All six stages sit under a shared umbrella: human review and evidence boundaries.

A workflow does not always move through every stage in one pass.

For example, the "Review code changes for security" workflow may focus on changed code and produce proof gaps rather than remediation.

The "Fix and verify findings" workflow may start after a finding is accepted or validated.

A report may lead to suppression, deferral, escalation, or more evidence instead of a patch.

The lifecycle is not a promise that Codex Security will discover, prove, and fix every issue.

It is a disciplined way to structure defensive security work.

Use this lifecycle view to see how Codex Security work moves from system context to evidence-backed review and, when appropriate, bounded remediation.

## Slide 24/58 - Threat modeling and finding discovery

Threat modeling helps establish what the system is, what assets matter, where entry points exist, and where trust boundaries or sensitive flows appear.

You do not need to perform the threat model yourself. You need to understand why the threat model helps AppSec and engineering focus the review on the parts of the system where security risk would matter most.

A useful threat model may clarify:

- What the application or service does.
- Which users, systems, or roles interact with it.
- Where untrusted inputs enter.
- Where authentication and authorization are enforced.
- Which data is sensitive.
- Which components or services trust each other.
- Which actions could create material risk if misused.
- Which assumptions need reviewer confirmation.

Codex Security can help build or review a threat model using repository context and related materials.

This gives finding discovery a stronger foundation.

Finding discovery then looks for security-relevant paths, missing controls, vulnerable patterns, risky dependencies, or weaknesses in areas such as:

- Authentication
- Authorization
- Input validation
- Data handling
- Secret handling
- Dependency risk
- Business logic
- Integration boundaries
- Configuration
- Error handling
- Access to sensitive operations

Threat modeling and finding discovery work together. The threat model helps the workflow focus on the parts of the system where security risk would matter most.

## Slide 25/58 - Validation and attack-path analysis

Validation tests whether a candidate finding is supported by evidence and relevant in the actual codebase context.

A candidate finding may be interesting, but validation asks:

- Is the issue real in this repository?
- Is the affected code reachable?
- Are the required preconditions plausible?
- Does an existing control mitigate the risk?
- Is the finding relevant to the customer's deployment context?
- Is the evidence strong enough for a human reviewer to act?

Attack-path analysis explains how a weakness could matter. It may identify where the issue starts, what conditions must be true, which security boundary may be affected, what evidence supports or weakens the concern, and what still needs review.

For example, a finding that untrusted input reaches a document parser is more useful when the output explains:

- Where the input enters
- Which validation is applied or missing
- Which internal worker receives the file
- What sensitive boundary may be crossed
- What assumptions still require confirmation

Validation helps teams separate real risk from noise, false positives, suppressed findings, and findings that need more proof.

## Slide 26/58 - Reporting as an evidence package

A Codex Security report should be treated as an evidence package, not as an automatic ticket queue.

A useful report should clarify:

**Scope** — What was reviewed? What was out of scope?

**Findings** — Which issues are candidates? Which are validated? Which were suppressed or marked not applicable?

**Evidence** — What source evidence, attack path, preconditions, or test output supports each finding?

**Gaps** — What remains unproven or needs further review?

**Next action** — What remediation, validation, reviewer decision, or escalation is recommended?

A report is valuable when it helps a human reviewer make a decision.

It should not bury the reviewer in generic observations or unsupported conclusions.

A strong finding summary might say:

> "Candidate authorization regression in account export route. Source evidence shows the route no longer calls the export-role helper. Related middleware still confirms session validity, but no source evidence confirms export-specific role enforcement. Recommended next action: AppSec review of expected authorization behavior and approved lower-level test before remediation is accepted."

That is more useful than:

> "Authorization vulnerability found. Fix immediately."

## Slide 27/58 - Revalidation mindset

Revalidation checks whether a proposed change addresses the finding and avoids regression.

Revalidation may rely on:

- Targeted tests
- CI output
- Code review
- Manual inspection
- Approved runtime validation
- Security reviewer sign-off
- Regression checks that confirm legitimate behavior still works

A workflow should end with a clear disposition, such as:

- Confirmed and fixed
- Confirmed but not yet fixed
- False positive
- Mitigated by existing controls
- Blocked by missing evidence
- Deferred
- Escalated

The disposition matters because it creates a decision record. It tells the customer what was decided, why, and what should happen next.

Avoid overstating fix status. "A patch was suggested" is not the same as "the issue is fixed." A finding is not closed until the customer's review, test, approval, and record process supports that conclusion.

## Slide 28/58 - Real-world example: Turning a threat model into attack-path evidence

A customer is reviewing a document-processing service. Users upload files through a public API. The files move into an internal worker that extracts text and stores metadata for downstream review.

The customer's concern is whether untrusted input can cross a trust boundary without expected validation.

A Codex Security workflow can help structure the review:

1. **Threat model:** Identify the public upload endpoint, internal worker, stored metadata, file parser, and trust boundary between public input and internal processing.
2. **Finding discovery:** Look for missing file-type checks, size limits, parser controls, or unsafe processing paths.
3. **Validation and attack-path analysis:** Determine whether the issue is supported by source evidence and whether existing controls mitigate the path.
4. **Evidence package:** Summarize source facts, supported inferences, proof gaps, and recommended next action.
5. **Reviewable remediation support:** If a finding is plausible or validated, suggest a bounded fix such as adding a validation control or test.
6. **Revalidation:** Confirm that the proposed change addresses the original concern and preserves legitimate file-processing behavior.

> The value is not that the workflow "finds and fixes everything." The value is that the team gets a structured, evidence-led path from security concern to reviewer decision. The takeaway for you is to ask whether untrusted input crosses an important boundary, what evidence supports that concern, and what remains unproven.

## Slide 29/58 - Knowledge check

**Question:** A customer has an approved repository review for a document-processing service. The team wants to understand whether untrusted file uploads can reach an internal parser without expected validation. Which sequence best represents a responsible Codex Security assessment lifecycle?

- Generate a patch, open a pull request, run production tests, close the ticket, and report that the vulnerability is fixed.
- **Build or review the threat model, discover candidate findings, validate evidence and attack paths, package findings for review, support bounded remediation if appropriate, and revalidate the result.** ✓ Correct
- Start with the "Fix and verify findings" workflow so Codex Security can propose remediation before the team spends time validating the finding.
- Scan the repository, count all findings, rank by severity, and assign every high-severity item directly to engineering.

*Explanation: This works because the lifecycle begins with system context and evidence, then moves toward reviewable action. Remediation support is appropriate only when the finding is plausible or validated enough to justify a bounded fix. The workflow should preserve human review and should not jump directly to production testing, automatic ticket closure, or patching before validation.*

## Slide 30/58 - Summary

The Codex Security lifecycle gives security and engineering teams a disciplined path from repository context to evidence-backed action.

Threat modeling helps define what matters. Finding discovery surfaces possible issues. Validation and attack-path analysis test whether the issue is supported. Reporting packages evidence for review. Remediation support stays bounded. Revalidation confirms what changed and what remains unresolved.

## Slide 31/58 - Introduction (Module: Choosing the right Codex security workflow pattern)

Different customer tasks call for different Codex Security workflow patterns. The safest pattern is usually the narrowest pattern that fits the work. A repository scan may be useful for a scoped assessment, but it is not the best answer for every pull request, backlog item, or accepted finding. The "Fix and verify findings" workflow may help after evidence exists, but it is not a substitute for validation.

The decision logic here focuses on four published Codex Security plugin workflows: run a security scan, run a deep security scan, review code changes for security, and fix and verify findings.

You'll use a five-question summary later to turn this technical workflow detail into a customer-safe handoff.

## Slide 32/58 - The pattern selection rule

You are not expected to configure these workflows. You are learning how to recognize which pattern best matches the customer's task so you can recommend a safe next step or hand off clearly.

Use this rule when choosing a Codex Security workflow: Choose the narrowest workflow pattern that matches the customer's target, timing, evidence need, and remediation readiness.

Ask four questions:

1. **What is the target?** Is the customer asking about a whole repository or service, a backlog slice, a specific pull request, or an already validated finding?
2. **What is the timing?** First assessment, high-risk review, pre-merge review, backlog triage, or post-validation remediation?
3. **What evidence is needed?** Candidate findings, validated findings, attack-path evidence, source-supported review, remediation guidance, or revalidation?
4. **Is remediation ready?** Is there enough evidence to prepare a bounded fix, or does the team need more validation first?

The answer usually points to one of four core review or remediation workflows taught here:

- Run a security scan
- Run a deep security scan.
- Review code changes for security.
- Fix and verify findings.

The plugin also publishes "Triage a backlog" for existing findings and "Export or track findings" for a controlled handoff after a completed scan.

## Slide 33/58 - Run a security scan

Use a Codex Security scan for a first review or routine assessment of an authorized repository or scoped folder.

This pattern is useful for:

- A first structured review of a bounded repository
- A focused assessment of a service or package
- A component or folder with a clear owner and security boundary
- A customer that wants to understand whether Codex Security can improve finding validation and prioritization
- A situation where breadth and practicality both matter

Expected outputs may include:

- Candidate findings
- Validated or partially validated findings, depending on available evidence and permitted activity
- Supporting evidence
- Prioritization guidance
- Attack-path notes
- Remediation direction
- Proof gaps
- Recommended reviewer decisions

A security scan is a good starting point when the customer has a clear scope and wants a practical first or routine review.

A customer-ready example could sound like:

> "The right first workflow may be to run a security scan of the approved account-service repository. The goal would be to assess scoped repository context, identify candidate findings, package evidence for AppSec review, and decide which findings are ready for validation or remediation."

## Slide 34/58 - Run a deep security scan

Run a deep security scan after a standard scan when the customer needs a slower, more thorough review of the same authorized repository or scoped folder.

It searches more comprehensively and uses more runtime and resources, so confirm reviewer capacity before proceeding.

This pattern is better suited to:

- Critical systems
- High-value repositories
- Sensitive services
- Complex codebases with material business risk
- Areas where missing security issues would carry significant impact
- Reviews where security stakeholders have explicitly agreed to deeper analysis and reviewer effort

A deep scan requires stronger readiness conditions:

- Clearer scope
- Named reviewers
- More time for review
- Better context materials
- Stronger expectations around review burden
- Clear data-handling boundaries
- Agreement on what "enough evidence" means

Deep scanning should not be used as a default answer to every customer request. It can produce more work for reviewers if the team has not defined what they will do with the output.

When discussing with a customer, it might sound like this:

> "A deep security scan may be appropriate after the initial scan because this service handles high-impact authorization decisions and the team wants a more comprehensive assessment. Before recommending it, we should confirm the exact service boundary, reviewer availability, evidence expectations, and what actions are permitted after findings are surfaced."

## Slide 35/58 - Review code changes for security

Use a security change review when the customer needs evidence about regressions introduced by one Git-backed change set, such as a pull request, branch range, commit, or working-tree change.

This pattern focuses on what changed and whether the change introduces or affects security risk.

| Review code changes for security when... | Expected outputs may include... |
|---|---|
| A pull request changes authentication, authorization, data handling, logging, dependencies, or security-sensitive configuration. | Change-specific findings. |
| Engineering wants pre-merge security review. | Source-supported evidence. |
| AppSec needs help understanding the security impact of a change. | Security impact notes. |
| The customer wants evidence tied to a specific code change, not a broad repository assessment. | Proof gaps. |
| The evidence ceiling is source-supported review unless approved runtime testing is included. | Suggested reviewer questions, merge guidance, and recommendations for further validation if needed. |

A security change review is often the narrowest and most responsible workflow for a security-sensitive pull request.

Frame it like this:

> "For this PR, reviewing code changes for security is a better fit than a full repository scan. The approved task is to review what changed, identify source-supported security concerns, and help the reviewer decide whether the change is ready to merge, needs more evidence, or should be revised."

## Slide 36/58 - Fix and verify findings

Use "Fix and verify findings" after a finding has been accepted for remediation or validated within the approved scope. It helps prepare a bounded patch, focused regression evidence, and review materials for human approval.

This pattern supports:

- A minimal patch
- Relevant test creation or updates
- CI verification where permitted
- Pull request preparation
- Reviewer handoff
- Revalidation of the original finding

The "Fix and verify findings" workflow is not the right starting point when the team has only a vague concern or unreviewed scanner output. First, the team needs enough evidence to justify action.

Fix support should stay bounded:

- Address the specific finding
- Preserve legitimate behavior
- Avoid broad refactors unless explicitly authorized
- Add or update relevant tests where appropriate
- Explain the security control being enforced
- Prepare outputs for human review

Do not describe "Fix and verify findings" as automatic remediation. The customer still owns patch acceptance, merge approval, release readiness, and closure.

Here's how you could explain it:

> "Because the AppSec reviewer has accepted the finding for remediation within the approved scope, the 'Fix and verify findings' workflow may be appropriate. The goal would be to prepare a minimal, reviewable patch and focused regression evidence for engineering review, not to automatically merge or close the issue."

## Slide 37/58 - Pattern comparison

Use this comparison when choosing the right pattern.

| Workflow pattern | Use when | What the customer gets | Main guardrail |
|---|---|---|---|
| Run a security scan | The customer wants a scoped review of a repository, service, package, module, or backlog slice | Candidate findings, supporting evidence, prioritization, remediation direction | Keep scope bounded and reviewer-led |
| Run a deep security scan | A standard scan is complete and the team wants a more comprehensive review of the same scope | More comprehensive search, richer coverage evidence, and greater review burden | Confirm reviewer capacity and material risk |
| Review code changes for security | The task is a PR, branch, commit, or working tree review | Change-specific findings, source-supported evidence, merge guidance | Do not claim runtime proof without approved testing |
| Fix and verify findings | A plausible or validated finding is ready for bounded remediation | Minimal patch support, tests, PR summary, revalidation question | Do not treat suggested fixes as accepted remediation |

A useful habit is to say the pattern and the reason together:

> "I recommend reviewing code changes for security because the customer's task is a pre-merge review of a specific authorization change, not a broad repository assessment."

## Slide 38/58 - Recommended exercise: Select the workflow pattern

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Help you practice choosing the narrowest Codex Security workflow that fits the customer's task.

**Task:** Review the four short customer requests below and choose "Run a security scan," "Run a deep security scan," "Review code changes for security," or "Fix and verify findings" for each. Add one sentence explaining why the selected workflow fits.

Fictional customer requests:

- "We want a first review of our customer-notification service. It is an owned repository, and our AppSec lead can review any findings next week."
- "We are about to merge a pull request that changes role checks for refund approval. We need security impact notes before the release review."
- "Our payment authorization service is high risk and complex. The security team is willing to spend extra review time because missing an issue would be material."
- "AppSec has validated a missing authorization check in a lower-level environment. Engineering wants a minimal patch and regression test for review."

**Estimated time:** 10 minutes

**Suggested output and reflection:** A four-row decision table with selected workflow, reason, required guardrail, and human review point.

**Optional stretch:** Add one phrase you would use to explain why a broader workflow is not needed.

## Slide 39/58 - Knowledge check

**Question:** A customer says, "We have a pull request that changes how admin permissions are checked. We need security review before merge. No production testing is allowed." Which Codex Security workflow pattern is the best fit?

- **Review code changes for security, because the task is a pre-merge review of a specific change and the evidence should stay tied to the diff and related files.** ✓ Correct
- Run a deep security scan, because admin permissions are high risk and should always receive maximum-depth analysis.
- Run a security scan, because every permission change should start with a full repository assessment.
- Fix and verify findings, because permission changes should be patched immediately before release.

*Explanation: This works because the customer's target is a pull request, the timing is pre-merge, and production testing is not approved. Reviewing code changes for security focuses on the changed code, source-supported evidence, proof gaps, and reviewer guidance. "Fix and verify findings" may become relevant only after a finding is accepted for remediation or validated within the approved scope.*

## Slide 40/58 - Summary

Pattern selection is a scope decision. Run a security scan for a first or routine review of an authorized repository or scoped folder. Run a deep security scan after a standard scan when the team needs a more comprehensive assessment and can accept longer runtime and greater review effort.

Review code changes for security when the task is a pull request, commit, branch range, or working-tree change. Use "Fix and verify findings" only after a finding is accepted for remediation or validated within the approved scope.

The safest recommendation is usually the narrowest workflow that fits the customer's task.

## Slide 41/58 - Introduction (Module: From finding to reviewable remediation)

A finding does not reduce risk by itself. Value appears when the customer can decide what the finding means, prepare a safe response, review the proposed change, and confirm whether the issue is addressed.

The focus here is the controlled path from plausible or validated finding to reviewable remediation. Codex Security can help prepare fix support, but the customer still owns remediation acceptance, release readiness, and closure.

## Slide 42/58 - Bounded fix support

A bounded fix is a targeted change that addresses the specific finding without broad refactoring, unrelated changes, or unapproved expansion of scope.

Codex Security can help propose or prepare remediation for findings that have enough evidence to justify action.

That evidence may come from:

- Source-supported analysis
- AppSec review
- Scanner output plus repository context
- Approved runtime validation
- A prior security report
- A customer-confirmed vulnerability or policy gap

Fix support should stay bounded.

A bounded fix should:

- Address the specific finding
- Preserve legitimate behavior
- Avoid broad refactors unless explicitly authorized
- Avoid changing unrelated files
- Add or update relevant tests where appropriate
- Explain the security control being enforced
- Identify remaining risk or proof gaps.
- Prepare the change for human review

A bounded fix should not become:

- A broad modernization project
- A rewrite of the affected service
- Automatic remediation across many repositories
- An unreviewed commit to a protected branch
- A ticket closure without reviewer acceptance

Use careful language:

> "Codex Security can help prepare a reviewable remediation path."

Avoid overclaiming:

> "Codex Security will fix the vulnerability."

## Slide 43/58 - Revalidation and disposition

After a proposed fix, the team should revalidate whether the original finding is addressed.

Revalidation asks:

- Does the patch address the root cause?
- Does the original attack path or risk path still exist?
- Do targeted tests pass?
- Does legitimate behavior still work?
- Are any assumptions still unproven?
- Is more review required before closure?

A good disposition clarifies whether the finding is:

- Confirmed and fixed
- Confirmed but not yet fixed
- False positive
- Mitigated by existing controls
- Blocked by missing evidence
- Deferred
- Escalated

The disposition should be precise.

Weak disposition:

> "Fixed by Codex."

Stronger disposition:

> "Engineering reviewed and accepted a minimal patch that restores role-specific authorization on the export endpoint. Targeted authorization tests pass in the approved lower-level environment. Production behavior was not tested. AppSec recorded the finding as confirmed and fixed within the approved scope."

That statement explains what changed, who decided, what was tested, and what was not proven.

## Slide 44/58 - Pull request review and human approval

Pull requests provide a structured handoff for security and engineering review.

Codex Security can support pull request preparation by summarizing:

- The finding being addressed.
- The evidence that justified remediation.
- The files changed.
- The security control being added or restored.
- The tests added or updated.
- The validation performed.
- Remaining risks or assumptions.
- What reviewers should pay attention to.

Human reviewers remain responsible for deciding severity, accepting or rejecting the patch, assessing engineering feasibility, confirming test sufficiency, approving release readiness, making the final merge decision, and updating the customer's system of record.

A good remediation handoff helps reviewers make a decision.

It does not ask them to trust the workflow blindly.

Customer-facing language sounds like this:

> "Codex Security can help prepare the patch summary, test evidence, and PR handoff. Your engineering and AppSec reviewers still decide whether the fix is correct, safe, and ready to merge."

## Slide 45/58 - What not to overstate

Remediation language is a common place where partners can accidentally overclaim.

Avoid these statements:

- "Codex Security fixed the vulnerability."
- "The issue is closed because a patch was generated."
- "The PR is safe to merge."
- "The finding is fully remediated across the enterprise."
- "This proves production is protected."
- "Codex Security can automatically fix all similar issues."
- "No further review is needed."

Use evidence-led statements instead:

- "Codex Security prepared a reviewable patch suggestion."
- "The patch addresses the specific finding within the approved scope."
- "Targeted tests were proposed or run where permitted."
- "Engineering and AppSec review are still required."
- "Runtime or production behavior remains unproven unless approved testing confirms it."
- "The customer should record the final disposition in its system of record."

The best language keeps the workflow useful and credible.

## Slide 46/58 - Recommended exercise: Draft a bounded remediation handoff

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Help you practice turning a validated finding into a safe, reviewable next step.

**Task:** Review the short finding summary below and draft a remediation handoff that includes the minimal patch request, expected test or CI verification, human reviewer step, and revalidation question. Focus on the handoff decision, not the code syntax. The important question is what needs to be reviewed, tested, accepted, and recorded.

Fictional finding summary:

> "AppSec validated that the refundApproval endpoint no longer checks whether the requester has the refund_manager role. Source review shows the old helper was removed during a refactor. In the approved staging environment, a user with standard support privileges could submit a refund approval request. The customer wants a fix prepared for engineering review. Engineering has approved changes only to the refund approval route and related authorization tests."

**Estimated time:** 8-12 minutes

**Suggested output or reflection:**

- A brief handoff note suitable for a security engineer or AppSec reviewer.
- Optional stretch: Add one sentence that prevents the customer from treating the suggested patch as automatically accepted remediation.

## Slide 47/58 - Knowledge check

**Question:** A Codex Security workflow proposes a patch for a validated authorization finding. The patch is not yet reviewed by engineering, and the related tests have not run. Which statement is the most accurate?

- The finding can be closed if the suggested patch appears to address the affected file and the security issue described in the finding. Additional testing is helpful, but it is not required before recording the finding as remediated.
- The finding can be treated as fixed because Codex Security generated a patch for a validated issue. The customer can still review the patch later, but the workflow has already completed the main remediation step.
- The patch should be merged as soon as possible because the finding has already been validated and delaying remediation may increase risk. Reviewers can use follow-up checks after merge to confirm whether any additional changes are needed.
- **Codex Security has prepared reviewable remediation support, but the customer still needs engineering review, test or CI verification, AppSec acceptance, and revalidation before calling the finding fixed.** ✓ Correct

*Explanation: This works because a suggested patch is not the same as accepted remediation. Codex Security can support bounded fix preparation, but the customer owns review, test sufficiency, acceptance, release readiness, and closure. Fix status should not be overstated when review or proof is incomplete.*

## Slide 48/58 - Summary

Remediation support should be bounded, reviewable, and evidence-led. Codex Security can help prepare a minimal patch, test guidance, PR summary, and revalidation question.

The customer's security and engineering teams still decide whether the fix is correct, safe, accepted, merged, released, and recorded. A finding is not fixed because a patch exists. It is fixed when the customer's review and evidence support that disposition.

## Slide 49/58 - Introduction (Module: Customer-safe workflow summary and handoff)

Partners often need to summarize a Codex Security workflow for a customer, AppSec reviewer, engineering lead, or technical pre-sales colleague.

A strong handoff does not oversell. It explains the approved scope, selected workflow pattern, accountable reviewers, evidence ceiling, and next step. It also makes clear when the workflow is not ready or when escalation is needed.

## Slide 50/58 - Explain the selected workflow without overclaiming

Codex Security can help authorized security and engineering teams analyze scoped code, validate findings, generate evidence, and prepare reviewable remediation support.

That is strong enough. Do not add claims that the workflow cannot support.

Avoid saying Codex Security:

- Replaces scanners or security teams.
- Guarantees vulnerability discovery.
- Fully automates remediation.
- Removes the need for human review.
- Automatically merges, ships, or closes tickets.
- Provides cyber-specialized model access by default.
- Proves runtime behavior without approved runtime testing.
- Can be applied to production or third-party systems without explicit authorization.

Use workflow-first, evidence-oriented language. Customer-ready framing sounds like this:

> "For the approved repository slice, Codex Security can run a security scan to identify candidate findings, package source-supported evidence, and help AppSec decide which items need validation, suppression, remediation, or escalation. The customer's AppSec and engineering reviewers remain accountable for severity decisions, fix acceptance, and final approval."

## Slide 51/58 - Know when the workflow summary is not ready

A workflow summary is not ready when core facts are missing.

Pause or clarify when any of these are unclear:

- Target asset
- Approved scope
- Customer ownership
- Approved environment
- Security or engineering owner
- Named human reviewer
- Data-handling boundary
- Permitted runtime activity
- Evidence ceiling
- Workflow pattern fit
- Stop condition
- Escalation path

Seek support or hand off when the customer asks for:

- Broad automation
- Production testing
- Live-target testing
- Third-party target testing
- Exploit-heavy work
- Special model access
- Special data-handling terms
- Pricing, provisioning, or availability commitments
- Custom harness or integration design beyond the agreed workflow
- Commitments the partner cannot approve

Do not fill missing facts with assumptions. A strong partner names the gap and recommends the next safe action.

## Slide 52/58 - Partner-ready workflow summary

An effective workflow summary answers five questions.

**1. What are we reviewing?** State the target asset and approved scope.

Example: "The approved scope is the customer-owned account-service repository, focused on the authorization module and the current scanner backlog slice."

**2. Which workflow fits?** Name the selected Codex Security workflow pattern and expected output.

Example: "Running a security scan fits because the customer wants a first structured assessment of a bounded repository slice."

**3. Who is accountable?** Name the owner, reviewer, and human decision points.

Example: "The AppSec lead reviews findings and severity. The engineering lead reviews any proposed remediation."

**4. What can we prove?** State the evidence ceiling and limits on claims.

Example: "The workflow can produce source-supported evidence and proof gaps. It should not claim runtime proof because runtime testing is not approved."

**5. What happens next?** State the next action.

Example: "Next, confirm the reviewer, run the scoped workflow, review the evidence package, and decide whether any findings need validation, suppression, remediation, or escalation."

## Slide 53/58 - Real-world example: Fix and verify findings is not automatic remediation

A customer asks:

> "Can Codex Security automatically fix all critical findings, merge the PRs, and close the tickets?"

A weak response would be:

> "Yes, it can automate remediation across the backlog."

A safer response is:

> "Let's first separate accepted or validated findings from candidate findings. For findings that AppSec has accepted for remediation within an approved scope, Codex Security may be able to use the 'Fix and verify findings' workflow to prepare a minimal, reviewable patch and focused regression evidence. Your engineering and AppSec reviewers would still approve changes, merge decisions, release readiness, and ticket closure. For unvalidated findings, we should start with validation and evidence before remediation."

This response does four things well:

- Narrows the scope
- Separates candidate from validated findings
- Selects the workflow based on evidence readiness
- Preserves human review and approval

## Slide 54/58 - Recommended exercise: Draft a safe workflow handoff

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Help you practice turning a customer ask into a concise workflow summary.

**Task:** Review the short customer request below and complete the five-part workflow summary.

Fictional customer request:

> "Our AppSec team has 300 scanner findings for the customer portal. Leadership wants to know whether Codex Security can scan everything, fix the critical items, and update the tickets by the end of the month. We can start with the account-service repository, but engineering has not confirmed who will review fixes. Production testing is not approved. The AppSec lead can review evidence for a small backlog slice next week."

**Estimated time:** 8-10 minutes

**Suggested output and reflection:**

- A brief handoff note suitable for a security engineer, AppSec reviewer, or technical pre-sales partner.
- Optional stretch: Add one sentence that explains why "scan everything and fix all criticals" is not the right first workflow.

## Slide 55/58 - Knowledge check

**Question:** A customer says, "We want Codex Security to fix all critical findings from our scanner backlog, merge the pull requests, and close the tickets automatically." Which response is the safest partner-ready handoff?

- The customer needs cyber-specialized model access before Codex Security can safely handle critical findings.
- Codex Security should start with a deep security scan across all repositories, then the team can prioritize the most serious issues.
- **We should define scope, separate candidate from accepted or validated findings, name reviewers, and use "Fix and verify findings" only for bounded, human-reviewed remediation support.** ✓ Correct
- Codex Security can run the full flow if the customer grants repository and ticketing access, with the team reviewing results afterward.

*Explanation: This works because it avoids unsupported claims about broad automation, automatic merging, ticket closure, and special access. It starts with scope, evidence, reviewer accountability, and the right workflow pattern. "Fix and verify findings" is appropriate only after a finding is accepted for remediation or validated within the approved scope.*

## Slide 56/58 - Summary

A partner-ready workflow summary should be specific, bounded, and safe. Name what is being reviewed, which pattern fits, who is accountable, what evidence can be claimed, and what happens next.

When scope, authorization, reviewer ownership, evidence ceiling, or access path is unclear, pause and clarify before recommending execution or remediation.

## Slide 57/58 - Recap

Codex Security is the Daybreak workflow layer that helps authorized teams turn repository context and security signal into reviewable decisions.

The central takeaway: start with the authorized workflow, move from threat model to revalidation, choose the narrowest fitting pattern, and keep human reviewers accountable for severity, remediation, release, and records.

## Slide 58/58 - Congratulations

Congratulations, you've completed this course!

In customer conversations, keep Codex Security recommendations bounded, evidence-led, and human-reviewed. Clarify the target, approved scope, reviewer, workflow pattern, evidence ceiling, proof gap, and next step.

If a core fact is unclear, pause and bring in technical or AppSec support before recommending execution or remediation.

**Course completed.**

Next up in OpenAI Cyber Deployment Practitioner: **Bounded evaluation and pilot design** (Course, 1 hr 8 min) — "Unlock the power of evidence-led security evaluations with a practical, step-by-step approach to piloting Daybreak and Codex..."
