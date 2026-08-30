# Codex Essentials

## Slide 1/43 - Title

Codex Essentials

Created July 2026

## Slide 2/43 - Introduction

Software development involves more than writing code. Teams also investigate issues, test changes, review work, document systems, and support existing applications.

Codex is OpenAI's coding agent for software development. It helps engineering teams move beyond one-off coding assistance toward agentic software delivery, with humans providing direction, context, review, and judgment.

You do not need to be a developer to take this course. The goal is to build practical baseline fluency in where Codex fits and why it matters for software delivery.

## Slide 3/43 - What you'll learn

By the end of this course, you'll be able to:

- Explain what Codex is and how it supports software development workflows.
- Describe how Codex differs from traditional coding assistance.
- Identify common software delivery workflows where Codex can create value.
- Explain the concept of agentic software delivery at a foundational level.
- Describe why organizations are exploring AI-assisted software delivery.

Let's get started!

## Slide 4/43 - What Codex is and why it matters

Codex is part of the OpenAI portfolio because software delivery has its own workflows, users, and challenges. This matters because an engineering need should not be treated as general employee productivity or an API build by default. Start by understanding whether the work is really about software delivery.

In this module, you'll build a foundation for understanding what Codex is, why it exists, and how it differs from ChatGPT and the OpenAI API.

As you move through the module, focus on the role Codex plays for engineering teams: helping them work across software delivery tasks while humans continue to guide, review, and approve the work.

## Slide 5/43 - What Codex is

Codex is OpenAI's coding agent for software development. That means Codex is designed to support software work—not simply generate a code snippet in response to a prompt.

In a simple coding-assistance interaction, a developer might ask for a function, explanation, or suggestion. The developer then has to copy, adapt, test, and integrate that output manually.

Codex introduces a broader pattern. It can support work across the software delivery workflow by helping teams understand code, investigate issues, implement changes, support testing and review, and maintain documentation.

At this level, focus on both the role Codex plays and the main places teams may use it. Depending on plan and configuration, teams may use Codex through the ChatGPT desktop app, Codex CLI, IDE extension, Codex cloud, and supported GitHub workflows. Capabilities such as skills, approvals, automations, and parallel-agent work vary by surface, workspace settings, permissions, and configuration.

Codex helps engineering teams work toward software delivery outcomes while humans remain responsible for direction, review, approval, and final decisions.

This is why Codex belongs in the OpenAI portfolio as the solution path for engineering and software delivery work.

## Slide 6/43 - Why Codex exists

Software delivery is complex because building software is much more than writing new code.

Engineering teams regularly spend time on activities such as:

- Understanding systems and requirements.
- Investigating issues and defects.
- Implementing and improving software.
- Testing and validating changes.
- Reviewing work and maintaining quality.
- Creating documentation and sharing knowledge.
- Maintaining existing systems.

As software systems grow, these activities can become harder to coordinate.

Codebases get larger. Dependencies increase. Legacy systems need support. Teams face pressure to deliver faster while maintaining quality.

Traditional coding tools often help with one part of this work: producing code. That can be useful, but it does not address the whole software delivery workflow.

Codex exists because many engineering challenges are workflow challenges.

Teams may not only need help writing code faster. They may need help understanding what to change, applying a change safely, validating behavior, reviewing results, and maintaining the knowledge around the system.

That is the shift this course will explore: from using AI to generate code toward using AI to help engineering teams complete software delivery tasks across multiple steps.

## Slide 7/43 - Comparing Codex with ChatGPT and API

Codex is one OpenAI solution path. It helps to compare it with ChatGPT and the OpenAI API so you can recognize where each one typically fits.

**ChatGPT**

Supports end-user productivity and guided knowledge work.

ChatGPT is often a strong fit when people need a ready-to-use workspace for asking questions, drafting, researching, analyzing, and iterating.

Within ChatGPT, Chat supports collaborative thinking and creation, while ChatGPT Work supports delegated knowledge work.

**OpenAI API**

Supports building AI into products, applications, and workflows.

The API is often a strong fit when organizations need custom AI-powered experiences, integrations, or product features.

**Codex**

Supports software delivery work for engineering teams. In this course, we'll refer to this broader approach as agentic software delivery: using AI to help engineering teams complete software delivery tasks across multiple steps, while humans continue to provide direction, context, review, and approval.

Codex is often a strong fit when organizations need help with engineering workflows such as understanding code, investigating issues, making changes, testing, reviewing, documenting, or maintaining software.

A simple way to remember the difference:

- ChatGPT: People collaborate with or delegate knowledge work in a workspace.
- API: Builders embed AI into products, applications, or workflows.
- Codex: Engineering teams use AI to support software delivery work.

**Diagram:** Three columns — ChatGPT (Chat: Collaborate / Work: Delegate), OpenAI API (Embedded + custom AI), Codex (Software delivery work: ChatGPT desktop app, Codex CLI, IDE extension, Codex cloud, GitHub workflows) — with a "Build + Maintain" arrow connecting Codex back to the OpenAI API column.

Use this comparison to quickly distinguish where Codex fits in relation to ChatGPT and the OpenAI API.

This course focuses on Codex. As you continue through PartnerU, use the comparison to identify the primary work: collaborative or delegated knowledge work in ChatGPT, an embedded or custom experience built with the API, or software delivery work supported by Codex.

These paths can work together—for example, Codex may support the engineering work needed to build or maintain an API-based solution.

## Slide 8/43 - Real-world example: Delegating a software task

An engineering team is managing a growing backlog.

New feature requests keep arriving. Existing systems need maintenance. Quality expectations remain high. At first, leaders ask, "How can we help developers write code faster?"

As the team looks more closely, they notice that developers are spending time across the full workflow:

- Understanding how existing systems work.
- Investigating defects.
- Implementing changes.
- Creating and updating tests.
- Reviewing work.
- Maintaining documentation.

The question starts to change.

Instead of asking only, "How can we write code faster?" the team asks, "How can we help engineers complete software delivery work more effectively?"

That is where Codex becomes relevant. Codex can support activities across the software delivery workflow, including understanding systems, implementing changes, supporting testing and review activities, and maintaining documentation.

The key takeaway:

Many software delivery challenges are not just coding challenges. They are workflow challenges.

## Slide 9/43 - Knowledge check

Which statement best describes Codex?

**Correct!** OpenAI's coding agent for software development and broader engineering workflows. Codex is the OpenAI solution path for agentic software delivery and engineering workflows.

## Slide 10/43 - Summary

Codex is OpenAI's coding agent for software development. It supports engineering teams across software delivery work, including understanding systems, investigating issues, implementing changes, supporting testing and review, and maintaining documentation.

Codex is primarily focused on software delivery workflows. ChatGPT supports collaborative and delegated knowledge work, while the OpenAI API is the path for embedding intelligence into products, applications, or processes. Codex can support the engineering work needed to build and maintain those solutions.

## Slide 11/43 - What makes Codex different

Now that you know where Codex fits, let's look at what makes it different from traditional coding assistance. Many AI coding tools help with narrow tasks, such as suggesting code or answering technical questions. Codex is designed for broader software delivery work, where a task may require context, steps, validation, and human review.

In this module, you'll explore the shift from producing coding outputs to supporting software delivery outcomes.

## Slide 12/43 - From coding assistant to coding agent

Many people first encounter AI in software development through coding assistants.

Traditional coding tools often focus on individual tasks such as:

- Completing a line of code.
- Suggesting a code snippet.
- Answering a technical question.
- Explaining a small piece of code.
- Helping with a narrow implementation task.

Those capabilities can be useful. They help developers move faster on specific coding steps.

Codex introduces a broader approach.

Instead of focusing only on a single coding output, Codex is designed to help with software delivery work. It can support tasks that require context, multiple steps, validation, and review.

For example:

"Write a function that formats a date" is a narrow coding task.

"Investigate why the checkout flow fails for returning users and suggest a fix" is a broader software delivery task.

That broader task requires understanding the system, tracing behavior, identifying likely causes, and producing work that can be reviewed. That is the kind of shift Codex represents.

## Slide 13/43 - Outputs versus outcomes

Many AI interactions focus on producing outputs rather than outcomes.

**Outputs**

An output might be:

- A code snippet.
- An explanation.
- A suggested implementation.
- A list of possible causes.
- A draft test case.

Outputs are useful, but they are not the same as outcomes.

**Outcomes**

An outcome is the result the team is trying to achieve. In software delivery, an outcome might be:

- A bug is investigated and a fix is proposed.
- A feature is implemented in a way that matches project expectations.
- Tests are added or updated to validate expected behavior.
- A code change is reviewed for risks.
- Documentation is updated so future engineers understand the system.

Codex is different because it can help teams work toward broader, reviewable software delivery outcomes, not just produce standalone outputs.

This does not mean Codex completes work without humans. It means the task can be framed around a software delivery result, with humans still guiding, reviewing, approving, and taking responsibility for what is accepted.

A helpful question is:

"Are we asking for a piece of output, or are we asking Codex to help move a software task toward completion?"

This helps keep Codex conversations tied to a reviewable engineering outcome, not just an isolated AI-generated artifact.

## Slide 14/43 - Delegation versus prompting

Traditional AI interactions often begin with prompting. Prompting usually means asking the AI to respond to a request. For example:

"Write a Python function that sorts a list."

That is a useful prompt, but it is narrow. It asks for an output.

Agentic software delivery introduces the idea of delegation. Delegation means giving Codex a goal and enough context to work toward that goal.

Instead of asking only for an answer, the user frames a task that may require steps, investigation, constraints, and review.

Delegation may involve:

- Defining the goal.
- Providing relevant context.
- Giving access to the information, systems, requirements, and constraints needed to complete the work effectively.
- Specifying what should not change.
- Identifying how the result should be checked.
- Reviewing progress and results.

A delegated task might sound like:

"Investigate why the customer import process fails when a file contains duplicate email addresses. Identify the likely cause, propose a fix, and summarize what should be tested before the change is accepted."

This is different from asking for a generic function. It asks Codex to work toward an engineering outcome.

## Slide 15/43 - Human and agent collaboration

Codex does not remove the human role in software delivery.

Humans still provide:

- Direction
- Context
- Judgment
- Approval
- Accountability

Codex can help perform work, gather information, support engineering activities, and prepare results for review. But engineering teams still need to validate outputs, decide whether changes are appropriate, and ensure work meets quality, security, and business expectations.

How that supervision works varies by surface and configuration. Codex may complete permitted work inside a defined workspace, while actions that cross configured boundaries, use the network, or require elevated access can trigger an approval step.

Human accountability matters for three reasons:

1. Software systems often contain business rules that may not be obvious from code alone.
2. Some decisions require product, security, legal, or customer context.
3. Software changes can affect users, systems, performance, and reliability.

That is why agentic software delivery should be understood as collaboration—not replacement.

A strong Codex workflow keeps humans close to the work. The human defines the goal, provides context, reviews progress, checks results, and decides what to accept.

## Slide 16/43 - Knowledge check

Which option best shows the difference between coding assistance and agentic software delivery?

**Correct!** Coding assistance often produces a specific output; agentic software delivery helps work toward a software delivery outcome with human direction and review. The key difference is that Codex can help with a broader software task, such as investigating a problem, proposing a fix, and identifying what needs to be tested. The human still guides the work and reviews the result.

## Slide 17/43 - Summary

Codex represents a shift from narrow coding assistance toward agentic software delivery. Instead of only producing standalone outputs, Codex can help teams work toward broader, reviewable software outcomes.

A strong Codex workflow depends on clear goals, useful context, defined constraints, human review, and engineering accountability.

## Slide 18/43 - Common software delivery workflows in Codex

Codex becomes easier to understand when you connect it to the work engineering teams already do.

In this module, you'll explore common software delivery workflows, including understanding systems, building and improving software, testing and review, documentation, and maintenance.

These examples show Codex as support across the software lifecycle, not just at the moment code is written.

## Slide 19/43 - Understanding systems and investigating issues

Engineering teams often need to understand systems before they can change them.

This is especially common when teams work with unfamiliar codebases, legacy systems, large applications, or complex dependencies.

A developer may need to answer questions such as:

- What does this part of the system do?
- Where is this behavior controlled?
- What files or modules are involved?
- Why is a bug happening?
- What changed recently?
- What context should I understand before making a fix?

Codex can support this kind of work by helping gather technical context, explain parts of a system, and investigate likely causes of issues.

This workflow is valuable because understanding often consumes significant engineering time. Before a team can fix, refactor, or improve a system, it needs to know how that system behaves.

Human review remains important. Codex can help accelerate investigation, but engineers still need to verify the explanation, check the evidence, and decide what action to take.

## Slide 20/43 - Building and improving software

Another common workflow is building or improving software.

This can include:

- Implementing a feature.
- Making a targeted software improvement.
- Refactoring part of a system.
- Addressing repetitive engineering tasks.
- Improving code readability or maintainability.

A useful Codex task usually has a clear goal.

For example:

"Add validation so the form displays an error when the required field is missing."

That is more actionable than:

"Improve the form."

The more specific task gives Codex a clearer target. It also makes the result easier for a human to review.

Codex can help move implementation work forward, but teams should still define constraints.

For example, they may specify that public APIs should not change, user-facing copy should remain the same, or only a certain part of the codebase should be touched.

At Foundation level, the main point is simple: Codex can support software-building work when the task is clear enough to guide and review.

## Slide 21/43 - Testing, validation, and review

Software delivery depends on quality. Engineering teams spend time checking whether changes behave as expected, whether tests are needed, whether a change introduces risk, and whether the work is ready for review.

Codex can support activities such as:

- Creating or updating tests
- Reviewing changes
- Validating behavior
- Identifying potential risks
- Summarizing what was changed and what still needs attention

This workflow is important because faster implementation does not help if quality suffers. The aim is not simply to create more code. The aim is to support work that can be checked, reviewed, and trusted.

Supported GitHub workflows can also let teams request a pull request review or configure automatic reviews. Engineers still decide how findings are addressed and whether a change moves forward.

Human review remains essential.

Codex can help prepare tests, surface issues, and summarize risks. Engineers still need to review the change, judge whether the validation is sufficient, and decide whether the work should move forward.

## Slide 22/43 - Documentation and maintenance

Software delivery also includes documentation and maintenance.

Engineering teams often need to:

- Update documentation.
- Explain how a system works.
- Capture decisions.
- Maintain existing software.
- Improve older parts of a codebase.
- Share knowledge with other engineers.

Documentation can be easy to postpone, but poor documentation creates friction later. New team members take longer to onboard. Existing engineers lose time rediscovering context. Maintenance work becomes harder.

Codex can support documentation and maintenance by helping explain code, draft updates, summarize changes, and make existing software easier to understand.

This does not mean documentation should be accepted without review. Technical documentation must still be checked for accuracy, completeness, and fit with team conventions.

The important point is that Codex can support the work around code as well as the code itself.

## Slide 23/43 - Software delivery workflows: Real-world examples

Here are four short examples of common Codex-supported workflows.

**Understanding a system**

A developer joins a team and needs to understand how the notification service works. Codex helps summarize relevant files, explain the flow, and identify where configuration happens. The developer reviews the explanation and confirms it against the codebase.

**Implementing a change**

A product team requests a small update to error handling in an application. Codex helps identify where the behavior is controlled and proposes a targeted change. The engineer reviews the change before accepting it.

**Testing and validation**

A bug fix needs test coverage. Codex helps draft a test that reproduces the issue and checks the expected behavior. The engineer runs and reviews the test to confirm it is meaningful.

**Maintaining software**

A team needs to update documentation after changing an internal workflow. Codex helps draft a clear technical note based on the change. The team reviews the note before adding it to the repository or internal documentation.

These examples show that Codex is not only about creating new code. It can support the broader set of activities that make software delivery possible.

## Slide 24/43 - Knowledge check

Match each activity to the most appropriate Codex-supported workflow.

- Update technical notes after a system change = Documentation and maintenance
- Explore an unfamiliar codebase and explain how a module works = Understanding systems and investigating issues
- Create tests and identify risks in a proposed change = Testing, validation, and review
- Add a targeted product improvement to an existing application = Building and improving software

**Correct!** All pairs matched correctly!

## Slide 25/43 - Summary

Codex can support the broader software delivery lifecycle, not just the moment code is written. Common workflows include understanding systems, investigating issues, building and improving software, testing and reviewing changes, and maintaining documentation.

Across each workflow, Codex can help move work forward, while engineers remain responsible for checking accuracy, validating results, and deciding what to accept.

## Slide 26/43 - Understanding agentic software delivery

You've seen how Codex can support common engineering workflows. Now, let's connect those workflows to the bigger idea behind Codex: agentic software delivery.

This module explains how AI-assisted development is moving from code completion and coding assistance toward delegated software work.

You'll learn what agentic delegation means, why long-running work changes the collaboration rhythm, and how humans stay involved through direction, review, and judgment.

## Slide 27/43 - The evolution of AI in software development

AI-assisted software development has evolved over time.

A simple way to see the progression is:

**Code completion**

Early tools helped suggest the next line or complete a small section of code.

**Coding assistance**

More advanced tools helped answer questions, explain errors, suggest implementations, and support individual coding tasks.

**Agentic software delivery**

Agentic systems can help work toward broader software delivery outcomes. They may investigate, gather context, make changes, support validation, and prepare results for human review.

This progression shows how AI in software development has moved from small suggestions toward delegated software work.

The shift matters because the bottleneck in software delivery is not always writing code. Teams also need to understand systems, validate changes, review work, maintain quality, and keep knowledge up to date.

Codex sits in this newer pattern. It helps teams think about AI as support for software delivery work, not just as a code generator.

## Slide 28/43 - Understanding agentic delegation

Agentic delegation means giving Codex a software task that has a goal, context, constraints, and review expectations.

For learners who completed Agents & Agentic Workflows, this is the software delivery version of the same idea: goal-directed work with context, boundaries, tools, and human review.

A strong delegated task usually includes:

**Objective**

What should be true when the work is complete?

**Context**

What information does Codex need to understand the task?

**Constraints**

What should Codex avoid changing? What rules, requirements, or boundaries matter?

**Expected outcome**

What should Codex produce or prepare for review?

**Review expectations**

How should the human evaluate the result?

For example:

"Investigate why the customer import process fails when duplicate email addresses appear in a CSV file. Start by identifying where import validation happens. Do not change the database schema. Recommend the smallest safe fix and summarize the tests that should be run."

This task is not just asking for code. It describes a goal, context, boundary, and expected review path.

That is agentic delegation at a practical level.

## Slide 29/43 - Long-running and asynchronous work

Many software delivery activities take time. They may require multiple steps, ongoing investigation, iterative review, or progress over time. A task may begin with exploration, uncover new information, require a decision, and then continue in a new direction.

Examples include:

- Investigating a hard-to-reproduce bug.
- Reviewing a complex change.
- Refactoring part of a system.
- Preparing a fix and related tests.
- Updating documentation after a larger change.

As work becomes longer-running, human guidance becomes even more important. A team may need to review progress, provide more context, approve a direction, or stop the task if the work is moving outside the intended scope.

Agentic software delivery is not "set it and forget it." It is a different collaboration rhythm.

Codex can help keep work moving, while humans remain available to guide, redirect, and validate.

Some Codex surfaces can also use automations or parallel agents to coordinate or repeat parts of the work.

These capabilities can help longer-running tasks move forward, but they also increase the need for clear ownership, progress checks, approval boundaries, and review.

A good habit is to ask, "What decision points might require human judgment before this work continues?"

## Slide 30/43 - Why agentic software delivery matters

Agentic software delivery matters because it can support the broader work that surrounds code.

Potential benefits include:

- Greater efficiency.
- Reduced repetitive effort.
- Better support for complex workflows.
- More focus on higher-value engineering work.
- Faster movement from issue to reviewed result.
- Clearer support for work that includes investigation, implementation, validation, and documentation.

The important point is not that Codex removes engineering work, but that it can help teams delegate broader, multi-step software delivery tasks while engineers stay responsible for direction, review, and final judgment.

When routine or well-scoped tasks can be delegated, engineers may spend more time on architecture, product judgment, complex problem-solving, review, and decisions that require human expertise.

At the same time, agentic delivery requires responsible use.

Teams still need clear task framing, appropriate context, review, and validation. Codex can help move work forward, but the team remains accountable for what ships.

## Slide 31/43 - Recommended exercise: From prompt to delegation

This is an optional practice activity to help you apply what you just learned.

**Purpose**

Practice distinguishing traditional coding assistance from agentic software delivery.

**Task**

Compare the two examples below.

Example A: "Write a Python function that sorts a list of names alphabetically."
Example B: "Investigate why our customer import process is failing and recommend a fix."

Identify:

- Which example reflects traditional coding assistance.
- Which example reflects agentic software delivery.
- What makes the two examples different.

**Estimated time**

5 minutes

**Suggested output**

Explain the difference between generating an output and working toward an outcome.

## Slide 32/43 - Knowledge check

**Question:** Which task is the clearest example of agentic software delivery?

- **"Investigate why a login bug occurs, identify the likely cause, propose a fix, and summarize what should be tested."** ✓ (Correct answer)
- "Give me five clear variable names for a function that processes user input."
- "Write a short code snippet that reverses a string in a simple function."
- "Explain what an API is in one paragraph for a non-technical reader."

**Result:** Correct! This task involves a goal, investigation, context, proposed action, and reviewable outcome.

## Slide 33/43 - Summary

Agentic software delivery is about delegating structured software tasks, not simply prompting for code. Strong delegation gives Codex a goal, context, constraints, expected outcome, and review path.

Longer-running software work creates a different collaboration rhythm, where Codex can investigate and prepare work while humans guide direction, review progress, and make final decisions.

## Slide 34/43 - Introduction: Why organizations are interested in Codex

Organizations are interested in Codex because software delivery affects more than engineering productivity. Software supports products, customer experiences, internal operations, and innovation. When delivery slows down, business outcomes can slow down too.

In this module, you'll explore why software delivery is a business capability, what challenges engineering teams face, and what outcomes organizations may hope to achieve with Codex.

## Slide 35/43 - Software delivery as a business capability

Software is not only an engineering concern.

Software increasingly supports products, services, customer experiences, internal operations, and organizational innovation.

A company's ability to build, improve, and maintain software can affect how quickly it serves customers, responds to market changes, launches products, and operates internally.

That is why software delivery is a business capability.

When software delivery slows down, the impact is not limited to engineering teams. Product releases may slip.

Customer experience improvements may take longer. Internal systems may remain inefficient. Maintenance work may crowd out innovation.

Codex is relevant because it connects AI to this broader business capability. It supports the engineering work behind products, services, operations, and innovation.

At Foundation level, you do not need to quantify the business case. You do need to understand why organizations care: better software delivery can affect business outcomes.

This helps you discuss Codex credibly even if you are not in a technical role: focus on the business impact of software delivery without pretending to design the engineering workflow.

## Slide 36/43 - Common engineering challenges

Engineering teams often manage several pressures at the same time.

- **Growing software complexity** — Systems become larger, more interconnected, and harder to understand.
- **Technical debt** — Older decisions, shortcuts, or outdated systems can make future changes slower or riskier.
- **Maintenance responsibilities** — Teams must keep existing systems reliable while also building new capabilities.
- **Delivery pressure** — The business may want faster releases, more features, or quicker response to customer needs.
- **Quality expectations** — Teams must move quickly without compromising reliability, security, maintainability, or user experience.

These challenges are often connected. A team may be asked to release faster, but technical debt makes every change harder. Or an engineering group may want to innovate, but maintenance work consumes too much capacity.

Codex is not a magic fix for these challenges. It is a way to support parts of the software delivery workflow so engineering teams can work more effectively.

## Slide 37/43 - Outcomes organizations hope to achieve

Organizations may explore AI-assisted software delivery because they want to improve how engineering work gets done.

Common desired outcomes include:

**Improve delivery speed**
Teams want to move from idea to working software more efficiently.

**Improve software quality**
Teams want more support for tests, review, validation, and risk identification.

**Expand engineering capacity**
Teams want engineers to spend less time on repetitive or routine tasks and more time on high-value work.

**Reduce repetitive work**
Teams want support for tasks such as documentation updates, small refactors, test creation, or investigation prep.

**Increase efficiency**
Teams want software delivery processes to require less friction and manual rework.

These outcomes are broader than "write code faster." Codex may contribute when the work is structured, reviewable, and connected to real software delivery needs.

The right question is not only, "Can Codex produce code?" A better question is, "Where does the engineering workflow need support, and what parts of that work are clear enough to delegate and review?"

## Slide 38/43 - Real-world example: Looking beyond coding speed

A software organization wants to release product updates more frequently.

At first, the conversation focuses on coding speed. Leaders ask whether AI can help developers write more code in less time.

As the team examines its process, a different picture appears. Engineers spend significant time understanding systems, reviewing changes, testing updates, and maintaining existing software. Writing code is only one part of the work.

The conversation shifts from:

"How can developers write code faster?"

to:

"How can engineering teams complete software delivery work more effectively?"

That shift matters.

Codex may help with several parts of the workflow: understanding a system, preparing a targeted change, supporting test creation, reviewing risks, and maintaining documentation.

The value is not only in faster code generation. It is in supporting the overall delivery process.

**The takeaway**

Software delivery challenges often involve coordination, review, validation, and maintenance activities in addition to implementation work.

A useful next step is to identify which part of the delivery workflow is creating friction before deciding whether Codex should be explored further.

## Slide 39/43 - Recommended exercise: Identify the software delivery challenge

This is an optional practice activity to help you apply what you just learned.

**Purpose**

Practice recognizing where Codex may be relevant within a software delivery workflow.

**Task**

Review the workflow example below.

A product team wants an engineering group to release customer-requested improvements faster. The engineering group says the biggest delay is not writing new code. The team spends time understanding older services, reproducing bugs, checking whether fixes affect other areas, creating tests, reviewing changes, and updating documentation.

Identify:

- The primary software delivery challenge.
- The activities consuming engineering effort.
- Where Codex might provide support.
- Where human review would remain important.

**Estimated time**

5 minutes

**Suggested output**

Describe the difference between helping developers write code faster and helping engineering teams complete software delivery work more effectively.

## Slide 40/43 - Knowledge check

**Question:** A customer says, "Our engineers are not only slowed down by writing code. They spend a lot of time understanding legacy systems, reviewing changes, creating tests, and maintaining documentation." What is the best interpretation?

- The customer is asking for the OpenAI API because the work involves software.
- The customer should avoid using AI because software delivery work is too complex.
- The customer only needs a faster code-completion tool for writing small snippets.
- **"The customer may have a broader software delivery workflow challenge where Codex could be relevant."** ✓ (Correct answer)

**Result:** Correct! The customer is describing work across the software delivery lifecycle, not only code creation.

## Slide 41/43 - Summary

Organizations are interested in Codex because software delivery affects products, services, customer experiences, operations, and innovation.

Many engineering challenges are broader than coding speed. They involve complexity, technical debt, maintenance, quality expectations, and delivery pressure.

Codex may be relevant when teams need support across the software delivery workflow and the work is clear enough to delegate, review, and validate.

## Slide 42/43 - Recap

In this course, you learned where Codex fits within the OpenAI portfolio and how it supports engineering teams with software delivery work.

You learned that Codex differs from traditional coding assistance because it can help teams work toward broader, reviewable software delivery outcomes, not just isolated outputs.

As a final takeaway from this course, remember that Codex can help teams move software work forward across the delivery lifecycle, while humans remain responsible for review and what ultimately ships.

## Slide 43/43 - Congratulations

Congratulations, you've completed this course!

Apply this foundation by listening for software delivery challenges in customer conversations.

Ask whether the need is about delivery, not just writing code: which workflow is consuming engineering effort, whether the work is clear enough to delegate and review, and where human judgment remains essential.

You do not need to design a Codex deployment at this stage. Your role is to recognize where Codex may fit, describe it responsibly, and know when another OpenAI path or deeper technical or deployment validation may be needed.

**Course completed**

**Next up in OpenAI Foundational Knowledge:** API Essentials (Course, 41 min) — Unlock the power of AI where it matters most—inside the products, systems, and workflows people already use. Explore what APIs are, why they're essential for embedding intelligence into real-world experiences, and how the OpenAI API empowers developers to build custom AI solutions for everything from customer support portals to internal tools and business processes. Discover common API use cases, integration patterns, and practical signals for when an API-based approach is the right fit, all without needing to be a developer. Learn to recognize opportunities for seamless AI integration, distinguish the OpenAI API from ChatGPT and Codex, and understand the safeguards and best practices that ensure reliable, responsible AI-powered workflows.
