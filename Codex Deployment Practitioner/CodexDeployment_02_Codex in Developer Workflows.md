# Codex in Developer Workflows

*OpenAI PartnerU — Full course transcript (56/56 slides)*

---

# Chapter: Match Codex Collaboration to Workflow Friction

## Introduction

Before mapping Codex into developer workflows, clarify the customer context and the decisions that will shape the recommendation.

In this module, you'll use the Cavendish Cables context, three workflow lenses, and six workflow threads to connect engineering friction to practical Codex collaboration choices.

The key question to think about is: How do you decide which Codex collaboration pattern fits the workflow, while keeping engineering ownership, review, and controls clear?

## Customer Context: Rocco Labs and Cavendish Cables

Throughout the course, you'll work with Rocco Labs, a fictional partner organization supporting a customer called Cavendish Cables. The engineering organization at Cavendish Cables is under pressure.

Teams are facing:
- Delayed releases
- Review bottlenecks
- Fragmented engineering context
- Inconsistent documentation
- Growing pull request queues
- Repeated debugging work
- Rising coordination overhead between teams

Engineering leadership believes Codex could help teams move work forward more efficiently. But leaders are cautious. They do not want AI-assisted workflows to create unreviewed code, unclear ownership, weaker quality controls, or unmanaged long-running work.

Rocco Labs needs to help Cavendish Cables answer four practical questions:
1. Where is the workflow friction across the SDLC?
2. What kind of Codex collaboration fits each workflow?
3. What do engineers still own?
4. What context, validation, review, and governance controls are needed?

A weak recommendation would say:
> "Use Codex to help developers work faster."

That is too broad. It does not explain where engineering work is slowing down, how Codex should collaborate, what engineers still own, or how the team will preserve quality.

A stronger recommendation would say:
> "Use Codex for interactive debugging support and governed pull-request review preparation, starting with one workflow where review friction is repeated, context is available, validation evidence can be returned, and a human reviewer remains accountable."

This course uses one Golden Principle:

**Match the collaboration pattern to the workflow — not the other way around.**

You'll return to this principle throughout the course. It helps keep Codex collaboration practical, reviewable, and accountable.

## Three Workflow Lenses

Use three lenses to evaluate Codex collaboration: Context, Agentic runtime, and Observability.

You may encounter these lenses in other Codex deployment courses. Here, you'll apply them specifically to developer workflow decisions.

| Lens | In developer workflow decisions, ask… |
|---|---|
| Context | What files, tickets, logs, test results, review expectations, engineering conventions, or operational constraints does Codex need? What should stay out of scope? |
| Agentic runtime | Where and how should Codex work: the Codex IDE extension, Codex CLI, the ChatGPT desktop app with Codex, Codex cloud, native GitHub code review, another asynchronous workflow, a review checkpoint, or a human-led workflow? Is the engineer actively steering the work, or is Codex working toward a bounded result? |
| Observability | What evidence should Codex return? What should the reviewer inspect? What remains uncertain? What should be visible before the workflow expands? |

A strong workflow recommendation answers three questions:
1. What does Codex need to know?
2. Where should Codex work?
3. What evidence should the team review?

Use these lenses to avoid treating Codex as a generic coding tool. The right collaboration pattern depends on the workflow friction, the context available, the runtime pattern, and the evidence needed for review.

## The Workflow Threads You'll Follow

As you move through the course, you'll follow six workflow threads.

1. **Workflow friction thread** — Where do developers lose time, continuity, or operational context across planning, implementation, review, testing, debugging, documentation, and handoff?
2. **Collaboration-pattern thread** — Should Codex support the engineer interactively, prepare evidence for a review checkpoint, or take on bounded delegated work?
3. **Engineer-ownership thread** — What decisions, approvals, and accountability must remain human-owned?
4. **Task-structure thread** — Is the request clear enough for useful Codex collaboration?
5. **Context-quality thread** — Does Codex have the information it needs without unnecessary or risky scope?
6. **Review-and-controls thread** — What evidence should Codex return, who inspects it, what requires approval, and what should trigger escalation?

If one thread is unclear, the recommendation is probably not ready yet.

## Knowledge Check

**Question:** Cavendish Cables has a recurring CI failure. Logs are available, the affected repository is known, and Codex is expected to identify likely causes and return evidence before any code changes happen. A reviewer will decide what to do next. Which collaboration pattern is the best fit?

Options:
- Autocomplete, because the main need is faster code suggestions.
- Pair programming, because the engineer should steer every step interactively.
- Stronger manual workflow, because all CI issues should stay fully human-led.
- Governed delegation, because the task is bounded, reviewable, and evidence-based. — **Correct answer**

Feedback: Governed delegation fits when the task has a clear boundary, approved context, reviewable evidence, and a human owner for decisions and follow-up.

## Summary

In this module, you analyzed engineering workflows before introducing Codex.

You learned to:
- Start with workflow friction, not code generation alone.
- Distinguish autocomplete, pair programming, agentic delegation, review checkpoints, and stronger manual workflows.
- Use the delegation readiness checklist to identify when governed delegation is appropriate.
- Keep judgment, approval, and accountability human-owned.

Next, you'll structure engineering collaboration so Codex has clearer goals, context, validation expectations, and stop conditions.

---

# Chapter: Analyze Engineering Workflows Before Introducing Codex

## Introduction

Before introducing Codex into a developer workflow, partners need to understand how engineering work actually moves.

In this module, you'll look beyond code generation and identify where developers repeatedly lose time, continuity, or operational context. You'll also practice distinguishing between autocomplete, pair programming, agentic delegation, review checkpoints, and workflows that should remain human-led.

This module teaches the core collaboration model. Later modules will apply that model across the SDLC rather than re-explaining it.

## Start with Workflow Continuity

A weak starting question is:
> "Where can AI generate code?"

A stronger starting question is:
> "Where do developers repeatedly lose time, continuity, or operational context?"

This matters because engineering bottlenecks often appear outside the act of writing code. Work may slow down during planning, implementation, review, testing, debugging, documentation, handoff, release preparation, or operational follow-up.

At Cavendish Cables, Rocco Labs looks for workflow friction such as:
- Repeated handoffs
- Fragmented documentation
- Duplicated troubleshooting
- Review delays
- Unclear ownership
- Coordination overhead
- Context switching
- Validation evidence that is missing or hard to interpret

Codex can only help if the workflow can be made clear enough to support collaboration, validation, and review.

For example, "developers want help with code" is too general.

"Reviewers repeatedly need implementation context, changed files, validation evidence, and open questions before they can review pull requests efficiently" is much more useful.

It points to a workflow, an output, and a possible review checkpoint.

## Rocco Labs Field Note: What the Team Is Hearing

During discovery, Rocco Labs hears the same issue from different people at Cavendish Cables.

A developer says:
> "I don't always need someone to write the code for me. Sometimes I need help finding the right place to start."

A test engineer says:
> "When debugging notes are missing, we repeat the same investigations and lose context between people."

A platform stakeholder says:
> "If Codex is going to help with longer-running work, we need to know what it used, what it changed, and what evidence came back."

These comments point to different kinds of collaboration. The developer may need interactive support. The reviewer may need Codex to prepare evidence before review. The test engineer may need better context continuity. The platform stakeholder may need boundaries and visibility before the workflow expands.

That is why this course is not only about "using Codex." It is about matching the collaboration pattern to the workflow moment.

## Visual: From Autocomplete to Agentic Delegation

AI-assisted engineering has evolved from small suggestions to more structured collaboration.

Early AI coding support often focused on autocomplete: helping a developer move faster in the moment by suggesting the next line or small block of code. That can be useful, but it only supports a narrow part of engineering work.

As AI-assisted engineering has matured, the collaboration pattern has expanded. Developers can now work with AI more interactively, using it to explain code, reason through debugging steps, compare implementation options, or draft tests. In more structured workflows, Codex can also take on bounded delegated tasks and return outputs for human review.

(Diagram: shows a progression/shift in responsibility and structure from Autocomplete → Pair programming → Agentic delegation.)

Use this progression to show why Codex should not be treated as simple autocomplete. As Codex moves from suggesting to doing, workflow structure, validation, and review become more important.

As the collaboration pattern becomes more agentic, the workflow needs more structure. Goals, scope, context, validation evidence, stop conditions, and review ownership become more important because Codex is doing more than suggesting. It is helping move work toward a result.

| Stage | What it does | Best fit | Human role |
|---|---|---|---|
| Autocomplete | Suggests small code completions. | Fast local edits or repetitive syntax. | The developer stays fully in control. |
| Pair programming | Supports interactive problem solving. | Explaining code, debugging, refactoring, drafting tests, and exploring implementation options. | The developer steers the work turn by turn. |
| Agentic delegation | Works toward a bounded goal and returns outputs for review. | Reviewable, verifiable, multi-step tasks with clear goals and validation expectations. | The human defines the task, reviews the output, and remains accountable. |

The shift matters because different collaboration models need different levels of structure. Autocomplete can stay lightweight because the developer remains in direct control. Pair programming needs enough context for useful back-and-forth.

Agentic delegation needs stronger goals, boundaries, validation evidence, and review expectations because Codex is working more independently toward a result.

## Compare Collaboration Models

Now compare the collaboration models more directly.

The progression from autocomplete to agentic delegation is useful, but real customer workflows are not always that simple.
- Some work should stay interactive.
- Some work can be delegated if the task is clear and reviewable.
- Some work should be treated as a review checkpoint, where Codex prepares evidence but a human still makes the decision.
- Some work should remain human-led until the workflow is clearer, safer, or better governed.

Use this comparison to decide which collaboration pattern fits the work.

| Collaboration model | What it does | Best fit | Watch out for |
|---|---|---|---|
| Autocomplete | Suggests small code completions. | Fast local edits or repetitive syntax. | Does not solve broader workflow bottlenecks. |
| Pair programming | Supports interactive problem solving with the developer in the loop. | Exploration, debugging, implementation guidance, and small refactors. | Can become messy if scope and context are unclear. |
| Agentic delegation | Carries out bounded work toward a defined goal and returns evidence. | Repetitive, reviewable, verifiable work that can run over multiple steps. | Requires clear goals, constraints, validation, and review. |
| Stronger manual workflow | Keeps the work human-led until the workflow is clearer or safer. | High-risk judgment, production approval, ambiguous requirements, or undefined ownership. | Should not become a permanent blocker if the workflow can be improved. |
| Review checkpoint | Uses Codex to prepare evidence, while the human decides. | Pull-request summaries, validation evidence, documentation drafts, and investigation notes. | The reviewer must still inspect the output before acting on it. |

For Cavendish Cables, Codex may support several patterns. The skill is choosing the right pattern for the workflow rather than assuming every workflow should be delegated.

## Where Does the Workflow Lose Time?

Now apply the collaboration model to specific workflow friction.

When customers describe engineering pain, they may start with broad statements like "reviews are slow," "debugging takes too long," or "documentation is inconsistent." Those statements are useful signals, but they are not yet workflow recommendations.

To make them actionable, you need to identify:
- Where the work loses time
- What kind of output would help
- Which collaboration pattern fits

The table below shows how a workflow issue might affect Codex collaboration.

| Workflow issue | Potential Codex support |
|---|---|
| Pull requests sit open because reviewers lack implementation context. | Review preparation. Codex may help summarize intent, files changed, validation evidence, and reviewer questions. |
| Engineers repeatedly investigate similar CI failures. | First-pass investigation. Codex may help summarize logs, identify likely causes, and propose next steps for review. |
| Documentation is updated inconsistently after implementation. | Documentation drafting. Codex may help produce drafts from approved change context for human review. |
| A team wants Codex to make production deployment approval decisions. | Not an early delegation candidate. Production approval should remain human-owned and requires defined governance and escalation paths. |
| Tickets often lack clear "done" criteria. | Improve the workflow first. Codex collaboration works better when goals, constraints, and validation expectations are clear. |

## Delegation Readiness Checklist

A task is more suitable for governed Codex delegation when it passes the delegation readiness checklist. This is the definitive checklist for the course. Later modules will refer back to it instead of restating the criteria.

A task should be:
- **Clear**: The goal can be stated plainly.
- **Bounded**: The task has a defined scope.
- **Context-supported**: Codex has the files, logs, tickets, or docs it needs.
- **Verifiable**: The team can check the result.
- **Reviewable**: A human can accept, revise, or reject the output.

**Stronger delegation example:**
> "Investigate this recurring CI failure using the provided failure output. Identify the likely cause, list the files inspected, and propose the smallest safe next step. Do not edit files until a reviewer approves the plan."

**Weaker delegation example:**
> "Fix the build."

The stronger version is clearer because it defines the goal, context, boundary, output, and review expectation.

A simple way to remember this is:

**Delegate bounded work. Keep judgment, approval, and accountability human-owned.**

## Human Judgment Remains Essential

Codex collaboration should improve workflow efficiency while preserving engineering trust.

Codex may help analyze, summarize, draft, investigate, or prepare evidence.

Humans remain accountable for decisions that affect architecture, prioritization, production approval, risk, quality, and final acceptance.

For every workflow, identify what Codex can support, what engineers still own, and what controls are needed.

That is the central discipline of DX2 (this course).

## Recommended Exercise: Create a Lightweight Workflow Collaboration Assessment

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** This activity helps you identify workflow areas appropriate for pair programming, governed delegation, review checkpoints, or stronger manual workflow.

**Task:** Rocco Labs has gathered several observations from Cavendish Cables:
- Pull request queues are growing because reviewers often lack context about implementation intent.
- Developers frequently recreate troubleshooting steps for recurring CI failures.
- Documentation is updated inconsistently after implementation work.
- Engineers want Codex to help with production deployment decisions, but approval paths are not defined.
- Several teams use different review expectations, which makes pull request quality inconsistent.
- Some developers want fast local help in the IDE, while others want longer-running tasks to continue asynchronously.
- Tickets often lack clear "done" criteria before engineering work begins.
- Engineering leaders want faster delivery but do not want to weaken quality or accountability.

Open the companion worksheet and complete Sections 1 and 3: Customer workflow friction and Collaboration-pattern selection. Choose one workflow and capture the repeated friction, how it affects software delivery, why it is worth addressing, the recommended collaboration pattern, and why that pattern fits.

**Estimated time:** 7 minutes

**Suggested output and reflection:** After completing your response, download the Recommended Exercise Reflection Guide for this activity (referenced PDF: "DX2-3.8 OpenAI Partner University _ Codex in Developer Workflows Course _ Reflection Guide 1.pdf", 3.3 MB).

Use it to compare your response with a strong example and reflect on whether your answer is specific, grounded in the workflow context, and clear about the reasoning behind your decisions.

**Optional deeper reflection:** Choose one additional workflow and explain why it should wait, be refined, or stay human-led for now.

## Knowledge Check

**Question:** Which workflow is the best candidate for governed Codex delegation?

Options:
- A production deployment approval decision where no approval path is defined.
- A recurring CI failure investigation where logs are available and a reviewer can inspect likely causes. — **Correct answer**
- A broad request to "modernize the whole service" without constraints.
- A recurring architectural decision about whether to replace a core system next quarter.

Feedback: This is a stronger delegation candidate because it is bounded, context-supported, and can return reviewable evidence before implementation work begins. Codex can summarize likely causes, but engineers still own decisions, approval, and final changes.

## Summary

In this module, you analyzed engineering workflows before introducing Codex. You started with workflow friction, compared collaboration patterns, identified tasks suited to governed delegation, and clarified what Codex can support, what engineers still own, and which controls are needed.

You now have the first part of your AI-native workflow recommendation for Cavendish Cables: a workflow collaboration assessment supported by the delegation readiness checklist.

Next, you'll improve task structure, context quality, and delegation clarity.

---

# Chapter: Structure Engineering Collaboration with Codex

## Introduction

Codex collaboration works best when the engineering task is structured before work begins.

At Cavendish Cables, Rocco Labs observes that many engineering tasks are poorly scoped. Tickets may have unclear requirements, fragmented context, missing validation expectations, or inconsistent workflow guidance. That makes work harder for humans and harder for Codex.

In this module, you'll improve task structure, context quality, and delegation clarity before work begins. This module teaches the delegation brief, which you'll reuse in later activities.

The key question to think about is: How can we make the work clear enough for useful Codex collaboration and human review?

## Why Task Structure Matters

A vague task can create confusion for both humans and Codex.

For example:
> "Fix the flaky test and clean up anything related."

This sounds practical at first. But it leaves too much open:
- Which test is flaky?
- Which files are relevant?
- What does "clean up" mean?
- Should Codex edit files or only investigate?
- What counts as a successful result?
- What should Codex avoid?
- What evidence should a reviewer receive?
- When should the work stop for human review?

When a request lacks structure, Codex may spend effort on the wrong area, expand the scope too broadly, or return output that is hard to inspect.

A stronger request does not need to be long. It needs to define the work clearly enough for collaboration, validation, and review.

## The Five Elements of a Stronger Delegated Task

A more effective delegated task gives Codex enough structure to work usefully and gives the human reviewer enough information to inspect the result.

This does not mean every prompt needs to be long. It means the task should make the important parts explicit: what Codex is trying to achieve, what context it should use, what is in or out of scope, how the result should be validated, and which related constraints or dependencies matter.

To achieve this, a stronger delegated task includes these five elements:

1. **Clear objective** — What should be true when the work is complete?
   - Weak: "Fix the issue."
   - Stronger: "Identify why the checkout test fails when the discount code is empty, propose the smallest safe fix, and return the likely root cause before editing files."

2. **Bounded scope** — What is in scope and out of scope?
   - Weak: "Clean up the code."
   - Stronger: "Limit investigation to the checkout validation flow and related tests. Do not refactor unrelated files."

3. **Expected output** — What should Codex return? Examples include a plan, summary, diff, test proposal, documentation draft, open questions, or validation summary.

4. **Validation expectation** — How should the work be checked? Examples include running a targeted unit test, returning the diff and files changed, identifying missing test coverage, or flagging anything that could not be verified.

5. **Dependency awareness** — What related systems, files, owners, or constraints matter? Examples include following existing patterns, avoiding public API changes, pausing for customer-facing behavior, or escalating security-sensitive work.

Together, these elements make the work more steerable for Codex and more inspectable for the reviewer.

## Use a Delegation Brief

A delegation brief is a concise way to structure Codex collaboration. It gives Codex a clear task and gives the human reviewer a clear way to inspect the result.

This is the course's definitive task-structure tool. Later activities will refer back to it.

| Brief section | Prompt |
|---|---|
| Goal | What should be true when the work is complete? |
| Context | What files, tickets, logs, screenshots, docs, or constraints should Codex use? |
| Scope | What is in scope, and what is out of scope? |
| Validation | What tests, checks, diffs, summaries, or review evidence should be returned? |
| Stop conditions | When should Codex pause and ask for help? |

This template is especially useful when the task moves beyond interactive pair programming and becomes delegated work.

A developer can use a lightweight version for simple tasks. A team can use a more complete version for review preparation, CI investigation, documentation drafting, or longer-running analysis.

## Before and After: Delegation Brief Example

**Weak request:**
> "Fix the failing checkout test."

This request does not explain where to look, what not to change, what evidence to return, or when to stop.

**Stronger delegation brief:**

| Brief section | Example |
|---|---|
| Goal | Investigate why the checkout test fails when the discount code is empty. Propose the smallest safe fix. |
| Context | Start with the failing test output and the checkout validation files. Follow existing patterns in nearby tests. |
| Scope | Stay within the checkout validation flow and related tests. Do not refactor unrelated files or change the public API. |
| Validation | Return the likely root cause, files inspected, proposed change, and targeted test command. If you make a change, return the diff and test result. |
| Stop conditions | Pause before editing if the issue appears to involve pricing logic, customer data, or deployment configuration. |

This is stronger because it gives Codex a goal, boundary, validation expectation, and clear point to pause. It also gives the human reviewer a better way to inspect the output.

## Practical Guide: Context Continuity

Context continuity means the work stays understandable as it moves through investigation, planning, implementation, validation, review, documentation, and follow-up.

For long-running or multi-step work, the team should be able to answer:
- What was the goal?
- What context was used?
- What files were inspected?
- What changed?
- What was tested?
- What remains uncertain?
- Who owns review?
- What next step was approved or deferred?

Context continuity matters because engineering work often passes between people, tools, and time windows. If the context is lost, the next person has to reconstruct what happened.

At Cavendish Cables, this shows up when one engineer investigates a CI failure, but the next engineer cannot see which logs were inspected, what was ruled out, or what test command should be run next.

Codex collaboration should reduce that fragmentation, not add to it.

## Context Continuity Habits

Context continuity does not happen automatically.

Teams need simple habits that make Codex collaboration easier to steer while the work is happening, easier to review when an output is returned, and easier to recover if the task drifts or needs to be handed off.

Use these habits to keep Codex collaboration easier to steer, review, and recover:
1. Start with the smallest useful context.
2. Point Codex to relevant files rather than broad directories.
3. Include logs, stack traces, or test output when debugging.
4. Define what "done" means.
5. Ask for a plan before broad changes.
6. Ask Codex to summarize what changed and what remains.
7. Keep review evidence attached to the workflow.
8. Start a fresh thread with a checkpoint if the work drifts.
9. Pause when the task touches sensitive logic, production behavior, or unclear ownership.

Remember, useful context makes Codex collaboration more steerable, reviewable, and recoverable.

Too little context can lead to shallow or misdirected work. Too much context can make the task harder to control.

The goal is not to give Codex everything. You need to provide enough approved information to support the workflow.

## Runtime Patterns as Collaboration Patterns

Treat Codex surfaces as collaboration patterns, not interchangeable choices.

A runtime decision is not just about where a developer prefers to work. It shapes how closely the human stays involved, how much structure the task needs, what context Codex can use, what evidence comes back, and where review or approval should happen.

| Surface or pattern | Best fit | Example request |
|---|---|---|
| Codex IDE extension | Fast, local implementation where the developer stays close to the code. | "Explain this function, suggest a smaller validation change, and draft the test update. Do not edit until I approve the plan." |
| Codex CLI | Terminal-native investigation, logs, scripts, or repeatable commands. | "Inspect the failing test output, identify likely files, and list the command you would run to verify the fix." |
| ChatGPT desktop app with Codex | Desktop-based engineering work that benefits from local context, multiple threads, visible task history, or reviewable outputs. | "Create a plan for updating documentation from this change set, then prepare a draft summary for review." |
| Codex cloud or asynchronous workflow | Longer-running delegated work that can return evidence for review. | "Investigate the recurring CI failure, summarize the likely cause, propose the smallest safe fix, and return validation evidence." |
| Native GitHub code review | Reviewing a GitHub pull request in the repository workflow, either on request or automatically when configured. | "@codex review this pull request and follow the repository review guidance in AGENTS.md." |

The operating question is: Does this task require interactive collaboration, or can it be delegated with clear context, validation, and review?

A runtime pattern should be selected because it fits the workflow. It should not be selected only because a team prefers a tool or wants to try a new interface.

## When to Involve a Technical or Security SME

This course does not require you to design a full technical control model. However, you should know when a workflow recommendation needs expert review before it goes further.

Involve a technical, platform, governance, or security SME when the workflow involves:
- New repository or workspace access
- Cloud or asynchronous execution
- Sensitive files, data, systems, or environments
- Tool or command execution beyond the initial boundary
- Production-impacting steps
- Audit, compliance, or policy reporting expectations
- Advanced integration patterns
- Unclear approval boundaries
- Elevated permissions
- Any action where the consequence of error is hard to reverse

Your role is not to solve those details alone. Your role is to identify that they matter and make sure the right experts are involved before the customer expands the workflow.

For Cavendish Cables, local debugging support may stay lightweight. A longer-running CI investigation, cloud workflow, broad repository analysis, or deployment-adjacent workflow should trigger additional validation.

## Recommended Exercise: Improve a Delegated Engineering Task

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** This activity helps you improve delegation quality through clearer engineering instructions.

**Task:** Cavendish Cables gives Rocco Labs the following request:
> "Use Codex to fix the flaky test and clean up anything related."

This request is too broad. It does not define the goal, scope, validation expectations, operational constraints, review output, or stop conditions.

Open the companion worksheet and complete Sections 8–12: Required context, Recommended runtime or collaboration pattern, Task structure, Validation evidence, and Review checkpoints. Rewrite the request as a clear delegation brief and define what Codex needs, where it should work, what evidence it should return, and where human review should happen.

**Estimated time:** 7 minutes

**Suggested output and reflection:** After completing your response, download the Recommended Exercise Reflection Guide for this activity (referenced PDF: "DX2-4.9 OpenAI Partner University _ Codex in Developer Workflows Course _ Reflection Guide 2.pdf", 3.3 MB).

Use it to compare your response with a strong example and reflect on whether your answer is specific, grounded in the workflow context, and clear about the reasoning behind your decisions.

**Optional deeper reflection:** Identify which collaboration pattern fits this task best: pair programming, governed delegation, review checkpoint, or stronger manual workflow first.

## Knowledge Check

**Question:** A developer asks Codex: "Fix this module and improve the tests." What is the main problem with this request?

Options:
- It lacks clear scope and review output. — **Correct answer**
- It asks Codex to work in the IDE instead of the CLI.
- It includes too much repository context.
- It should always be sent to a cloud workflow.

Feedback: A strong delegated task should define the goal, relevant context, boundaries, validation evidence, and review expectations before work begins.

## Summary

In this module, you learned to structure delegated Codex tasks, maintain context, select the right Codex surface and collaboration pattern, identify when SME input is needed, and define review and validation expectations before work begins.

You now have the second part of your AI-native workflow recommendation for Cavendish Cables: a clearer task-structure and collaboration-pattern approach.

Next, you'll apply Codex across the software-delivery lifecycle.

---

# Chapter: Apply Codex Across the Software-Delivery Lifecycle

## Introduction

Codex collaboration is most useful when it supports the way engineering work actually moves.

In this module, you'll apply the Golden Principle across the software-delivery lifecycle: Match the collaboration pattern to the workflow — not the other way around.

You'll map Codex into planning, implementation, review, testing, debugging, documentation, long-running tasks, and context continuity. For each workflow, you'll identify what Codex can support, what engineers still own, and what controls are needed.

The key question to think about is: Which collaboration pattern fits this workflow moment, and what must remain human-owned?

## SDLC Workflow Map: Codex Support, Engineer Ownership, and Controls

Codex collaboration is not limited to one moment in the software-development lifecycle.

It may support planning, implementation, review, testing, debugging, documentation, long-running work, and context continuity. But that does not mean Codex should be introduced everywhere at once.

Use this lifecycle map to evaluate where Codex collaboration fits. The point is not to force Codex into every step. The point is to make each workflow decision explicit.

| SDLC workflow | What Codex can support | What engineers still own | Controls needed |
|---|---|---|---|
| Planning | Summarize tickets, identify missing acceptance criteria, map dependencies, draft implementation plans, and highlight unclear requirements. | Prioritization, product tradeoffs, architecture direction, final acceptance criteria, and commitment to scope. | Approved ticket context, product-owner review, clear scope, decision owner, and stop conditions for ambiguous requirements. |
| Implementation | Explain code, suggest implementation options, draft small changes, scaffold tests, and follow existing patterns. | Design judgment, code quality, merge decisions, production-readiness decisions, and accountability for changes. | Scoped files, coding conventions, human review, targeted validation, and restrictions on broad refactoring or public API changes. |
| Review | Prepare local pull-request summaries and review evidence or—when native GitHub code review is configured—review the pull-request diff, follow applicable repository guidance, and post a standard GitHub code review. | Human reviewers still own approval, merge decisions, architectural judgment, risk acceptance, and feedback quality. | Choose the review pattern deliberately; use a named human reviewer, repository-specific guidance such as AGENTS.md where appropriate, required evidence, no autonomous approval or merge, and escalation for missing or sensitive context. |
| Testing | Suggest test cases, draft unit or integration tests, summarize failing tests, and identify likely coverage gaps. | Test strategy, acceptance of coverage, interpretation of quality risk, and decisions about release readiness. | Test scope, approved commands, expected outputs, validation records, and human confirmation before relying on results. |
| Debugging | Summarize logs, identify likely causes, inspect bounded files, propose next steps, and capture investigation notes. | Root-cause decision, fix approval, customer-impact assessment, and production incident ownership. | Approved logs, repository boundary, command restrictions, stop conditions, and escalation for sensitive or production-impacting findings. |
| Documentation | Draft release notes, update technical docs, summarize changes, create handoff notes, and explain repository behavior from approved context. | Accuracy, publication, customer-facing wording, policy-sensitive language, and final approval. | Approved source context, documentation owner, review before publication, and restrictions on confidential or unapproved details. |
| Long-running tasks | Run bounded investigation, dependency mapping, refactor preparation, or asynchronous analysis that returns a plan, diff, or evidence for review. | Task approval, environment risk, final acceptance, and decisions to continue, stop, or escalate. | Defined goal, repository and environment access approval, checkpoints, validation evidence, activity visibility, and SME review for higher-risk work. |
| Context continuity | Capture what was inspected, what changed, what was tested, what remains uncertain, and what the next reviewer needs. | Maintaining team standards, deciding what becomes source of truth, and approving handoff notes. | Context summary template, storage location, owner review, source boundary, and process for correcting incomplete or inaccurate summaries. |

This table is the heart of the course. For each workflow, a strong recommendation should name all three parts: Codex support, engineer ownership, and controls.

## Planning Workflows

Planning workflows determine whether engineering work starts with enough clarity. If the plan is vague, the downstream workflow usually becomes harder to implement, test, review, document, and hand off.

**What can Codex support?** Codex can summarize ticket context, identify missing acceptance criteria, map dependencies, draft implementation plans, and flag unclear requirements.

**What do engineers still own?** Engineers and product stakeholders still own prioritization, tradeoff decisions, architecture direction, final acceptance criteria, and scope commitment.

**What controls are needed?** Use approved ticket context, product-owner review, clear scope, named decision ownership, and stop conditions when requirements are ambiguous.

At Cavendish Cables, planning friction often appears when tickets lack "done" criteria or dependencies are unclear. A good recommendation would not say, "Codex should plan the work." It would say, "Codex can help identify missing planning information and draft a plan for human review."

## Implementation Workflows

Implementation workflows are where many teams first imagine using Codex, but implementation support still needs boundaries.

Codex can be useful when engineers need help understanding code, exploring implementation options, drafting small changes, scaffolding tests, or following existing patterns in a codebase.

This is often where interactive pair programming works well because the engineer can guide the work, inspect suggestions, and make decisions turn by turn.

However, implementation work can become risky when the scope is too broad or the task is treated as open-ended.

A request such as "clean up the service" or "improve this module" may touch design choices, public behavior, dependencies, tests, or production-sensitive logic.

In those cases, Codex needs a clearer goal, bounded scope, validation expectations, and review checkpoint before the work should continue.

Use the table below to distinguish what Codex can support, what engineers still own, and what controls are needed.

| Question | Implementation workflow guidance |
|---|---|
| What can Codex support? | Codex can explain code, suggest implementation options, draft small changes, scaffold tests, follow existing patterns, and help an engineer reason through local implementation decisions. |
| What do engineers still own? | Engineers and documentation owners still own accuracy, publication, customer-facing wording, policy-sensitive language, and final approval. |
| What controls are needed? | Use approved source context, documentation owner review, review before publication, storage location for context summaries, and restrictions on confidential or unapproved details. |

*(Note: as presented on this page, the "engineers own" and "controls" rows above reuse documentation-workflow language, likely a course content artifact — treat "engineers still own" generally as design judgment, code quality, merge decisions, and production-readiness decisions, consistent with the earlier SDLC map.)*

The best implementation workflows are usually interactive or guided at first. If implementation becomes delegated, the task should pass the delegation readiness checklist and use the delegation brief.

## Review Workflows

Review workflows are strong candidates for Codex support because they often involve repeated friction, reviewable outputs, and explicit human decision points.

In many engineering teams, review slows down not because reviewers lack expertise, but because the information they need is incomplete or scattered.

Reviewers may need to reconstruct implementation intent, inspect changed files, find test evidence, identify missing validation, or ask the same clarification questions across multiple pull requests.

Pull-request support can take two distinct forms:
- In **local or interactive review preparation**, Codex helps assemble context and evidence for a human reviewer.
- In **native GitHub code review**, a reviewer can request @codex review or use configured automatic reviews; Codex reviews the pull-request diff, follows applicable repository guidance from AGENTS.md, and posts a GitHub code review.

In both patterns, people retain approval and merge decisions.

| Question | Review workflow guidance |
|---|---|
| What can Codex support? | Codex can prepare local pull-request summaries and review evidence or—when native GitHub code review is configured—review the pull-request diff, follow applicable repository guidance, and post a standard GitHub code review. |
| What do engineers still own? | Human reviewers still own approval, merge decisions, architectural judgment, risk acceptance, and feedback quality. |
| What controls are needed? | Use a named human reviewer, choose local preparation or native GitHub review, supply repository guidance such as AGENTS.md where appropriate, require review evidence, prevent autonomous approval or merge, and escalate missing or sensitive context. |

For Cavendish Cables, the first decision is whether the workflow needs local review preparation or native GitHub code review. Either pattern can reduce repeated review friction, but a human reviewer still decides what is acceptable and whether the pull request should be approved or merged.

## Testing and Debugging Workflows

Testing and debugging often create repeated work and lost context. Codex may help capture investigation logic and improve validation visibility, but engineers still own the quality decision.

**Testing workflows**

| Question | Testing workflow guidance |
|---|---|
| What can Codex support? | Codex can suggest test cases, draft unit or integration tests, summarize failing tests, and identify likely coverage gaps. |
| What do engineers still own? | Engineers own test strategy, acceptance of coverage, interpretation of quality risk, and release-readiness decisions. |
| What controls are needed? | Use test scope, approved commands, expected outputs, validation records, and human confirmation before relying on results. |

**Debugging workflows**

| Question | Debugging workflow guidance |
|---|---|
| What can Codex support? | Codex can summarize logs, identify likely causes, inspect bounded files, propose next steps, and capture investigation notes. |
| What do engineers still own? | Engineers own root-cause decisions, fix approval, customer-impact assessment, and production incident ownership. |
| What controls are needed? | Use approved logs, repository boundaries, command restrictions, stop conditions, and escalation for sensitive or production-impacting findings. |

Recurring CI investigation may become a governed-delegation candidate if logs, repository access, command boundaries, review ownership, and validation expectations are clearly defined.

## Documentation and Context-Continuity Workflows

Documentation and context continuity are often overlooked, but they shape how engineering work survives handoff, review, release, and future maintenance.

When documentation is incomplete or context is scattered, teams lose time later. Reviewers may not understand why a change was made. Developers may repeat the same investigation. Release owners may struggle to explain what changed. Future maintainers may have to reconstruct decisions from tickets, pull requests, logs, and chat threads.

| Question | Documentation and continuity guidance |
|---|---|
| What can Codex support? | Codex can draft release notes, update technical docs, summarize changes, create handoff notes, explain repository behavior, and capture what was inspected, changed, tested, and left unresolved. |
| What do engineers still own? | Engineers and documentation owners still own accuracy, publication, customer-facing wording, policy-sensitive language, and final approval. |
| What controls are needed? | Use approved source context, documentation owner review, review before publication, storage location for context summaries, and restrictions on confidential or unapproved details. |

At Cavendish Cables, inconsistent documentation is not just a writing problem. It creates continuity problems. Codex may help draft documentation, but a human owner must review and approve what becomes the source of truth.

## Long-Running and Asynchronous Workflows

Long-running and asynchronous workflows can be powerful, but they require stronger structure because Codex is working more independently.

In an interactive workflow, the engineer can steer Codex turn by turn. In a longer-running or asynchronous workflow, Codex may continue investigating, preparing, or producing outputs while the human is not actively guiding every step.

That can be useful for work such as recurring CI investigation, dependency mapping, refactor preparation, repository analysis, or other bounded tasks that need time to complete.

The tradeoff is that the workflow must be clearer before it begins. Codex needs a defined goal, approved context, a clear boundary, validation expectations, and stop conditions. The team also needs to know what evidence will come back, who will review it, and what requires approval before the work continues.

| Question | Long-running workflow guidance |
|---|---|
| What can Codex support? | Codex can run bounded investigation, dependency mapping, refactor preparation, repository analysis, or asynchronous work that returns a plan, diff, or evidence for review. |
| What do engineers still own? | Engineers still own task approval, environment risk, final acceptance, and decisions to continue, stop, or escalate. |
| What controls are needed? | Use defined goals, repository and environment access approval, checkpoints, validation evidence, activity visibility, stop conditions, and SME review for higher-risk work. |

Long-running work should not be introduced just because it is possible. It should be introduced only when the task is clear, bounded, context-supported, verifiable, reviewable, and visible enough for the team to trust.

## Controls Across the SDLC

Across the SDLC, the same control questions keep appearing.

These questions help you decide whether a Codex collaboration pattern is ready to use, needs more structure, or should remain human-led for now.

| Control question | Why it matters |
|---|---|
| What is in scope? | Keeps Codex focused on the intended workflow, files, logs, tickets, or repositories. |
| What is out of scope? | Prevents broad refactoring, unrelated investigation, sensitive data exposure, or production-impacting action. |
| What evidence should Codex return? | Makes human review practical and supports continuity across handoffs. |
| Who reviews the output? | Preserves human ownership and accountability. |
| What requires approval? | Creates boundaries before Codex continues or expands the task. |
| What should trigger escalation? | Protects the workflow when ambiguity, failed validation, sensitive logic, or elevated risk appears. |
| What would justify expansion? | Keeps rollout evidence-based rather than enthusiasm-based. |

Remember to always use these questions before recommending that a workflow move from interactive support to governed delegation or from a small pilot to broader adoption.

If the answers are unclear, the workflow may need a stronger delegation brief, clearer review expectations, or additional technical, platform, governance, or security validation before Codex is introduced.

## Recommended Exercise: Map Codex Collaboration Across the SDLC

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** This activity helps you apply the Golden Principle across real engineering workflows.

**Task:** Cavendish Cables has identified five workflow moments where Codex may help:
- A developer is actively debugging a local issue and wants help understanding a failing function.
- A recurring CI failure has logs, a scoped repository, and a defined reviewer. Codex should summarize likely causes before any code changes.
- Engineering leadership wants Codex to make production deployment approval decisions. Approval paths are not defined.
- A pull request is ready for review. Cavendish Cables must decide whether Codex should prepare local review evidence for a human reviewer or use native GitHub code review through @codex review or configured automatic reviews.
- A developer wants Codex to "clean up the whole service" without scope, constraints, or validation expectations.

Open the companion worksheet and complete Sections 2 and 4–7: SDLC workflow map, Recommended pair-programming workflows, Recommended governed-delegation workflows, Workflows requiring stronger manual control, and Codex support, engineer ownership, and controls. Choose one or more workflow moments and identify the collaboration pattern, what Codex can support, what engineers still own, and what controls are needed. For the pull-request workflow, distinguish local review preparation from native GitHub code review and explain the repository guidance and human ownership required.

**Estimated time:** 7 minutes

**Suggested output and reflection:** After completing your response, download the Recommended Exercise Reflection Guide for this activity (referenced PDF: "DX2-5.9 OpenAI Partner University _ Codex in Developer Workflows Course _ Reflection Guide 3.pdf", 3.3 MB).

Use it to compare your response with a strong example and reflect on whether your answer is specific, grounded in the workflow context, and clear about the reasoning behind your decisions.

**Optional deeper reflection:** Choose one second workflow and explain what would need to change before it could move to governed delegation.

## Knowledge check

Match each workflow moment to the most appropriate collaboration pattern.

| Workflow moment | Correct collaboration pattern |
|---|---|
| A developer wants interactive help understanding a local function | Pair programming |
| A team asks Codex to approve a production deployment with no approval path | Stronger manual workflow |
| Codex prepares pull-request evidence before a human reviewer decides | Review checkpoint |
| Codex investigates a recurring CI failure using approved logs and returns likely causes | Governed delegation |

**Correct answer:** All four pairs above are correct as matched (Pair programming / Stronger manual workflow / Review checkpoint / Governed delegation).

## Summary

In this module, you applied Codex collaboration patterns across the software-delivery lifecycle, using the Golden Principle: match the collaboration pattern to the workflow, not the other way around.

You mapped what Codex can support across planning, implementation, review, testing, debugging, documentation, handoff, context continuity, and long-running engineering work, while keeping clear what engineers still own and which controls are needed.

You now have the third part of your recommendation for Cavendish Cables: a lifecycle-level view of where Codex collaboration fits across developer workflows.

Next, you'll consolidate those decisions into a governed AI-native engineering workflow recommendation.

---

# Chapter: Build Governed AI-Native Engineering Workflows

## Introduction

Build governed AI-native engineering workflows

AI-native engineering does not mean every task should be delegated.

A practical AI-native workflow uses the right collaboration pattern for the work. Some workflows need close, interactive support. Others can be delegated if the goal, context, constraints, validation, and review expectations are clear.

Some should remain human-led until the workflow is safer or better defined.

## Putting It all together

In this module, you'll consolidate the decisions you have made throughout the course.

Use your earlier outputs:
- Workflow-friction assessment and collaboration-pattern selection.
- Required context, runtime or collaboration pattern, delegation brief, validation evidence, and review checkpoints.
- SDLC workflow map showing Codex support, engineer ownership, and controls.

The key question to think about is: Where can Codex collaboration improve developer workflows while preserving engineering trust?

## Use the Collaboration Pattern Decision

At this point in the course, you have identified workflow friction, compared collaboration models, structured delegated tasks, and mapped Codex across the SDLC.

Now you need to bring those decisions together. Use the Golden Principle:

Match the collaboration pattern to the workflow — not the other way around.

This principle helps Rocco Labs avoid recommending Codex in a generic way. The same customer environment may need several different patterns at once. The decision should depend on the workflow condition, not on a desire to use the most advanced form of AI assistance.

Use the table below to match the workflow condition to the recommended collaboration pattern.

| Workflow condition | Recommended pattern |
|---|---|
| The engineer needs to explore, learn, or steer continuously. | Pair programming. |
| The task passes the delegation readiness checklist. | Governed delegation. |
| The output supports a human decision but does not make the decision. | Review checkpoint. |
| The workflow includes production approval or high-risk judgment. | Stronger manual workflow. |
| The request is broad, vague, or missing context. | Improve task structure first. |

## Test Delegation Readiness Before Expanding

Before recommending governed delegation, consider the delegation readiness checklist encountered earlier in this course.

A workflow should be: Clear, Bounded, Context-supported, Verifiable, Reviewable.

If the answer is "no" for any item, do not force the workflow into delegation. Improve the task structure first using the delegation brief introduced earlier.

Poor delegation candidates include:
- Ambiguous requirements
- Undefined business rules
- Sensitive production actions
- High-risk architectural decisions
- Unrestricted repository access
- No human reviewer
- No validation path
- No escalation path

This keeps the final recommendation focused. The goal is not to delegate more work. The goal is to recommend the right collaboration pattern for the workflow.

## What Must Stay Visible in a Governed Workflow?

A governed AI-native engineering workflow should make the important parts of the work visible.

Visibility is what allows a team to trust Codex collaboration.

If people cannot see what Codex was asked to do, what context it used, what it inspected, what it changed or produced, and what still needs human judgment, the workflow becomes difficult to review and difficult to govern.

A strong governed workflow makes the handoff clear.

Engineers should be able to inspect the output, understand the evidence, identify the reviewer, see what requires approval, and know when the work should pause or escalate.

Use the table below as a final visibility check before recommending workflow expansion.

| Visibility question | What to define |
|---|---|
| What can Codex access? | Repositories, files, logs, tickets, tools, environments, or actions in scope. |
| What is Codex being asked to do? | Interactive support, guided work, bounded delegation, review preparation, or long-running asynchronous work. |
| What did Codex inspect or produce? | Files reviewed, evidence returned, changes proposed, tests considered, command outputs, open questions, or limitations. |
| What should the human reviewer inspect? | Diff, test result, summary, command output, assumption, missing evidence, open question, or review note. |
| What requires approval? | Actions that must stop until a human confirms the next step. |
| What should trigger escalation? | Sensitive logic, unclear ownership, failed validation, broader scope than expected, or production-impacting risk. |

## Bring the Recommendation Together

You have now made four connected decisions:
1. You identified where Cavendish Cables loses time, continuity, or operational context.
2. You distinguished collaboration patterns: autocomplete, pair programming, governed delegation, review checkpoint, and stronger manual workflow.
3. You improved task structure with a delegation brief.
4. You mapped Codex collaboration across the software-delivery lifecycle.

The final step is to turn those decisions into a recommendation leaders can act on.

Do not start again. Reuse your outputs from earlier modules and consolidate them into one AI-native engineering workflow recommendation.

Your recommendation should answer:
- Where is the workflow friction?
- How does that friction appear across the SDLC?
- Which workflows should use pair programming?
- Which workflows are suitable for governed delegation?
- Which workflows require stronger manual control?
- What can Codex support in each recommended workflow?
- What do engineers still own?
- What controls are needed?
- What context does Codex need?
- Where should Codex work?
- What validation evidence should Codex return?
- Where do review checkpoints happen?
- What evidence would support expansion?

## Recommended Exercise: Create an AI-Native Engineering Workflow Recommendation

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** This activity helps you synthesize workflow, delegation, validation, and governance decisions for Cavendish Cables.

**Task:** Rocco Labs needs to recommend how Cavendish Cables should introduce Codex collaboration into developer workflows without weakening engineering ownership, validation, or review quality.

Open the companion worksheet and complete Sections 13–15: Governance and operating boundaries, Expansion evidence, and Recommendation summary. Use your earlier decisions to define the approved boundary, restricted actions, approval requirements, visibility needs, expansion evidence, and final recommendation summary.

**Estimated time:** 8 minutes

**Suggested output and reflection:** After completing your response, download the Recommended Exercise Reflection Guide for this activity (referenced PDF: "DX2-6.6 OpenAI Partner University _ Codex in Developer Workflows Course _ Reflection Guide 4.pdf", 3.3 MB).

Use it to compare your response with a strong example and reflect on whether your answer is specific, grounded in the workflow context, and clear about the reasoning behind your decisions.

## Knowledge check

Which recommendation best maps Codex into the SDLC while preserving engineering ownership?

- Codex should only be used for autocomplete because lifecycle workflows are too complex to support.
- Codex should approve production deployments when review queues become too long.
- Codex should take over planning, implementation, review, testing, and release decisions because it can work across the entire lifecycle.
- Codex should support bounded workflow moments such as ticket clarification, implementation assistance or review evidence prep, while engineers retain decisions, approvals, and accountability.

**Correct answer:** "Codex should support bounded workflow moments such as ticket clarification, implementation assistance or review evidence prep, while engineers retain decisions, approvals, and accountability."

Feedback: The strongest recommendation maps Codex into practical workflow moments while preserving human ownership. Codex can support evidence preparation, drafting, investigation, and continuity, but engineers still own decisions, approval, quality, and accountability.

## Summary

In this module, you consolidated your earlier decisions into a governed AI-native engineering workflow recommendation for Cavendish Cables.

The key takeaway is: Codex collaboration should expand where work is clear, reviewable, validated, governed, and tied to workflow continuity — not simply where automation seems possible.

**Worksheet checkpoint:** Before moving to the wrap-up, use Section 16: Final readiness check in the companion worksheet. If any answer is unclear, refine the recommendation or seek SME validation before using it in a customer conversation.

# Chapter: Wrap Up

## Recap

In this course, you practiced matching Codex collaboration to real developer workflow friction.

You looked across the software-delivery lifecycle, selected collaboration patterns, structured delegated work, and identified what Codex can support, what engineers still own, and what controls are needed.

## Congratulations

Congratulations, you've completed this course!

As you apply this learning with customers, return to the Golden Principle: Match the collaboration pattern to the workflow — not the other way around.

Use that principle to help customers decide where Codex should support engineers interactively, where it can take on bounded delegated work, where it can prepare evidence for review, and where the workflow should remain human-led until it is clearer or safer.

A strong recommendation does more than list Codex features. It maps Codex into the customer's software delivery lifecycle, clarifies what engineers still own, and defines the controls needed for workflow continuity, validation, and trust.

---

*End of course: "Codex in Developer Workflows" (56/56 slides). This was the final module of the program — the program contained no further chapters corresponding to files 07 onward (e.g., "Codex Security, Governance and Controls", "Advanced Codex Workflow Integration", etc. were not found as additional chapters within this program and may belong to a separate OpenAI PartnerU program/course not yet opened in this session).*
