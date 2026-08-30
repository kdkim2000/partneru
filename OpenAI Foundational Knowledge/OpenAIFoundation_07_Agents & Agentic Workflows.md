# Agents & Agentic Workflows

## Slide 1/39 - Title

Agents & Agentic Workflows

Created July 2026

## Slide 2/39 - Introduction

Customers increasingly want AI to help complete work, not just answer questions. In enterprise settings, this means understanding how agents can support real workflows. An agentic workflow can use the right business context, work across approved tools or systems, follow boundaries, and pause for human review where needed.

This course gives you an agentic-workflow lens for the broader PartnerU journey. It is a practical recognition course, not a build or deployment course. You'll focus on the workflow: what the customer is trying to achieve, what steps are involved, what tools or context might be needed, and where human oversight should remain part of the process.

## Slide 3/39 - What you'll learn

By the end of this course, you'll be able to:

- Explain what an AI agent is in plain language.
- Recognize how goal pursuit, planning, tool use, and action shape different degrees of agency.
- Recognize the core building blocks of agentic workflows.
- Identify workflow patterns where an agentic approach might be relevant.
- Distinguish the product surface, required capabilities, and operating controls that shape an agentic workflow.
- Use appropriate language when discussing agents, autonomy, human oversight, safety, and AGI.

Let's get started!

## Slide 4/39 - Introduction (What agents are and why they matter)

Agents are easier to understand when you start with the work they help complete. A simple AI interaction can answer a question or generate a response. An agentic workflow can work toward a goal by using context, coordinating steps, using tools, and pausing for human review where appropriate.

In this module, you'll learn what agentic AI means, what agents are not, and why agentic workflows matter for customers.

## Slide 5/39 - What is Agentic AI?

An AI agent is a system that can work toward a goal by reasoning about what to do, using context, and taking steps through tools or workflows.

**Lower-agency interactions**

May respond to a single prompt or complete one bounded step.

For example, a user might ask, "Summarize this paragraph," and the AI returns a summary.

**More agentic workflows**

Work toward a goal and may plan, coordinate, use tools, or take actions across multiple steps.

For example, an agentic workflow can:

- review a request,
- gather relevant information,
- compare it against approved sources,
- prepare an output,
- route the work to the right person or system,
- and pause for human review before a final action.

Several ideas are important:

- **Goal orientation** — Agents start from a task or goal, not only a single question.
- **Context** — Agents need relevant information to work well. This includes conversation history, files, documents, policies, user inputs, workflow information, or approved business context.
- **Tool use** — Agents can use tools, apps, files, APIs, or other approved information sources to complete work.
- **Human control** — Agentic does not mean fully autonomous or unsupervised. Human oversight and clear boundaries are still important.

A useful shorthand is:

> Agency exists on a continuum. As a system pursues goals, plans, uses tools, and takes actions across more steps, the workflow becomes more agentic—while human direction, permissions, and review still shape what it can do.

## Slide 6/39 - What agents are not

Agents can be useful, but the term can also be overused.

**An agent is not just a chatbot.**

A chatbot can answer questions, but an agentic workflow usually involves goals, steps, tools, or actions.

**An agent is not magic automation.**

Agents still need clear instructions and well-defined access boundaries.

**An agent is not a replacement for governance.**

Agentic workflows need clear oversight and ownership.

**An agent is not AGI.**

Agents are not the same as artificial general intelligence. AGI remains a long-term research concept connected to OpenAI's mission, not a current customer solution label.

**An agent is not always the right answer.**

Some workflows only need retrieval, summarization, classification, text generation, or a simple assistant.

Clarity here is important because "agent" can sound more advanced than the customer's actual need. The better question is not "Can we use an agent?" but "What work needs to happen, and does it require a goal-directed, multi-step workflow?"

## Slide 7/39 - Why agentic workflows matter for customers

Agentic workflows matter when customers want AI to help move work forward.

They can support:

**Work completion**

Agentic workflows can help move from "answering" to "doing," especially when work requires several steps.

**Repeatable processes**

Agents can support repeatable tasks such as preparing reports, researching accounts, summarizing changes, triaging requests, or coordinating handoffs.

**Tool-connected work**

Agents become more useful when work spans multiple systems, documents, or actions.

**Capacity and consistency**

Agentic workflows help teams handle repeated work with more consistent process steps.

**Enterprise workflow transformation**

Agentic workflows can help organizations move from isolated AI assistance toward repeatable ways of working across teams, systems, approvals, and operating practices.

Getting clear on this is important. Agents are not valuable because they sound advanced. They are valuable when they reduce friction in real workflows.

## Slide 8/39 - Agentic AI: real-world example

A sales team uses an AI agent to prepare a weekly account update.

This is agentic because the AI is:

- working toward a goal,
- using context,
- completing multiple steps,
- and pausing for human oversight before the final output is used.

The agent reviews approved account notes, checks recent customer activity, summarizes key changes, drafts a short update, and flags items that need human review before sharing.

Now compare that with a simpler request:

> "Rewrite this sentence in a more professional tone."

That is useful AI assistance, but it is not necessarily agentic. It is a single-step generation request. It does not require planning, tool use, workflow state, handoffs, or approvals.

The difference is the shape of the work.

## Slide 9/39 - Knowledge check

**Question:** Which example is most clearly agentic?

- AI summarizes a pasted article and highlights the points most relevant to the sales team.
- AI translates a support response and adjusts the wording for a regional audience.
- **AI reviews account notes, checks recent activity, drafts an update, and flags items for review. (Correct)**
- AI rewrites a customer email in a friendlier tone and suggests a clearer call to action.

**Explanation:** The correct answer is most clearly agentic because it works across multiple steps, uses business context, checks activity, prepares an output, and includes a review signal.

## Slide 10/39 - Summary

Agents are best understood by the work they help complete. AI systems can show different degrees of agency.

A single response is lower on the continuum; a workflow becomes more agentic as it pursues a goal, coordinates steps, uses tools, and takes actions. Human direction, permissions, boundaries, and review remain important across the continuum.

## Slide 11/39 - Introduction (The building blocks of agentic workflows)

Agentic workflows depend on more than a capable model. They need a clear goal, useful instructions, the right context, appropriate tools, clear handoffs, guardrails, and human checkpoints.

In this module, you'll learn the core building blocks that make agentic workflows work. You are not expected to design or configure an agent, just focus on recognizing the parts that need to be clear before an agentic workflow can operate responsibly.

## Slide 12/39 - Goal, instructions, and context

Agentic workflows are usually shaped by three core inputs: goal, instructions, and context.

**Goal**

The goal is the desired outcome the agent is working toward.

A weak goal might be: "Help with support tickets."

A clearer goal might be: "Review incoming support tickets, identify the issue type, draft a suggested response using approved support content, and flag sensitive cases for human review."

**Instructions**

Instructions are the rules, preferences, steps, or boundaries that guide how the agent should work.

Instructions might clarify:

- what the agent should do first,
- what sources it should use,
- what tone or format it should follow,
- what it should avoid,
- and when it should stop or ask for help.

**Context**

Context is the information the agent can use. This includes conversation history, files, documents, user inputs, policies, prior outputs, business rules, or relevant workflow information.

In enterprise workflows, context is not just background information.

It includes what the agent needs to know about the business, the user's task, approved sources, permissions, policies, and the systems involved.

Weak goals, unclear instructions, missing context, or unclear access boundaries can cause poor agent behavior even when the model is capable.

This also helps you connect agentic workflows to the broader enterprise operating lens: what the AI needs to know, where it does work, and how the organization monitors or improves the workflow.

## Slide 13/39 - Tools, apps, and actions

Agents complete work by using tools, apps, and actions.

**Tools**

Tools are capabilities the agent can use to complete work. Examples might include search, file retrieval, code execution, calendar access, or business applications.

**Apps**

Apps are approved integrations that connect the agent to external tools, information, or actions. In managed workspaces, availability and permissions depend on workspace and role settings.

**Actions**

Actions are steps the agent can take. Examples include drafting, searching, filling a form, updating a document, sending a request, or triggering a workflow.

Together, these define where and how the agent does work.

In enterprise settings, the practical question is not only "What can the agent do?" It is also:

> What tools, apps, permissions, approvals, and boundaries shape how the agent does the work?

This matters because agentic workflows depend on the systems and capabilities the agent can access. If the required tools, apps, actions, permissions, or approval steps are unclear, the workflow might not be practical or safe to use.

## Slide 14/39 - State, memory, and handoffs

Multi-step agentic workflows also rely on state, memory or retained context, and handoffs.

**State**

State is information about where the workflow is in a process. This might include completed steps, pending decisions, current task status, or what the agent has already found.

**Memory or retained context**

Memory or retained context is information the agent may use across steps or sessions, depending on product settings and policy.

**Handoffs**

Handoffs are points where the agent passes work to a person or another system.

These elements help the organization understand:

- What has happened
- What is still pending
- Who needs to act next
- Where the work should continue

Multi-step work often fails when state, context, or handoffs are unclear.

**For example**

If an agent drafts a response but does not clearly show that the response still needs manager review, the handoff is weak. Or if the agent updates a record without capturing why it made the change, the workflow could be hard to audit or improve.

## Slide 15/39 - Guardrails and human checkpoints

Agentic workflows need clear boundaries.

- **Guardrails** — Constraints that define what the agent can and cannot do. They guide what sources the agent can use, what actions it can take, what content it should avoid, or when the workflow should stop.
- **Human checkpoints** — Moments where a person reviews or approves before the workflow continues.
- **Risk sensitivity** — Means that higher-stakes workflows usually require stronger oversight and clearer escalation.
- **Monitoring and feedback** — Help the organization catch issues and improve the workflow over time.

Agents can increase workflow capability, but they also increase the need for clear boundaries and visibility into how work is being completed.

A useful question is:

> Where should the agent act, and where should a human review or approve?

## Slide 16/39 - Knowledge check

**Question:** Match each statement to the most relevant agentic workflow building block.

- "What system or capability can the agent access?" → **Tool or app (Correct)**
- "What rules or boundaries should guide the agent?" → **Instructions (Correct)**
- "What information can the agent use?" → **Context (Correct)**
- "What step can the agent take?" → **Action (Correct)**
- "Where should a person review or approve before work continues?" → **Human checkpoint (Correct)**
- "What outcome should the agent work toward?" → **Goal (Correct)**

All pairs matched correctly!

## Slide 17/39 - Summary

Agentic workflows depend on more than a capable model. Clear goals, useful instructions, relevant context, tool access, handoffs, guardrails, and human checkpoints all shape how the workflow operates.

When these parts are unclear, the workflow may be harder to control or improve.

## Slide 18/39 - Introduction (Where agentic workflows may solve customer problems)

Not every AI workflow needs to be agentic. Some customer needs can be handled with a simple answer, a generated draft, a retrieval-grounded response, or a classification step. Other workflows involve multiple steps, tools, decisions, handoffs, or approvals.

In this module, you'll learn how to recognize workflow shapes where an agentic approach may be relevant—and where a simpler AI pattern could be more appropriate.

## Slide 19/39 - Common agentic workflow patterns

Agents can fulfill different roles in customer workflows.

Common agentic workflow patterns include:

**Research and synthesis**

The agent gathers information from multiple sources, summarizes findings, and prepares an output for review.

Example: An agent prepares an account briefing by reviewing approved account notes, recent activity, and relevant internal materials.

**Triage and routing**

The agent classifies requests and routes work to the right team or workflow.

Example: An agent reviews incoming support requests, identifies issue type and urgency, and routes complex cases for specialist review.

**Document and knowledge workflows**

The agent retrieves information, compares documents, drafts updates, and flags gaps.

Example: An agent compares a new policy draft against existing guidance and highlights areas that may need review.

**Operational coordination**

The agent tracks steps, prepares follow-ups, updates records, or coordinates handoffs.

Example: An agent helps prepare follow-up tasks after a customer meeting, updates a tracker, and flags actions that need manager approval.

**Software delivery support**

The agent plans coding tasks, generates or reviews code, runs tests, and summarizes changes.

Example: An agent helps an engineering team review a code change, suggest tests, and prepare a summary for human review.

These patterns share a common feature: the work usually involves more than a single response.

## Slide 20/39 - Signals that a workflow may be agentic

A workflow may point toward an agentic approach when it includes several signals.

**Multiple steps**

The work requires more than one action or decision.

**Goal-directed process**

The work is driven by an outcome, not only a single answer.

**Tool or system interaction**

The work requires accessing, comparing, updating, or moving information across tools.

**Changing context**

The workflow may need to adapt based on what is found in earlier steps.

**Human oversight need**

The workflow may require review or escalation before final action.

The more of these signals you see, the more likely it is that a simple AI interaction might not be enough.

For example: "Summarize this document" is a simple request. But "Summarize this document, compare it against our current policy, flag conflicts, draft an update, and route the draft to Legal for review" is a multi-step workflow with context, tool use, and a handoff.

## Slide 21/39 - When an agentic workflow may not be needed

Agentic workflows are powerful, but they are not always necessary.

A workflow might not need an agentic approach when it involves:

**Single-turn answers**

A simple question-and-answer interaction might not need an agentic workflow.

**Simple generation**

Drafting or rewriting may only require text generation.

**Simple retrieval**

Finding or summarizing existing information often only requires retrieval-grounded answers.

**Low-value automation**

A workflow may not justify agentic complexity if the task is unclear or low-impact.

**High-risk automation**

A workflow might not be appropriate for agentic execution if the risk is high and oversight is weak.

Agentic workflows add complexity. They may require clearer instructions, tool access, state tracking, handoffs, permissions, monitoring, and human review.

The practical question is:

> Does the workflow need goal-directed, multi-step work—or is a simpler AI pattern enough?

This question helps you connect agentic thinking back to earlier AI application patterns. Sometimes the right next step is not an agent, but retrieval-grounded answers, summarization, classification, or simple generation.

## Slide 22/39 - Agentic workflows: real-world examples

**Shows stronger agentic signals**

A customer support team wants AI to review incoming support requests, classify each issue, check approved knowledge sources, draft a response, route complex cases to the right team, and flag sensitive cases for human review.

This example shows stronger agentic signals because the work is:

- goal-directed,
- multi-step,
- connected to tools or approved knowledge,
- dependent on handoffs,
- and shaped by oversight needs.

**Shows fewer agentic signals**

A marketing team wants AI to rewrite a short product description in a clearer tone.

This example shows fewer agentic signals and can likely use a simpler generation pattern. It does not require planning, tool use, actions across systems, ongoing state, or handoffs.

Both examples can be valuable. The difference is how much goal pursuit, coordination, tool use, and action the workflow requires.

## Slide 23/39 - Recommended exercise: Recognizing degrees of agency

This is an optional practice activity to help you apply what you just learned.

**Purpose**

Help you identify agentic signals and decide whether a simpler AI pattern may be enough.

**Suggested learner task**

Review the workflow examples below. For each one, identify the agentic signals that are present and decide whether a simpler AI pattern may be enough or a more agentic workflow is warranted.

- A user asks AI to rewrite a short customer email in a friendlier tone.
- A support workflow reviews a new case, classifies it, retrieves approved guidance, drafts a response, routes complex cases to a specialist, and flags sensitive cases for human review.
- A team asks AI to summarize one uploaded document.
- An operations workflow checks a request, gathers information from approved systems, prepares a status update, and asks a manager to approve the next step.

**Estimated time**

3-5 minutes

**Suggested output or reflection**

Use this pattern for each example:

- Agentic signals present:
- Likely fit and why:

## Slide 24/39 - Knowledge check

**Question:** A team wants AI to classify incoming support requests, retrieve approved information, draft a response, route complex cases, and flag sensitive cases for human review. What is the best interpretation?

- This is likely an image-generation request because the main task is creating one visual output.
- This is best described as AGI because it can complete several steps without a person writing each step manually.
- This is likely a simple single-turn answer because it asks for one response without workflow steps.
- **This could suggest an agentic workflow because it is multi-step, goal-directed, tool-connected, and requires handoffs and review. (Correct)**

**Explanation:** The workflow involves several agentic signals: multiple steps, approved sources, routing, and human oversight.

## Slide 25/39 - Summary

Agentic workflows are most relevant when the work involves a goal-directed process across multiple steps. Signals such as tool use, changing context, handoffs, and human review can suggest that a simple AI interaction may not be enough.

A simpler AI pattern may still be the better fit when the request is a single answer, a draft, a summary, or a low-value task.

## Slide 26/39 - Introduction (Agentic workflows across common technology paths)

Agentic work can appear through different product surfaces, but surface, capability, and operating model are separate decisions. When evaluating an agentic workflow, distinguish where the person or workflow primarily operates—such as ChatGPT, Codex, or an application or process built with the API—from what the system must do and how the work is controlled.

In this module, you'll learn to recognize those layers without going into product configuration, API design, orchestration, or deployment architecture.

## Slide 27/39 - User-facing agents and workspace workflows

Some agentic workflows support people directly inside ChatGPT or another managed workspace experience.

This is a user-facing path. Within ChatGPT, Chat supports collaborative thinking and creation, while ChatGPT Work supports delegated, multi-step knowledge work. ChatGPT workspace agents can package repeatable tasks and workflows for shared use.

User-facing or workspace workflows support tasks such as:

- gathering information,
- preparing updates,
- summarizing documents,
- coordinating actions,
- drafting follow-ups,
- and helping employees complete repeatable work.

For example, an employee might use ChatGPT Work to prepare a one-off, multi-step project update.

A team might use a workspace agent when the same approved process needs to be repeated, shared, or scheduled.

Several practical considerations still matter:

- ChatGPT Work availability can vary by plan and surface.
- Workspace agents require an eligible managed workspace and may require administrator enablement.
- Access to agents, apps, tools, sharing, schedules, publishing, and actions depends on workspace settings, role permissions, and admin controls.
- Approval and governance settings shape what the agent can access or do.

The key recognition clue is that the work stays inside a user-facing ChatGPT or managed workspace experience.

## Slide 28/39 - API-based or product-embedded agents

Some agentic workflows are built into a customer's own product, internal system, backend process, or customer-facing experience.

This is an API-based or product-embedded path.

In this path, the customer or implementation team controls the user interface, business logic, integrations, and governance model.

API-based agents may be relevant when:

- AI needs to appear inside a product or application.
- The organization wants a custom user experience.
- The workflow needs to connect with business systems.
- The organization needs to define what the agent can access and what actions it can take.
- Approval points and monitoring need to be designed into the workflow.

For example, a company builds an agent into a customer support portal. The agent can classify the customer request, retrieve approved information, draft a response, and route complex cases to a support specialist.

The user does not leave the product experience. The agentic capability is built into the product or workflow itself.

This path usually involves more technical and operational ownership. It requires design, testing, evaluation, monitoring, and ongoing technical support.

## Slide 29/39 - Recognizing where agentic experiences can live

To recognize where agentic work may live, separate three decisions that are easy to mix together.

- **User or product surface** — Where will the person or workflow primarily operate? Examples include ChatGPT—including Chat and Work—Codex, or an application or process built with the API.
- **Capability or architecture** — What must the system do? Examples include workspace agents, apps and tools, retrieval, code execution, step coordination, or automation.
- **Deployment and operations** — Where and how will the work run and be controlled? Consider identity, permissions, approvals, retention, logging, human review, and whether the work is hosted or embedded.
- **Combined solutions** — A customer may use more than one surface or capability, but the layers should still be evaluated separately.
- **Software delivery workload** — Software delivery is a workload—not a separate surface. It may use Codex, an API-based application, or a combination, depending on where the work happens and what capabilities and controls are required.

The right combination depends on the workflow—not on which option sounds most advanced.

A useful recognition question is:

> Where will the work happen, what must the system do, and how will it be controlled?

## Slide 30/39 - Knowledge check

**Question:** Match each workflow description to the most relevant layer or workload.

- Administrators define roles, permissions, approvals, logging, and human review → **Deployment and operations (Correct)**
- Employees delegate a multi-step account briefing in ChatGPT Work → **ChatGPT surface (Correct)**
- A workspace agent uses approved apps and tools to gather information and update a report → **Capability or architecture (Correct)**
- Engineers use Codex to plan, test, review, and summarize code changes → **Software delivery workload on the Codex surface (Correct)**
- Customers interact with an agent inside an existing support portal → **API-built application surface (Correct)**

All pairs matched correctly!

## Slide 31/39 - Summary

Agentic work can appear in ChatGPT, Codex, or an application or process built with the API.

Product surface is separate from the capabilities the workflow needs and the operating controls that govern it. ChatGPT Work supports delegated knowledge work, while workspace agents support repeatable shared workflows in eligible managed workspaces.

Software delivery is a workload, not a peer surface. Use the workflow, required capabilities, permissions, approvals, and human review to determine the right combination.

## Slide 32/39 - Introduction (Common misconceptions about agents)

Agents can be useful, but they are also easy to overclaim. Partners need to discuss agents in a way that is accurate and appropriately bounded. That means explaining what agents can help with while naming the boundaries, oversight, verification, and governance that may still be needed.

In this module, you'll review common misconceptions and practice stronger language for discussing agents responsibly.

## Slide 33/39 - Misconceptions about agent capabilities

Agents can make AI systems more capable, but they still need clear goals and oversight boundaries.

Here are common misconceptions to avoid.

- **Agents are fully autonomous by default** — An agentic workflow may complete defined steps, but it still needs boundaries and human approval where appropriate.
- **Agents are always correct** — Agentic workflows can still produce errors or incomplete outputs. Outputs and actions should be reviewed based on the risk and workflow.
- **Agents are automatically safe** — Safety depends on the workflow, the data involved, the tools available, and the controls around the system.
- **Agents remove the need for people** — Human review remains important, especially for higher-risk or customer-impacting work.
- **Agents are AGI** — Current agents and agentic workflows are not the same as artificial general intelligence. AGI remains a long-term research concept, not a current customer solution.

A credible discussion of agents should focus on defined work, clear boundaries, appropriate oversight, and what needs to be verified.

## Slide 34/39 - Stronger language to use

When you discuss agents as a partner, use bounded, specific language.

**Describe agent autonomy clearly**

Say the agent can support, coordinate, or execute defined steps within approved boundaries.

Instead of: "The agent can run the whole workflow by itself."

Say: "The agent can support defined workflow steps within approved boundaries, with human review where needed."

**Use oversight language**

Name where humans review or approve.

Example: "The workflow can draft a response and route sensitive cases for human review before anything is sent."

**Use verification language**

Identify what must be verified, such as tool access, data permissions, product availability, and governance requirements.

Example: "We'd need to confirm which systems the agent can access, which actions require approval, and how the workflow will be monitored."

**Use workflow language**

Focus on the work the agent helps complete, not on "autonomy" as a standalone claim.

Example: "The agentic workflow may help triage requests, gather approved information, draft responses, and coordinate handoffs."

**Use AGI carefully**

Treat AGI as a long-term research concept connected to OpenAI's mission, not a current product or solution label.

Strong agent language is clear and bounded. It helps customers understand the value without overpromising.

Your language might differ slightly depending on your role. In sales or business development, it can help you avoid inflated claims. In technical, deployment, or customer success work, it can help you identify where tool access, permissions, monitoring, or governance need deeper validation.

## Slide 35/39 - Recommended exercise: Rewrite an agentic overclaim

This is an optional practice activity to help you apply what you just learned.

**Purpose**

Help you practice replacing inflated agent language with credible language.

**Task**

Weak statement: "This agent can fully automate your support workflow from start to finish without human involvement."

Rewrite the statement using bounded, customer-facing language.

**Estimated time**

3-4 minutes

**Suggested output**

Write a revised statement that:

- explains the workflow value,
- names boundaries,
- includes human review where needed,
- and identifies what should be verified.

**Suggested strong response:** "An agentic workflow can help triage support requests, retrieve relevant information, draft responses, and route cases within approved boundaries. We would need to define which steps require human review, what systems it can access, and how performance and safety will be monitored."

**Why it works:** The stronger response explains the workflow value without promising full autonomy.

## Slide 36/39 - Knowledge check

Which statement best describes an agentic workflow without overclaiming?

- "The agent should decide its own goals and actions without predefined boundaries."
- **"The agentic workflow may triage requests, draft responses, and route cases within approved tool access, review points, and monitoring." (Correct)**
- "The agent is AGI because it can complete several steps in a workflow."
- "The agent can fully automate the support workflow without human review once it is connected to tools."

**Correct!** This statement explains the workflow value while keeping the claim bounded. It names the work the agent may support and includes tool access, review points, and monitoring.

## Slide 37/39 - Summary

Agents should be described with clear, carefully scoped language. Strong agent language explains the workflow value without promising full autonomy, guaranteed accuracy, or AGI.

A credible statement names what the agent may help with, where human review may be needed, and what should be verified before commitments are made.

## Slide 38/39 - Recap

Agents are goal-oriented systems that work toward outcomes by using context, tools, defined steps, boundaries, and human checkpoints. Agency exists on a continuum: as goal pursuit, planning, tool use, and action increase, a workflow becomes more agentic.

As you evaluate customer needs, start with the workflow. Ask what outcome the customer is trying to achieve, where the work should happen, what capabilities and context are needed, and how permissions, approvals, monitoring, and human review should control the process.

## Slide 39/39 - Congratulations

Congratulations, you've completed this course!

You're now ready to recognize where agentic workflows may be relevant, explain when a simpler AI pattern may be enough, and know when deeper product, technical, governance, or deployment expertise should be brought in.

**Course completed**

**Next up in OpenAI Foundational Knowledge:** OpenAI Product Portfolio Overview (Course, 53 min)

Discover how to connect real business needs to the right OpenAI technology paths with a practical, workflow-first approach. Explore the major OpenAI portfolio categories—ChatGPT, API, Codex, agents, and open models—and learn how each supports different users, workflows, and deployment requirements. Practice recognizing common solution patterns, mapping customer problems to technology categories, and understanding how multiple OpenAI capabilities can work together for broader outcomes. Build confidence in identifying relevant AI solutions by focusing on the work, the people involved, the experience, and the requirements—before jumping to a product recommendation.
