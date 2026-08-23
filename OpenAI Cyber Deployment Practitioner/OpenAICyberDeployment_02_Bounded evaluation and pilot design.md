# Bounded evaluation and pilot design

## Slide 1/57 - Title

Bounded evaluation and pilot design

Created July 2026

## Slide 2/57 - Introduction

A strong Daybreak evaluation does not start with "let's test everything." It starts with one bounded, authorized workflow where the customer can test whether Codex Security improves validation, evidence quality, remediation review, or reviewer efficiency.

In this course, you'll learn how to design that first evaluation so security and engineering teams can make a confident next-step decision.

## Slide 3/57 - What you'll learn

By the end of this course, you'll be able to:

- Bound a first Daybreak evaluation around one authorized workflow or target.
- Choose a safe, measurable first target.
- Define a pilot charter with scope, reviewers, evidence expectations, stop conditions, and escalation paths.
- Build a quality-based scorecard using validity, evidence, noise, patch quality, review burden, fix time, acceptance, and regression confidence.
- Plan the evaluation rhythm without overpromising.
- Complete an assessed bounded evaluation plan and package it as a customer-ready recommendation.

Let's get started!

## Slide 4/57 - Introduction (Module: Why bounded evaluation matters)

A customer may be excited about Daybreak, Codex Security, or advanced cyber capability. That interest is useful, but it is not yet an evaluation plan.

A bounded evaluation helps the customer learn safely by focusing on one approved workflow, target, review path, and success metric set. This structure shows whether the workflow produces evidence security and engineering teams can trust.

That shift protects the customer from overscoping, protects you from overpromising, and gives OpenAI teams a clearer basis for support or escalation.

## Slide 5/57 - From customer interest to defensible proof

Customer interest can take many forms:

- "We want to use AI for security."
- "Can Daybreak help with our vulnerability backlog?"
- "Can Codex Security review our repositories?"
- "Can we get access to the cyber model?"
- "Can this help us fix issues faster?"

Those signals may be promising, but they do not prove that the customer is ready for a pilot.

A useful evaluation should test whether Daybreak can improve a specific defensive workflow, such as:

- Validating scanner findings
- Reviewing a sensitive pull request
- Prioritizing a defined backlog slice
- Preparing reviewable remediation
- Creating stronger evidence for AppSec and engineering reviewers

The evaluation should produce evidence that people can assess.

A list of outputs is not enough. The customer needs to know whether the outputs were useful, reviewable, accurate enough to support decisions, and bounded by the agreed scope.

A simple test for evaluation readiness is:

> "Can we name what will be reviewed, who will review it, what evidence will count, and what decision the customer will make at the end?"

When the answer is yes, the opportunity can move toward a bounded evaluation plan.

## Slide 6/57 - Why one bounded workflow is the right starting point

A bounded evaluation gives commercial and technical stakeholders the same focused learning loop.

Strong first evaluations usually focus on one of the following:

- One owned repository
- One application or service
- One vulnerability backlog slice
- One vulnerability class
- One PR or diff pattern
- One approved lower-level environment.

This keeps the evaluation concrete, reviewable, and easier to govern.

A broad evaluation may sound more ambitious, but it often produces weaker learning.

If the customer scans too many repositories, reviewers may not have time to inspect the findings. If the scope includes unclear ownership, evidence may not be trusted. If the evaluation moves directly into production, risk and governance questions may overwhelm the learning goal.

A bounded evaluation gives the customer a focused learning loop:

1. Pick one authorized target
2. Define the workflow question
3. Confirm reviewers and evidence boundaries
4. Run the approved workflow
5. Review the evidence
6. Decide whether to continue, adjust, expand, pause, stop, or escalate

## Slide 7/57 - What a bounded evaluation is not

A bounded evaluation should be clear about its limits.

A bounded evaluation is not:

- A production rollout.
- A promise of cyber-specialized model access.
- Broad vulnerability research across all systems.
- Permission to test production systems without explicit approval.
- Permission to run exploit-heavy workflows without appropriate escalation.
- Automatic remediation across repositories.
- A replacement for the customer's scanners, security tools, systems of record, or human review process.

This matters because Daybreak conversations can quickly become access-first or automation-first.

A customer may ask about special access, reduced refusals, production testing, CI/CD integration, or automated patching before the workflow is scoped.

Your role is to redirect the conversation back to the first defensible proof point:

> "Before we discuss broader rollout or access paths, let's define the authorized workflow, the asset in scope, who will review the outputs, and what evidence would show improvement."

That language keeps the conversation customer-safe and workflow-led.

## Slide 8/57 - Quality over finding volume

The goal is to understand whether Codex Security can help improve decision quality. A first evaluation is not to maximize the number of findings.

Decision quality means the customer has better evidence to decide whether a finding should be confirmed, suppressed, deferred, remediated, escalated, or left unresolved because more proof is needed.

Useful proof points may include:

- Stronger evidence
- Fewer false positives
- Clearer prioritization
- Better developer handoff
- Reviewable remediation
- Faster movement from finding to reviewed fix
- Clearer proof gaps
- Better reviewer confidence
- Stronger evidence for the system of record

A high finding count can create more work if the findings are noisy, duplicative, low-confidence, or difficult to act on. A smaller set of findings may be more valuable if each finding is supported by clear evidence, affected code locations, reviewer guidance, and an actionable next step.

A good evaluation asks:

> "Did the workflow help the customer make better security decisions?"

Not:

> "How many issues did the workflow produce?"

## Slide 9/57 - Real-world example: Moving beyond "scan everything"

A customer says:

> "Our AppSec backlog keeps growing. We want to run Daybreak across every repository and see what it finds."

That request shows urgency, but it is too broad for a first evaluation.

A stronger first step would be:

> "Let's choose one high-priority owned repository or one noisy backlog slice, name an AppSec reviewer and engineering owner, define what evidence will count, and measure whether the workflow improves validation and remediation decisions."

The bounded version gives the customer a better chance to learn something useful.

It also creates a cleaner decision path. At the end of the evaluation, the customer can decide whether the workflow should continue, be adjusted, expand to an adjacent repository, or stop because it did not produce enough trusted evidence.

The partner should avoid making the evaluation feel smaller in value. The message is not:

> "We can only do a small test."

The message is:

> "A bounded evaluation is the fastest responsible way to prove whether the workflow is worth scaling."

## Slide 10/57 - Knowledge check

**Question:** A customer says, "We want to start by running Daybreak across all our repositories so we can get the full picture. We'll figure out reviewers and success metrics once we see the results." Which response best explains why a bounded evaluation is a stronger starting point?

- The customer should start by applying for cyber-specialized model access because broad repository coverage requires a more permissive model.
- Running across all repositories is the best way to prove value because it gives the customer more findings and shows the broadest possible capability.
- The customer should prioritize automatic patching first so the evaluation can prove immediate remediation impact across the backlog.
- **A broad scan can be useful later, but the first evaluation should start with one authorized target, named reviewers, evidence expectations, and quality-based success metrics so the customer can make a trusted decision.** ✓ Correct

*Explanation: This works because a first Daybreak evaluation should be narrow, authorized, evidence-led, and human-reviewed. The goal is to test whether the workflow improves decision quality, not to maximize finding volume or jump into access, automation, or broad rollout.*

## Slide 11/57 - Summary

A bounded evaluation turns customer interest into a structured proof point. The key move is to define one approved defensive workflow, one target, one review path, and one set of success metrics before the work begins.

This helps the customer learn whether Codex Security improves validation, evidence, remediation quality, or review efficiency without creating unnecessary scope, access, or governance risk. Expansion should come after evidence shows the workflow is useful and reviewable.

## Slide 12/57 - Introduction (Module: Selecting the first evaluation target)

The first evaluation target shapes the quality of the pilot. A strong target gives Codex Security enough context to support useful analysis and gives human reviewers a scope they can realistically assess. A weak target is too broad, risky, unclear, or disconnected from the customer's real bottleneck.

Choose a target that helps answer one practical question, such as whether the team can validate a noisy backlog slice, review a sensitive change, or prepare clearer evidence for a customer-owned repository.

The best target is safe, authorized, measurable, and tied to a real customer decision.

## Slide 13/57 - Characteristics of a strong first target

A strong first evaluation target meets these criteria:

| Criterion | What it means |
|---|---|
| Owned | The customer controls the repository, application, backlog, or environment. |
| Authorized | Security and engineering stakeholders approve the review. |
| Bounded | The scope can be clearly described and enforced. |
| Relevant | The target connects to a real security bottleneck or business-relevant risk. |
| Reviewable | A named reviewer can assess findings, evidence, and proposed actions. |
| Measurable | The team can define success metrics before the evaluation starts. |
| Context-rich | The workflow includes enough code, system, test, scanner, ticket, or architecture context to support useful analysis. |
| Safe | The activity avoids unapproved production testing, exploit-heavy behavior, unclear data handling, or unclear ownership. |

A useful shorthand is:

> Owned, authorized, bounded, relevant, reviewable, measurable, context-rich, and safe.

If one of these is missing, the evaluation may still be possible, but it needs more scoping before work begins.

## Slide 14/57 - Common first evaluation target patterns

Different customer bottlenecks call for different target patterns. Each target pattern is simply a different way to make the first evaluation small enough to govern and specific enough to measure.

The right pattern depends on where the customer's security workflow is stuck.

| First target pattern | Useful when | Watch for |
|---|---|---|
| One owned repository | The customer wants a structured Codex Security evaluation on a known codebase. | Confirm repository ownership, branch or commit scope, reviewer, and data-handling boundaries. |
| One application or service | The customer has a high-value system with a known AppSec concern. | Avoid expanding into every connected service before the first evaluation proves value. |
| One backlog slice | The customer has a noisy scanner backlog and wants to validate which findings matter. | Define how findings are selected and what evidence is required to confirm or suppress them. |
| One vulnerability class | The customer wants focused review of a recurring issue type, such as authorization, input validation, dependency risk, or secrets handling. | Keep the class broad enough to be useful but narrow enough to review. |
| One PR / diff pattern | The customer wants review support before merge, especially for sensitive changes. | Confirm the decision point: merge readiness, review evidence, or remediation guidance. |
| One approved lower-level environment | Limited testing or revalidation is approved outside production. | Do not claim production proof unless production testing was explicitly authorized and observed. |

The pattern should match the customer's immediate workflow question.

**For example**

If the customer's main problem is scanner noise, a backlog slice may be the right first target.

If the customer's main problem is release risk, a sensitive PR or diff pattern may be more useful.

## Slide 15/57 - Poor first targets and escalation triggers

Some proposed targets are poor starting points because they create too much scope, risk, or ambiguity.

Poor first targets usually fall into five categories.

**Too broad** — The request covers all repositories, all applications, or broad autonomous testing instead of one bounded workflow.

**Unclear ownership or approval** — The target is third-party infrastructure, production services without explicit approval, or has no named reviewer or decision owner.

**High-risk testing** — The request involves red-team activity, exploit-heavy work, or offensive testing.

**Sensitive or unusual environment** — The target involves critical infrastructure, a custom harness, unusual deployment patterns, sensitive data, or unclear data handling.

**Access-first framing** — The conversation starts with cyber-specialized access instead of a clearly scoped defensive workflow.

When these signals appear, you should slow down. The right response may be to clarify scope, involve security and engineering owners, or escalate to OpenAI SMEs before recommending a pilot.

Here's a customer-facing redirect:

> "That may become relevant later, but the first step is to define the authorized defensive workflow, the asset in scope, the review owner, the evidence boundary, and the success metric. If the workflow involves production testing, exploit-heavy activity, special access, or unclear authorization, we should bring in the right OpenAI support before proceeding."

## Slide 16/57 - Real-world example: Choosing the narrowest useful target

A customer has three possible starting points:

1. "Run Daybreak across all repositories." ✓ (Click to complete)
2. "Review the payment-service repository because it handles sensitive transaction logic." ✓ (Click to complete)
3. "Validate the top 40 findings from last week's SAST scan for the payment-service repository." ✓ (Click to complete)

The strongest first target depends on the customer's bottleneck.

If the customer's bottleneck is broad AppSec coverage, the payment-service repository may be a good first target because it is owned, bounded, relevant, and reviewable.

If the customer's bottleneck is scanner noise, the top 40 findings from a recent scan may be even better because the evaluation can focus on finding validity, false-positive reduction, evidence quality, and reviewer burden.

The weakest first target is "all repositories." It may become part of a later expansion path, but it is too broad for a first evaluation unless the customer has already proven the workflow, governance model, and reviewer process at smaller scope.

## Slide 17/57 - Recommended exercise: Select the first evaluation target

This is an optional practice activity you can complete to reinforce what you just learned.

**Exercise title:** Classify workflow needs and propose an initial integration pattern.

**Purpose:** Help you practice choosing a safe, measurable starting point for a Daybreak evaluation.

**Task:** Review three short fictional customer requests and identify which one is the strongest first evaluation target. For each, mark it as "ready," "needs more scoping," or "pause and escalate."

Fictional customer requests:

**Request A: Broad repository coverage**

> "We want to run Daybreak across all 180 repositories in the next two weeks. Our CISO wants a complete view of our risk exposure. We have not chosen reviewers yet, but the platform team can give access once we decide to move forward."

**Request B: Bounded AppSec backlog slice**

> "Our AppSec team has 60 high-priority scanner findings for the customer-account-service repository. The repository is owned by our digital banking team. Our AppSec lead and engineering manager can review outputs together. We want to know which findings are real, which are likely false positives, and whether remediation guidance is clear enough for engineering."

**Request C: Third-party target testing**

> "We want to test a vendor-managed payment gateway from the outside to see whether we can reproduce a suspected vulnerability. We do not operate the system, but it is important to our business."

**Estimated time:** 8-10 minutes

**Suggested output and reflection:** A short target-selection note that explains the chosen target, why it fits, what must be confirmed, and what should be avoided.

**Optional stretch:** Write one customer-safe question for each request.

## Slide 18/57 - Knowledge check

**Question:** A customer has a noisy backlog of scanner findings for an owned internal repository. The AppSec lead and engineering manager are available to review outputs, and the customer wants to understand whether the findings are real and actionable. Which first evaluation target is strongest?

- A cyber-specialized access request, because scanner validation usually requires advanced cyber access before any evaluation can begin.
- **The owned internal repository's defined scanner backlog slice, reviewed by the named AppSec and engineering owners against evidence quality and decision metrics.** ✓ Correct
- All repositories in the customer's engineering estate, so the customer can compare which teams have the highest security exposure.
- The production application, tested live to prove whether any findings are exploitable in the real environment.

*Explanation: This works because the target is owned, bounded, authorized, relevant, reviewable, measurable, and connected to a real workflow bottleneck. The other options introduce unnecessary scope, production testing, or access-first framing before the first evaluation is ready.*

## Slide 19/57 - Summary

A strong first target gives the customer a real decision to make without creating unnecessary risk.

Look for a target that is owned, authorized, bounded, relevant, reviewable, measurable, context-rich, and safe. Avoid broad coverage, unclear ownership, production testing, exploit-heavy activity, and access-first requests unless the right scope, approval, and escalation path are in place.

The first target should be narrow enough to govern and meaningful enough to teach the customer whether the workflow is worth continuing.

## Slide 20/57 - Introduction (Module: Building the Evaluation Charter)

Once the first target is selected, define the evaluation charter. This short planning artifact keeps the evaluation safe, measurable, and reviewable by clarifying:

- The question being tested
- What is in and out of scope
- Who reviews the evidence
- What evidence can and cannot be claimed
- Which metrics define success
- What stops the evaluation or triggers escalation

The charter creates a shared reference point and helps prevent early scope drift into access, automation, remediation, or production testing.

## Slide 21/57 - Evaluation question and hypothesis

Every bounded evaluation should start with a clear question.

A good evaluation question connects the customer's workflow bottleneck to a measurable improvement.

Example evaluation question:

> "Can Codex Security help our AppSec team validate and prioritize a defined backlog slice with stronger evidence and lower review burden?"

A good hypothesis states what the team expects to learn.

Example hypothesis:

> "For this owned repository and scanner backlog slice, Codex Security will help reviewers separate valid findings from noise and prepare clearer developer handoff."

The question and hypothesis should be specific enough to guide the work.

**Weak evaluation question:** "Can Daybreak improve our security?"

**Stronger evaluation question:** "Can Codex Security help reviewers validate the top 50 scanner findings in the customer-account-service repository with clearer evidence, fewer false positives, and less review burden?"

The stronger version names the workflow, the target, the reviewer task, and the type of proof the customer needs.

## Slide 22/57 - Scope and boundaries

A strong evaluation charter should define exactly what is in scope and what is out of scope.

**Scope** should include:

- The in-scope asset, repository, application, backlog slice, vulnerability class, PR / diff pattern, or environment
- The branch, commit, timeframe, or finding set, if relevant
- The approved workflow to run
- The expected outputs
- The reviewer process
- The final decision point.

**Boundaries** should include:

- What is explicitly out of scope
- Whether runtime testing is permitted
- Whether remediation support is permitted
- Whether outputs may be used only for review or also for handoff into normal remediation processes
- Whether production systems are excluded
- What data, logs, files, or artifacts may be used
- What must stop the evaluation and trigger review or escalation.

Out-of-scope items are not administrative details. They protect the evaluation.

For example:

> "In scope: source-supported review of the customer-account-service repository and selected SAST backlog items."

> "Out of scope: production testing, third-party systems, exploit-heavy validation, automatic merge or deployment, and any repository not named in the charter."

That level of clarity gives the team permission to move quickly inside the approved boundary and slow down when the work crosses it.

## Slide 23/57 - Named owners and reviewers

A bounded evaluation needs named people, not just named tools.

The charter should identify who is accountable for each part of the workflow.

| Role | Responsibility |
|---|---|
| Business or security sponsor | Confirms why the evaluation matters and how it supports the customer's security goals. |
| AppSec or security reviewer | Reviews findings, evidence quality, validity, severity rationale, and proof gaps. |
| Engineering owner | Assesses technical feasibility, code impact, test expectations, and remediation readiness. |
| Decision owner | Decides whether to continue, adjust, expand, pause, stop, or escalate. |
| Partner or OpenAI support role | Helps scope, facilitate, or escalate as appropriate, without replacing the customer's accountable security and engineering owners. |

A common pilot failure is to define the tool and target, but not the human review path.

The charter should make the review path explicit:

- Who reviews candidate findings?
- Who decides whether a finding is valid?
- Who decides whether remediation is acceptable?
- Who records the decision?
- Who decides whether the evaluation expands?

Codex Security can support analysis, evidence generation, and reviewable outputs. Customer security and engineering teams remain accountable for risk decisions, remediation acceptance, and release decisions.

## Slide 24/57 - Evidence expectations and evidence ceiling

The charter should define what evidence the evaluation is expected to produce. It should also define the evidence ceiling.

An evidence ceiling is the highest level of proof the team can responsibly claim based on the permitted activity.

Use these evidence labels:

- **Source-supported evidence** — Something directly visible in code, configuration, scanner output, logs, tickets, or provided artifacts.
- **Supported inference** — A reasonable conclusion drawn from available source evidence.
- **Approved runtime proof** — Evidence observed from runtime activity that was explicitly authorized and actually performed.
- **Proof gap** — Something that remains untested, unobserved, or undecided.
- **Unsupported claim** — A statement that goes beyond the evidence available.

For technical reviewers, evidence should point back to concrete artifacts wherever possible: files, functions, scanner outputs, tickets, logs, tests, commands, reviewer notes, or system documentation.

For commercial conversations, these labels help avoid overstating what the evaluation proved.

The evaluation should not claim runtime proof unless runtime testing was explicitly authorized and observed.

It should not claim production impact unless production conditions were in scope and properly reviewed. It should not claim a vulnerability is fixed because a patch was suggested.

The charter should also define retained artifacts, such as:

- Review record
- Evidence summary
- Scorecard
- Remediation handoff
- Proof-gap list
- Executive-ready summary
- System-of-record entry, if approved by the customer.

Evidence quality matters because the output of the evaluation should support human review. It should not become an automatic closure decision.

## Slide 25/57 - Real-world example: A lower-environment review charter

A customer wants to evaluate Codex Security on a lower-environment authentication service.

A strong charter might define:

| Field | Detail |
|---|---|
| Evaluation question | Can Codex Security help AppSec and engineering reviewers validate and prioritize authentication-related findings in the customer-auth-service repository with clearer evidence and less review burden? |
| Target | Customer-auth-service repository, current release branch, selected authentication-related backlog items. |
| In scope | Source-supported review, existing scanner findings, architecture notes provided by the customer, approved lower-level test evidence if available, and reviewer assessment of findings. |
| Out of scope | Production testing, third-party systems, exploit-heavy validation, automatic remediation, automatic merge, and repositories not named in the charter. |
| Reviewers | AppSec lead reviews finding validity and evidence quality. Engineering owner reviews remediation feasibility and test expectations. Security sponsor owns the final pilot decision. |
| Evidence ceiling | Source-supported evidence and approved lower-environment test evidence only. No production runtime proof will be claimed. |
| Stop condition | Pause and escalate if the workflow identifies a potential issue that may affect production release risk, requires live production testing, or requires access or activity outside the approved scope. |

This charter keeps the evaluation focused, reviewable, and safe.

## Slide 26/57 - Recommended exercise: Draft a bounded evaluation charter

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Help you practice turning customer interest into a structured pilot plan.

**Task:** Use the fictional customer scenario to draft the core elements of an evaluation charter: evaluation question, target, scope, out-of-scope items, reviewers, evidence ceiling, success metrics, and escalation triggers.

Fictional customer excerpt:

> "Harborline Bank is modernizing its digital customer portal. The AppSec team has a backlog of scanner findings for the customer-account-service repository. Engineering says many tickets lack enough evidence to act on. The CISO wants to know whether Daybreak can help reduce risk faster, but the AppSec lead wants to start with a lower-risk review before discussing broader rollout. The customer can provide the repository, recent SAST findings, service documentation, and an AppSec reviewer. Production testing is not approved."

**Estimated time:** 10-12 minutes

**Suggested output and reflection:** A one-page evaluation charter outline.

**Optional stretch:** Add one proof gap the team should expect at the end of the evaluation.

## Slide 27/57 - Knowledge check

**Question:** A partner is preparing a Daybreak evaluation plan for an owned repository. The plan names the repository and says Codex Security will review findings, but it does not define out-of-scope activities, evidence limits, reviewers, stop conditions, or success metrics. What is the strongest next step?

- Proceed with the evaluation because the target repository is owned and the missing details can be filled in after outputs are generated.
- Ask the customer to approve broader access so the evaluation can adapt if the workflow needs more context.
- **Complete the evaluation charter by defining scope, out-of-scope boundaries, named reviewers, evidence ceiling, success metrics, and escalation triggers before work begins.** ✓ Correct
- Replace the evaluation with a technical demo so the customer can see the capability before committing reviewers.

*Explanation: This works because a bounded evaluation needs more than a named repository. The charter should define what is in scope, what is out of scope, who reviews the outputs, what evidence can be claimed, what success means, and when to stop or escalate.*

## Slide 28/57 - Summary

A bounded target becomes actionable when it is turned into a charter. The charter makes the evaluation question, scope, owners, evidence expectations, success metrics, and stop conditions explicit. It gives the customer enough structure to move quickly inside the approved boundary and pause when the work crosses that boundary.

The charter is not paperwork for its own sake. It is the operating agreement that protects the quality, safety, and credibility of the evaluation.

## Slide 29/57 - Introduction (Module: Defining success metrics)

A Daybreak evaluation should measure better security decisions, not more activity. Finding volume can mislead: low-confidence results add burden, while fewer high-quality findings may be more useful.

Tie metrics to the bottleneck:

- Validation: finding validity and evidence usefulness
- Handoff: remediation clarity and engineering acceptance
- Review capacity: reviewer burden and time to decision
- Governance: evidence quality and system-of-record fit.

A good scorecard helps the customer decide whether to continue, adjust, expand, pause, or stop.

## Slide 30/57 - Tie metrics to the customer bottleneck

Start by asking where the customer's workflow is slow, noisy, or difficult to govern.

Common bottlenecks include:

| Metric area | Use when |
|---|---|
| Finding quality | The customer struggles with triage, validation, prioritization, or evidence gathering. |
| Developer handoff | Security findings are not clear enough for engineering teams to act on. |
| Fix progress | The customer needs safer movement from confirmed finding to reviewed remediation, testing, and revalidation. |
| Reviewer effort | The customer wants to reduce review burden while preserving human judgment. |
| Operating control | The customer needs confidence that outputs can be reviewed, retained, recorded, and used inside existing systems. |

The right metric depends on the bottleneck.

**Example**

> If the customer says, "Engineering does not trust the tickets," a finding-count metric will not prove much. Better metrics include evidence usefulness, developer handoff quality, accepted fix rate, reviewer confidence, and quality of proof-gap labeling.

## Slide 31/57 - Finding quality metrics

Finding quality metrics help determine whether Codex Security improves decision quality.

Useful measures may include:

- **Finding validity** — How many reviewed findings were confirmed as real, relevant, and actionable within the agreed scope?
- **Evidence usefulness** — Could reviewers accept, reject, suppress, or escalate the finding based on the evidence provided?
- **False-positive reduction** — Did the workflow help suppress or explain findings that were not relevant or not reachable in the customer's context?
- **Duplicate reduction** — Did the workflow help group or remove duplicate findings so reviewers did not spend time on repeated issues?
- **Prioritization quality** — Did the workflow help reviewers focus on findings that mattered most for the target and business context?
- **Attack path or precondition clarity** — Did the output explain what would need to be true for the finding to matter?
- **Proof-gap labeling** — Did the output clearly state what was not proven?
- **Reviewer confidence** — Did the reviewer trust the evidence enough to make a decision?

Finding quality metrics are especially useful when the customer's workflow is stuck in triage, validation, or prioritization.

## Slide 32/57 - Remediation and review metrics

Remediation and review metrics help determine whether the workflow supports movement from finding to reviewed action.

Useful measures may include:

| Metric area | What it checks |
|---|---|
| Patch quality | Are suggested changes narrow, understandable, and aligned to the confirmed finding? |
| Test or CI pass rate | Do relevant tests or checks pass where testing is approved and available? |
| Accepted fix rate | How often does engineering accept the remediation path as usable, with or without changes? |
| Time to reviewed fix | How long does it take to move from selected finding to reviewer decision? |
| Developer handoff quality | Does engineering have enough context to understand the issue, affected locations, expected behavior, and next action? |
| Reviewer burden | Does the workflow reduce the time or effort required for AppSec and engineering reviewers to decide? |
| Regression confidence | Does the evidence suggest the issue was addressed while legitimate behavior was preserved, within scope? |
| Remaining-risk summary quality | Does the output clearly state what risk remains and what still needs review? |

These metrics should only be used when remediation or review support is part of the approved evaluation scope.

A suggested fix is not the same as accepted remediation. The customer still owns review, testing, approval, merge decisions, release timing, and closure.

## Slide 33/57 - Operating and governance metrics

Operating metrics help the customer decide whether the workflow is practical to scale.

Useful measures may include:

| Metric | What it checks |
|---|---|
| Review time required per finding | How much human review time is needed to reach a decision? |
| Escalation rate | How often does the workflow hit unclear scope, access, evidence, or risk boundaries? |
| Rework required | How often do outputs need substantial correction before reviewers can use them? |
| Quality of retained evidence | Does the evaluation produce a review record that can be retained according to customer policy? |
| Fit with existing tools or systems of record | Can decisions, owners, and next actions be recorded in the customer's normal workflow? |
| Clarity of human control points | Are the moments of human review, decision, and approval explicit? |
| Efficiency measures | Where appropriate, the customer may measure cost, token use, or effort per reviewed finding. These should support the evaluation question, not replace quality metrics. |

Operating metrics are important because a workflow that works once may not be ready to scale.

The customer needs to know whether the process is repeatable, governable, and compatible with how security and engineering teams already work.

## Slide 34/57 - Real-world example: Identifying more findings is not the goal

Two pilot teams run bounded evaluations.

**Pilot A**

> Identifies many possible issues. Reviewers find that most are low-confidence, duplicated, or hard to act on. The pilot increases review burden because AppSec has to spend more time separating useful evidence from noise.

**Pilot B**

> Identifies fewer findings. Each finding includes clear source evidence, affected locations, severity rationale, reviewer guidance, proof gaps, and a bounded remediation path where approved. Reviewers can make decisions faster and engineering can understand the handoff.

Pilot B is more useful.

The customer did not get more activity. They got better decision quality. This is the type of evidence a Daybreak evaluation should produce.

## Slide 35/57 - Recommended exercise: Build an evaluation scorecard

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Help you practice choosing metrics that match the customer's workflow bottleneck.

**Task:** Review the fictional customer scenario and select six to eight metrics for the evaluation scorecard. Separate finding quality, remediation / review, and operating metrics.

Fictional customer excerpt:

> "Harborline Bank's AppSec lead says the team spends too much time validating scanner findings before sending anything to engineering. Engineering says tickets often lack enough evidence to act on. The CISO wants proof that the workflow can reduce risk, but the team is not ready for production testing or broad automation. Remediation suggestions may be reviewed only for confirmed findings."

**Estimated time:** 10 minutes

**Suggested output and reflection:** A short scorecard with metric name, what it measures, who reviews it, and what result would support expansion.

**Optional stretch:** Identify one metric that should not be used as a primary success measure and explain why.

Metric not to use as the primary success measure: total number of findings. Finding volume alone does not prove quality, actionability, or reduced risk.

## Slide 36/57 - Knowledge check

**Question:** A customer proposes measuring a Daybreak evaluation by "number of findings generated" and "number of repositories scanned." Their real bottleneck is that AppSec cannot tell which findings are valid, and engineering does not trust the handoff. Which scorecard is strongest?

- Number of automated patches generated, number of production systems tested, and number of findings closed without engineering review.
- **Finding validity, evidence usefulness, false-positive reduction, developer handoff quality, reviewer burden, and time to reviewed fix.** ✓ Correct
- Number of model refusals avoided, number of access requests submitted, and number of cyber-specialized workflows attempted.
- Total findings generated, total repositories scanned, total pages in the report, and number of issues ranked as high severity.

*Explanation: This works because the scorecard measures the customer's actual bottleneck: validation, evidence, trust, handoff quality, and reviewed action. Raw finding count and broad coverage do not prove decision quality, and automatic closure, production testing, or access-first metrics introduce the wrong evaluation focus.*

## Slide 37/57 - Summary

A strong scorecard measures whether the evaluation improved security decisions.

The best metrics are tied to the customer's bottleneck. They show whether findings were valid, evidence was useful, false positives were reduced, handoffs were clearer, remediation was reviewable, reviewer effort was manageable, and the workflow could fit existing governance.

A first evaluation should prove quality before scale.

## Slide 38/57 - Introduction (Module: Planning the evaluation rhythm)

A bounded evaluation needs more than a good target and scorecard. It also needs a clear rhythm for how the work will begin, how evidence will be reviewed, and when the customer will decide what happens next.

In this module, you'll plan the evaluation loop from preflight readiness through final review.

The goal is to keep momentum while preserving scope, human review, and evidence-led decision-making.

## Slide 39/57 - Plan the learning loop

A bounded evaluation needs a simple rhythm: plan, run the approved workflow, review the evidence, and decide next steps.

It should clarify:

- Whether the team is ready to begin
- What workflow will run
- Who reviews the evidence
- How remediation is handled, if in scope.
- When to stop and decide.
- What evidence would justify expansion.

The rhythm keeps momentum without turning the evaluation into a deployment plan, technical lab, or automation commitment.

Use this evaluation loop to see how a bounded pilot moves from scope to evidence to a next-step decision.

**Evaluation loop diagram:** Choose target → Define charter → Set metrics → Run approved workflow → Review evidence → Decide next step (Continue / Adjust / Expand / Pause / Stop / Escalate), which feeds back into Choose target.

## Slide 40/57 - Planning and preflight

Before the evaluation begins, confirm the basics.

| Evaluation area | Key question |
|---|---|
| Purpose and target | What question are we testing, and which approved asset or workflow are we evaluating? |
| Boundaries | What is in scope, what is out of scope, and what access, data, environment, or testing limits apply? |
| Accountability | Who owns review, decisions, and follow-up actions? |
| Success criteria | What evidence ceiling, success metrics, and expected outputs will determine whether the evaluation worked? |
| Safety controls | What stop conditions or escalation paths apply if scope, risk, authorization, data handling, or access becomes unclear? |

Preflight protects the evaluation. It confirms that the target is authorized, the reviewers are ready, and the evidence expectations are clear before any workflow begins.

A useful preflight question is:

> "What would make us stop?"

Strong stop conditions might include:

- The workflow requires access outside the approved target
- Runtime testing becomes necessary but is not approved
- Production systems become involved
- Findings imply urgent release or production risk
- Customer data handling is unclear.
- Remediation activity is requested but not approved
- The customer asks for cyber-specialized access before the workflow is scoped.

## Slide 41/57 - Run and review

The evaluation should proceed through a controlled run-and-review cycle.

A simple cycle is:

1. Run the approved Codex Security workflow against the bounded target. ✓ (Click to complete)
2. Review the report as an evidence package. ✓ (Click to complete)
3. Classify candidate findings, validated findings, false positives, suppressed findings, deferred items, and proof gaps. ✓ (Click to complete)
4. Decide whether any finding should move to remediation review. ✓ (Click to complete)
5. Keep human reviewers accountable for severity, acceptance, and next action. ✓ (Click to complete)

This is a planning rhythm, not a product setup guide. The exact workflow steps should be confirmed with the customer's security and technical owners. The report is not the decision. It is evidence for the decision.

Human reviewers should inspect whether the output includes:

- Scope reviewed
- Affected locations
- Source evidence
- Supported inference
- Confidence or uncertainty
- Proof gaps
- Reviewer guidance
- Remediation guidance, if in scope
- Remaining risk
- Next action

This keeps the workflow evidence-led rather than output-led.

## Slide 42/57 - Remediation review, if in scope

Remediation should only be included if it is approved in the charter. If remediation support is in scope, it should stay narrow and tied to confirmed findings.

A bounded remediation review should ask:

- Is the finding confirmed or sufficiently supported for remediation review?
- Is the proposed fix aligned to the root cause?
- Does the fix preserve intended behavior?
- Are relevant tests, CI checks, or review steps defined?
- Does engineering accept the approach?
- What proof gaps remain?
- Who owns final approval and release decisions?

Proposed fixes should be treated as reviewable outputs, not automatic merge decisions.

Codex Security can help prepare remediation guidance or suggested changes where approved.

The customer still owns engineering review, acceptance, testing, merge, release, and closure.

Safe phrasing sounds like this:

> "Codex Security may help prepare a reviewable remediation path for confirmed findings. The customer's engineering and security teams decide whether the change is correct, safe, accepted, and ready for release."

## Slide 43/57 - Checkpoints and final review

A first evaluation should include clear checkpoints.

**Planning checkpoint:** Is the scope ready? Are target, reviewers, evidence ceiling, and stop conditions clear?

**Initial review checkpoint:** Are findings useful and reviewable? Are proof gaps visible? Are reviewers able to make decisions?

**Remediation checkpoint:** If remediation is in scope, are fixes bounded, testable, and acceptable for human review?

**Final review checkpoint:** Did the evaluation produce enough evidence to continue, adjust, expand, pause, stop, or escalate? What remains untested, unobserved, or undecided.

The final review should produce a decision, not just a summary of activity.

A strong final review includes:

- What was reviewed
- What evidence was produced
- What reviewers decided
- What metrics show
- What remains unproven
- What should happen next
- Who owns the next action
- When the next decision will happen

## Slide 44/57 - Expansion criteria

Expansion should be based on evidence, not excitement.

Use this simple decision guide after the first evaluation.

| If the evidence shows... | The responsible next step is... |
|---|---|
| Findings are valid and useful, evidence quality is strong, and review burden is manageable. | Consider expanding to one adjacent repository, backlog slice, workflow, or team. |
| Human reviewers trust the workflow, and outputs fit the customer's existing systems of record. | Repeat the evaluation pattern with updated metrics and the same review discipline. |
| Remediation outputs are reviewable, where in scope, and governance and data-handling expectations are clear. | Expand carefully while preserving human review, evidence retention, and escalation paths. |
| The next scope cannot be bounded clearly. | Pause and tighten the proposed scope before expanding. |
| The customer wants production testing, critical infrastructure, exploit-heavy work, custom harnesses, headless CI/CD integration, broad autonomous testing, cyber-specialized access, special data-handling commitments, or unclear third-party / external targets. | Pause and escalate before making any recommendation. |

A strong expansion decision is narrow and evidence-led:

> "The evidence supports adding one adjacent repository or one additional backlog slice using the same review process and updated metrics."

A risky expansion decision is broad and excitement-led:

> "The first test was promising, so we should turn it on everywhere."

The discipline from the first evaluation should carry into the next one. Expansion is not the moment to loosen scope, skip review, or treat early promise as proof of readiness.

## Slide 45/57 - Real-world example: From one repository to broader coverage

A customer runs a first evaluation on one owned repository.

The review shows:

- Findings were supported by useful evidence
- Reviewers could separate valid findings from false positives
- Developer handoff quality improved
- Two confirmed findings received reviewable remediation guidance
- Reviewer burden was manageable
- Proof gaps were clearly labeled
- No production testing was performed.

The customer asks:

> "Can we now roll this out across every repository?"

A better next step is not "yes, everywhere."

A better next step is:

> "Based on the evidence, we can expand to one adjacent repository or one additional backlog slice with the same review model, updated success metrics, and the same evidence boundaries. Broader integration should come after the customer proves repeatability across a second bounded scope."

This keeps momentum while protecting governance and decision quality.

## Slide 46/57 - Recommended exercise: Build the evaluation rhythm

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Help you practice sequencing a bounded evaluation from planning to final decision.

**Task:** Create a simple evaluation timeline with checkpoints, reviewer actions, artifacts, and final decision options.

Fictional customer excerpt:

> "Harborline Bank has approved a first evaluation on the customer-account-service repository. The target is a defined slice of SAST findings. The AppSec lead and engineering manager are available for weekly review. Remediation support is allowed only for confirmed findings. Production testing is not approved. The CISO wants a decision at the end of the evaluation on whether to continue, adjust, expand, pause, or stop."

**Estimated time:** 8-10 minutes

**Suggested output and reflection:** A phase-by-phase evaluation rhythm that includes planning, run / review, remediation if in scope, final review, and expansion decision.

**Optional stretch:** Add one stop condition to each phase.

## Slide 47/57 - Knowledge check

**Question:** A first evaluation on one owned repository produced useful evidence, several validated findings, manageable reviewer burden, and one accepted remediation path. The customer now asks to embed the workflow into CI/CD across all repositories next week. What is the strongest recommendation?

- Agree to the CI/CD rollout because the first evaluation proved the workflow works and the customer is ready to automate.
- Shift the conversation to cyber-specialized model access because CI/CD integration requires a different access path.
- **Recommend adding one adjacent repository or backlog slice using the same review process and updated metrics, while treating CI/CD integration as a later step that requires stronger evidence, governance, and technical review.** ✓ Correct
- Pause all work because any expansion after a first evaluation is unsafe.

*Explanation: This works because expansion should be earned through evidence and kept bounded. A successful first evaluation may justify a narrow adjacent expansion, but broad CI/CD integration requires additional readiness, governance, and technical review. The response keeps momentum without overpromising automation or access.*

## Slide 48/57 - Summary

A strong evaluation rhythm moves from preflight to controlled execution, human review, optional bounded remediation review, and a final decision.

The purpose is not to keep running activity. The purpose is to produce enough evidence for the customer to decide what should happen next. Continue, adjust, expand, pause, stop, or escalate should be explicit outcomes.

## Slide 49/57 - Introduction (Module: Customer-ready evaluation recommendation)

A bounded evaluation plan only works when it is easy to communicate. The customer-ready recommendation should make clear:

- The workflow and first target
- The reviewers and success metrics
- What is out of scope
- The end decision
- What triggers pause or escalation

It should sound like a responsible plan to prove value, not a product pitch.

## Slide 50/57 - Review-readiness before sharing the plan

Before sharing the recommendation, check whether the evaluation plan is ready for customer or OpenAI review.

A ready plan should include:

- A clear evaluation question
- One approved target
- Defined in-scope and out-of-scope boundaries
- Named reviewers and decision owner
- Success metrics tied to the customer's workflow bottleneck
- Evidence expectations and known limits
- Stop conditions and escalation triggers
- A review process
- A final decision point.

If any of these are missing, the plan is incomplete.

You should not push the customer into a pilot too quickly. A rushed pilot can create weak evidence, unclear ownership, and disappointed stakeholders.

Customer-facing language sounds like this:

> "We are close, but I would tighten the evaluation plan before we start. We should confirm the reviewer, evidence ceiling, success metrics, and decision path so the pilot produces evidence the team can trust."

## Slide 51/57 - Decision paths after the evaluation

The evaluation should end with a decision.

Help customers prepare for one of six outcomes:

| Decision | What it means |
|---|---|
| Continue | The evaluation is useful, and the same scope should continue. |
| Adjust | The workflow is promising, but the target, metrics, evidence expectations, or review process needs refinement. |
| Expand | The evidence supports adding one adjacent repository, backlog slice, workflow, or team. |
| Pause | The evaluation needs stronger evidence, reviewer confidence, or resolution of scope, access, data, or governance questions. |
| Stop | The workflow does not appear useful for the customer's current need. |
| Escalate | The evaluation hits a boundary involving authorization, production testing, exploit-heavy activity, critical infrastructure, special access, unclear data handling, or another issue requiring customer, OpenAI, or technical SME review. |

A responsible recommendation does not assume success. It defines what each decision would mean.

Example:

> "If evidence quality is strong and reviewer burden is manageable, expand to one adjacent backlog slice. If findings are low-confidence or proof gaps dominate, adjust scope or metrics. If the workflow requires production testing or access outside the charter, pause and escalate."

That language shows the customer that expansion is disciplined, not automatic.

## Slide 52/57 - Real-world example: Customer wants to skip the pilot

A customer says:

> "We have seen enough to know this is promising. Can we move straight to broad rollout across multiple services?"

The partner should redirect the conversation toward an evidence-led first evaluation.

A strong response:

> "The interest is a good signal, but broad rollout should be earned through evaluation evidence. I recommend we start with one approved repository, application, backlog slice, vulnerability class, PR / diff pattern, or lower-level environment. We should agree on reviewers, success metrics, evidence expectations, and the decision path before expanding."

The customer may view this as slowing down. The partner should frame it as a way to move faster responsibly:

> "A bounded pilot gives the security and engineering teams enough evidence to decide what should scale, what should change, and what should stay out of scope."

The takeaway: Expansion should be earned through evaluation evidence, not assumed from early interest.

## Slide 53/57 - Recommended exercise: Draft the bounded evaluation plan

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Combine the target, charter, scorecard, evaluation rhythm, and customer-ready recommendation into one review-ready plan.

**Task:** Using the target, charter, metrics, and evaluation rhythm from earlier modules, complete a bounded evaluation plan that includes the evaluation question; target and rationale; in-scope and out-of-scope boundaries; named reviewers and decision owner; evidence ceiling and proof gaps; quality-based success metrics; checkpoints and timeline; stop conditions and escalation triggers; and final decision path.

Fictional customer follow-up note:

> "Thanks for the discussion. We want to understand whether Daybreak and Codex Security can help with our AppSec backlog. Our first priority is the customer-account-service repository because it has a high volume of scanner findings and engineering has pushed back on ticket quality. We want a practical recommendation we can share with the AppSec lead, engineering manager, and CISO before deciding whether to start."

**Estimated time:** 10-12 minutes

**Suggested output and reflection:** One completed bounded evaluation plan suitable for customer or OpenAI review.

## Slide 54/57 - Knowledge check

**Question:** A customer asks for a recommendation after an initial Daybreak conversation. The customer has one owned repository, a noisy scanner backlog, an AppSec reviewer, and an engineering owner. They also ask whether they can skip the pilot and move directly to broad rollout. Which recommendation is strongest?

- **Recommend a bounded first evaluation on the owned repository or backlog slice, with named reviewers, success metrics, evidence expectations, stop conditions, and a final decision path before any broader expansion.** ✓ Correct
- Recommend broad rollout because the customer has named a repository and already knows the backlog is important.
- Recommend automatic remediation across the backlog because engineering has already said ticket quality is a problem.
- Recommend applying for cyber-specialized access first so the customer can avoid workflow friction during the pilot.

*Explanation: This works because it packages the evaluation as a bounded, authorized, evidence-led plan. It preserves human review and decision-making while creating a responsible path to expansion. The other options jump too quickly into broad rollout, access-first framing, or automation.*

## Slide 55/57 - Summary

A customer-ready recommendation should turn the evaluation plan into a clear next step.

It should name the target, rationale, reviewers, metrics, evidence limits, timeline, decision path, and guardrails. It should help the customer understand what will be proven, what will remain out of scope, and what decision they can make at the end.

A strong recommendation moves the conversation from broad interest to a practical pilot decision.

## Slide 56/57 - Recap

A strong Daybreak evaluation starts with one bounded, authorized workflow that tests security decision quality.

In this course, you learned how to choose a safe first target, define scope and reviewers, set evidence expectations and metrics, plan the review rhythm, decide next steps, and package the plan as a customer-ready recommendation.

The goal is to prove value safely before expanding into broader coverage, deeper integration, production-adjacent work, or advanced cyber workflows.

## Slide 57/57 - Congratulations

Congratulations, you've completed this course!

You can now turn early Daybreak interest into a bounded, defensible evaluation plan. When customers want to move quickly, ask: "What is the one authorized workflow, bounded target, review path, and success metric set that would support the next decision?"

Keep the conversation focused on evidence, governance, human accountability, and responsible expansion.
