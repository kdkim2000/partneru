# OpenAI Technical Practitioner- Final Exam

## Slide 1/2 - Title

OpenAI Technical Practitioner- Final Exam

## Slide 2/2 - Assessment

**OpenAI Technical Practitioner- Final Exam**

20 questions. Get at least 16 correct to pass.

## Question 1

**Question:** What does technical fluency add to product familiarity?

- A guarantee that the first architecture will be correct
- The ability to choose the newest feature without discovery
- Permission to make specialist decisions without validation
- **Practical judgment about workflow, context, data, runtime, tools, evaluation, governance, and tradeoffs** ✓ Correct

Technical fluency helps partners frame and route solutions responsibly. It supports better questions and decisions without replacing detailed implementation or specialist validation.

*Source: Technical Fluency Orientation*

## Question 2

**Question:** A customer says, "We need an AI assistant." Which response shows the strongest practical technical judgment?

- Build a prototype before asking questions
- Recommend an agent because the request says assistant
- **Start with the workflow, then map the surface, capability or architecture, and deployment and operations** ✓ Correct
- Choose a model immediately

Technical routing starts with the workflow. The three decision axes separate where the work happens, what the system must do, and how it will run and be controlled. The combined route remains a starting hypothesis until the workflow, capability needs, deployment constraints, operating controls, and success criteria are clear.

*Source: Technical Fluency Orientation*

## Question 3

**Question:** When should an early technical recommendation be escalated to a specialist?

- Only after production launch
- Whenever a customer uses the word API
- Never, if the partner has completed Foundation
- **When detailed architecture, security, compliance, or platform behavior must be validated** ✓ Correct

Technical fluency supports a credible first recommendation and clear validation questions. Specialist involvement is appropriate when the decision requires depth beyond that boundary.

*Source: Technical Fluency Orientation*

## Question 4

**Question:** Which sequence best represents the implementation lifecycle?

- **Frame the workflow, confirm dependencies, prototype with safe inputs, add safeguards and evals, then test, release, monitor, and improve** ✓ Correct
- Prompt, copy, and publish
- Demo, buy, and stop
- Select a model and skip validation

Implementation is a lifecycle of connected decisions rather than a single build step. Teams frame the workflow, confirm dependencies, choose an interaction path, prototype safely, add safeguards, define evals, test and iterate, and prepare for release and ongoing improvement. They may revisit earlier decisions when testing reveals new constraints.

*Source: Technical Implementation Foundations*

## Question 5

**Question:** What does "implementation ready" mean?

- Every future decision is complete
- **The team has enough clarity on workflow, owners, interfaces, data, environments, controls, and validation to begin the next build step responsibly** ✓ Correct
- The customer has selected a model name
- A demo worked once

Readiness is evidence for action, not perfection. Important gaps must be resolved, owned, or treated as conditions before the team commits to build or release.

*Source: Technical Implementation Foundations*

## Question 6

**Question:** Why should API keys and other secrets be kept out of source code?

- To improve model reasoning
- To make requests run faster
- **To reduce the risk of accidental exposure and unauthorized access** ✓ Correct
- To eliminate the need for authentication

Secrets should be handled through controlled environment and access practices. Hard-coding them can expose credentials through repositories, logs, or shared files.

*Source: Technical Implementation Foundations*

## Question 7

**Question:** Why should rollback be planned before release?

- So ownership is unnecessary
- **So the team can restore a safe state if the change causes unacceptable behavior** ✓ Correct
- So testing can be skipped
- So every failure can be hidden

Release readiness includes recovery. Rollback planning clarifies how the team responds to a bad deployment and who owns the decision.

*Source: Technical Implementation Foundations*

## Question 8

**Question:** What should drive model selection first?

- Social-media popularity
- **Task shape, output requirements, risk, quality needs, latency, cost, and scale** ✓ Correct
- The model name
- The largest possible context window regardless of need

Durable selection begins with what the workflow must accomplish and the constraints it must satisfy. Model choice is a testable recommendation, not a brand preference.

*Source: Model Selection and Solution Patterns*

## Question 9

**Question:** A workflow needs fast classification at high volume with a simple structured output. Which approach is best?

- Choose based only on context-window size
- Use an agent with unrestricted tools
- Start with the most complex reasoning pattern available
- **Evaluate a simpler model class that meets quality, latency, cost, and structured-output requirements** ✓ Correct

The appropriate model is the simplest one that satisfies the task and risk requirements. A more complex model or agent may add cost and latency without improving the workflow.

*Source: Model Selection and Solution Patterns*

## Question 10

**Question:** How should a team validate a model-selection recommendation?

- With one impressive example
- By asking the model whether it is suitable
- **With representative eval cases tied to quality, failure, risk, latency, and cost expectations** ✓ Correct
- By relying only on public benchmark rankings

Evals test whether the selected pattern meets the actual workflow requirements. They should include normal cases, edge cases, and important failure conditions.

*Source: Model Selection and Solution Patterns*

## Question 11

**Question:** What is a platform building block?

- A mandatory feature used in every solution
- **A capability that plays a defined role such as interaction, context, action, orchestration, evaluation, or developer workflow support** ✓ Correct
- A complete architecture by itself
- A product marketing slogan

Building-block thinking maps capabilities to workflow needs. A solution should use the minimum useful set rather than combine features without a purpose.

*Source: Platform Capabilities and Developer Tools*

## Question 12

**Question:** When is retrieval or File Search relevant?

- When permissions should be ignored
- When no source material exists
- **When the workflow needs answers grounded in approved knowledge that is not reliably available in the model's current context** ✓ Correct
- Whenever the user asks a yes-or-no question

Retrieval supplies relevant source context at request time. Teams still need to validate source quality, freshness, access, and output behavior.

*Source: Platform Building Blocks and Developer Tools*

## Question 13

**Question:** A workflow retrieves information from an external system and may later update a record or trigger work. Which boundary is the strongest starting point?

- **Use a read-only lookup with access validation, source quality checks, and logging; require human approval before write-back** ✓ Correct
- Shared administrator credentials
- No logs or approvals
- Broad write access across all systems

Retrieving information and changing a business record have different control needs. A read-only lookup may require access validation, source quality checks, and logging. Write-back requires human approval, restricted actions, failure handling, testing, and clear ownership.

*Source: Platform Capabilities and Developer Tools*

## Question 14

**Question:** What is the difference between an architecture pattern and a solution blueprint?

- A pattern contains no technical decisions
- A blueprint is always a final detailed design
- They are unrelated concepts
- **A pattern is a reusable solution shape; a blueprint applies that shape to a specific workflow, data flow, tools, controls, and success measures** ✓ Correct

Patterns help teams recognize common approaches. A first-pass blueprint makes the selected approach concrete for the customer's context while leaving detailed design decisions for validation.

*Source: Architecture Patterns & Solution Blueprints*

## Question 15

**Question:** What should a retrieval-grounded blueprint make visible?

- Only the user interface colour
- **Approved sources, access, retrieval or context, output format, source references, evals, review, and escalation** ✓ Correct
- A guarantee that all answers are correct
- Only the model name

A retrieval-grounded blueprint should connect the user's task to approved source content and show how context is supplied, who owns and can access the sources, what the output and source evidence should look like, and how unsupported or sensitive cases will be evaluated, reviewed, or escalated.

*Source: Architecture Patterns & Solution Blueprints*

## Question 16

**Question:** When is human review required in a solution blueprint?

- Never if structured output is used
- **When the consequence, uncertainty, policy, or action risk requires a person to verify or approve the output** ✓ Correct
- Only after an incident
- Only when the model is slow

Review is a design component. Higher-impact or uncertain decisions need explicit checkpoints, reviewer roles, and evidence before action.

*Source: Architecture Patterns & Solution Blueprints*

## Question 17

**Question:** Which data questions belong in early technical discovery?

- None until after launch
- Only whether the data is stored in the cloud
- **What data is used, who owns it, how sensitive it is, who may access it, where it moves, and how long it is retained** ✓ Correct
- Only how many files exist

Data readiness and governance affect architecture, permissions, evaluation, and release decisions. These questions should be surfaced early.

*Source: Security, Governance & Data*

## Question 18

**Question:** What does least privilege mean?

- Give every user the same administrator access
- **Give each person or system only the access needed for its approved task** ✓ Correct
- Remove all authentication
- Let tools decide their own permissions

Least privilege limits the impact of mistakes or misuse. Permissions should align with role, workflow, and action boundaries.

*Source: Security, Governance & Data*

## Question 19

**Question:** A tool can issue refunds. What control is most important?

- **An approval boundary for consequential actions, with clear identity, logging, and escalation** ✓ Correct
- Anonymous shared access
- A longer system prompt only
- Removing transaction limits

Action-taking tools introduce operational risk. Approval gates and auditability help ensure that consequential actions remain authorized and reviewable.

*Source: Security, Governance & Data*

## Question 20

**Question:** Which statement best describes governance in technical solution work?

- Paperwork added only after production
- A guarantee that failures cannot occur
- A substitute for testing
- **A set of decision rights, controls, evidence, and ownership that helps the solution operate safely and accountably** ✓ Correct

Governance is a trust enabler when it is designed into the workflow. It clarifies who may act, what evidence is needed, and how risks are managed.

*Source: Security, Governance & Data*

## Result

**You passed the assessment!** Great work! You completed the assessment with **20 of 20 questions answered correctly.**

Course completed. Next up in OpenAI Technical Practitioner: **OpenAI Technical Practitioner Feedback** (Course, 2 min) — OpenAI Technical Practitioner Feedback form.
