# Platform Capabilities and Developer Tools

## Slide 1/48 - Title

Platform Capabilities and Developer Tools

Created July 2026

## Slide 2/48 - Introduction

Platform capabilities help teams turn AI ideas into working products, workflows, and developer experiences.

In this course, you'll practice choosing capabilities based on workflow need, not feature lists.

You'll focus on what role each capability plays, what tradeoffs it introduces, and what needs validation before recommendation.

## Slide 3/48 - What you'll learn

By the end of this course, you'll be able to:

- Distinguish platform capabilities by the roles they play in interaction, context, action, orchestration, evaluation, and developer workflows.
- Use the Responses API as the default starting primitive for new custom API projects, and identify when Structured Outputs, File Search, tool calling, the Agents SDK, MCP, evals, Audio or Realtime capabilities, or Codex may be relevant.
- Map capabilities to customer or developer workflows.
- Recognize tradeoffs, dependencies, controls, and escalation signals.
- Apply building-block logic in technical conversations and handoffs.

Let's get started!

## Slide 4/48 - Introduction (Module: Think in capabilities, not feature lists)

This module introduces platform capabilities. You'll use them to move from a broad feature list to a smaller, clearer set of capabilities that a workflow actually requires.

This matters because partners are often asked about capabilities by name.

The key question for this module is: Which building-block roles are required for this workflow to succeed, and which capabilities can be deferred, validated, or escalated?

## Slide 5/48 - What a platform building block is

A platform capability is a reusable technical building block that helps a solution perform one part of the work. A capability becomes useful when it is connected to a clear workflow requirement.

For example, a workflow may need a user to request something, a system to retrieve approved context, a model to generate an output, a tool to check a system, a review step before action, and observability signals after launch.

Each of those needs may point to a different building block.

A strong recommendation explains four things: what role the building block plays, why it is needed now, what dependency, control, or tradeoff it introduces, and what must be validated before it becomes part of a recommendation.

Think about OpenAI capabilities by their role in work (flip cards):

- **API capabilities** — Can act as the builder and integration path for embedding intelligence into products, operations, and customer-facing experiences.
- **ChatGPT experiences** — Can support employee-facing work: ChatGPT Chat for collaborative thinking and creation, and ChatGPT Work for delegated knowledge work where available and enabled.
- **Codex and developer workflow tools** — Can support software delivery and engineering work.
- **Agents** — Can move from answering questions toward doing work with context, tools, guardrails, and approval.

The course is not asking you to memorize a catalog. It is asking you to connect each capability to the job it performs in the workflow.

## Slide 6/48 - Why feature-first thinking creates weak recommendations

Feature names can sound decisive. A customer may say: "We need retrieval," "We need an agent," or "We want to use Codex."

But a feature name by itself does not explain what the workflow requires.

Feature-first recommendations often add complexity before the team has confirmed the user need, source content, output format, action boundary, risk level, or evidence required.

This can lead to solutions that are overbuilt, hard to validate, poorly routed, or difficult to hand off.

For example, an account brief assistant may need approved account context. Retrieval may be relevant. It may need every brief to follow the same format. Structured output may be relevant. It may need to query CRM data. Tool use may be relevant, but only after the team confirms access, permissions, failure handling, ownership, and whether the first version truly needs system access.

Before adding a capability, ask: What role does this capability play in the workflow? What dependency or control does it introduce? What would happen if we left it out of the first version? What must be validated before recommending it?

Feature names help describe a solution. Workflow roles explain why each capability belongs there.

## Slide 7/48 - Capability roles

Capabilities are easier to select when you group them by the role they play in a workflow.

A role tells you what the capability contributes, what dependency it may introduce, and what questions you need to validate before recommending it.

- **Interaction** — How users or systems engage with the solution. For example, a sales user requests an account brief through an internal app, workspace surface, or workflow.
- **Context** — How the system accesses the information it needs. For example, the assistant uses approved account notes, opportunity details, call summaries, policy documents, or other business context before generating a brief.
- **Action** — How the system uses tools or affects other systems. For example, the workflow checks CRM status, runs a calculation, creates a follow-up task, or prepares an update for approval.
- **Orchestration** — How multi-step work is coordinated. For example, the workflow collects a request, retrieves context, checks for missing fields, drafts a brief, asks for review, and prepares a next step.
- **Evaluation** — How quality and reliability are tested. For example, evals check whether the brief is complete, grounded in approved sources, correctly formatted, and useful for the sales workflow.
- **Developer workflow** — How builders create, test, review, and maintain solutions. For example, a development team may use Codex or related tooling to implement an assistant, add tests, review code changes, or maintain an integration.
- **Governance and observability** — How activity is controlled, monitored, and improved. For example, the team defines permissions, approval points, logs, usage signals, quality checks, and escalation paths.

Use this map to see that each capability is selected because it plays a role in the workflow, not because it appears on a feature list.

A strong recommendation explains which roles are required, which capabilities may fill those roles, and what still needs validation before the capability set is confirmed.

Visual diagram: a circular map with "Workflow need" at the center, surrounded by seven connected role nodes: Interaction, Context, Action, Orchestration, Evaluation, Developer workflow, and Governance (observability).

## Slide 8/48 - Minimum viable capability set

A minimum viable capability set is the smallest responsible combination of capabilities needed for the workflow to succeed.

This is not the smallest demo.

It is the smallest responsible version of the workflow: enough capability to serve the user need, enough controls to manage the risk, and enough evidence to support the next technical decision.

Use the minimum viable capability set to distinguish: what is required now, what can be added later, what adds risk, complexity, cost, or operational burden, what depends on data, access, permissions, source quality, or system readiness, and what needs product, security, data, integration, or implementation validation.

For example, an internal account brief assistant may need an interaction layer, retrieval from approved account notes, structured output, evals, and human review. It may not need Realtime, multimodal input, MCP-style connections, Codex, or agentic tooling unless the workflow specifically requires those capabilities.

A smaller, well-justified set gives the customer and internal team a clearer starting point.

It also makes dependencies, tradeoffs, validation questions, and escalation needs easier to explain.

Visual diagram: "Minimum viable capability set" with three columns — "Required now," "Optional later," and "Needs validation."

## Slide 9/48 - Real-world example: account brief

A customer says: "We want an assistant that helps sales teams prepare account briefs."

That request gives you a useful workflow area, but it does not yet tell you which platform capabilities are required.

Before recommending capabilities, identify what the assistant needs to do, what information it can use, what output it must produce, and how the result will be reviewed.

In an account brief workflow, a practical capability set could include an interaction layer so a sales user can request the brief from the right surface, such as an internal app, workflow, or workspace experience.

It may include retrieval from approved sources so the assistant can use account notes, opportunity details, call summaries, or other approved customer context.

It may include structured output so each brief follows a consistent format, such as account overview, business priorities, open opportunities, risks, and suggested next steps.

It may include tool use if the workflow needs to query a CRM, check opportunity status, or retrieve account fields from a connected system.

It may include evals to test whether the brief is complete, grounded in approved sources, formatted correctly, and useful for the sales workflow.

It should include human review before the brief is used in a customer-facing meeting, proposal, or follow-up.

Each capability should have a clear reason for being included.

Retrieval depends on approved, current, and accessible source content. Structured output depends on a defined brief format. Tool use depends on system access, permissions, failure handling, and ownership.

Evals depend on success criteria and representative test cases. Human review depends on how the brief will be used and what risk the output carries.

Useful validation questions include: Which account sources are approved? Where do they live? Do users have different access permissions? Does the assistant need CRM access, or can users provide the required context? What format should every brief follow? Who reviews the output before customer-facing use?

## Slide 10/48 - Recommended exercise: Identify capability roles

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Practice moving from a broad feature request to the capability roles a workflow may actually require.

**Task:** Use the workflow below: A customer says: "We want an assistant that helps sales teams prepare account briefs." The assistant may need to let a sales user request a brief, use approved account notes or call summaries, produce a consistent brief format, and route the output to a sales user for review before customer-facing use.

The customer has not yet confirmed which account sources are approved, where those sources live, whether users have different access permissions, whether CRM access is required, what format the brief should follow, or who reviews the output.

Reflect on what capability roles this workflow may require before naming specific platform capabilities.

Write short notes that identify:

- The workflow outcome
- The user group
- The required capability roles
- Any optional capability roles
- Questions that must be answered before capability selection

**Estimated time:** 2-3 minutes

Suggested output and reflection: Create a short capability-role note that clarifies what the workflow needs before naming specific platform capabilities.

## Slide 11/48 - Knowledge check

**Question:** A customer asks for an internal account brief assistant. Which recommendation shows the strongest capability judgment for a first version?

- Start with CRM write-back so the assistant can update records as soon as it generates a brief.
- Start with all major platform capabilities so later teams do not need to rework the solution.
- **Start with the workflow roles: user request, approved context, consistent output, review, and validation.** ✓ Correct
- Start with an agentic pattern because account planning often involves several sales steps.

This starts with the work the assistant must support before naming capabilities. It keeps the first version focused on the roles required for a useful account brief: interaction, context, structure, review, and validation.

## Slide 12/48 - Summary

You can now explain a platform capability as a reusable technical capability that performs a specific part of a workflow. The main decision logic is simple: start with the workflow, name the role each capability plays, and avoid adding capabilities that are not required by the first responsible version.

This keeps the recommendation grounded in what the workflow needs instead of what a feature list makes possible.

Next, you'll apply that logic to two foundational building-block decisions: how the workflow interacts with AI and what approved context it needs.

## Slide 13/48 - Introduction (Module: Select interaction and context capabilities)

This module introduces interaction and context capabilities. You'll use them to decide how the workflow should interact with AI, what output it must produce, and what approved information it needs.

This matters because many weak recommendations jump straight to "use the API" or "add retrieval" before the team knows what request is being made, who or what consumes the output, what format is needed, or whether the source material is ready.

The key question for this module is: How should the workflow interact with AI, what output must it produce, and what approved context does it need to use?

## Slide 14/48 - The interaction layer

The interaction layer is the part of a solution where an application, workflow, or system asks AI to perform work and receives an output it can use.

In a customer workflow, this layer shapes the basic exchange between the surrounding system and the AI capability.

It determines what request is sent, which instructions guide the response, what inputs or context are included, what output format is expected, and what happens after the output is returned.

You can think of the interaction layer as the workflow handoff point: Request → Instructions → Inputs → Context → Output → Review or action.

For example: An account brief assistant may let a sales user request a brief from an internal app or workspace surface. The interaction layer would pass the account identifier, brief instructions, approved context, and required output format to the AI capability. The returned brief might then go to the user for review before it is used in a customer meeting.

For a new custom API project, the Responses API is the default starting primitive for the interaction layer.

At this level, focus on the role the interaction layer plays in the workflow: how AI is called, what information is included, what output is needed, and how the result will be reviewed, stored, displayed, or acted on.

Useful questions include: Who or what sends the request? What does the request need to include? What instructions should guide the response? What context should be included or retrieved? What format should the output follow? Who or what uses the output next? Does the output trigger review, storage, a tool call, or another workflow step?

A clear interaction layer helps the team decide whether the workflow needs an API interaction path, a workspace surface, structured outputs, retrieval context, tool use, review steps, or evals.

Visual diagram: a flow labeled "Request → Instructions → Inputs → Context → Output → Review or action," showing what the surrounding workflow sends to AI and what must happen after AI returns an output.

## Slide 15/48 - Responses API as the starting point for new custom API projects

For a new custom API project, start with the Responses API. It is the default starting point when a team needs AI capability inside a custom application, workflow, product feature, or system-to-system process.

In this type of path, the surrounding application controls how AI is called, what information is provided, what format the output should follow, and what happens after the response is returned.

Fit signals may include: a custom application experience; text, image, or file inputs supported by the selected Responses API model and configuration; voice or live audio routed through current Audio or Realtime guidance; structured outputs; tool use; multi-step interaction; retrieval or grounding; system-to-system workflow; need for API-level control.

For example, an internal account brief generator embedded in a sales workflow may need an API interaction layer if the brief must be generated inside an existing application, returned in a structured format, logged for review, or passed to another workflow step.

Do not treat a custom API build as automatically required for every AI workflow.

If an employee-facing ChatGPT experience supports the workflow — including ChatGPT Work for delegated knowledge work, where available and enabled — that may be the better starting point. When the customer needs a custom application, product feature, or system integration, use the Responses API as the default starting primitive.

Before making detailed technical claims, validate current capabilities and implementation details in approved product material or official documentation.

## Slide 16/48 - Designing outputs for downstream use

Do not only ask: "What should the model generate?"

Ask: "What does the output need to become in the workflow?"

An output might become a user-facing answer, a structured record, a draft document, a JSON object, a field update recommendation, a ticket summary, a review item, a search result, or a handoff note. The downstream use affects the capabilities you need.

When a downstream system needs a reliable structured contract, use Structured Outputs with an appropriate JSON Schema.

For an account brief assistant: the output may need a consistent brief format — that points toward structured output. It may need source references — that points toward retrieval evidence or citations. It may need human review before customer-facing use — that points toward review and eval decisions. It may need to trigger a CRM update — that points toward tool-use boundaries and approval design.

Before recommending an interaction layer, clarify: Who or what will consume the output? Does the output need a fixed or structured format? Are evidence, citations, or source references needed? Does the output trigger a tool, update, or human review? What should happen when the output is uncertain, incomplete, or unsupported?

A strong output design makes the next step clear. It shows what AI should produce, what the surrounding system or user will do with it, and which capabilities are needed to make that output reliable enough for the workflow.

## Slide 17/48 - The context layer: File Search, retrieval, and structured knowledge

Many workflows need access to business-specific context before AI can produce a useful output. Context may include approved documents, policies, knowledge bases, support content, customer records, account notes, product information, workflow history, or prior outputs.

In the Intelligence at Work language, context is what AI knows about the business. In this course, focus on context as a building-block role: the information the workflow needs to do the work responsibly.

In some workflows, the user or application can provide enough context directly in the request.

In other workflows, the system needs to retrieve information from approved sources before generating the answer.

More complex workflows may also require structured knowledge, permissions logic, source filtering, or specialist implementation input.

File Search and retrieval are context-layer capabilities. They may be relevant when the workflow needs to ground outputs in approved files, documents, or knowledge sources.

The key decision is not: "Should we add retrieval?"

The key decision is: "What approved context does the workflow need, and is that context ready to support reliable outputs?"

For example, an account brief assistant might receive a few approved notes directly from a user for a one-off draft.

A more repeatable version might retrieve approved account notes, opportunity details, and call summaries from defined sources.

If different sales users have different access rights, the recommendation also needs access and permission validation before retrieval is included.

## Slide 18/48 - Retrieval fit and readiness questions

Retrieval is useful only when the workflow has source content that can support the answer or output.

Before adding retrieval or File Search-style support, confirm that the workflow has trustworthy sources, clear ownership, appropriate permissions, and a plan for testing whether the right information is being found.

Ask: What is the source of truth? Who owns and maintains the content? How current, complete, and trustworthy is the content? Do access or permissions vary by user group? Are citations, source links, or evidence required? What happens when content is missing, outdated, or conflicting? How will retrieval quality be tested?

Retrieval readiness includes both content readiness and access readiness.

A strong recommendation explains which sources the workflow should use, why those sources are appropriate, what permission boundaries apply, and how the team will evaluate whether retrieval is accurate enough for the workflow.

For example, an internal application that turns meeting notes into project updates may not need retrieval if the user provides the approved notes directly each time.

An assistant that answers internal IT policy questions likely needs retrieval from approved policy sources, source freshness checks, access validation, and a review process for conflicting or outdated guidance.

## Slide 19/48 - Recommended exercise: Decide interaction and context needs

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Practice deciding how a workflow should interact with AI, what output it must produce, and what approved context it needs.

**Task:** An internal team wants an account brief generator. A sales user selects an account and requests a brief from an internal application or workspace experience. The output must follow a consistent format and include source references. The brief may use approved account notes, opportunity details, call summaries, or user-provided notes. Some sales users may have different access to account documents.

The team has not yet confirmed: which sources are approved, whether users will provide context directly, whether retrieval or File Search-style support is needed, or how access permissions should be handled.

Reflect on the interaction and context decisions this workflow requires.

Write short notes that identify:

- Whether the workflow likely needs an API interaction layer, workspace surface, or another interaction path
- What approved context sources may be required
- Whether review or evals may be needed
- Whether retrieval or File Search-style support may be relevant
- What source quality questions need validation
- What access and permission questions need validation
- Whether structured output is needed

**Estimated time:** 3–4 minutes

Suggested output and reflection: Create a short interaction-and-context note that identifies the required output, approved context, and validation questions.

## Slide 20/48 - Knowledge check

**Question:** A team wants an internal application that generates account briefs from approved account notes. The output must follow a consistent format and include source references. Some users may have different access to account documents. Which recommendation is strongest?

- Use Realtime so every brief can be generated as the user speaks
- Use Codex because the team may need software changes later.
- **Use structured output, approved retrieval, access validation, and review/evals** ✓ Correct
- Use retrieval only; permissions can be handled after launch.

The workflow requires a consistent output, grounded context, source-aware retrieval, and permission validation. Review or evals also help confirm that the generated brief is complete, grounded, and appropriate before use.

## Slide 21/48 - Summary

You can now separate two foundational questions: how the workflow interacts with AI and what context the workflow needs. Interaction decisions clarify the request, instructions, inputs, output, and next step. Context decisions clarify approved sources, source quality, access, permissions, and retrieval-readiness questions.

Together, these decisions help you avoid recommending API or retrieval capabilities before the workflow requirements are clear.

Next, you'll examine what changes when the workflow needs to connect with external systems or take action through tools.

## Slide 22/48 - Introduction (Module: Connect systems with tools, MCP-style integrations, and boundaries)

This module introduces tool use, MCP-style integrations, and tool boundaries. You'll use these concepts to decide when a workflow needs access to external systems and what controls must be clarified before that access is recommended.

This matters because connected workflows can move from "AI helps produce an answer" to "AI affects another system." That shift introduces stronger requirements around permissions, approvals, logging, failure behavior, testing, ownership, and escalation.

The key question for this module is: What tools or system connections does the workflow need, and what boundaries must be in place before those tools are used?

## Slide 23/48 - When workflows need tools

Tools allow AI-supported workflows to interact with external systems, functions, or services. A tool might help the workflow look up information, run a calculation, create a draft, check a status, call an internal API, update a field, or trigger the next step in a process.

Tool use becomes relevant when the AI output depends on something outside the prompt, retrieved documents, or static context.

For example, an account brief assistant may need to check current CRM opportunity status, retrieve account fields, calculate pipeline value, or prepare a draft update for a sales record.

Start by clarifying the role the tool plays in the workflow. Some tools only retrieve or inspect information.

Others create, update, send, approve, schedule, or trigger work. Those differences matter because action-taking tools usually introduce stronger requirements for permissions, approval, logging, testing, failure handling, and ownership.

Current API guidance distinguishes direct tool calling from programmatic tool calling.

Use direct tool calling when the model needs to select a tool, inspect the result, reason about intermediate information, or decide what to do next.

Use programmatic tool calling only for predictable, bounded processing — such as high-volume retrieval, joins, aggregation, or transformation — when the model does not need to inspect every intermediate result.

Tools may support actions such as: retrieving records, checking status, running calculations, creating drafts, updating fields, triggering workflows, calling internal APIs.

The key question is: What should the tool be allowed to do, and what must happen before the result is used?

A strong recommendation explains why the tool is needed, whether it is read-only or action-taking, what boundaries apply, and what must be validated before tool use becomes part of the solution.

## Slide 24/48 - Read-only versus action-taking tools

When a workflow uses tools, first distinguish between tools that only retrieve or inspect information and tools that can change something in another system.

Read-only tools help the workflow look up, retrieve, inspect, or calculate information without changing a record or triggering a downstream process.

For example, an account brief assistant might retrieve CRM opportunity status, check account fields, or calculate pipeline value.

Action-taking tools can create, update, delete, send, approve, schedule, or trigger downstream work.

For example, the same account brief workflow might update a CRM field, create a follow-up task, send a draft email, or trigger an approval workflow.

That distinction changes the controls required. A read-only lookup may still need access permissions, source validation, logging, and retrieval-quality testing. An action-taking tool usually requires stronger boundaries because the AI-supported workflow can affect records, users, customers, or business processes.

Action-taking tools usually require: approval gates, restricted actions, logging or traceability, failure handling, clear ownership, testing.

Move from lookup to action only after the boundaries are clear. Before recommending an action-taking tool, confirm what the tool can do, which actions are allowed, what requires human approval, what happens if the tool call fails, who owns the integration, and how the behavior will be tested.

## Slide 25/48 - MCP-style connections

MCP-style connections may be relevant when a workflow needs repeatable, governed access to external tools, systems, or context across agentic or developer workflows.

At this level, think of MCP-style connections as a possible pattern for making tool or context access more reusable and controlled.

The purpose is not to teach MCP implementation.

The purpose is to help you recognize when a simple one-off integration may not be enough and when specialist validation may be needed.

MCP-style connections may be worth evaluating when the workflow involves: multiple tools or systems, reusable tool connections, agentic workflows, developer or platform-team involvement, governance over tool access.

For example, an account brief workflow may only need a simple tool call if it checks one CRM field. A broader sales-workflow assistant may need reusable access to CRM records, call summaries, account documents, task systems, and approval workflows.

In that case, an MCP-style connection may be worth evaluating because the access pattern is broader, repeatable, and governance-sensitive.

Use MCP-style connections selectively. Simpler workflows may only need a direct API integration, a read-only lookup, or a basic tool call. When the connection pattern affects permissions, system access, developer tooling, agent behavior, or governance, involve the right product, platform, security, data, or implementation specialists before making a recommendation.

## Slide 26/48 - Tool-boundary questions

A tool boundary explains what the AI-supported workflow can access, what it can do, what requires approval, what happens when something goes wrong, and who owns the integration.

This is especially important when a workflow moves from reading information to taking action. An account brief assistant that retrieves CRM opportunity status has a different risk profile from one that updates a forecast field, creates a task, or sends a follow-up message.

Before recommending tool use, ask: Which tools are needed? Which tools are read-only? Which tools are action-taking? What actions are allowed? What actions are restricted? What requires human approval? What happens if a tool call fails? What should be logged? Who owns the integration? What should be tested? What needs to be escalated?

Use the answers to decide whether tool use belongs in the minimum viable capability set, whether it should be deferred, or whether product, security, data, integration, or implementation specialists need to validate the recommendation first.

## Slide 27/48 - Real-world example

A procurement assistant may need to check vendor status before helping a business user prepare an intake request.

In a read-only version, the assistant retrieves vendor records, policy status, or contract metadata and returns a summary for review.

The workflow might answer questions such as: Is the vendor already approved? Is the contract active? Are there policy notes the requester should review?

In an action-taking version, the assistant might create a ticket, update a vendor record, or send an approval request.

That version introduces stronger controls: approval gates, restricted actions, logging, ownership, testing, failure behavior, and escalation.

Use this comparison to see how the same vendor-status need can create two different workflow boundaries: one that retrieves information for review, and one that may change an external system.

The important distinction is not the vendor system itself. It is whether the workflow only retrieves information or can change something in that system.

A read-only workflow still needs access validation, source quality checks, and logging where appropriate. But once the workflow can take action, the recommendation also needs stronger boundaries: what actions are allowed, what requires human approval, what happens if a tool call fails, who owns the integration, and what should be tested before use.

This is why a recommendation should define the tool boundary before adding tool use to the minimum viable capability set.

Visual diagram: a chart with "level of control" rising diagonally, split into two boundary boxes — "Read-only boundary" (Retrieve → Inform → Review) and "Action-taking boundary" (Prepare change → Approve → Execute → Log/monitor) — axes labeled "Y - action taking" and "X - retrieval."

## Slide 28/48 - Recommended exercise: Define tool-use boundaries

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Practice distinguishing read-only tool access from action-taking tool use and identifying the controls that follow.

**Task:** A procurement assistant may need to help a business user prepare an intake request. The assistant may need to check vendor status from an approved vendor system. In a first version, the assistant may only retrieve vendor information and return a summary for review. In a later version, the assistant may create a ticket, update a vendor record, or send an approval request. The team has not yet confirmed whether the workflow is read-only, action-taking, or a combination of both.

Reflect on the tool-use boundary this workflow requires.

Write short notes that identify:

- Whether tools or system connections are needed
- Which parts of the workflow would be read-only
- Whether an MCP-style connection pattern may require specialist validation
- Which parts of the workflow would be action-taking
- What approvals, restrictions, or human review points may be needed
- What should happen if a tool call fails
- What needs to be logged, tested, owned, or escalated

**Estimated time:** 3–4 minutes

Suggested output and reflection: Create a short tool-boundary note that distinguishes read-only access from action-taking behavior and names the main control questions.

## Slide 29/48 - Knowledge check

**Question:** A workflow needs to retrieve CRM opportunity status and update a forecast field. Which statement is strongest?

- Use MCP automatically because an external business system is involved.
- **Split the boundary: read status; require approval before write-back.** ✓ Correct
- Avoid tool use because connected systems always create too much risk.
- Treat both as read-only because they involve the same CRM system.

Retrieving information and changing a business record have different control needs. The read-only step may require access validation and logging, while write-back should introduce approval, restrictions, failure handling, testing, and ownership.

## Slide 30/48 - Summary

You can now explain why tool use is not just a capability choice. It is also a boundary decision. Read-only tools, action-taking tools, and MCP-style connection patterns can each be useful, but only when they serve a clear workflow role.

The stronger the system access or action-taking behavior, the more important it is to define approvals, restrictions, logging, testing, ownership, and escalation.

Next, you'll decide when higher-complexity capabilities are justified, including Realtime, multimodal capabilities, agentic tooling, evals, observability, Codex, and developer workflow tools.

## Slide 31/48 - Introduction (Module: Choose real-time, multimodal, agentic, or developer workflow tools when justified)

This module introduces conditional capabilities: capabilities that can be valuable, but should be added only when the workflow justifies them.

You'll use this module to decide when Realtime, multimodal capabilities, agentic tooling, evals, observability, Codex, or developer workflow tools are required by the workflow and when a simpler pattern is enough.

The key question for this module is: Which conditional capabilities are required by the workflow experience, risk level, or operating model, and which should be deferred or validated further?

## Slide 32/48 - Interaction shape matters

The interaction shape describes how the user, application, or system engages with AI.

Before recommending Realtime, multimodal capabilities, or other conditional capabilities, clarify what kind of experience the workflow actually requires.

Some workflows can happen asynchronously.

For example, an internal account brief can be requested, generated, reviewed, and refined before a customer meeting.

Other workflows need a more immediate experience, such as live customer support, voice interaction, or real-time assistance while a user is completing a task.

Interaction shapes may include: asynchronous processing, chat-style interaction, embedded product interaction, voice conversation, real-time support, image or document understanding, multimodal input and output.

The interaction shape affects the capability set. A voice-support workflow may need Realtime or audio capabilities because the user expects a live exchange.

A document-review workflow may need multimodal capability if the system must interpret screenshots, scanned forms, images, or document layouts.

An embedded product workflow may need an API interaction layer, structured outputs, evals, and observability so the surrounding application can use the AI output reliably.

Choose the simplest interaction shape that supports the workflow. Realtime and multimodal capabilities are strongest when they are required by the user experience, input format, or output format. When the workflow can succeed with asynchronous processing or text-based interaction, the simpler pattern is often easier to validate, govern, and operate.

## Slide 33/48 - Realtime and multimodal validation questions

Realtime and multimodal capabilities can change the user experience, but they also introduce new validation needs.

Before recommending them, confirm that the workflow truly requires live interaction, voice, images, documents, or mixed input and output formats.

These capabilities are strongest when modality is part of the workflow requirement.

Real-time voice may be important for live support or hands-free assistance.

Multimodal capability may be important when the system needs to interpret screenshots, forms, images, or document layouts.

If the same workflow can succeed through asynchronous or text-based interaction, the simpler pattern may be easier to validate and operate.

Ask: What modality does the user provide? What modality should the system return? How quickly does the response need to happen? Can the workflow tolerate delay? What data is captured, stored, or reviewed? What consent, privacy, or accessibility needs apply? What happens when the system mishears, misreads, or lacks confidence? How will quality be evaluated?

Use the answers to decide whether the workflow should follow current Audio or Realtime guidance, use multimodal capabilities, remain asynchronous or text-based, or receive specialist validation before recommendation.

## Slide 34/48 - When agentic tooling is justified

Agentic tooling may be relevant when a workflow needs to coordinate multiple steps toward an outcome.

This usually means the AI-supported system must keep track of context, use tools, follow instructions, manage handoffs, request approval, and support testing or monitoring across the workflow.

In Intelligence at Work language, the agentic runtime is where and how AI does work.

In this course, focus on the practical selection question: does the workflow need coordinated steps, tools, controls, and validation beyond a simple interaction or tool call?

Use the Agents SDK when a custom application requires managed orchestration, handoffs, guardrails, and tracing. A single bounded call that does not need those orchestration features may be better served by a simpler interaction or tool-calling pattern.

For example, an account brief assistant that only drafts a brief from approved notes may need retrieval, structured output, evals, and human review.

A more agentic version might gather account context from several systems, check whether required fields are missing, ask the user for clarification, draft the brief, prepare follow-up actions, request approval before updating a CRM, and log the steps taken.

Agentic tooling may be relevant when a workflow requires: multi-step orchestration, tool use across systems, workflow context or state, human approval points, reusable instructions, handoffs, testing and tracing, integration with applications or systems, production monitoring.

Use agentic tooling when the workflow needs coordinated steps, controls, and validation across a process. Simpler workflows may be better served by an interaction layer, retrieval, structured output, or a single bounded tool call.

Before recommending agentic tooling, confirm what steps need to be coordinated, what tools or systems are involved, where approvals are required, what should be traced, who owns the workflow, and how the team will evaluate safe and reliable behavior.

## Slide 35/48 - Evals and observability as selection considerations

Every selected capability creates quality and operational questions.

Retrieval raises questions about source relevance and groundedness. Structured outputs raise questions about format compliance. Tool use raises questions about correctness, permissions, failure handling, and approval behavior. Agentic workflows raise questions about step sequence, tool use, handoffs, tracing, and monitoring.

Evals help teams test whether the selected capabilities perform well enough for the workflow.

Observability helps teams understand what happened during a workflow run, especially when something fails, changes, or needs investigation.

For example: An account brief assistant that uses retrieval should be tested for whether it finds the right approved account context. If it uses structured outputs, the team should test whether every brief follows the required format. If it uses tools, the team should test whether tool calls are correct, bounded, and handled safely when they fail. If it includes human review or escalation, the team should test whether the right cases are routed for review.

Evals may check: output quality, format compliance, retrieval quality, tool-use correctness, escalation behavior, safety behavior, regression after changes.

Observability may help teams understand: which steps ran, which tools were used, which context or sources were included, what errors occurred, which approvals were requested or granted, where failures happened, what information is available for investigation.

When a platform capability introduces a new quality, safety, or operational question, capture it in the capability decision structure as an eval need, observability signal, validation question, or escalation point.

## Slide 36/48 - When Codex or developer workflow tools fit

Codex and developer workflow tools may be relevant when the customer need sits inside software delivery.

These capabilities support engineering teams as they understand codebases, make or review changes, generate or repair tests, debug issues, maintain documentation, and delegate structured engineering tasks across repositories or development workflows.

Before recommending Codex, identify the specific developer workflow.

For example, a team may need help reviewing pull requests, generating tests for a service, debugging a recurring issue, documenting a repository, or maintaining release-related changes. Each need may point to different context requirements, permissions, review rules, validation checks, and ownership questions.

Codex or developer workflow tools may be relevant when the customer need involves: codebase understanding, code changes, test generation or repair, debugging, repository-based workflows, pull request review, documentation generation, release or maintenance support, engineering task delegation, developer productivity bottlenecks.

An internal account brief assistant probably does not need Codex unless the work is about building, testing, reviewing, or maintaining the software behind that assistant.

The account brief workflow may need interaction, retrieval, structured output, evals, observability, or human review.

Codex becomes relevant when the recommendation shifts toward developer work, such as implementing the assistant, reviewing code changes, adding tests, or maintaining the integration.

A strong recommendation names the developer workflow first, then explains why Codex or developer tooling is the right building block. It should also identify repository access, environment or sandbox considerations, approval and review expectations, testing requirements, and any product, security, implementation, or engineering-owner validation needed before recommendation.

## Slide 37/48 - Recommended exercise: Sort conditional capabilities

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Practice deciding which higher-complexity capabilities are required now, optional later, not needed for this version, or need validation before recommendation.

**Task:** An internal account brief assistant uses approved account notes, produces a consistent brief, and routes the output to a sales user for review. The first version does not require live voice interaction, image understanding, document layout interpretation, codebase work, autonomous system updates, or engineering task delegation. CRM lookup may be useful, but the team has not confirmed whether the first version needs CRM access, what fields would be approved, or what permissions apply.

Reflect on which capabilities are justified by this first-version workflow and which would add unnecessary complexity.

Sort the capabilities below into four categories: Required now, Needs validation, Optional later, Not needed for this version.

Capabilities to sort: interaction layer or workspace surface, retrieval from approved account notes, structured output, human review, evals for completeness and groundedness, basic observability signals, CRM read-only lookup, CRM write-back or action-taking tool, Realtime voice interaction, multimodal image or document understanding, agentic orchestration, Codex or developer workflow tools.

**Categories:** Required now / Needs validation / Optional later / Not needed for this version.

**Estimated time:** 3–4 minutes

Suggested output and reflection: Create a short conditional-capability sort that separates required capabilities from optional, unnecessary, and validation-dependent capabilities.

## Slide 38/48 - Knowledge check

**Question:** A customer wants a first-version internal account brief assistant. It uses approved account notes, follows a consistent brief format, and routes output to a sales user for review. It does not need voice, image understanding, codebase work, or autonomous updates. Which choice best avoids overbuilding?

- Use Codex because the assistant will eventually need software implementation.
- Add CRM write-back now because sales users may want updates later.
- **Start with approved context, structured output, review, evals, and basic observability; validate CRM lookup separately.** ✓ Correct
- Add Realtime, multimodal, Codex, and agentic orchestration now so the workflow is future-ready.

This choice keeps the first version tied to the workflow need. Higher-complexity capabilities should be added only when the workflow requires them or when validation shows they belong in the recommendation.

## Slide 39/48 - Summary

You can now distinguish foundational capabilities from conditional ones.

Realtime, multimodal capabilities, agentic tooling, evals, observability, Codex, and developer workflow tools can all be valuable, but they should be selected based on workflow shape, modality needs, operating complexity, quality requirements, and developer-workflow fit. They should not be added just because they are available.

Next, you'll apply the course decision logic to choose the minimum viable capability set for a workflow.

## Slide 40/48 - Introduction (Module: Choose the smallest responsible capability set)

This module brings the course decision logic together.

You'll practice choosing the smallest responsible capability set for a workflow: what is required now, what can wait, and what needs validation or escalation before recommendation.

The key question is: What belongs in the first responsible recommendation?

## Slide 41/48 - Four-part capability decision structure

A strong first-version capability recommendation answers four questions. Use the structure below as a reference for organizing technical judgment.

- **Workflow need and required capability roles** — Clarifies what the workflow must do, who uses the output, and which roles are needed, such as interaction, context, action, evaluation, developer workflow, governance, or observability. Guiding question: What work must the solution support?
- **Minimum viable capability set** — Clarifies the smallest responsible set of capabilities needed for the first version, separated from optional later enhancements. Guiding question: Which capabilities are required now, and which should be deferred?
- **Key dependencies, controls, and tradeoffs** — Clarifies approved data sources, access permissions, tool boundaries, approval gates, eval needs, logging, ownership, operational complexity, and other dependencies. Guiding question: What does each capability introduce or depend on?
- **Validation and escalation questions** — Clarifies product details, source readiness, system access, security review, data permissions, integration ownership, implementation feasibility, and governance requirements. Guiding question: What needs validation or specialist review?

Use this structure to prepare better questions and clearer handoffs. Do not use it to make unsupported product, pricing, compliance, security, architecture, implementation, or availability claims.

## Slide 42/48 - How to use the decision structure in technical conversations

The four-part decision structure helps keep early recommendations grounded when stakeholders move quickly from a customer need to product or capability names.

Use it to clarify: what the workflow needs, which capability roles are required, which capabilities belong in the first version, which capabilities add unnecessary complexity, what dependencies or controls each capability introduces, and what must be validated before the recommendation moves forward.

For example, if a customer asks for "an agent that prepares account briefs," do not start by naming every possible capability. First clarify the workflow outcome, required context, output format, tool needs, review points, eval needs, observability needs, and unresolved validation questions.

The goal is not to fill in a document. The goal is to make a clearer, safer, and more technically defensible recommendation.

## Slide 43/48 - Boundary language for early recommendations

A platform-capability recommendation should be clear about its boundaries.

Use language like: "Based on the workflow described, this looks like a first-version capability set to validate, not a final implementation design." Or: "This recommendation identifies likely building blocks and open validation questions. Product, security, data, integration, governance, or implementation details may require specialist review before customer-facing use."

Avoid language that makes the recommendation sound more final than it is.

Do not present an early capability set as: a confirmed architecture, a production implementation plan, a security or compliance approval, a product availability commitment, a pricing or commercial recommendation, a detailed API, SDK, MCP, Codex, eval, or observability design, or a customer-ready implementation specification.

## Slide 44/48 - Recommended exercise: Choose the smallest responsible capability set

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Practice deciding which capabilities belong in a first-version recommendation and which should be deferred, validated, or escalated.

**Task:** An internal account brief assistant will use approved account notes, produce a consistent brief, and route the output to a sales user for review.

A draft recommendation includes: API interaction layer or workspace surface, retrieval from approved account notes, structured output, tools, MCP-style connection, Realtime voice interaction, multimodal image understanding, Agents SDK or agentic orchestration, evals, observability, Codex or developer workflow tools, CRM read-only lookup, CRM write-back tool.

The customer has not confirmed whether CRM lookup is needed, whether CRM write-back is allowed, which account sources are approved, whether users have different access permissions, or what review and eval criteria should apply.

Reflect on:

- Which capabilities are required for a responsible first version
- Which capabilities should be deferred or removed
- Which capabilities need validation before recommendation
- Which product, security, data, integration, governance, or implementation questions may need specialist review

**Estimated time:** 4–5 minutes

Suggested output and reflection: A brief reflection on the minimum viable capability set, deferred capabilities, and unresolved validation or escalation questions.

## Slide 45/48 - Knowledge check

**Question:** Match each item to the decision area where it belongs.

- Capabilities needed for the first responsible version → **Minimum viable capability set** ✓ Correct
- Workflow outcome, user group, and required capability roles → **Workflow need and required capability roles** ✓ Correct
- Product, security, data, integration, or implementation questions → **Validation and escalation questions** ✓ Correct
- Approved sources, permissions, tool boundaries, and approval gates → **Key dependencies, controls, and tradeoffs** ✓ Correct

All pairs matched correctly!

## Slide 46/48 - Summary

You can now apply building-block selection judgment to choose the smallest responsible capability set for a workflow.

A strong recommendation explains what the workflow needs, which capability roles are required, which building blocks belong in the first version, which capabilities should be deferred, and what dependencies, controls, tradeoffs, validation questions, or escalation points remain.

The four-part decision structure from this module can help organize that thinking. It is not a separate artifact to complete. The goal is to make a clearer, safer, and more technically defensible recommendation.

## Slide 47/48 - Recap

Strong platform-capability judgment depends on workflow fit, capability roles, tradeoffs, validation, and escalation.

In this course, you practiced how to think in capabilities rather than feature lists.

The central principle is: start with the workflow, choose only the capabilities the workflow needs, and escalate product, security, data, integration, governance, or implementation questions that require specialist validation.

## Slide 48/48 - Congratulations

Congratulations, you've completed this course!

You now have a practical decision process for selecting and combining platform capabilities without defaulting to feature lists or overbuilt first versions.

Before recommending a capability, question the right thing first: what workflow the solution must support, what role each capability plays, and what must be validated before it belongs in the recommendation.

Use that approach in your next customer conversation, solution review, discovery prep, or implementation handoff.

Course completed. Next up in OpenAI Technical Practitioner: "Architecture Patterns & Solution Blueprints" (Course, 50 min) — Unlock the power of pattern thinking to shape clear, practical conversations about OpenAI-powered workflows. Learn to recognize common architecture patterns — like retrieval-grounded generation, agentic orchestration, human review, multimodal interaction, and enterprise integration — and use them to build lightweight, discussable solution blueprints. Discover how to connect user needs, data, context, tools, review points, risks, and validation steps without jumping into overbuilt designs. By mastering these skills, you'll confidently guide teams from broad ideas to actionable blueprints, making assumptions visible and ensuring every solution is ready for specialist validation before deeper technical design begins.
