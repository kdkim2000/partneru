# Cyber Opportunity Qualification and Personas

## Slide 1/53 - Title

Cyber Opportunity Qualification and Personas

Created July 2026

## Slide 2/53 - Introduction

Cybersecurity conversations often begin with broad interest in AI, faster vulnerability discovery, or model capability. Those signals matter, but they are not yet qualified opportunities.

A qualified cyber opportunity connects that interest to a real defensive workflow, a known stakeholder, a current security input, a workflow bottleneck, and a proof point that would show improvement.

In this course, you'll practice turning vague cyber interest into a structured view of the customer's situation, so Daybreak and Codex Security conversations stay grounded in authorized defensive workflows, evidence, and human review.

## Slide 3/53 - What you'll learn

By the end of this course, you'll be able to:

- Identify cyber-fit opportunities using a workflow-first qualification lens.
- Identify CISO, AppSec, DevSecOps, security engineering, and engineering leadership stakeholders and their priorities and evidence needs.
- Identify current security inputs, tools, systems of record, and handoffs.
- Use the find → validate → test → remediate → prove workflow to locate bottlenecks.
- Define proof points that show whether a defensive cyber workflow has improved.
- Recognize red team, security research, exploit-heavy, offensive testing, or unclear-authorization contexts that require careful routing or escalation.

Let's get started!

## Slide 4/53 - Introduction (Module: What makes a cyber-fit opportunity)

A strong cyber opportunity is not defined by how excited the customer is about AI, but by whether the customer has a real defensive workflow that can be improved responsibly.

In early discovery, your job is to move from broad interest to qualification evidence. That means listening for where security work begins, where it slows down, who owns the decision, and what proof would make improvement visible.

## Slide 5/53 - What cyber-fit means (Module: What makes a cyber-fit opportunity)

A cyber-fit opportunity is a customer problem where an approved defender needs to improve a bounded defensive security workflow.

Approved defender means the work is being performed by, or for, a customer team that has permission to protect systems, applications, repositories, accounts, networks, or data that it owns, operates, or is explicitly authorized to test or analyze.

Bounded workflow means the work is specific enough to qualify. It may involve one repository, one application, one backlog slice, one vulnerability class, one pull request pattern, one lower-level environment, or one security review process.

A strong cyber-fit opportunity is usually connected to a concrete customer reality, such as:

- A noisy vulnerability backlog.
- A repository that needs secure review.
- SAST or SCA findings that are hard to validate.
- Security tickets that engineering teams do not trust.
- Evidence that is difficult to prepare for audit or governance review.
- A recurring handoff problem between AppSec and engineering.

By contrast, "we want AI for security" is not yet a qualified opportunity. It may be an opening signal, but it does not tell you what workflow needs help, which assets are in scope, who owns the decision, or what evidence would prove value.

A workflow-first qualification question sounds like this:

> "What defensive security workflow are you trying to improve first?"

That question anchors the rest of discovery in the customer's operating reality and gives you the evidence needed for a later routing decision.

## Slide 6/53 - The three diagnostic questions (Module: What makes a cyber-fit opportunity)

Use these diagnostic questions throughout cyber discovery:

1. Where does security signal come from?
2. Where does the workflow slow down?
3. What proof would show improvement?

Security signal is any input that prompts security review. It may come from scanner findings, code changes, bug reports, audit findings, dependency alerts, incident learnings, threat-modeling outputs, or manual code review.

The first question helps you identify the source of the work. For example, a customer may receive security signal from SAST scans, dependency scanning, bug bounty submissions, pull request review, or cloud configuration checks.

The second question helps you locate the bottleneck. The customer may not struggle with finding issues. They may struggle with validating whether the issue is real, prioritizing it, handing it to engineering, testing the fix, or producing evidence that the issue was reviewed.

The third question helps you identify what would make the opportunity worth pursuing. A proof point could be faster validation, fewer false positives, better evidence, accepted remediation, clearer developer handoff, or stronger audit readiness.

These questions are discovery prompts, not a rigid script. Use them to guide the conversation toward a qualification hypothesis.

A qualification hypothesis is a short statement of what the customer problem appears to be and what evidence would confirm that the opportunity is real.

For example:

> "The customer appears to have a validation bottleneck in its AppSec backlog. Findings come from SAST and dependency scanning, but AppSec spends too much time confirming which findings are real before engineering will act. A useful proof point would be faster validation and fewer rejected tickets for one bounded backlog slice."

## Slide 7/53 - Strong fit, needs clarification, or escalation (Module: What makes a cyber-fit opportunity)

During discovery, classify the opportunity into one of three categories.

**Strong fit**

A strong-fit opportunity has enough evidence to qualify further. The customer has an authorized defensive workflow, the affected asset or backlog is bounded, the stakeholder or owner is named, the bottleneck is visible, and the customer can describe what evidence would show improvement.

Example:

> "Our AppSec team has a backlog of SAST findings in one customer portal repository. Most delays happen during validation because engineering rejects tickets without clear evidence. The AppSec lead can review the outputs, and success would mean fewer disputed findings and faster reviewed fixes."

This is a strong fit because it names the workflow, signal source, bottleneck, owner, and proof point.

**Needs clarification**

Some opportunities show potential, but the qualification evidence is incomplete. The customer may have interest, but no clear asset, owner, signal source, bottleneck, or proof point.

Example:

> "We want to use AI for security, but we have not decided where to start."

This needs clarification. The next step is not to recommend a product path. The next step is to ask what security workflow the customer wants to improve first.

**Escalation or careful routing**

Some conversations involve sensitive cyber contexts. These may include offensive testing, exploit-heavy work, live-target activity, malware, unclear authorization, critical infrastructure, production testing, special model access, or special data-handling terms.

These requests are not always invalid, but they require careful handling. Do not continue into advanced capability claims. Clarify the authorized defensive workflow, confirm ownership and review, and involve the appropriate OpenAI or technical SME before progressing.

## Slide 8/53 - Real-world example: Broad AI-for-security interest becomes a workflow hypothesis (Module: What makes a cyber-fit opportunity)

A customer says:

> "We want to use AI for security, but we are not sure where to begin."

That statement alone is too broad to qualify. A partner should not immediately position Daybreak, discuss cyber-specialized access, or propose scanning everything.

Instead, the partner asks:

> "Where does security signal come from today?"

The customer explains that most findings come from SAST and dependency scans.

The partner asks:

> "Where does the workflow slow down?"

The customer explains that the AppSec team spends days validating which findings are real before sending them to engineering.

The partner asks:

> "What evidence would show the process improved?"

The customer says they would want fewer disputed findings, clearer evidence in tickets, and faster decisions on which issues need remediation.

The opportunity becomes more concrete. It is no longer a generic AI-for-security request. It is a validation and prioritization bottleneck in an existing defensive workflow.

A strong qualification hypothesis might be:

> "The customer has a validation bottleneck in its AppSec workflow. Security signal comes from SAST and dependency scanning, but AppSec spends too much time determining which findings are real before engineering will act. A bounded next step would focus on one owned repository or backlog slice, with proof based on evidence usefulness, reduced dispute rate, and faster reviewed decisions."

## Slide 9/53 - Recommended exercise: Build a cyber-fit snapshot (Module: What makes a cyber-fit opportunity)

This is an optional practice activity to help you apply what you just learned.

**Purpose**

Practice turning broad customer interest into a clear cyber-fit qualification view.

**Suggested learner task:**

Review the fictional customer note below. Answer the three diagnostic questions, then classify the opportunity as strong fit, needs clarification, or requires escalation.

**Fictional customer note:**

> "We're interested in using AI for security. Our AppSec team has a growing backlog of scanner findings from SAST and dependency scans, but it is not clear which findings are real or worth sending to engineering. Some tickets get rejected because they lack enough evidence, and ownership is unclear once a finding moves from security review to remediation. The customer also asks whether a more advanced cyber model would help clear the backlog faster."

Use the three diagnostic questions:

- Where does security signal come from?
- Where does the workflow slow down?
- What proof would show improvement?

**Estimated time**

10-12 minutes

**Suggested output and reflection**

A short cyber-fit snapshot with signal source, bottleneck, proof point, fit classification, and one next discovery question.

**Optional stretch**

Add one safe phrase that redirects the model-access question back to the customer's defensive workflow.

## Slide 10/53 - Knowledge check (Module: What makes a cyber-fit opportunity)

**Question:** A customer says, "We want to use AI for security. We have a lot of scanner findings, but we have not chosen a repository, named a reviewer, or defined what success would look like." Which response best classifies the opportunity?

- This is a strong fit because the customer has a clear security problem and enough scanner findings to justify a Daybreak conversation.
- This should be escalated immediately because any mention of scanner findings requires OpenAI SME review before discovery can continue.
- This is ready for a Codex Security evaluation because scanner findings are already available and the customer has expressed interest.
- **This needs clarification because there is potential workflow pressure, but the asset, reviewer, bottleneck, and proof point are not yet clear.** ✓ Correct

*Explanation: This works because the customer has a possible signal source, but not enough qualification evidence yet. You should clarify the defensive workflow, bounded scope, owner, reviewer, and proof point before recommending a next step.*

## Slide 11/53 - Summary (Module: What makes a cyber-fit opportunity)

A cyber-fit opportunity becomes visible when broad interest turns into a workflow hypothesis. The strongest early signal is not "the customer wants AI." It is evidence that an approved defender has a specific defensive workflow that is slowing down, and that the customer can describe what improvement would look like.

Use the three diagnostic questions to produce a qualification hypothesis and record the facts the next routing decision will need: the workflow, bounded scope, owner, reviewer, proof point, sensitivity or escalation flags, and open questions.

## Slide 12/53 - Introduction (Module: Identify personas and stakeholder priorities)

Cyber qualification is persona-sensitive. The same workflow can look different depending on who is describing it.

A CISO, or Chief Information Security Officer, may talk about exposure and governance.

An AppSec lead may talk about false positives and exploitability.

An engineering leader may talk about release risk and developer burden.

Strong qualification connects these views without confusing them.

## Slide 13/53 - Core cyber stakeholders and decision lenses (Module: Identify personas and stakeholder priorities)

Personas are not just job titles. They represent decision lenses, success measures, and review responsibilities. In Cyber / Daybreak conversations, you should be ready to identify the following stakeholders.

**CISO or security leadership**

CISOs and security leaders focus on risk reduction, exposure, governance, auditability, executive confidence, and controlled use of advanced AI capability.

They may ask:

- "Which material risks were reduced?"
- "How do we know the workflow is governed?"
- "Can we produce evidence for audit or board-level reporting?"
- "How do we avoid creating uncontrolled security automation?"

Their evidence requirement is usually decision-grade proof. They do not need every technical detail, but they do need confidence that the workflow is authorized, monitored, reviewed, and tied to risk reduction.

**AppSec**

AppSec teams focus on finding validity, false positives, exploitability, severity, attack-path context, and evidence for reviewer decisions.

They may ask:

- "Which findings are real?"
- "Which issues are reachable or exploitable in our environment?"
- "Can we reduce the time spent triaging false positives?"
- "Can the evidence help us decide what engineering should fix?"

Their evidence requirement is practical and technical. They need enough context to accept, reject, suppress, or escalate findings.

**DevSecOps**

DevSecOps teams focus on scalable SDLC automation, PR-time checks, CI/CD integration, developer-ready remediation, and lower-friction handoffs.

They may ask:

- "Can this fit into our existing SDLC?"
- "Can we support review earlier in the development process?"
- "Can we reduce security friction without slowing delivery?"
- "How would outputs connect to PR checks, tickets, or pipeline gates?"

Their evidence requirement is workflow compatibility. They need to understand where the work would run, how outputs would be reviewed, and how it would connect to existing systems.

**Security engineering**

Security engineering teams focus on tooling, harnesses, integrations, telemetry, systems of record, permissions, and operational control.

They may ask:

- "What tools and systems are involved?"
- "Where are logs, findings, and decisions recorded?"
- "What permissions are required?"
- "How will we monitor usage and outputs?"

Their evidence requirement is operational. They want to know whether the workflow can be controlled, audited, and integrated responsibly.

**Engineering leadership**

Engineering leaders focus on developer productivity, release velocity, patch quality, change risk, sprint impact, and remediation ownership.

They may ask:

- "Will this create more work for engineering?"
- "Are the tickets actionable?"
- "Does the patch preserve intended behavior?"
- "Can we review fixes without increasing release risk?"

Their evidence requirement is delivery-focused. They need confidence that security outputs are useful, reviewable, and aligned with engineering workflows.

## Slide 14/53 - Listen for persona-specific signals (Module: Identify personas and stakeholder priorities)

In cyber discovery, a persona is not just a job title. It is a way of framing the same workflow through a specific responsibility, decision, or risk.

Customers often reveal that lens through the language they use.

Listen for what they emphasize:

- Executive risk
- Finding quality
- Workflow integration
- Operational control
- Engineering impact

Those cues help you adapt the conversation without changing the underlying workflow.

When you hear language about board risk, exposure, audit, control, or executive confidence, you may be hearing a CISO or security leadership lens.

When you hear language about false positives, exploitability, severity, attack paths, or validation evidence, you may be hearing an AppSec lens.

When you hear language about CI/CD, PR checks, automation, or developer handoff, you may be hearing a DevSecOps lens.

When you hear language about tooling, logs, permissions, systems of record, or operational control, you may be hearing a security engineering lens.

When you hear language about release risk, developer burden, backlog pressure, or delivery velocity, you may be hearing an engineering leadership lens.

These signals help you adapt the conversation. They also help you avoid giving the wrong message to the wrong stakeholder.

For example:

A CISO does not usually need a feature-by-feature walkthrough of repository scanning. They need to understand risk reduction, governance, evidence, and controlled use.

An engineering leader does not usually need an executive governance speech. They need to understand whether outputs will be actionable, whether remediation will be reviewed, and whether release risk will be managed.

Strong qualification usually requires more than one persona. A cyber workflow problem often spans leadership, security operators, and engineering teams. If only one stakeholder is present, identify who else must be involved before the opportunity can progress.

Diagram: "Same workflow" at the center connects to five stakeholder nodes: CISO / security leadership (risk and evidence), Security engineering (operational control), AppSec (finding validity), Engineering leadership (reviewable remediation), and DevSecOps (workflow fit).

## Slide 15/53 - Persona alignment pitfalls (Module: Identify personas and stakeholder priorities)

Persona-aware discovery helps you avoid common qualification mistakes.

**Pitfall: Treating CISO interest as proof that the workflow is ready**

CISO urgency matters, but it does not automatically identify the workflow owner, signal source, reviewer, or proof point. If a CISO says exposure needs to be reduced before an audit, you still need to understand where the work happens and who will review evidence.

A better move is to connect the executive concern to the operator workflow:

> "To qualify this responsibly, we should identify where the current security signal comes from, which team validates it, and what evidence would show progress against the exposure concern."

**Pitfall: Discussing Codex Security workflow potential without confirming who reviews findings**

Codex Security may support analysis and remediation workflows, but human security and engineering teams remain accountable for review and decisions. If the customer has not named who will review findings or accept remediation, the opportunity is not ready for a strong next step.

A better move is to ask:

> "Who would evaluate whether the findings are valid and decide whether a proposed remediation is acceptable?"

**Pitfall: Assuming AppSec pain will translate into engineering adoption**

AppSec may want faster validation, but engineering teams must still trust the output and accept the work. If engineering leaders are not involved, tickets may continue to be rejected or delayed.

A better move is to ask:

> "What does engineering need to see before a security ticket is considered actionable?"

**Pitfall: Treating integration interest as a complete opportunity**

A DevSecOps team may ask about CI/CD integration, PR-time checks, or automation. That can be a strong signal, but it is not a complete opportunity until proof points and review responsibilities are defined.

A better move is to ask:

> "What decision should the first workflow help reviewers make, and where should that decision be recorded?"

## Slide 16/53 - Real-world example: CISO urgency but AppSec owns the bottleneck (Module: Identify personas and stakeholder priorities)

A CISO is concerned about reducing exposure before the next audit cycle. The executive concern is real, but it does not identify where the workflow is blocked.

During discovery, the partner learns that the AppSec team receives too many findings from scanners and spends significant time validating which ones are real.

Engineering teams often reject tickets because they lack reproduction notes, affected code context, or practical remediation guidance.

The partner keeps the executive risk concern in view while qualifying the operator workflow.

A weak response would be:

> "Daybreak can help reduce exposure across your security program."

That is too broad for qualification.

A stronger response would be:

> "It sounds like the exposure concern is connected to a validation and evidence bottleneck in the AppSec workflow. To qualify this, we should identify which findings enter the backlog, how AppSec validates them, who engineering trusts as the reviewer, and what evidence would show faster progress before the audit."

This response respects the CISO's concern while grounding the opportunity in the workflow that must improve.

## Slide 17/53 - Recommended exercise: Connect personas to proof requirements (Module: Identify personas and stakeholder priorities)

This is an optional practice activity to help you apply what you just learned.

**Purpose**

Practice connecting cyber stakeholders to priorities, workflow concerns, proof requirements, and discovery questions.

**Suggested learner task:**

Review the fictional stakeholder notes below. For each stakeholder, identify the likely priority, the workflow concern, the proof they would care about, and one follow-up question.

**Fictional stakeholder notes:**

CISO / security leadership:

> "We have board-level pressure to show that exposure is going down, not just that we are finding more issues. I need confidence that any AI-assisted workflow is governed, auditable, and tied to risk reduction."

AppSec lead:

> "Our scanners generate plenty of findings, but too many require manual validation before we can decide what is real. We need better evidence on exploitability, reachability, severity, and false positives before we send work to engineering."

DevSecOps manager:

> "If this stays outside our SDLC, it will become another side process. I need to understand where it would fit into pull requests, CI/CD, ticketing, and security review without creating extra friction for developers."

Engineering leader:

> "My teams already have a full sprint backlog. Security tickets need to be specific, reviewable, and safe to act on. I need to know whether a proposed fix preserves intended behavior and whether the work is worth interrupting planned delivery."

**Estimated time**

10-12 minutes

**Suggested output and reflection:**

A short statement identifying each stakeholder's priority, workflow concern, proof requirement, and next question.

**Optional stretch**

Identify which stakeholder is the economic buyer, which is the workflow owner, and which is the reviewer.

## Slide 18/53 - Knowledge check (Module: Identify personas and stakeholder priorities)

**Question:** A stakeholder says, "Our board wants to know whether material exposure is going down, and I need confidence that any AI-assisted security workflow is controlled and auditable." Which persona lens is most likely represented?

- AppSec, because the stakeholder is asking about exploitability and finding validity.
- **CISO or security leadership, because the stakeholder is focused on exposure, governance, and executive confidence.** ✓ Correct
- Engineering leadership, because the stakeholder is focused on release velocity and patch quality.
- DevSecOps, because the stakeholder is asking about CI/CD integration and PR-time checks.

*Explanation: This works because the stakeholder's language centers on exposure, control, auditability, and board-level confidence. Those are typically CISO or security leadership concerns. You should connect the executive concern to the operator workflow before recommending a next step.*

## Slide 19/53 - Summary (Module: Identify personas and stakeholder priorities)

Persona-aware qualification keeps the conversation relevant. The same workflow may need to satisfy several stakeholder lenses: leadership needs confidence, AppSec needs usable evidence, and engineering needs reviewable work that does not create unnecessary delivery risk.

Before positioning a next step, confirm who owns the workflow, who reviews outputs, who accepts remediation, and what each stakeholder needs to see.

## Slide 20/53 - Introduction (Module: Map current security inputs and systems)

Customers do not enter Daybreak conversations from a blank slate. They already have scanners, repositories, tickets, dashboards, communication channels, and governance processes. Qualification gets stronger when you understand that current environment before proposing a next step.

A good current-state map shows where security signal enters the workflow, where decisions are recorded, and where work actually happens.

## Slide 21/53 - What produces security signal today (Module: Map current security inputs and systems)

Security inputs are the sources that create findings, alerts, reviews, or security work.

Common security input sources include:

- SAST, which scans source code for potential weaknesses.
- DAST, which tests running applications for insecure behavior.
- SCA, which identifies vulnerabilities in dependencies and open-source components.
- Secrets scanning, which identifies exposed credentials or tokens.
- Container scanning, cloud configuration checks, or infrastructure-as-code checks.
- Dependency alerts.
- Pull request or diff reviews.
- Threat modeling outputs.
- Bug bounty reports.
- Audit findings.
- Incident learnings.

The qualification question is not simply, "Do you have enough security signal?" Many security teams already have more signal than they can process.

The better question is:

> "Can the customer turn security signal into validated, prioritized, reviewable action?"

More inputs can make the problem worse if the customer cannot validate findings, assign ownership, remediate safely, and document decisions.

A large backlog may indicate a scanning problem, but it may also indicate validation latency, unclear ownership, poor developer handoff, or weak evidence capture.

Some inputs need extra care.

Penetration testing outputs, red-team findings, exploit-heavy reports, malware-related findings, production activity, or externally scoped targets may require careful routing depending on authorization and intended use.

## Slide 22/53 - Identify where the security workflow is managed (Module: Map current security inputs and systems)

Once you know where security signal comes from, identify where the customer manages the work. Look for the tools and systems that hold ownership, evidence, status, and decisions.

Common workflow systems include:

- Code repositories such as GitHub, GitLab, or Bitbucket.
- Work tracking systems such as Jira, Azure DevOps, or ServiceNow.
- Security tools such as SAST, DAST, SCA, SIEM, SOAR, GRC, or vulnerability management platforms.
- Communication and evidence locations such as Slack, Teams, documents, dashboards, or audit repositories.

Two terms are especially useful in discovery: system of record and execution surface.

A system of record is where the customer tracks ownership, status, evidence, or decisions. For example, Jira may track remediation ownership, while a GRC platform may hold audit evidence.

An execution surface is where work gets investigated, changed, tested, or reviewed. For example, a repository, pull request, local development environment, test environment, or security review tool may be an execution surface.

This distinction matters because Daybreak qualification should preserve the customer's governance and systems of record. You should not imply that the customer needs to abandon existing tools or create a parallel security process. The goal is to understand the current workflow well enough to recommend a safe first step later.

## Slide 23/53 - Identify a safe first step (Module: Map current security inputs and systems)

A safe first step is a specific, authorized slice of work that is small enough to evaluate responsibly.

Examples include:

- One owned repository
- One business-critical application
- One backlog slice
- One vulnerability class
- One PR or diff pattern
- One approved lower-level environment

A safe first step is not "scan all our code" or "automate security across production."

Those requests are too broad and may introduce governance, authorization, data-handling, or review risks.

Before recommending any next step, confirm four conditions.

First, confirm ownership. The customer should own, operate, or be explicitly authorized to inspect the asset or environment.

Second, confirm authorization. The security and engineering stakeholders should approve the activity for a defined defensive purpose.

Third, confirm reviewer responsibility. A named human reviewer should evaluate findings, evidence, or proposed remediation.

Fourth, confirm evidence expectations. The customer should know where evidence needs to be captured and what would show improvement.

A bounded first step helps the customer move from interest to impact without overextending the workflow before it has been proven.

## Slide 24/53 - Real-world example: Scanner findings spread across too many tools (Module: Map current security inputs and systems)

A customer's security findings come from SAST, dependency scanning, and cloud configuration tools. Remediation work is tracked in Jira. Audit evidence is stored in a GRC platform.

AppSec says findings are hard to validate. Engineering says tickets lack enough context. Leadership says reporting is too manual.

The partner keeps the executive risk concern in view while qualifying the operator workflow.

A weak qualification response would be:

> "Daybreak can help automate your security workflow."

That statement is too broad and skips the current-state map.

A stronger qualification response would be:

> "Before we recommend a next step, let's map where the findings originate, where decisions are recorded, where engineering reviews work, and where evidence needs to land. Then we can identify one bounded asset or backlog slice where improvement can be evaluated responsibly."

The partner qualifies the opportunity by mapping the workflow environment:

- Security signal comes from SAST, dependency scanning, and cloud configuration tools.
- Remediation ownership is tracked in Jira.
- Governance evidence is stored in the GRC platform.
- The bottleneck appears to involve validation, developer handoff, and evidence capture.

A safe first step may be one owned repository or one backlog slice with a named AppSec reviewer.

## Slide 25/53 - Recommended exercise: Inventory security inputs and systems (Module: Map current security inputs and systems)

This is an optional practice activity to help you apply what you just learned.

**Purpose**

Practice identifying a customer's current security workflow environment before proposing a solution path.

**Suggested learner task:**

Review the fictional stakeholder notes below. For each stakeholder, identify the likely priority, the workflow concern, the proof they would care about, and one follow-up question.

**Fictional customer note:**

> "Our AppSec team receives findings from SAST, SCA, and secrets scanning. Most findings are reviewed by AppSec before they are turned into Jira tickets for engineering. Developers work in GitHub, and any code change must go through pull request review and CI checks before it can be merged. Closure evidence is currently copied into our GRC platform for audit, but that step is manual and often happens late. We are confident this is our own codebase, but we have not yet agreed which repository or backlog slice would be in scope for a first review."

**Estimated time**

10–12 minutes

**Suggested output and reflection**

A short current-state note identifying signal source, system of record, execution surface, owner, handoff, and evidence gap.

**Optional stretch**

Mark which parts of the workflow are clearly authorized, which are assumed, and which need confirmation.

## Slide 26/53 - Knowledge check (Module: Map current security inputs and systems)

**Question:** A customer says, "Our findings come from SAST and SCA tools. Remediation is tracked in Jira, but final closure evidence has to be stored in our GRC platform. We want to scan all repositories right away." Which response best supports responsible qualification?

- Recommend replacing Jira and the GRC platform with a single AI-assisted workflow so the process is easier to manage.
- Ask the customer to pause until they can consolidate all findings into one security tool before discussing Daybreak.
- **Map the current workflow, confirm the system of record and execution surface, then identify one authorized repository or backlog slice as a bounded starting point.** ✓ Correct
- Start with all repositories because the customer already has signal sources, a ticketing system, and a governance platform.

*Explanation: This works because the partner preserves the customer's current systems while narrowing the first step. A strong qualification path maps signal sources, systems of record, execution surfaces, ownership, and evidence needs before recommending a bounded starting point.*

## Slide 27/53 - Summary (Module: Map current security inputs and systems)

Current-state mapping prevents premature solutioning.

When you can name the customer's security inputs, systems of record, execution surfaces, handoffs, and evidence gaps, the opportunity becomes easier to qualify. It also becomes easier to avoid overbroad recommendations that sound impressive but are not ready to run.

## Slide 28/53 - Introduction (Module: Diagnose workflow bottlenecks using find → validate → test → remediate → prove)

A security workflow can slow down at several points. The customer may describe the problem as "too many findings," but the actual bottleneck may be validation, testing, remediation, evidence capture, or handoff between teams.

The find → validate → test → remediate → prove workflow gives you a practical way to locate the slowdown and turn it into a qualification hypothesis. This workflow is reusable across Cyber / Daybreak customer conversations because it helps you turn broad security pressure into a specific qualification hypothesis.

## Slide 29/53 - Use the defensive workflow as a qualification lens (Module: Diagnose workflow bottlenecks using find → validate → test → remediate → prove)

Use this workflow to diagnose where security signal becomes action.

**Find**

The customer surfaces a potential issue. It may come from a scanner, code change, bug report, audit, incident review, threat model, or manual review.

Discovery focus:

- What creates the finding?
- How much signal is generated?
- Which assets or repositories are affected?
- Are findings grouped, deduplicated, or prioritized?

A bottleneck at the finding stage may appear when the customer has too many sources, duplicate results, weak prioritization, or unclear ownership at intake.

**Validate**

The customer determines whether the issue is real, relevant, reachable, exploitable, and worth action.

Discovery focus:

- Who validates findings?
- What evidence do they use?
- How do they distinguish real issues from false positives?
- What slows validation down?

A validation bottleneck may appear when AppSec lacks context, findings are noisy, or reviewers cannot decide which issues matter.

**Test**

The customer confirms behavior safely through approved tests, reproduction steps, integration checks, or regression boundaries.

Discovery focus:

- Is testing authorized?
- What environment is approved?
- What proof is available?
- What remains untested?

A testing bottleneck may appear when there is no safe environment, unclear authorization, limited test coverage, or high risk of breaking expected behavior.

**Remediate**

The customer applies a patch, dependency update, configuration change, mitigation, or workaround.

Discovery focus:

- Who owns remediation?
- What does engineering need before acting?
- Are remediation tickets actionable?
- How is change risk reviewed?

A remediation bottleneck may appear when engineering rejects tickets, patches are unclear, ownership is disputed, or security work competes with delivery priorities.

**Prove**

The customer records evidence that the issue was reviewed, addressed, accepted, and tracked in the right system.

Discovery focus:

- Where is evidence stored?
- Who accepts closure?
- What proof is required for audit or governance review?
- What reporting is manual?

A proof bottleneck may appear when evidence is scattered, reviewer decisions are not recorded, or leadership cannot see progress clearly.

## Slide 30/53 - Locate latency and handoff friction (Module: Diagnose workflow bottlenecks using find → validate → test → remediate → prove)

A bottleneck is the point where work slows down enough to affect the customer's ability to reduce risk. Some bottlenecks are easy to hear.

A customer may say:

> "We have too many false positives."
> "Engineering does not trust our security tickets."
> "It takes too long to validate whether findings are real."
> "We do not have enough evidence for audit."
> "We can find issues, but we cannot fix them fast enough."

Other bottlenecks are hidden inside handoffs.

For example:

AppSec may validate a finding, but the ticket may not include enough context for engineering. Engineering may create a fix, but AppSec may not have enough test evidence to accept closure. Leadership may see backlog volume, but not enough evidence to know whether exposure is going down.

When you hear a customer describe a pain point, map it to the workflow stage where it occurs.

A simple mapping can look like this:

- Scanner noise → find or validate
- False-positive review → validate
- Lack of reproduction steps → validate or test
- Engineering pushback → remediate or handoff
- Unclear patch ownership → remediate
- Weak audit evidence → prove
- Manual reporting → prove

The purpose is not to solve the workflow right now. The purpose is to qualify where the customer needs help.

## Slide 31/53 - Turn the bottleneck into a qualification hypothesis (Module: Diagnose workflow bottlenecks using find → validate → test → remediate → prove)

Once you identify the bottleneck, turn it into a qualification hypothesis.

A useful qualification hypothesis includes:

- The workflow
- The signal source
- The bottleneck
- The stakeholder or reviewer
- The proof point

Use plain language. Avoid broad claims about AI performance or full automation.

Weak hypothesis:

> "The customer needs AI to improve security."

Stronger hypothesis:

> "The customer has a validation bottleneck in its AppSec workflow. Security signal comes from SAST and dependency scanning, but AppSec spends too much time confirming which findings are real before engineering will act. The AppSec lead would review outputs, and improvement would be shown by fewer disputed tickets and faster reviewed remediation decisions."

Another weak hypothesis:

> "The customer should use Codex Security to fix vulnerabilities."

Stronger hypothesis:

> "The customer has a developer handoff bottleneck. AppSec can identify likely issues, but tickets often lack enough code context and remediation guidance for engineering to accept them. A bounded first step could focus on one owned repository or backlog slice, with proof based on ticket usefulness and reviewer confidence."

A good hypothesis should be specific enough that another person could understand the opportunity without having attended the original customer call.

## Slide 32/53 - Real-world example: The issue is not the scanner, it is validation latency (Module: Diagnose workflow bottlenecks using find → validate → test → remediate → prove)

A customer initially says:

> "Our scanner is producing too many findings."

That may sound like a tool problem. After discovery, the partner learns that the scanner is only part of the issue.

The AppSec team lacks enough context to validate findings quickly.

Engineering teams often reject tickets that do not include reproduction notes or remediation guidance.

Audit evidence is difficult to compile because decisions are scattered across tools and messages.

The bottleneck is not only finding volume. The workflow is slowing down at validation and developer handoff.

A strong qualification hypothesis might be:

> "The customer has a validation and developer handoff bottleneck. Scanner findings are entering the AppSec backlog faster than the team can validate them, and engineering rejects tickets without enough evidence. Improvement would be shown by fewer disputed tickets, clearer evidence, and faster reviewed remediation decisions for one bounded backlog slice."

This hypothesis gives the partner a more responsible starting point than "scan more" or "automate fixes."

## Slide 33/53 - Recommended exercise: Locate the workflow bottleneck (Module: Diagnose workflow bottlenecks using find → validate → test → remediate → prove)

This is an optional practice activity to help you apply what you just learned.

**Purpose**

Practice using the find → validate → test → remediate → prove workflow to diagnose customer friction.

**Suggested learner task:**

Review the fictional customer note below. Identify the customer's security input sources, systems of record, execution surfaces, workflow owners, handoff points, and evidence gaps.

**Fictional customer excerpt:**

> "Our AppSec team is overwhelmed by scanner findings from SAST and dependency scans. We can find issues, but it takes too long to decide which ones are real, reachable, and worth engineering time. When we do send tickets to engineering, developers often push back because the tickets do not include enough context, reproduction notes, or remediation guidance. Even when something gets fixed, audit evidence is hard to assemble because validation notes, Jira updates, pull request comments, and closure records are spread across different places."

Use the workflow stages: Find → Validate → Test → Remediate → Prove

**Estimated time**

10–12 minutes

**Suggested output and reflection**

A bottleneck map and one qualification hypothesis using the provided structure.

**Optional stretch**

Identify one unsupported assumption in the hypothesis and write a follow-up question to confirm it.

## Slide 34/53 - Knowledge check (Module: Diagnose workflow bottlenecks using find → validate → test → remediate → prove)

**Question:** A customer says, "We already have scanners, but our AppSec team cannot validate findings quickly enough, and engineering does not trust the tickets." Which response best explains the workflow bottleneck?

- **The customer appears to have a validation and developer handoff bottleneck. The opportunity is to improve evidence quality and reviewed remediation decisions for a bounded defensive workflow.** ✓ Correct
- The customer is ready for full automation because scanners already identify the findings and engineering wants fewer manual tasks.
- The customer's main issue is engineering awareness, so the next step should be to tell developers that all security tickets should be treated as urgent.
- The customer's main issue is finding volume, so the next step should be to increase scanning coverage across repositories.

*Explanation: This works because the customer's pain is not simply scanner volume. The workflow slows down when AppSec validates findings and when engineering decides whether tickets are actionable. A responsible qualification hypothesis should preserve human review and focus on evidence, prioritization, and reviewed decisions.*

## Slide 35/53 - Summary (Module: Diagnose workflow bottlenecks using find → validate → test → remediate → prove)

The find → validate → test → remediate → prove workflow helps turn customer complaints into qualification evidence.

A customer may describe the surface problem as scanner noise, backlog size, or slow remediation. Your role is to identify where the workflow actually slows down and express the opportunity as a bounded hypothesis that can be tested later.

## Slide 36/53 - Introduction (Module: Define proof points and opportunity readiness)

A cyber opportunity is easier to progress when the customer can say what improvement would look like.

Proof does not need to be a full ROI model in early qualification. It does need to be specific enough that the customer, partner, and OpenAI team can understand what evidence would make the opportunity worth structured follow-up.

## Slide 37/53 - What proof means in cyber qualification (Module: Define proof points and opportunity readiness)

In cyber qualification, proof means observable evidence that a customer's defensive workflow improved in a way stakeholders recognize.

Proof should be tied to the workflow bottleneck.

If the bottleneck is validation, a useful proof point may be faster time to validated finding or fewer false positives.

If the bottleneck is developer handoff, a useful proof point may be fewer rejected tickets or more accepted remediation paths.

If the bottleneck is audit evidence, a useful proof point may be clearer evidence packets or less manual effort to document closure.

Useful proof points may include:

- Finding validity
- Noise reduction
- Evidence usefulness
- Time to validated finding
- Time to reviewed fix
- Patch acceptance
- Regression confidence
- Reviewer confidence
- Audit readiness

Avoid proof points that rely on unapproved ROI claims, benchmark comparisons, competitive claims, or broad promises about model performance.

Weak proof point:

> "AI will reduce security costs across the enterprise."

Stronger proof point:

> "For one AppSec backlog slice, reviewers can validate findings faster and produce evidence that engineering accepts."

Weak proof point:

> "The model will find more vulnerabilities than the current tools."

Stronger proof point:

> "For one owned repository, the customer can determine whether outputs improve finding validity, evidence quality, and reviewer confidence."

## Slide 38/53 - Opportunity readiness checklist (Module: Define proof points and opportunity readiness)

A ready cyber opportunity does not require a complete solution design. It requires enough evidence to move into structured opportunity development responsibly.

Use this lightweight readiness checklist:

- A clear defensive workflow problem
- A named stakeholder or owner
- A known security input or signal source
- A visible workflow bottleneck
- A bounded asset, repository, application, backlog slice, or vulnerability class
- A human reviewer or approver
- A system of record or evidence location
- A proof point that would show improvement
- Known open questions, assumptions, or escalation needs

If several items are missing, the opportunity may still be valuable, but it needs clarification.

For example, a customer may say:

> "We have thousands of vulnerabilities."

That is not yet ready.

You still need to know where the findings come from, which subset matters first, who validates them, where decisions are recorded, and what proof would show the workflow improved.

If the opportunity includes sensitive contexts, such as exploit-heavy testing, cyber-specialized model access, unclear authorization, production systems, or critical infrastructure, it may require escalation before structured follow-up.

Readiness is about quality of evidence, not enthusiasm.

## Slide 39/53 - Document the qualification snapshot (Module: Define proof points and opportunity readiness)

A qualification snapshot is a concise record of what you know, what you assume, and what still needs confirmation.

It should be clear enough for an OpenAI or partner colleague outside the original conversation to understand the opportunity.

Capture the following:

- Customer problem
- Stakeholders and persona lenses
- Security signal source
- Current workflow and system of record
- Bottleneck stage
- Bounded starting point
- Proof point
- Routing handoff and next safe step: confirmed workflow facts, sensitivity or escalation flags, unresolved questions, and the next decision required
- Open questions and escalation notes

Separate known facts from assumptions.

Known fact:

> "The customer says SCA findings are tracked in Jira and reviewed by the AppSec team."

Assumption:

> "The customer may have one repository suitable for a bounded first step, but this has not been confirmed."

Proof gap:

> "The customer has not yet defined what evidence engineering needs before accepting remediation."

A concise snapshot may look like this:

> "Customer problem: AppSec backlog is growing, and engineering rejects many tickets as lacking context.
> Stakeholders: AppSec lead owns validation; engineering manager owns remediation acceptance; CISO wants audit-ready evidence.
> Signal source: SCA and SAST findings.
> System of record: Jira for remediation, GRC platform for closure evidence.
> Bottleneck: Validation and developer handoff.
> Bounded starting point: One owned customer portal repository or one backlog slice, pending confirmation.
> Proof point: Fewer rejected tickets and faster reviewer decisions.
> Open questions: named reviewer, approved scope, evidence requirements, escalation needs.
>
> Routing handoff: Confirm the named reviewer, approved scope, and evidence requirements before solution routing; carry any escalation needs forward for review."

## Slide 40/53 - Real-world example: Turning a backlog complaint into a proof-led qualification note (Module: Define proof points and opportunity readiness)

A customer says:

> "We need help with thousands of open vulnerabilities."

The partner does not treat the number alone as the opportunity. A large backlog may indicate a real problem, but the qualification value comes from understanding the workflow behind it.

The partner asks where the findings come from and learns that SCA and SAST findings enter Jira.

The partner asks where the workflow slows down and learns that AppSec review is delayed by false positives and limited context.

Engineering accepts only tickets with reproduction evidence or clear remediation guidance.

Audit reviewers need evidence of closure in a GRC platform.

A proof-led qualification note might say:

> "The customer has a validation and remediation handoff bottleneck in its vulnerability backlog. SCA and SAST findings enter Jira, but AppSec review is delayed by false positives and limited context. Engineering accepts tickets only when evidence and remediation guidance are clear. A bounded first step could focus on one owned repository or backlog slice. Proof would be based on faster validation, fewer rejected tickets, and clearer evidence for audit review."

This note is more useful than "customer has thousands of vulnerabilities" because it identifies the workflow, the bottleneck, the stakeholder needs, and the evidence that would show improvement.

## Slide 41/53 - Recommended exercise: Draft a proof-led qualification snapshot (Module: Define proof points and opportunity readiness)

This is an optional practice activity to help you apply what you just learned.

**Purpose**
Practice documenting a cyber opportunity so it is clear, evidence-led, and ready for responsible follow-up.

**Task**

Review the fictional discovery summary below. Draft a qualification snapshot that includes stakeholder, signal source, bottleneck, bounded starting point, proof point, next safe step, routing handoff, and open questions.

**Fictional discovery summary**

> "The customer is a software company with a growing AppSec backlog. Findings come from SAST and SCA tools and are tracked in Jira. The AppSec lead says the team spends too much time validating whether findings are real, reachable, and worth sending to engineering. Engineering managers say many tickets lack enough context to act on confidently, so tickets are often delayed or sent back for clarification.
>
> The CISO wants proof that material exposure is being reduced before the next audit review. The AppSec lead has offered to review outputs for one owned customer portal repository, but the exact backlog slice has not been selected. Closure evidence currently needs to be copied into the customer's GRC platform, and the team wants a clearer way to document reviewer decisions and proof gaps."

**Estimated time**

10–12 minutes

**Suggested output and reflection:**

A concise qualification snapshot that separates known facts, assumptions, proof gaps and next steps.

**Optional stretch**

Rewrite the proof point so it is measurable without relying on unapproved benchmark, ROI, or competitive claims.

## Slide 42/53 - Knowledge check (Module: Define proof points and opportunity readiness)

**Question:** A customer says, "Our AppSec backlog is large. SAST and SCA findings enter Jira, but engineering often rejects tickets because the evidence is not actionable. The AppSec lead can review outputs for one owned repository." Which proof point best supports opportunity readiness?

- The customer should receive a complete ROI calculation showing enterprise-wide cost savings from AI-assisted security.
- The model should identify more vulnerabilities than the customer's current scanners across the full application estate.
- The customer should be able to remove manual review from vulnerability remediation once the workflow is configured.
- **The customer should see faster validation and fewer rejected tickets for the bounded repository workflow, based on evidence the AppSec lead and engineering team can review.** ✓ Correct

*Explanation: This works because the proof point is tied to the actual bottleneck and bounded scope. It focuses on validation, evidence usefulness, and reviewer decisions rather than unapproved ROI claims, broad benchmark claims, or removal of human review.*

## Slide 43/53 - Summary (Module: Define proof points and opportunity readiness)

Proof makes qualification actionable. A strong proof point is specific to the customer's workflow and visible to the stakeholders who care about the outcome.

It does not need to prove everything. It needs to show what would improve, for whom, and within which bounded scope.

## Slide 44/53 - Introduction (Module: Recognize sensitive contexts and route responsibly)

Cyber conversations can shift quickly. A customer may begin with an AppSec backlog and then ask about cyber-specialized model access. Another customer may ask about red-team automation, exploit validation, malware analysis, or production testing.

Responsible qualification means recognizing when a conversation is no longer a standard AppSec discovery motion and should be clarified, bounded, or escalated.

## Slide 45/53 - Sensitive contexts that require caution (Module: Recognize sensitive contexts and route responsibly)

Some contexts should trigger a pause before you continue.

Examples include:

- Red team requests
- Security research requests
- Exploit-heavy work
- Offensive testing
- Malware analysis or generation
- Live-target testing
- Unknown or unclear authorization
- Production testing without defined guardrails
- Critical infrastructure or high-risk environments
- Custom harnesses, API gateways, or advanced automation paths
- Cyber-specialized model access requests
- Special data handling, pricing, availability, or internal access-tier questions

These contexts are not always invalid. Many legitimate defenders perform advanced cyber work in authorized environments.

Before recommending next steps, confirm whether the work is authorized, defensive, customer-owned or explicitly permitted, bounded, reviewed by humans, and connected to clear evidence expectations.

A safe framing is:

> Clarify the workflow before discussing capability.

## Slide 46/53 - Safe clarification and routing language (Module: Recognize sensitive contexts and route responsibly)

Use bounded, responsible language when a customer raises sensitive or unclear requests.

Safe clarification language includes:

> "Let's confirm the authorized defensive workflow first."
> "Which asset or environment does your team own and have approval to review?"
> "Who will review findings and decide whether remediation is acceptable?"
> "What system of record should evidence be captured in?"
> "This sounds like it may require OpenAI SME review before we discuss access or advanced workflow details."

Avoid unsupported claims such as:

> "We can get you cyber-specialized model access."
> "This removes refusals."
> "This can automate offensive testing."
> "This will fix vulnerabilities without review."
> "Special data handling, pricing, or deployment terms are included."

Escalation is not a failed conversation and it is not something to avoid. It protects customer trust and OpenAI platform integrity. It also helps ensure the right experts review sensitive details before you make claims about access, availability, deployment, data handling, or advanced cyber workflows.

## Slide 47/53 - Readiness and routing categories (Module: Recognize sensitive contexts and route responsibly)

Use three practical routing categories during qualification.

**Ready to qualify further**

The customer has an authorized defensive workflow, named stakeholders, clear security signal, visible bottleneck, bounded scope, reviewer, and proof point.

Example:

> "We have one owned repository with a backlog of SAST findings. The AppSec lead will review evidence. Engineering needs clearer remediation guidance. Success would be fewer rejected tickets and faster reviewed decisions."

This is ready to qualify further.

**Needs clarification**

The customer has a potential workflow problem, but ownership, scope, signal source, proof point, or review process is unclear.

Example:

> "We want to use AI to improve cyber defense, but we are not sure where to start."

This needs clarification.

**Escalate before progressing**

The request involves sensitive cyber context, unclear authorization, offensive or exploit-heavy work, production or critical infrastructure concerns, special access requests, or unsupported product claims.

Example:

> "Can your model help us automate exploit development against external targets?"

This should be escalated before progressing. Do not discuss tactics, model capability, or advanced workflow details. Clarify authorization and involve the appropriate OpenAI or technical SME.

When you document the category, include the reason. A category without rationale is not enough for responsible follow-up.

## Slide 48/53 - Red-team language shifts the conversation to clarification and escalation (Module: Recognize sensitive contexts and route responsibly)

A customer asks:

> "Can AI help us automate red-team activity against external targets?"

A weak response would be:

> "Yes, we have advanced cyber capabilities that can help with that."

That response is unsafe because it makes a capability claim before confirming authorization, scope, ownership, reviewer responsibility, and intended defensive purpose.

A stronger response would be:

> "Before we discuss advanced workflow details, let's clarify the authorized defensive context. Which targets are owned or explicitly authorized for review? What is the approved environment? Who will review outputs? This may require OpenAI SME review before we can recommend a path."

Do not continue into tactics. Clarify whether the work is authorized, owned, bounded, and defensive. Ask who will review outputs and route the request appropriately.

The conversation stays responsible when you recognize the sensitivity and avoid treating the request as a standard AppSec qualification path.

## Slide 49/53 - Recommended exercise: Triage cyber qualification excerpts (Module: Recognize sensitive contexts and route responsibly)

This is an optional practice activity to help you apply what you just learned.

**Purpose**
Practice deciding whether a cyber opportunity is ready to qualify further, needs clarification, or should be escalated.

**Suggested learner task:**

Review the fictional customer excerpts below. For each excerpt, select a routing category, explain why, and write one safe next-step question or escalation note.

**Fictional customer excerpts:**

**Excerpt 1: AppSec validation problem**

> "We own the customer portal repository, and our AppSec team is trying to work through a backlog of SAST and SCA findings. The AppSec lead can review outputs, and engineering has agreed to look at tickets if the evidence is clearer. We want to start with one backlog slice and understand whether we can reduce rejected tickets."

**Excerpt 2: Unclear model-access request**

> "We heard there may be a more advanced cyber model. Can we get access to that? We have a lot of security work to get through, but we have not decided which repository, application, or workflow should be reviewed first."

**Excerpt 3: Exploit-heavy testing request**

> "We want to use AI to automate exploit development against external targets. Some of the targets may belong to third parties, and authorization is still being worked out. Can you help us test what the model can do?"

**Estimated time**

10–12 minutes

**Suggested output and reflection:**

A triage note for each excerpt with routing category, reason, safe next step, and escalation flag where needed.

**Optional stretch**

Rewrite one unsafe partner response into responsible routing language.

## Slide 50/53 - Knowledge check (Module: Recognize sensitive contexts and route responsibly)

**Question:** A customer says, "Can your cyber model automate exploit development against external targets? We have not finalized the authorization details yet." Which response best reflects responsible routing?

- Suggest starting with a broad scan across the customer's production environment so the team can identify which targets matter most.
- Reframe the request as a standard AppSec workflow and recommend a repository-based evaluation without asking further questions.
- Explain that cyber-specialized model access may be available and ask the customer what exploit workflow they want to automate first.
- **Pause the capability discussion, clarify authorization and defensive purpose, and route the request to the appropriate OpenAI SME before discussing advanced workflow details.** ✓ Correct

*Explanation: This works because the request involves exploit-heavy activity, external targets, and unclear authorization. You should not continue into tactics or access claims. The responsible path is to clarify authorization, confirm defensive scope, preserve human review, and escalate before progressing.*

## Slide 51/53 - Summary (Module: Recognize sensitive contexts and route responsibly)

Sensitive cyber contexts require disciplined language. When authorization, ownership, scope, review, or access expectations are unclear, slow the conversation down.

A responsible partner can still keep momentum by asking safe clarification questions, documenting the reason for caution, and routing the opportunity to the right experts.

## Slide 52/53 - Recap (Module: Wrap up)

In this course, you practiced the Cyber / Daybreak qualification loop, moving from broad interest in "AI for security" to a clear view of the customer's authorized defensive workflow.

You identified opportunity signals and stakeholder priorities, mapped current security inputs and systems, used the find → validate → test → remediate → prove workflow to locate bottlenecks, and defined proof points for improvement.

Your core output is a workflow-first qualification snapshot that captures the signal source, bottleneck, reviewers, proof points, fit classification, confirmed facts, sensitivity or escalation flags, open questions, and the information needed for solution routing.

## Slide 53/53 - Congratulations (Module: Wrap up)

Congratulations, you've completed this course!

You now have a practical baseline for qualifying early Daybreak conversations. You can identify cyber-fit opportunities, recognize CISO, AppSec, DevSecOps, security engineering, and engineering leadership priorities, document current workflow inputs and systems, define proof points, and route sensitive cyber requests responsibly.

In customer work, complete the qualification snapshot before moving into solution routing. Carry forward the authorized workflow, bounded scope, stakeholders, systems of record, bottleneck, proof point, sensitivity or escalation flags, and open questions so the next decision is evidence-led.

**Course completed**

**Next up in OpenAI Cyber Solutions Practitioner:** OpenAI Cyber Solutions Practitioner - Final Exam (Course, 2 min)

Discovery questions may include:

- "Where do findings enter the workflow?"
- "Where are remediation decisions recorded?"
- "Where does engineering review the work?"
- "Where does audit or governance evidence need to end up?"
- "Which tool is trusted as the source of truth?"

Use this map to identify where the customer's security work starts, where decisions are recorded, where work is reviewed, and where evidence needs to land before recommending a next step.