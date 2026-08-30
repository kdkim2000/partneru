# Tool Use, Actions, and Agentic API Workflows

## Slide 1/47 - Title

Tool Use, Actions, and Agentic API Workflows

Created July 2026

## Slide 2/47 - Introduction

**Introduction**

API solutions can do more than generate text. They can help route work, retrieve information, call systems, check status, create records, draft handoffs, and support multi-step workflows.

This course is about designing those action patterns safely. You'll compare model-only and retrieval-supported patterns, direct and Programmatic Tool Calling across function, built-in, and custom tools, and agentic workflows, then decide which pattern fits a workflow.

You'll also learn how to create a Function, Tool, and Agentic Workflow Plan that explains the recommended pattern, tool contract, execution boundary, approvals, fallback path, observability needs, verification tests, and open risks.

## Slide 3/47 - What you'll learn

**What you'll learn**

By the end of this course, you'll be able to:

- Distinguish model-only and retrieval-supported patterns, direct and Programmatic Tool Calling, function, built-in, and custom tool types, and agentic workflows; then select the appropriate pattern, or defer or mark the workflow not ready.
- Define a function or tool contract covering purpose, system access, input and output schemas, validation requirements, execution boundary, and error states.
- Explain how tools connect to agentic workflows involving multi-step work, state, approvals, or cross-system action, and set action boundaries, approval gates, escalation conditions, access assumptions, and observability requirements.
- Produce a Function, Tool, and Agentic Workflow Plan.

## Slide 4/47 - What you'll produce

**What you'll produce**

In this course, you'll build and use a Function, Tool, and Agentic Workflow Plan; a practical artifact for explaining a tool-enabled or agentic API workflow before build or deployment review.

Your plan will capture:

- **Workflow and pattern recommendation:** The workflow goal, best-fit pattern, and whether it is ready, deferred, or not ready.
- **Function or tool design:** The required function or tool, trigger, input and output schemas, and execution boundary.
- **Action and access boundaries:** Allowed, disallowed, and approval-only actions, plus access assumptions.
- **Controls and readiness evidence:** Fallback and escalation paths, observability, verification tests, and open risks.

Let's get started!

## Slide 5/47 - Introduction: Compare function calling, tool calling, hosted tools, and agent patterns

**Compare function calling, tool calling, hosted tools, and agent patterns**

Before you can recommend tools or agents, you need a shared way to name the pattern you are actually proposing. This module helps you distinguish between different patterns and tools.

You'll compare model-only responses, retrieval-supported responses, direct and Programmatic Tool Calling across function, built-in, and custom tools, and agentic workflows. Remember that the goal is to choose the simplest safe pattern for the workflow, not the most advanced option.

## Slide 6/47 - Patterns and tools definitions

**Patterns and tools definitions**

Before you decide whether a workflow needs tools or agents, you need to understand the patterns available.

These definitions are decision tools for describing what the workflow needs.

The list mixes OpenAI product terms with course-level planning categories, so keep the relationships clear:

- function calling is one form of tool calling;
- direct and Programmatic Tool Calling describe how tools are used;
- and function, built-in, and custom tools are tool types.

The course label "hosted tool" refers to platform-provided built-in tools, while "managed agent pattern" is a planning category, not a single permanent product surface.

Validate current names, support, and availability in official documentation before implementation.

Here are the definitions you'll use as you continue through the course:

**Model-only pattern**
The API generates a response without retrieving external information, calling tools, or taking action in another system.

**Retrieval-supported pattern**
The API uses approved source content to ground the response, but does not take action in an external system.

**Function tool and function calling**
A function is a specific kind of tool defined by JSON Schema. The model can return a function call with structured arguments; application code decides whether and how to execute it and returns the tool output.

**Tool calling**
The broader interaction in which the model requests use of tools made available to it. Direct tool calling returns tool calls and results through the model interaction; Programmatic Tool Calling lets the model write code that calls approved tools and processes intermediate results in a bounded stage, where currently supported.

**Programmatic Tool Calling**
A currently documented tool-calling pattern for predictable, bounded processing such as retrieval, joins, aggregation, transformation, or large intermediate results. Use direct tool calling when the model needs to inspect intermediate information and decide what to do next. Validate current model and tool support before implementation.

**Built-in tool (course label: hosted tool)**
A platform-provided tool, such as a currently documented search or code-execution capability. Availability and behavior can change.

**Custom tool**
An OpenAI tool type that accepts free-form text input and returns text output. This is distinct from a function tool, which uses JSON Schema for structured arguments.

**Managed agent pattern (course-level category)**
A planning category for a documented platform-supported or application-managed agent implementation that coordinates goals, tools, state, approvals, and handoff within defined boundaries. Validate the specific agent surface before implementation.

## Slide 7/47 - Function calling

**Function calling**

Function calling is one form of tool calling.

A function tool is defined by JSON Schema, and the model can return a function call with structured arguments.

Your application validates those arguments, checks permissions and approvals, executes the code when appropriate, and sends the tool output back to the model or client.

Use a function tool when the workflow needs the model to translate natural language into structured arguments for a narrow application function, such as:

- Structured routing
- Data extraction
- External API calls
- Predictable integration behavior
- Conversion from natural language into structured arguments
- A clear function name, description, input schema, and expected result

Function calling is useful when the workflow is narrow and the action boundary is clear. For example, a user may ask, "What is the status of order 12345?"

The model may identify that the workflow needs an order-status lookup and produce structured arguments such as order_id and customer_id. The backend system performs the actual lookup, checks permissions, and returns the result.

The important point is that the model is not directly "looking inside the order system." It is producing structured arguments that another layer can validate and execute.

This example shows a function tool definition only. It is not a complete API request and does not execute the function.

Confirm the current API and SDK format in official documentation before implementation.

```json
{
  "type": "function",
  "name": "get_refund_status",
  "description": "Read refund status for a support ticket; do not approve, deny, or issue refunds.",
  "parameters": {
    "type": "object",
    "properties": {
      "ticket_id": {"type": "string"},
      "customer_account_id": {"type": "string"},
      "requesting_user_role": {
        "type": "string",
        "enum": ["support_agent", "support_lead", "admin"]
      }
    },
    "required": [
      "ticket_id",
      "customer_account_id",
      "requesting_user_role"
    ],
    "additionalProperties": false
  },
  "strict": true
}
```

**Security note:** The application must independently verify the caller's identity and permissions before executing the function. Do not treat the role value supplied in the tool arguments as proof of authorization.

## Slide 8/47 - Tool calling

**Tool calling**

Tool calling is the broader interaction in which a model requests use of one or more tools made available to it.

A function call is one type of tool call; built-in tools, custom tools, remote MCP servers, and other documented tool types can use different contracts and execution flows.

Use direct tool calling when the model needs to select a tool, inspect the returned result, reason about intermediate information, and decide what to do next.

Use Programmatic Tool Calling, where currently supported, when a predictable and bounded processing stage can call approved tools and handle intermediate results more efficiently — for example, bounded retrieval, joins, aggregation, transformation, or large intermediate results.

Do not use it when the model needs to inspect all raw intermediate information directly.

Both patterns still require a clear execution boundary, approved tool access, validation, logging, approval gates, fallback behavior, and current support checks.

A tool needs enough definition to be safe, testable, and reviewable. This means capturing four essentials:

**Identity and purpose**
What is the tool called, what does it do, and which workflow need does it support?

**Inputs, outputs, and errors**
What information does the tool require, what result should it return, and what happens when something goes wrong?

**Access and permissions**
What data, system, or action can the tool reach, and who or what is allowed to use it?

**Review and controls**
What needs to be logged, reviewed, approved, or limited before the tool can be used safely?

Tool availability should be constrained to what the workflow needs. Do not expose every possible tool just because the system can support it.

A workflow that only needs to check a service status should not also have access to create tickets, update customer records, or send messages unless those actions are explicitly part of the approved workflow.

Tool calls must be logged, reviewed, or approved when they affect systems, users, customers, business decisions, or sensitive data.

For example, a tool that checks whether a customer's refund has already been processed may be low risk if it only reads from an approved system of record and returns a simple status.

A tool that creates a refund approval request is higher risk because it starts a business process. A tool that issues the refund directly is higher risk still and may require strict approval, permission checks, and additional review.

The tool definition should make those differences visible.

## Slide 9/47 - Hosted and custom tools

**Hosted and custom tools**

Current OpenAI documentation distinguishes built-in tools, function tools, and custom tools. In this course, "hosted tools" is a planning label for platform-provided built-in tools.

These categories differ in how they are defined and executed.

**Built-in tools (course label: hosted tools)**
Platform-provided capabilities that may be available to the API or agentic system, depending on current documented support. Examples can include web search, file search, code interpreter, computer use, or other currently documented built-in tools. Validate exact names, availability, and behavior before implementation.

**Application-defined function tools**
Tools defined with a function name, description, and JSON Schema parameters. The model returns structured arguments; application code validates and executes the function when appropriate.

**Custom tools**
An OpenAI tool type that uses free-form text input and output rather than JSON Schema-defined arguments. Use it only when that input/output pattern fits the workflow and current documentation confirms support.

All tool types still require design judgment. When using them, you should identify:

**Workflow fit**
Does this tool solve the workflow need without adding unnecessary complexity?

**Access and permissions**
What data, sources, systems, or actions can the tool reach, and who is allowed to use it?

**Contract and execution boundary**
What inputs and outputs are required, and what layer actually performs the work?

**Controls and recovery**
What approvals, logs, review steps, and fallback paths are needed if the tool fails or returns an uncertain result?

A built-in tool is not automatically safer because it is platform-provided, and an application-defined tool is not automatically riskier.

In every case, the workflow still needs fit, access boundaries, action controls, observability, fallback behavior, and validation evidence.

## Slide 10/47 - Choose the simplest safe pattern

**Choose the simplest safe pattern**

The strongest recommendation is not always the most advanced pattern.

You'll now practice working from the workflow need toward the least complex pattern that can satisfy it safely, while recognizing when a recommendation should be deferred or marked not ready because key access, approval, fallback, or validation details are missing.

When reviewing a workflow, compare the patterns in order of complexity. Use this decision logic:

**Model-only**
The workflow only needs drafting, classification, transformation, or reasoning from user-provided context.

**Retrieval-supported**
The workflow needs approved source content, but no external action.

**Tool-enabled workflow**
The workflow needs one or more tools. Function calling is one form of tool calling; select both the tool-calling pattern and the specific tool type rather than treating them as separate peer systems.

- **Direct tool calling** — The model needs to select a tool, inspect the returned result, reason about intermediate information, or decide the next step.
- **Programmatic Tool Calling** — A predictable, bounded stage should call approved tools and process intermediate results, and current model and tool support has been validated.
- **Function tool** — The workflow needs structured arguments for a narrow application function defined by JSON Schema.
- **Built-in tool (course label: hosted tool)** — The workflow can use a platform-provided capability, and current documentation validates that the tool fits.
- **Custom tool** — The workflow needs free-form text input and output, and current documentation validates that the custom-tool type fits.

**Agentic workflow**
The workflow requires multi-step coordination, state, tools, approvals, monitoring, handoff, or action across systems, and a simpler pattern is not sufficient.

**Defer**
The pattern may fit, but permissions, source readiness, tool contract, approval ownership, or validation evidence is incomplete.

**Not ready**
The workflow has unsafe action boundaries, unclear access, missing approvals, missing fallback behavior, or insufficient review evidence.

For example, do not recommend a tool call when the workflow only needs a grounded answer from approved source material. Retrieval may be enough.

Do not recommend direct system action when approval ownership, logging expectations, or fallback behavior are unclear. In that case, the right recommendation may be "defer" or "not ready."

The decision shouldn't be "What can the technology do?" You're instead asking "What is the simplest safe action design that satisfies the workflow?"

## Slide 11/47 - Real-world example: Tool and agent pattern selection

**Real-world example: Tool and agent pattern selection**

A customer support team wants an API workflow that helps support agents respond to refund questions.

Some requests only need a drafted response based on user-provided information.

Some requests need an approved policy lookup. Some need a refund-status lookup from the order system. A few require creating an internal approval request.

The pattern should change based on the work:

- A simple "draft a polite response" task may be model-only.
- A "summarize the refund policy" task may be retrieval-supported if it needs approved policy content.
- A "check refund status" task may use function calling if the model produces structured arguments for a narrow backend lookup.
- A "create an internal approval request" task may need a defined tool, approval fields, logging, and escalation.
- A multi-step workflow that checks status, reviews policy, drafts a response, creates an approval request, and pauses for approval may justify a bounded agentic workflow.

The workflow should not automatically become agentic just because several actions are possible. The team should choose the least complex pattern that can satisfy each part of the workflow safely.

## Slide 12/47 - Recommended exercise: Choose the right tool or agent pattern

**Recommended exercise: Choose the right tool or agent pattern**

This is an optional practice activity to help you apply what you just learned.

**Purpose**
Practice comparing model-only, retrieval-supported, direct and Programmatic Tool Calling, and agentic workflow decisions, including when a function tool, built-in tool, or custom tool fits and when to defer or mark the workflow not ready.

**Task**
Review three workflow examples:

- A product support API classifies incoming messages by category.
- A sales operations workflow looks up account status, drafts a follow-up, and creates an internal task.
- A policy assistant answers employee questions using approved company documents.

For each workflow, choose the simplest safe pattern and explain why.

**Estimated time**
10–12 minutes

**Suggested output and reflection**
Pattern decision section of the Function, Tool, and Agentic Workflow Plan. Optional stretch: Add one example that should be deferred because approval ownership or access boundaries are unclear.

## Slide 13/47 - Knowledge check (drag-and-drop, all correct)

**Knowledge check**

Match each workflow need to the simplest safe pattern.

- The workflow requires multi-step work with state, approvals, monitoring, and handoff → **Agentic workflow** ✓ (Correct)
- The workflow needs the model to select a tool, inspect the result, and decide the next step → **Direct tool calling** ✓ (Correct)
- The workflow needs predictable, bounded retrieval, joins, aggregation, or transformation without returning every intermediate result to the model → **Programmatic Tool Calling, after current support validation** ✓ (Correct)
- The workflow needs structured arguments for a single narrow application function → **Function tool** ✓ (Correct)
- The workflow needs approved source content to answer, but no external action → **Retrieval-supported** ✓ (Correct)

All pairs matched correctly!

## Slide 14/47 - Summary

**Summary**

In this module, you compared the main API action patterns and when each one fits.

When you apply this learning in the future, start with the workflow need, then choose the simplest safe pattern that satisfies it.

Move toward tools only when a simpler response, retrieval pattern, or structured output is not enough; then choose direct or Programmatic Tool Calling, the specific tool type, and the execution boundary.

Use an agentic workflow only when multi-step coordination, state, approvals, monitoring, or handoff justify the added complexity.

## Slide 15/47 - Introduction: Define the function or tool contract

**Define the function or tool contract**

Once a workflow needs a function or tool, the next step is to define it clearly enough for review. This is because a tool idea like "look up the customer," "check the order," or "create a ticket" is not specific enough on its own. Technical, security, workflow, and customer stakeholders need more information.

In this module, you'll learn how to describe a function or tool's purpose, inputs, outputs, access assumptions, execution boundary, and error behavior. This turns a general tool idea into a contract that technical, security, workflow, and customer stakeholders can evaluate.

## Slide 16/47 - Define function or tool purpose

**Define function or tool purpose**

A function or tool idea is not enough for review; a tool-enabled workflow needs a contract.

A function or tool contract is the documented agreement that explains what the function or tool does, what it can access, what inputs it requires, what output it returns, what can go wrong, and what boundary separates model behavior from system execution.

The goal is to prevent vague instructions such as "look up the customer" or "update the ticket." A safe contract makes the workflow specific enough to test, review, and hand off.

Start by defining the function or tool purpose. Capture these essentials for each function or tool:

**Purpose and result**
What does it do, which workflow does it support, and what result should it return?

**Access and permissions**
What system, source, or record can it access, and who or what is allowed to call it?

**Trigger and action boundary**
When should it run, what should never trigger it, and can it read, write, create, change, send, or trigger anything?

**Risk and approval level**
Is the action low-risk, sensitive, approval-only, or disallowed?

For example, a refund-status lookup and a refund-issuing action should not share the same contract.

The lookup may only read from an approved system of record and return a status.

The refund-issuing action may change financial or customer-facing records and should likely require approval, stronger permission checks, and clearer escalation behavior.

A good purpose statement is narrow. It explains the specific job the tool is allowed to do and avoids broad, flexible wording that could create unsafe behavior.

A weak purpose statement might be:

"Use this tool to handle refund issues."

This becomes a more effective purpose statement like so:

"Use this function to retrieve the current refund status for a specific ticket from the approved refund system. The function returns refund status, source system, and timestamp. It does not create, approve, deny, or issue refunds."

The second version is safer because it defines both the action and the boundary.

## Slide 17/47 - Define input and output schema

**Define input and output schema**

A schema makes the tool contract testable. These input and output fields reduce ambiguity, help the system validate whether the tool has what it needs, and make it easier for downstream reviewers or systems to understand what happened when the function or tool ran.

An input schema defines the fields the function or tool needs before it can run.

An output schema defines the shape of the result returned by the function, tool, application code, hosted tooling, or orchestration layer.

Clear schemas help reduce ambiguity.

They also make it easier to validate inputs, handle missing fields, route outputs, and detect errors.

For input schema, capture:

- **Required information:** The fields the tool must have before it can run, such as ticket ID, customer account ID, request type, or user role.
- **Optional information:** Helpful fields that improve the result but should not block the tool if they are missing.
- **Allowed values and validation rules:** The accepted field types, formats, enums, or limits that prevent unclear or invalid tool calls.
- **Permission or approval fields:** Any role, access, confirmation, or approval information required before sensitive actions can continue.

For output schema, capture:

- **Response format:** The structure the tool should return, such as a status, summary, record, error object, or structured JSON result.
- **Required result fields:** The fields downstream systems or reviewers need every time, such as status, source system, timestamp, or result ID.
- **Success and error states:** The expected success response and the defined error responses when the tool cannot complete the request.
- **Routing or review guidance:** Whether the result can be shown to the user, returned to the model, sent to another system, or held for human review.

Here is a planning-level example for a refund-status lookup. This is not implementation code. It shows how an output schema can make both successful results and failure states predictable.

Example success response:

```json
{
  "refund_status": "pending_review",
  "source_system": "refund_system",
  "last_updated_timestamp": "2026-06-29T10:15:00Z",
  "result_status": "success",
  "safe_to_show_user": true,
  "error_code": null
}
```

Example error response:

```json
{
  "refund_status": null,
  "source_system": "refund_system",
  "last_updated_timestamp": null,
  "result_status": "permission_denied",
  "safe_to_show_user": false,
  "error_code": "CALLER_NOT_AUTHORIZED"
}
```

Notice that the error response does not return a free-form explanation only. It returns a defined failure state that another system, reviewer, or fallback path can interpret.

For example, permission_denied should prevent the tool from continuing, while safe_to_show_user: false signals that the raw result should not be shown directly to the user.

Schemas aren't designed to capture every possible field. The goal is to make the tool predictable enough that another team can test it, validate it, and understand what should happen when required information is missing or the result cannot be trusted.

The schema should also identify what happens when the model cannot provide valid arguments, when the caller lacks permission, when the source system is unavailable, or when the result is ambiguous.

## Slide 18/47 - Define the execution boundary

**Define the execution boundary**

The execution boundary is the line between what the model requests or selects and what external code, hosted tooling, or runtime orchestration actually performs. It's one of the most important safety concepts in tool-enabled API design.

The model may request or select a function or tool. It may produce structured arguments. It may interpret the returned result. But the model does not independently perform the external action.

Depending on the implementation, application code, hosted tooling, or runtime orchestration performs the actual work.

Define the execution boundary by capturing four essentials:

**Model role**
What can the model select, request, or turn into structured arguments?

**Execution role**
What application code, hosted tooling, or orchestration layer performs the actual work, and which system or source does it access?

**Result and review path**
What result comes back to the model or client, and what must be logged, reviewed, or approved?

**Stop, fallback, and protection rules**
What failures should stop the workflow, trigger escalation, or require fallback—and what sensitive data, credentials, or fields must never be exposed?

This keeps the contract reviewable. It also helps avoid unsafe assumptions such as "the model updates the customer record."

A safer and more precise design is: "The model requests an update with structured arguments; application code checks permissions and approval before executing the update."

For review, the execution boundary should be visible every time a workflow reads from a system, writes to a system, creates a record, sends a message, triggers another workflow, or affects a customer-facing or business-critical process.

Here's a pseudocode example of an execution boundary:

```python
# Planning-level pseudocode only

tool_request = model_selected_tool()

if tool_request.name != "get_refund_status":
    return refuse_or_route("Tool is not available for this workflow.")

if not validate_schema(tool_request.arguments):
    log_tool_event(result_status="invalid_input")
    return request_clarification("Required fields are missing or invalid.")

if not authorize(
    caller_role=tool_request.arguments["requesting_user_role"],
    action="refund_status:read"
):
    log_tool_event(result_status="permission_denied")
    return fallback_or_escalate("Caller is not authorized.")

result = refund_system.get_status(
    ticket_id=tool_request.arguments["ticket_id"],
    customer_account_id=tool_request.arguments["customer_account_id"]
)

log_tool_event(
    tool_name="get_refund_status",
    result_status=result.status,
    source_system="refund_system",
    redacted_fields=["customer_account_id"]
)

return result
```

The model selects the tool and proposes structured arguments.

Application code or orchestration validates the request, checks authorization, executes the system call, logs approved evidence, and returns the result.

This is the execution boundary in practice.

Remember that if the execution boundary is unclear, the workflow is not ready.

As you define the tool's inputs and outputs, use this diagram to make the execution boundary visible: the model can request or select a function or tool, but application code, hosted tooling, or orchestration performs the actual work.

**Diagram — Execution boundary flow:** User request → Model selects function/tool [Model selection] | (Execution boundary) | App, hosted tool, or orchestration executes → External system returns result → Model or client returns final response [Execution and return]

## Slide 19/47 - Real-world example: Function or tool contract

**Real-world example: Function or tool contract**

A customer support team wants an API workflow that can route refund-related tickets.

A narrow get_refund_status function may only need a ticket ID and customer account ID, then return the refund status, source system, and timestamp.

A separate request_refund_approval tool would need stricter inputs, permission checks, approval fields, logging, and escalation behavior because it can trigger a business process.

The lookup and approval actions need separate contracts, different permissions, different error states, and different execution boundaries.

A safe design does not combine all refund behavior into one broad tool. It separates the low-risk lookup from the higher-risk approval workflow.

## Slide 20/47 - Recommended exercise: Define a safe function or tool contract

**Recommended exercise: Define a safe function or tool contract**

This is an optional practice activity to help you apply what you just learned.

**Purpose**
Practice defining a function or tool contract.

**Task**
Draft a function or tool contract for this refund-status lookup workflow:

A support agent asks an internal API for the current refund status for a specific support ticket.

The function reads from the approved refund system and returns:

- Refund status
- Source system
- Timestamp or a defined error state.

It must not:

- Create,
- Approve
- Deny or issue refunds

The contract should define:

- Required inputs
- Output shape
- Caller permissions
- Execution boundary
- Allowed actions
- Disallowed actions
- Approval-only actions
- Error states
- Fallback behavior

**Estimated time**
10–12 minutes

**Suggested output and reflection**
Function/tool contract section of the Function, Tool, and Agentic Workflow Plan, including purpose, schema, access assumptions, execution boundary, allowed actions, disallowed actions, approval-only actions, error states, and fallback behavior.

## Slide 21/47 - Knowledge check

**Knowledge check**

Which function or tool contract is safest to move into review?

- A lookup_customer_record function that accepts a customer ID and returns available account, ticket, and refund details for follow-up use.
- An update_case_status tool that accepts a ticket ID and new status, then updates the case when the model decides the change is helpful.
- **A get_refund_status function that checks caller permission, accepts required ticket and account IDs, and returns refund status, source, timestamp, or defined error states.** ✓ (Correct)
- A customer_case_tool that can look up refund status, update tickets, and send customer messages when those actions seem relevant.

**Explanation:** This is the safest option because it is narrow, permission-aware, and reviewable. It defines a specific lookup purpose, required inputs, expected outputs, and error behavior without allowing broad access or unsupervised record changes.

## Slide 22/47 - Summary

**Summary**

You've now defined what makes a function or tool contract safe, testable, and reviewable.

Remember that a strong contract does more than name a tool. It explains what the tool does, what it needs, what it returns, what it can access, where execution happens, and what should happen when something fails.

## Slide 23/47 - Introduction: Connect tools to agentic workflows

**Connect tools to agentic workflows**

Tool use and agentic workflows are related, but they are not interchangeable. A function or tool call gives the workflow access to a specific capability, such as looking up a record, checking policy, running a calculation, or creating a ticket.

An agentic workflow is broader: it coordinates steps, tools, context, state, approvals, and handoffs to move work toward an outcome over time.

In this module, you'll learn when a workflow may justify an agentic pattern because it needs multi-step work, state, tool coordination, approvals, monitoring, or handoff. You'll also learn when an agent would add unnecessary complexity.

## Slide 24/47 - Identify agentic workflow signals

**Identify agentic workflow signals**

By this point, you've looked at functions and tools as individual capabilities. Agentic workflow design builds on that foundation.

Instead of asking only, "What tool should be called?", using agentic workflow design means you also ask, "Does this workflow need to coordinate several steps, preserve state, pause for approval, recover from failure, or hand work off to a person?"

Use the definitions below to describe those added workflow needs clearly:

**Agentic workflow**
A workflow where AI uses goals, instructions, context, tools, state, approvals, and monitoring to move work toward an outcome over multiple steps.

**Agentic runtime**
Where and how the AI does work: the environment that lets it use tools, coordinate steps, act across systems, follow guardrails, and move work toward completed outputs.

**State**
The information the workflow keeps track of across steps, such as task progress, previous tool results, user decisions, approvals, or unresolved questions.

**Stop condition**
A defined point where the workflow must pause, end, ask for clarification, request approval, or escalate.

**Human handoff**
Routing the workflow to a person when the task becomes sensitive, ambiguous, high-risk, blocked, or outside the approved action boundary.

**Agentic complexity**
The added design, validation, approval, observability, and operational burden that comes with multi-step tool-enabled workflows.

Not every tool-enabled workflow needs to become agentic. Start by looking for signals that the work cannot be handled safely by a simple model response, retrieval pattern, structured output, or single function call.

Agentic workflow signals usually fall into four areas:

**Multi-step coordination**
The workflow needs to coordinate several steps, tools, systems, or results.

**State and continuity**
The workflow needs to track progress, remember prior steps, run on a trigger or schedule, or continue toward an outcome over time.

**Control and handoff**
The workflow needs approval, monitoring, escalation, or human handoff before sensitive or blocked actions continue.

**Recovery from uncertainty**
The workflow needs a plan for missing information, partial completion, tool failure, or unclear results.

For example, a single refund-status lookup may only require function calling. A workflow that checks refund eligibility, reviews policy, drafts a customer response, creates a ticket, and pauses for approval before issuing a refund may justify a bounded agentic workflow.

## Slide 25/47 - Define agent workflow behavior

**Define agent workflow behavior**

If an agentic pattern is justified, you need to define the workflow behavior clearly enough that another team can review it. To do this, capture four essentials for any agentic workflow:

**Goal and guidance**
What outcome should the workflow move toward, and what instructions should guide the agent's behavior?

**Context, tools, and state**
What information does the agent need, which tools can it use, how should tools be selected, and what progress must be tracked across steps?

**Action boundaries**
What can the agent do automatically, what can it recommend but not execute, and what must it never do?

**Controls and handoff**
Where must the workflow stop, ask for approval, escalate, hand off to a person, or capture evidence for review?

Whereas a single tool call may only need inputs and outputs, an agentic workflow often needs state so the workflow can track what has happened, what is pending, where it should stop, and when a person needs to take over.

Here's a planning-level example for a refund request — remember that this is not full implementation code:

```json
{
  "workflow_goal": "Prepare refund approval request",
  "current_step": "policy_check",
  "completed_steps": ["refund_status_lookup", "order_history_check"],
  "pending_approval": false,
  "last_tool_result": "refund_status_pending",
  "stop_condition": null,
  "handoff_owner": null
}
```

This kind of state helps reviewers understand how the workflow progresses across steps.

For example, the workflow has already checked refund status and order history, is now reviewing policy, has not yet reached an approval gate, and has not triggered a stop condition or handoff.

The plan should also name the execution boundary. The model or agent may select a tool, request an action, or generate structured arguments.

External code, hosted tooling, or runtime orchestration performs the actual work depending on the implementation.

That distinction helps avoid unsafe statements such as "the agent refunds the customer."

A safer design would be: "The agent checks eligibility and prepares a refund request; the system requires human approval before any refund is executed."

Agent behavior should be specific enough that reviewers can answer:

- What does the workflow consider "done"?
- What happens if the workflow cannot complete all steps?
- Where does it stop?
- Who approves sensitive actions?
- What evidence proves the workflow followed its boundary?

If those questions cannot be answered, the workflow is not ready for agentic design.

## Slide 26/47 - Avoid unnecessary agents

**Avoid unnecessary agents**

Agentic workflows can be powerful, but they also add design, validation, governance, and operational complexity. You should never recommend an agentic pattern just because it sounds more advanced.

Avoid an agentic pattern when any of these are true:

**A simpler pattern is enough**
What this means: The workflow can be handled with drafting, summarization, classification, transformation, structured output, retrieval, or one function call.
Better direction: Use the simpler pattern that satisfies the workflow safely.

**Deterministic automation is a better fit**
What this means: The workflow depends on fixed business rules, exact calculations, simple routing logic, or repeatable system steps.
Better direction: Use conventional code, rules, or workflow automation instead of an agent.

**The workflow is not ready**
What this means: Permissions are unclear, the tool contract is incomplete, or approval ownership has not been defined.
Better direction: Defer until access, contract, and approval assumptions are validated.

**The workflow cannot be governed safely**
What this means: The action boundary is unsafe, failure behavior is undefined, or the workflow cannot be observed or audited.
Better direction: Do not proceed until governance, fallback, and review evidence are defined.

**The outcome is unclear**
What this means: The workflow owner cannot define what "done" means, when the agent should stop, or when work should escalate or hand off to a person.
Better direction: Clarify the workflow goal, stop conditions, escalation path, and handoff owner first.

**The system dependencies are not reliable enough**
What this means: The workflow depends on a source, API, database, or downstream system with unclear ownership, weak freshness, unstable availability, or unresolved access rules.
Better direction: Validate the dependency, owner, access model, freshness, and reliability before considering an agent.

An effective recommendation should choose the least complex design that can satisfy the workflow safely.

If the workflow can be solved with a single function or tool call, keep it simple. If the workflow needs multiple steps, state, approvals, monitoring, and cross-system action, then an agentic workflow may be appropriate.

A useful test is to ask:

"What would break if this were not agentic?"

If the answer is "nothing," the agentic pattern is probably unnecessary. If the answer is something like "the workflow would lose state, skip approvals, fail to coordinate tools, or require manual stitching across systems," then an agentic workflow may be worth evaluating.

## Slide 27/47 - Real-world example: Tools in an agentic workflow

**Real-world example: Tools in an agentic workflow**

An enterprise IT team wants an API workflow that helps review employee software requests.

Employees submit requests for tools they want to use, and IT needs to check whether the software is already approved, whether the requester's role is eligible, whether a license is available, and whether security review is required.

A simple approval-status lookup can stay as a function call.

For example, the model might request a check_software_approval_status function with structured arguments such as software name, employee role, and department. Application code would validate the request, check the approved software catalog, and return a status.

But a broader workflow may justify an agentic pattern if it needs to coordinate multiple steps.

For example, the workflow might check the approved software catalog, review policy requirements, check license availability, draft a recommendation, create an IT review ticket, pause for security approval when needed, and escalate if ownership or policy evidence is unclear.

The agentic version needs:

- State to track which checks have been completed and what is still pending.
- Tool-selection rules to decide when to check policy, license availability, requester eligibility, or ticket status.
- Approval points before security-sensitive, paid, or unapproved software requests move forward.
- Stop conditions when the request is outside policy, missing required details, or depends on an unapproved system.
- Escalation paths for security review, procurement review, or system-owner review.
- Evidence of each step so IT can see what was checked, what result came back, and why the workflow paused or escalated.

The agentic version also needs clear boundaries. It might be allowed to prepare a recommendation, create an IT review ticket, or summarize the policy evidence.

It should not automatically approve software, provision access, modify identity groups, purchase licenses, or send employee information to a vendor unless those actions are explicitly allowed and approved.

The value of the agentic pattern comes from coordinating the review workflow, not from removing IT, security, or procurement control.

## Slide 28/47 - Recommended exercise: Connect tool use to an agentic workflow

**Recommended exercise: Connect tool use to an agentic workflow**

This is an optional practice activity to help you apply what you just learned.

**Purpose**
Practice deciding when tools become part of an agentic workflow.

**Task**
Review the following workflow and decide whether it should remain a single tool call, become a bounded tool-enabled workflow, or become an agentic workflow with approvals and monitoring.

As you decide, consider:

- Does the workflow need one tool call, or coordination across several steps?
- Does it need state to track what has already been checked?
- Which actions can happen automatically?
- Which actions require approval or human review?
- Where should the workflow stop or escalate?
- What evidence should be captured so reviewers can see what happened?

**Example workflow: Product feedback routing**

A product team wants an API workflow that helps process product feedback from multiple internal channels. Feedback may come from support tickets, sales call notes, Slack messages, and customer-success summaries.

The team wants the workflow to:

- Collect feedback from approved internal sources.
- Identify whether the feedback is a bug report, feature request, usability issue, or account-specific request.
- Check whether a similar issue or feature request already exists.
- Summarize the evidence and affected customer context.
- Create or update an internal product ticket.
- Escalate high-priority issues to the product operations owner.
- Pause before creating tickets that include sensitive customer context or unverified claims.

The proposed workflow may use these functions or tools:

- **classify_feedback_type** — Classifies feedback as bug, feature request, usability issue, account-specific request, or unclear.
- **search_existing_product_tickets** — Searches approved product-ticket records for similar issues or requests.
- **retrieve_feedback_evidence** — Retrieves approved feedback snippets from connected internal sources.
- **create_product_review_ticket** — Creates a draft ticket for product review, but should not publish or assign it automatically without required fields and permissions.
- **escalate_to_product_ops** — Routes unclear, sensitive, or high-priority feedback to the product operations owner.

**Estimated time**
10–12 minutes

**Suggested output and reflection**
Completed Agentic workflow section of the Function, Tool, and Agentic Workflow Plan.

## Slide 29/47 - Knowledge check

**Knowledge check**

Which workflow best justifies an agentic workflow?

- A support API rewrites customer replies using brand voice, tone rules, and approved examples.
- A support API classifies tickets, assigns priority, and returns a structured routing label.
- A support API extracts ticket details, validates required fields, and returns a structured case summary.
- **A support workflow coordinates lookup, policy check, draft response, approval pause, and escalation.** ✓ (Correct)

**Explanation:** This workflow best fits an agentic pattern because it requires coordination across multiple steps, uses tools or sources, pauses for approval, and includes escalation. The other examples can likely be handled with simpler patterns such as rewriting, classification, or structured extraction.

## Slide 30/47 - Summary

**Summary**

In this module, you learned how to decide whether tool use should stay simple or become part of an agentic workflow.

Agentic workflows are useful when the work needs coordination over multiple steps. Remember that they should remain bounded by clear instructions, allowed actions, stop conditions, approval points, handoff paths, and review evidence.

## Slide 31/47 - Introduction: Add approvals, observability, and failure handling

**Add approvals, observability, and failure handling**

A tool-enabled or agentic workflow is not ready just because the ideal path works. In real deployment contexts, risky moments often appear when a tool times out, an input is missing, a user asks for something outside the approved boundary, a result is unclear, or a workflow reaches an action that should not continue without approval.

In this module, you'll add the controls that make the workflow safer to review: approval gates, observability expectations, fallback behavior, and escalation paths. These controls help teams understand what the workflow did, when it should stop, and who needs to review sensitive actions.

## Slide 32/47 - Add approval gates

**Add approval gates**

Tool-enabled and agentic workflows must be reviewable before deployment. That means the plan should define approval, observability, fallback, and escalation requirements before the workflow can be considered safe to build or recommend.

An approval gate is a defined point where approval is required before the workflow can continue.

An approval owner is the accountable person or team that can approve, reject, or redirect the action.

Approval gates are especially important when a workflow affects systems, customers, money, records, operations, or sensitive decisions.

Add approval gates when the workflow is about to:

**Affect a person, customer, or business process**
For example: sending a message, submitting a request, making a high-risk recommendation, or triggering a downstream workflow.

**Change a system or record**
For example: creating, updating, deleting, approving, denying, provisioning, assigning, or modifying data or access.

**Touch sensitive data or regulated context**
For example: using confidential, personal, regulated, customer-specific, security-related, or credential-related information.

**Move outside the approved boundary**
For example: handling an exception, unclear result, failed permission check, or action that is not explicitly allowed.

For each approval gate, define:

**Action and trigger**
What action requires approval, and when does the workflow reach that point?

**Approval owner**
Who can approve, reject, or redirect the action?

**Outcome path**
What happens if approval is granted, denied, delayed, or unavailable?

**Review record**
What evidence shows that approval was requested, reviewed, and resolved?

**Evidence needed**
What information does the approver need to make the decision?

A vague statement like "human review may be needed" is not enough. A useful approval gate tells the workflow exactly when to pause, who owns the decision, what evidence they need, and what happens next.

For example, a weak approval statement would be:

"Refund actions may need review."

A stronger approval statement would then be:

"Before any refund request is submitted, the workflow must route the draft request, refund eligibility result, policy reference, and customer account ID to a support lead for approval. If approval is denied or unavailable, the workflow must stop and record the escalation reason."

A clear approval gate makes the workflow safer and easier to verify.

## Slide 33/47 - Add observability

**Add observability**

Observability is the evidence that helps a business monitor, control, and improve tool-enabled or agentic activity.

It helps reviewers understand what the workflow did, what tools were used, what results came back, what approvals occurred, and where failures or escalations appeared.

Observability is not simply about "having logs." It is the review evidence needed to understand whether the workflow stayed within its boundary.

Observability should make the workflow reviewable without overwhelming reviewers with unnecessary detail.

Focus on four types of evidence:

**Tool activity**
Which function or tool was requested, what result came back, and whether the call succeeded, failed, or returned an uncertain result.

**Decisions and approvals**
Which actions required approval, who reviewed them, what decision was made, and which stop conditions were triggered.

**Errors and blocked actions**
Where permissions failed, tools returned errors, actions were restricted or refused, or the workflow could not continue safely.

**Escalation and handoff**
When the workflow routed work to a person, escalated an issue, stopped because of partial completion, or created an incomplete handoff that needs follow-up.

An observability plan might define fields such as:

```json
{
  "workflow_id": "support_refund_workflow",
  "tool_name": "get_refund_status",
  "caller_role": "support_agent",
  "action_type": "read",
  "result_status": "success",
  "approval_required": false,
  "stop_condition_triggered": false,
  "fallback_action": null,
  "redacted_fields": ["customer_account_id"],
  "escalation_owner": null
}
```

This isn't a production logging specification.

It's a planning example that shows the kinds of evidence reviewers may need to understand what happened, what was protected, and whether the workflow stayed within its approved boundary.

You also need to define what should not be logged.

Sensitive data, secrets, credentials, tokens, unnecessary customer data, confidential content, or restricted system details should not appear in logs, prompts, examples, screenshots, learner artifacts, or generated outputs unless explicitly approved and safe under customer policy.

A strong observability plan should answer:

- What needs to be visible?
- Who can review it?
- What evidence supports approval, escalation, or rollback decisions?
- What information must be protected or excluded?
- What should trigger action?

## Slide 34/47 - Add fallback behavior

**Add fallback behavior**

Fallback behavior keeps the workflow safe when something goes wrong or when the system does not have enough information to proceed.

Plan fallback behavior for four common situations:

**Tool or result issues**
The tool is unavailable, times out, returns conflicting information, or produces a result that cannot be trusted.

**Input, permission, or approval gaps**
Required inputs are missing, the caller does not have permission, or the workflow needs approval before continuing.

**Risk or boundary issues**
The user asks for a high-risk action, a restricted action, or something outside the approved workflow boundary.

**Incomplete work or blocked handoff**
The workflow partially completes, cannot finish the handoff, or the escalation owner is unavailable.

The fallback response should match the level of risk. Depending on the situation, the workflow may:

- Ask for clarification
- Retry within defined limits
- Return a safe partial answer
- Pause and request approval
- Refuse or block the action
- Route the work to a human reviewer
- Escalate to the system owner, platform team, security team, or workflow owner
- Stop the workflow and document why it stopped

A low-risk lookup failure may return a clear error and ask the user to try again.

A failed financial, operational, customer-facing, or system-changing action should pause, document the issue, and escalate through the approved path.

Fallback behavior should also protect against partial completion.

For example, if a workflow drafts a customer response but fails to create the internal approval request, it should not behave as if the workflow completed. It should record the incomplete handoff and route to the appropriate owner.

A tool-enabled workflow is not ready if nobody can explain what happens when the tool fails.

## Slide 35/47 - Real-world example: Approvals, observability, and fallback behavior

**Real-world example: Approvals, observability, and fallback behavior**

A procurement team wants an API workflow that helps review new vendor onboarding requests.

The workflow checks whether the vendor already exists in the approved supplier system, reviews required onboarding policy, drafts an internal recommendation, and can create a procurement review ticket.

The workflow should capture evidence of the tool call, supplier-system result, policy lookup, ticket creation attempt, approval record, and escalation path. It should not log bank details, tax identifiers, credentials, contract attachments, or unnecessary vendor-sensitive information.

If the supplier-system lookup fails, the workflow should not continue as if the vendor has been cleared. It should pause, explain which evidence is missing, and route the request to the procurement owner or vendor-risk reviewer.

If the request involves a restricted vendor category, missing policy evidence, or a high-value contract threshold, the workflow should stop and require approval before any onboarding step continues.

In this example, approval, observability, and fallback rules are not extra polish. They are what make the workflow reviewable. Without them, the team cannot tell whether the workflow stayed within its approved action boundary or whether a vendor was advanced without the required evidence.

## Slide 36/47 - Recommended exercise: Add approvals, observability, and fallback rules

**Recommended exercise: Add approvals, observability, and fallback rules**

This is an optional practice activity to help you apply what you just learned.

**Purpose**
Practice adding controls to a tool-enabled or agentic workflow.

**Task**

**Example workflow: Employee data-access request**

An enterprise IT team wants an API workflow that helps process employee requests for access to internal data tools. Employees submit a request that includes the tool they need, the business reason, their department, and the project they are supporting.

The proposed workflow should:

- Check whether the requested tool is approved for the employee's department.
- Verify whether the employee's role is eligible for the requested access level.
- Retrieve the relevant access policy.
- Draft an internal access recommendation.
- Create an access-review ticket for the system owner.
- Pause before any access is granted, expanded, or provisioned.
- Escalate requests involving sensitive datasets, missing business justification, or unclear approval ownership.

The proposed workflow may use these functions or tools:

- **check_tool_eligibility** — Checks whether the requested tool is approved for the employee's department and role.
- **retrieve_access_policy** — Retrieves approved internal access policy for the requested tool or dataset.
- **create_access_review_ticket** — Creates a draft ticket for the system owner to review. It should not provision access automatically.
- **escalate_to_data_owner** — Routes sensitive, unclear, or blocked requests to the accountable data owner or access-review team.

Add approval, observability, fallback, and escalation rules to this workflow.

As you work, decide:

**Approval rules**
Which actions require approval, who owns the approval, and what evidence should the approver review?

**Observability needs**
What should be logged for review, and what sensitive information should be excluded from logs?

**Fallback and escalation paths**
What should happen if required inputs are missing, policy lookup fails, the employee is not eligible, or the data owner is unavailable?

**Verification tests**
What tests would prove the workflow pauses, refuses, or escalates correctly when it reaches a restricted or uncertain action?

**Estimated time**
8–10 minutes

**Suggested output and reflection**
Complete the controls, observability, fallback, and verification section of the Function, Tool, and Agentic Workflow Plan.

## Slide 37/47 - Knowledge check

**Knowledge check**

What is the most important gap in this proposed workflow description? "The API can create refund approval requests and send customer updates. Human review may be needed. Logs will be kept."

- It leaves dashboards, alert thresholds, and rollback ownership undefined.
- **It leaves approval, evidence, fallback, and logging boundaries undefined.** ✓ (Correct)
- It leaves message tone, template rules, and personalization undefined.
- It leaves hosted-tool, custom-tool, and runtime selection undefined.

**Explanation:** The description gestures at review and logging, but it is not specific enough to test or approve. A safer plan should define who approves sensitive actions, when approval is required, what evidence reviewers need, what happens if the workflow cannot continue, and what sensitive information must not be logged.

## Slide 38/47 - Summary

**Summary**

In this module, you added the review and recovery layer for tool-enabled workflows.

Remember that approval, observability, fallback, and escalation are not optional extras. They are part of what makes a workflow bounded, governable, and ready for deeper validation before build or deployment review.

## Slide 39/47 - Introduction: Complete the Function, Tool, and Agentic Workflow Plan

**Complete the Function, Tool, and Agentic Workflow Plan**

Now in this final module you'll bring your decisions together into one reviewable handoff artifact.

You'll complete the Function, Tool, and Agentic Workflow Plan by combining the pattern decision, function or tool contract, execution boundary, action rules, approvals, fallback behavior, observability needs, verification tests, and open risks.

## Slide 40/47 - Build the plan

**Build the plan**

The Function, Tool, and Agentic Workflow Plan brings together the pattern decision, function or tool contract, execution boundary, action limits, approval gates, fallback behavior, observability needs, verification tests, and open risks into one reviewable plan.

The purpose is not to implement the workflow.

The purpose is to make the tool-enabled or agentic design clear enough for technical, security, platform, workflow, and customer stakeholders to review before build or deployment.

A Function, Tool, and Agentic Workflow Plan is the handoff artifact that explains the recommended workflow pattern, tool contract, execution boundary, approval model, fallback path, verification tests, and open risks.

Your plan should cover five areas:

**Workflow and pattern recommendation**
What the workflow is trying to accomplish, which pattern fits best, and why that pattern is the simplest safe option. This may be model-only, retrieval-supported, direct or Programmatic Tool Calling with a function, built-in, or custom tool, agentic workflow, defer, or not ready.

**Function or tool design**
What function or tool is needed, when it should be triggered, what inputs and outputs it requires, and where the execution boundary sits. Include the direct or programmatic tool-calling pattern, current tool type, and syntax assumptions where relevant.

**Action and access boundaries**
What systems, sources, records, or actions the workflow can access; what the model may request or select; what external code, hosted tooling, or orchestration actually executes; and which actions are allowed, disallowed, or approval-only.

**Controls and failure handling**
What permissions, approvals, fallback paths, escalation steps, and observability requirements are needed when inputs are invalid, permissions fail, tools are unavailable, or results are ambiguous.

**Readiness evidence and open risks**
What verification tests are required, what evidence should be captured for review, and which unresolved risks must be validated before the workflow can proceed.

A completed plan brings your decisions into one reviewable handoff artifact.

## Slide 41/47 - Make the plan safe to review

**Make the plan safe to review**

A tool-enabled or agentic workflow plan should be practical, bounded, and reviewable.

Use a final readiness check before recommending the workflow:

**Keep the design bounded** (checklist item, clicked to complete)
Choose the least complex pattern that can satisfy the workflow safely. Make clear what the workflow can do, what it cannot do, and which assumptions still need validation.

**Do not claim readiness too early** (checklist item, clicked to complete)
If permissions, approval ownership, execution boundaries, fallback behavior, observability, or verification evidence are unclear, recommend defer or not ready instead of moving forward.

**Keep the recommendation workflow-led** (checklist item, clicked to complete)
Focus on the customer workflow and action design, not a product tour. Any current product names, hosted-tool availability, SDK behavior, connector behavior, MCP references, or agent capability claims should be validated against official OpenAI documentation before implementation guidance is finalized.

The plan should support one of these defensible recommendations:

- **Model-only:** The workflow does not need retrieval or tools.
- **Retrieval-supported:** The workflow needs approved source grounding, but no external action.
- **Tool-enabled workflow:** The workflow needs one or more defined tools, and the plan identifies the tool-calling pattern, specific tool type, and execution boundary.
- **Direct tool calling:** The model needs to select a tool, inspect its result, reason about intermediate information, or decide the next step.
- **Programmatic Tool Calling:** Predictable, bounded processing may fit, pending current model and tool support, approved tools, and validation evidence.
- **Function tool:** The workflow needs structured arguments for a narrow application function defined by JSON Schema.
- **Built-in tool (course label: hosted tool):** A platform-provided capability may fit, pending current documentation and access validation.
- **Custom tool:** Free-form text input and output may fit, pending current documentation, tool contract, permissions, and validation evidence.
- **Agentic workflow:** Multi-step work, state, tools, approvals, monitoring, or cross-system action justify the added complexity.
- **Defer:** The pattern may fit, but permissions, source readiness, tool contract, approval ownership, or validation evidence is incomplete.
- **Not ready:** The workflow has unsafe action boundaries, unclear access, missing approvals, missing fallback behavior, or insufficient review evidence.

A strong recommendation should explain what is ready, what is not ready, who needs to validate the remaining questions, and what evidence would change the recommendation.

## Slide 42/47 - Real-world example: Tool and agent workflow recommendation

**Real-world example: Tool and agent workflow recommendation**

A sales operations team wants an API workflow that helps account teams prepare follow-up actions after an inbound enterprise lead is qualified.

The workflow needs to check account status, review recent engagement notes, apply a qualification rubric, draft an internal next-step summary, and create a CRM task for the account owner.

The plan recommends:

- A narrow function call for the account-status lookup.
- A defined tool for retrieving approved engagement notes or qualification criteria.
- A bounded workflow for drafting the internal next-step summary and preparing the CRM task.
- Approval-only handling before any customer-facing message is sent or any account-stage field is changed.
- Fallback behavior if account data is missing, qualification evidence conflicts, permissions fail, or the CRM task cannot be created.
- Observability evidence for tool calls, returned results, approval records, escalation events, and incomplete handoffs.

The plan does not recommend automatically updating the opportunity stage, assigning ownership, or sending customer-facing outreach until permission checks, approval ownership, logging expectations, fallback behavior, and verification tests are validated.

This is a defensible recommendation because it separates lower-risk lookup and drafting from higher-impact account actions.

The workflow can help gather evidence, prepare a recommendation, and create a reviewable task, but it does not take customer-facing or revenue-impacting action without the required controls.

## Slide 43/47 - Recommended exercise: Finalize the Function, Tool, and Agentic Workflow Plan

**Recommended exercise: Finalize the Function, Tool, and Agentic Workflow Plan**

This is an optional practice activity to help you apply what you just learned.

**Purpose**
Consolidate prior pattern, contract, boundary, control, and fallback decisions into a handoff-ready recommendation.

**Task**
Use the plan sections you developed earlier in the course, or use this sales-operations workflow as your starting point:

an API workflow checks account status, retrieves approved engagement notes or qualification criteria, drafts an internal next-step summary, and prepares a CRM task for the account owner.

Finalize the Function, Tool, and Agentic Workflow Plan by confirming:

- The pattern decision
- Function or tool requirement
- Tool contract
- Execution boundary
- Allowed actions
- Disallowed actions
- Approval-only actions
- Permission assumptions
- Fallback path
- Observability needs
- Verification tests
- Open risks

**Estimated time**
8–10 minutes

**Suggested output and reflection**
A finalized Function, Tool, and Agentic Workflow Plan with a defensible recommendation and next validation step. Optional stretch: Add a multi-tool orchestration note only if the workflow justifies it.

## Slide 44/47 - Knowledge check

**Knowledge check**

Which recommendation is most defensible?

- Proceed with a hosted tool because managed capabilities reduce the need for custom controls.
- **Defer because the pattern may fit, but approval ownership, permission assumptions, and fallback tests are incomplete.** ✓ (Correct)
- Proceed with tool calling because the workflow need is clear, but list approval ownership as a follow-up item.
- Proceed with an agentic workflow because the workflow may eventually involve multiple tools.

**Explanation:** "Defer" is the safest recommendation when the pattern may be useful but key readiness evidence is missing. The plan should not claim readiness until approval, access, fallback, and verification questions are resolved.

## Slide 45/47 - Summary

**Summary**

In this module, you finalized a plan that explains whether the workflow is ready, should be deferred, or is not ready.

A defensible recommendation should make the workflow boundary clear, explain why the selected pattern fits, show what must be controlled or verified, and identify any unresolved risks before the work moves forward.

## Slide 46/47 - Recap

**Recap**

In this course, you learned how API solutions can move from generating responses to using tools and taking bounded action. You compared model-only and retrieval-supported patterns, direct and Programmatic Tool Calling across function, built-in, and custom tools, and agentic workflows.

You also learned how to make tool-enabled workflows safer to review by defining function and tool contracts, execution boundaries, action limits, approval gates, fallback paths, observability needs, and verification tests.

The main takeaway is to choose the simplest safe pattern for the workflow. Tools and agents can help intelligence become part of how work gets done, but only when the workflow is bounded, reviewable, and supported by clear readiness evidence.

## Slide 47/47 - Congratulations

**Congratulations, you've completed this course!**

You can now use the Function, Tool, and Agentic Workflow Plan to evaluate real customer workflows before they move into build or deployment review.

In future API solution design work, use this plan to explain what pattern fits, what the model can request, what the system executes, what requires approval, and what risks still need validation.

Great work, you're all done!

**Recommended for you:**
- OpenAI's Partner Portal (Course, 21 min)
- Building Apps in ChatGPT (Course, 32 min)
