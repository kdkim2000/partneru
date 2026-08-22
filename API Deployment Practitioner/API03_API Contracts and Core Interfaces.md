# API Contracts and Core Interfaces

## Slide 1/53 - Title

API Contracts and Core Interfaces

## Slide 2/53 - Introduction

API-based AI solutions become reliable when the surrounding system knows what to send, what to expect back, what can go wrong, and how to verify the interaction. That is the role of an API contract.

In this course, you'll compare the Responses API and Chat Completions API as inference interfaces, then examine how the Conversations API can provide persistent state when it is used with Responses. You'll translate the interface and state approach into a Core Interface and API Contract Plan with request shape, response shape, structured-output requirements, state assumptions, error behavior, and verification tests.

For implementation teams, solution architects, technical consultants, and FDE-style builders, the Core Interface and API Contract Plan is a practical design and handoff tool.

## Slide 3/53 - What you'll learn

By the end of this course, you'll be able to:

- Explain the roles of the Responses API and Chat Completions API as inference interfaces, and the Conversations API as persistent conversation-state infrastructure used with Responses.
- Select an inference interface and state approach based on workflow, state, tools, streaming, async, and output needs, and assess their impact on context, errors, testing, logging, and governance.
- Define request, response, schema, authentication, structured-output, and error assumptions.
- Design success, error, structured-output, and state-behaviour tests.
- Produce a Core Interface and API Contract Plan for implementation, documentation, testing, and handoff.

## Slide 4/53 - What you'll produce

Throughout this course, you'll build a Core Interface and API Contract Plan. This is a practical design artifact you can use to explain how an API interaction should work before it moves into implementation, validation, or technical review.

Your plan will capture four things:

**Interface recommendation** — Which core API interface fits the workflow, why it fits, and what current product facts must be validated before implementation.

**Contract shape** — What the caller sends, what the API returns, what fields are required, what structure is expected, and what assumptions exist around authentication, state, and context.

**Behavior and failure expectations** — What should happen when inputs are missing, sources are unavailable, state is mismatched, structure is invalid, a tool fails, or the workflow cannot safely complete.

**Verification evidence** — What tests prove the contract works as expected, what the evidence does and does not prove, and which open implementation questions remain.

Let's get started!

## Slide 5/53 - Introduction (Module: Compare the core API interfaces)

Before you can define a strong API contract, you need to know which inference interface the workflow is likely to use and whether the workflow needs managed conversation state.

In this module, you'll compare the Responses API and Chat Completions API at decision depth, then examine the Conversations API as a persistent state resource that works with Responses. Use that comparison to choose the inference interface and state approach that fit the workflow, then capture which details must be checked in current documentation before build.

For technical implementation teams and solution architects, these decisions matter because interface and state choices can affect state handling, request shape, output structure, tool behavior, streaming, async handling, and downstream integration expectations.

## Slide 6/53 - Why core interface choice matters

An inference API interface is the primary way an application sends work to an OpenAI model and receives a result. In this course, the Responses API and Chat Completions API are inference interfaces; the Conversations API is a state resource used with Responses, not a third inference interface.

These interface and state decisions shape the solution design. They can affect: how the solution handles state; how context is supplied or retained; whether tools or actions are needed; whether structured outputs are required; whether the user sees output all at once or progressively; whether work happens synchronously or asynchronously; how errors are returned; how verification tests are written; how downstream systems consume the output.

A strong interface choice starts with the workflow requirement. The team should not choose an interface because it appears in an old code sample, a legacy customer implementation, or a familiar pattern. Instead, choose the interface that best supports the required behavior, then identify what current documentation facts must be validated before implementation.

Use this question to guide the decision: *What does the workflow need the API interaction to do reliably?*

If the workflow only needs a stateless response, the contract may be simple. If the workflow needs structured fields, tool calls, state across turns, streaming output, or long-running work, the interface and contract need to make those assumptions visible.

For partner teams, this is especially important during technical discovery and handoff. A vague interface recommendation creates downstream ambiguity. A clear recommendation gives implementation, security, validation, and product teams something concrete to review.

## Slide 7/53 - Responses API

Use the Responses API as the recommended starting point for new projects, then validate that current official documentation supports the workflow's required capabilities.

At a planning level, Responses API is often a strong starting point when the team needs backend or application-level control over: model interaction; output shape; structured output; tool behavior; multimodal or agentic patterns, where currently supported; verification evidence.

Responses API may be relevant when a workflow needs the model to do more than produce free-form text. For example, it may need to return predictable fields, use a tool, work with approved context, or support a more controlled application workflow.

The Responses API can also carry state between turns. When a workflow needs a durable conversation object across sessions, devices, or jobs, the Conversations API can be used with Responses. Treat the inference interface and state approach as related but separate contract decisions.

In a Core Interface and API Contract Plan, do not simply write "use Responses API" and stop there. Explain why it fits the workflow.

A strong interface rationale might say:

> "Responses API is the recommended starting point because the workflow needs a structured case summary, a defined review flag, and potential ticket-status tool use. Before implementation, confirm the current supported tool configuration, structured-output options, SDK examples, and streaming behavior."

This keeps the recommendation useful while making clear that the plan guides implementation, but does not replace detailed build documentation.

Before making implementation claims, validate current documentation for details such as: supported tools; structured-output options; streaming behavior; async behavior; SDK examples; multimodal support; current availability or limitations.

For technical pre-sales and partner technical consultants, the key is to frame Responses API as a fit recommendation, not as a final build specification. The handoff should explain why this interface is likely to support the workflow and which implementation details need product validation.

## Slide 8/53 - Chat Completions

The Chat Completions API remains supported and may still appear in existing implementations, examples, legacy integrations, or customer environments.

You should be able to recognize a Chat Completions-style pattern, especially when an existing solution uses message roles and a conversational request-response structure. A customer may already have code, prompts, tests, or operational processes built around it.

For new projects, current OpenAI guidance recommends the Responses API, so existing Chat Completions code should be treated as a compatibility or migration constraint—not as the default for new work.

Use Chat Completions recognition for practical review questions such as: is this an existing customer implementation? Is the customer asking for maintenance, extension, or compatibility? Is a newer interface now the documented fit for the workflow? Would changing the interface affect state, tools, output structure, tests, or downstream systems? What migration or compatibility questions need to be answered before recommending a change?

The focus in this course is decision-making, not migration procedure. You do not need to teach legacy implementation details. The key habit is to avoid copying a legacy interface choice into a new workflow without checking whether it still fits.

A useful planning statement might be:

> "The customer's current support bot uses the Chat Completions API. Because the new workflow requires structured summaries, possible tool use, and several-turn follow-up, the team should treat that implementation as a compatibility constraint. Evaluate the Responses API for the new inference path, then decide whether state can be handled in the application or whether the Conversations API should be used with Responses for persistent continuity."

For solution architects and implementation teams, this distinction matters. Existing customer code can create compatibility constraints, but it should not override workflow requirements, integration needs, or current platform guidance.

## Slide 9/53 - Conversations

The Conversations API is not a third inference interface alongside Responses and Chat Completions. It works with the Responses API to persist conversation state as a durable object with its own identifier, so context can continue across sessions, devices, or jobs.

This can be useful when the workflow needs to remember a user's current case, follow up on earlier information, maintain task context, or support a multi-turn process.

Not every Responses workflow needs a persistent conversation object. Use the Conversations API only when the workflow justifies continuity across turns, tasks, sessions, or user interactions.

If a single request can contain everything needed, a stateless interaction may be simpler, easier to test, and easier to govern.

If state is needed, the contract must distinguish the inference interface from the state mechanism and explain the state assumptions clearly.

Capture: what is retained; where state lives; who owns it; how long it is retained; what policy applies; what privacy or retention constraints matter; how state affects testing; how state affects logging and handoff documentation.

A useful planning statement might be:

> "The workflow uses the Responses API for inference and may use the Conversations API because it needs persistent continuity across follow-up questions about the same support case. Before implementation, validate current product behavior, limits, storage and retention expectations, and documentation guidance. The contract must identify what state is retained, where it lives, and how the user or system can recover when state is unavailable or mismatched."

State can improve user experience, but it also introduces governance questions. Treat it as a design decision, not a default.

For FDE-style builders and implementation partners, the practical checkpoint is: *What state does the workflow require, who owns it, and how will failure cases be tested?*

## Slide 10/53 - Interface decision table

By now, you've compared two inference interfaces and one state resource. The Responses API and Chat Completions API can generate model outputs; the Conversations API works with Responses to persist conversation state.

The goal is to connect the workflow requirement to an inference interface and, separately, a state approach.

A good recommendation always starts with the workflow: what does the application need to do? Does it need predictable structured output? Does it need tool use? Does it need continuity across turns? Is the customer starting from an existing implementation that creates compatibility or migration constraints?

Use the answers to choose the inference interface first, then the state approach.

Use the table below as a first-pass decision aid. It can help you identify the strongest starting point and the product facts you need to validate before implementation.

| Surface or resource | Use when the workflow needs… | Validate before build… |
|---|---|---|
| Responses API | Recommended inference interface for new projects; supports current documented capabilities such as structured outputs and tools | Required capabilities, state approach, streaming or background behavior, SDK examples, and current limitations |
| Chat Completions API | Supported inference interface for an existing implementation or compatibility requirement | Customer constraints, migration impact, manual state handling, and current support guidance |
| Conversations API | Persistent conversation state used with the Responses API across sessions, devices, or jobs | State ownership, storage and retention expectations, limits, privacy, and recovery behavior |

This table does not finalize the inference interface or state approach on its own, but it can help you make your assumptions visible. An effective contract should make the workflow clear enough for another technical stakeholder to build, test, document, and review.

Before build, confirm current product details in approved documentation and note any assumptions that still need validation.

## Slide 11/53 - Real-world example: Choosing the right core API interface

A customer has an existing customer-support chatbot built on a Chat Completions-style implementation. The customer now wants a new workflow.

The API must: generate structured case summaries; use approved account context; call a ticket-status tool; support follow-up questions across several turns; feed summary fields into an internal dashboard.

The implementation team should not copy the existing interface choice just because it already exists. Chat Completions may still appear in legacy implementations, examples, or customer environments. That is useful to know, but it does not settle the new design.

Current guidance recommends the Responses API as the starting point for new projects, including workflows that need supported structured outputs or tools. If the workflow needs persistent continuity, the Conversations API may be used with Responses; it is not an alternative inference interface.

The planning decision should say:

> "We recommend the Responses API as the inference starting point because the workflow needs structured output and potential tool use. We also need to decide whether the workflow can manage context without a persistent conversation object or should use the Conversations API with Responses for follow-up continuity. The existing Chat Completions implementation creates compatibility and migration questions, but it should not be copied into the new workflow without validation."

Separate what is already known from what still needs validation.

**Known:** the customer has an existing Chat Completions-style implementation; the new workflow needs structured case summaries; the workflow needs approved account context; the workflow may need a ticket-status tool; the workflow needs continuity across follow-up questions.

**Needs validation:** whether Responses API currently supports the required structured output and tool behavior; whether a persistent Conversations object is needed for follow-up continuity, and how state will otherwise be managed; whether the customer has compatibility, migration, governance, or timeline constraints; whether the existing implementation can be adapted safely or should be redesigned.

This is the kind of recommendation a partner technical consultant can use in a handoff: it is specific enough to guide review, but honest about unresolved product and customer-environment facts.

## Slide 12/53 - Recommended exercise: Choose a core API interface

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice selecting the right interface for a workflow.

**Task:** Use the customer-support workflow from the real-world example, then compare it with these two short workflow examples:

- **Simple stateless workflow:** A user pastes a short support note into an internal form. The API returns a concise summary for human review. No follow-up state, tool use, retrieval, streaming, or async behavior is required.
- **Existing chat-style workflow:** A customer already has a Chat Completions-style FAQ bot and wants to maintain compatibility while reviewing whether the new workflow requires a different interface.

For each workflow, choose the strongest inference starting point—the Responses API, the Chat Completions API for a supported compatibility need, or another validated current inference interface. Then choose a state approach: stateless, application-managed, or a persistent Conversations object used with Responses. Explain the rationale and name what must be validated in current documentation.

**Estimated time:** 8–10 minutes

**Suggested output and reflection:** Interface recommendation section of the Core Interface and API Contract Plan.

**Optional stretch:** Identify one reason a customer might still have Chat Completions in an existing implementation and one question that would guide migration or compatibility planning.

## Slide 13/53 - Knowledge check

**A customer has an existing Chat Completions-style support bot. The new workflow needs to generate structured case summaries for an internal dashboard, reference approved account context, check ticket status through a read-only tool, and support follow-up questions about the same case when needed. Which planning recommendation is strongest?**

- Start with the Responses API and assume it automatically covers structure, tools, context, and persistent state.
- **Evaluate the Responses API for structured output and tool needs; treat Chat Completions as a compatibility constraint; use the Conversations API with Responses only if persistent state is required.** ✓ Correct
- Keep Chat Completions because the current support bot already works.
- Use the Conversations API as the inference interface because follow-up questions make the workflow stateful by default.

The strongest recommendation starts from the new workflow requirement without ignoring the existing implementation. It identifies the Responses API as the recommended inference starting point for structured output and tool-supported behavior, treats Chat Completions as a supported compatibility or migration consideration, and separates state design from the inference choice by using the Conversations API with Responses only when persistent continuity is required. It also avoids assuming that all required capabilities can be combined without validating current documentation.

## Slide 14/53 - Summary

In this module, you compared the core API interfaces that can shape an API workflow.

Choose the interface from the workflow requirement, not from habit or legacy code. A strong interface recommendation explains why the interface fits, what technical assumptions it creates, and which current documentation details must be validated before implementation.

## Slide 15/53 - Introduction (Module: Explain how interface choice affects solution design)

Once you choose a core interface, the design consequences become clearer.

In this module, you'll connect interface choice to state, context, tools, actions, streaming, async behavior, structured outputs, retries, idempotency, and verification. These implications help you turn an interface decision into clear API contract assumptions that another team can build, review, and test.

For solution architects and technical implementation teams, this is where the design moves from "Which API surface fits?" to "What must the API interaction support, prove, and document?"

## Slide 16/53 - State and context

The interface choice affects how the API handles state and context.

Start with the difference between stateless requests and stateful interactions.

A **stateless request** contains enough information for the service to process that request on its own. The caller sends the input and any required context each time. This can make behavior easier to test because each request stands alone.

A **stateful interaction** depends on continuity across turns, tasks, or user interactions. The system may need to remember the current case, previous answers, user preferences, workflow progress, or other context.

**Use a stateless request when:** the request can include all required information; the user does not need continuity across turns; the workflow is simple, repeatable, and easy to validate; privacy or retention concerns make state unnecessary or undesirable.

**Use a stateful interaction only when the workflow justifies it.** For stateful interactions, define: what is retained; where it lives; who owns it; how long it is retained; what policy or customer constraint applies; what happens if state is unavailable, stale, or mismatched.

Context also affects quality, latency, cost, and testing. A request with too little context may produce incomplete output. A request with too much context may become expensive, slow, noisy, or hard to verify.

These decisions should be captured clearly so they can guide implementation and testing. In the Core Interface and API Contract Plan, capture state and context assumptions in plain language.

For example:

> "The workflow is stateful because users ask follow-up questions about the same support case. The plan assumes the case reference is retained across turns. Before implementation, validate where state is stored, how long it is retained, and what privacy rules apply."

Or:

> "The workflow is stateless. Each request must include account_id, issue_text, and approved_context_ids. The API should not rely on previous turns to complete the summary."

For implementation teams, state and context decisions should later translate into tests. A stateless contract should prove the request can stand alone. A stateful contract should test continuity, missing state, stale state, and mismatched state.

## Slide 17/53 - Tools and actions

Some API workflows can be completed with the request context and a structured response. Others need the API workflow to use a tool or interact with another system.

A tool is an external capability the workflow can use to get information, perform a calculation, or prepare an action. For example, a workflow may need to look up ticket status, retrieve account details, check inventory, calculate a value, route a request, or prepare an update for review.

Tool needs affect the interface contract because the API interaction must define more than the model's final response. It must also define what tool may be used, what input the tool needs, what output it returns, and how the workflow handles tool failure.

In the Core Interface and API Contract Plan, capture:

- **Tool purpose:** What does the workflow need the tool to do?
- **Tool input:** What fields or arguments does the tool require?
- **Tool output:** What should the tool return?
- **Execution boundary:** What does the model request, and what does application code or orchestration actually execute?
- **Permissions:** What system or data access is assumed?
- **Failure behavior:** What happens if the tool is unavailable, returns an error, or returns incomplete data?
- **Approval needs:** Does the tool only retrieve information, or could it change a system?

Separate read-only tool use from action-taking behavior. A read-only tool retrieves information, such as ticket status or an approved policy entry. An action-taking workflow changes something, such as updating a record, sending a message, creating a task, or triggering another system. Action-taking behavior usually needs stronger approval, logging, and verification.

At this stage, you are defining the interface and contract assumptions, not the full tool implementation. The contract should make tool-related assumptions visible so a later tool plan can define detailed execution, approvals, and observability.

A useful planning statement might say:

> "The workflow may need a read-only ticket-status tool. The contract should define the required tool input, expected tool result, failure behavior, permission assumption, and whether the structured summary can use the returned ticket status. System-changing actions are out of scope unless a later tool plan defines approval, execution, logging, and verification requirements."

Use this practical checkpoint: *Can the workflow be completed with request context and a structured response, or does the selected interface need to support tool use?*

## Slide 18/53 - Streaming and async behavior

The interface choice can affect how the user or calling system receives the result.

Some API interactions return a complete response only when the work is finished. Others may return output progressively, or start work and let the client check back later. These choices affect user experience, client behavior, structured-output validation, error handling, and testing.

**Streaming** means the response is delivered progressively instead of all at once. This can be useful when the user benefits from seeing output as it is generated, such as a long explanation, draft, or conversational response.

**Use streaming when:** the response may take long enough that progressive output improves the experience; the user can benefit from seeing partial output; partial output is acceptable for the workflow; the client can handle partial output and final completion behavior.

Streaming is less useful when the output must be validated as a complete structured object before another system can use it. For example, if a dashboard needs a complete JSON object with required fields, the contract should define the final response that downstream systems consume.

**Async behavior** means the client does not wait for the full result in the same request. The workflow may start a job, return a job or status reference, and let the client check progress or receive the result later.

**Use async behavior when:** the work may take longer than the client should wait; the workflow depends on slower tools, retrieval steps, or external systems; the user experience can support progress states; completion, failure, timeout, and retry behavior can be defined clearly.

For streaming or async behavior, the contract should capture: how the client recognizes success; how progress is shown or checked; what counts as completion; what timeout means; how failure is returned; whether retry behavior is expected; what the user or client should do next.

At this stage, you are not designing streaming protocols, queues, or production orchestration. You are deciding whether the interface needs to support progressive output, delayed completion, or a standard complete response.

A useful planning statement might say:

> "The dashboard needs a complete structured summary before it can consume the response. Streaming may be useful for a user-facing preview, but the contract must define the complete final response for downstream use."

Or:

> "The account review summary may take longer when source lookup is required. The contract should define whether the client waits for the result or receives a status reference and checks completion later."

The practical checkpoint is: *Does the workflow need a complete response immediately, progressive output as it is generated, or a delayed result that the client can check later?*

## Slide 19/53 - Structured outputs

Use structured model output when downstream systems, dashboards, routing logic, tools, or reviewers need predictable fields.

Structured output is not just a formatting preference. It is a reliability and integration control. OpenAI Structured Outputs can enforce adherence to a supported JSON schema. JSON mode ensures valid JSON but does not guarantee schema adherence.

A free-form paragraph may be fine for a human reader. It is usually not enough when another system needs to sort, filter, route, validate, store, or review the output.

Use structured outputs when the workflow needs fields such as: `issue_type`, `urgency`, `recommended_next_action`, `source_ids`, `confidence_note`, `needs_human_review`, `review_reason`, `escalation_path`.

A model-authored `confidence_note` is explanatory text—not a calibrated confidence score. Use deterministic checks, evaluators, or human review for decisions that depend on reliability or risk.

Schema adherence does not eliminate other response paths. The contract and tests must handle refusals, incomplete or truncated responses, invalid application state, and any evaluator or human-review outcome that prevents the object from being used.

Before implementation, define: required fields; optional fields; field meanings; data types; allowed values; invalid-output behavior; what happens when the API cannot produce valid structure.

A weak structured-output requirement says: *"Return a summary in JSON."*

A stronger requirement says:

> "Return a structured object with issue_summary as a string, urgency as one of low, medium, or high, source_ids as an array of approved source identifiers, recommended_next_action as a string, confidence_note as a short string, and needs_human_review as a boolean. If the response cannot be grounded in approved context, set needs_human_review to true and explain the reason in review_reason."

That is much easier to test, review, and hand off.

For implementation teams, structured-output fields should later become validation checks. For solution architects, they should become part of the handoff: what the downstream system requires, what the model is expected to return, and what happens if the output is malformed or incomplete.

## Slide 20/53 - Idempotency and retries, where relevant

Some workflows need retry behavior. A request might fail because of a timeout, dependency failure, or temporary service issue.

Retrying can be useful, but it can also create risk.

**Idempotency** means that repeating a request should not create unintended duplicate work or duplicate records when safe repeat behavior is required. This matters most for write operations or customer-visible actions.

Ask: *If this request runs twice, could it create duplicate work, duplicate records, duplicate messages, or duplicate customer-visible actions?*

For a read-only lookup, retry risk may be low. For an action that creates a support task, sends a customer email, or updates a record, retry risk is higher.

Capture retry and idempotency assumptions in the contract when relevant. For example:

> "If the client retries a request after timeout, the workflow must not create duplicate dashboard entries. The contract should include a request_id or another deduplication assumption before implementation."

At this stage, you are not designing production retry infrastructure. You are making retry-sensitive behavior visible before the build begins.

For partner implementation teams, this is a practical design checkpoint. Even if retry logic is implemented later, the contract should flag whether repeated calls are safe, risky, or require a deduplication mechanism.

## Slide 21/53 - Real-world example: Understanding how interface choice changes the design

A customer-support workflow needs the assistant to: remember the user's current case; ask a clarifying question if required details are missing; call a ticket-status tool; return a structured summary with fields for issue_type, urgency, recommended_next_action, and needs_human_review.

This is not just an interface naming decision. The interface choice affects the whole design.

**If the workflow is stateless:** the request must include enough context to stand alone. The contract must define which case details, user details, and approved context references are required in every call.

**If the workflow is stateful:** the plan must explain what is retained, where it lives, who owns it, how long it is retained, and what happens when the state is unavailable or mismatched.

**If the workflow uses a ticket-status tool:** the contract must define tool input assumptions, expected tool results, tool error behavior, approval needs, and verification tests.

**If the workflow returns structured output:** the output fields must be defined before testing begins.

A weak plan says: *"Use the API to help support agents answer questions."*

A stronger plan says:

> "Use an interface that supports the required structured output and potential ticket-status tool use, with state only if follow-up continuity is required. The contract must define request fields, tool assumptions, structured response fields, error states, and verification tests for missing context, unavailable ticket status, invalid structure, and human-review triggers."

A plan written at this level gives implementation teams a clear path to build and test. It also gives technical pre-sales teams a clearer way to explain scope, dependencies, and validation needs to the customer.

## Slide 22/53 - Recommended exercise: Map interface implications

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice connecting interface choice to design consequences.

**Task:** Use the customer-support workflow from the real-world example, or a workflow from your own work, to identify how interface choice affects state, context, tools, streaming, async behavior, structured outputs, retries, idempotency, and verification.

**Estimated time:** 8–10 minutes

**Suggested output and reflection:** Interface implications section of the Core Interface and API Contract Plan.

**Optional stretch:** Add one privacy or retention question related to state, and one retry or idempotency question related to a write action.

## Slide 23/53 - Knowledge check

**Match each design assumption to the contract implication it creates.**

- Structured output for a dashboard → Define required fields, data types, allowed values, and invalid-output behavior.
- Write operation with retries → Identify idempotency requirements so repeated requests do not create duplicate records or actions.
- Tool-supported workflow → Define tool input assumptions, tool result handling, permission assumptions, and tool failure behavior.
- Stateful interaction → Document what is retained, where it lives, who owns it, and what privacy or retention constraints apply.
- Stateless request → Include all required context in each request so the request can stand alone.

## Slide 24/53 - Summary

In this module, you learned that interface choice affects more than the API surface. A strong Core Interface and API Contract Plan should make design implications visible: state, context, tools, streaming, async behavior, structured outputs, retries, idempotency, errors, and verification.

The goal is to produce a contract that implementation, architecture, validation, and customer-facing technical teams can use.

## Slide 25/53 - Introduction (Module: Define request, response, schema, and error contract)

Now that you have connected interface choice to design implications, you can define the actual contract.

In this module, you'll describe what the caller sends, what the API returns, what structure is required, which errors must be handled, and how to avoid vague contracts that are hard to build or test.

For technical implementation teams and solution architects, this is the core of the handoff. The contract should be precise enough to guide implementation and validation, while still avoiding unvalidated product or SDK details.

## Slide 26/53 - Define the request

A request contract defines what the caller sends.

Start by naming the purpose of the API interaction. The endpoint or interface should connect to a workflow requirement, not a generic "AI request."

Capture:

- **Endpoint purpose:** What should this interaction accomplish?
- **Method and route:** Where relevant, what application endpoint or service boundary does the design include?
- **Headers:** What configuration, content type, or request metadata is assumed?
- **Authentication assumption:** Who or what is calling the API?
- **Caller type:** Is the caller a user, application, service account, internal system, or another API component?
- **Required body fields:** What must be present?
- **Optional body fields:** What can be included when available?
- **Validation rules:** What values are allowed?
- **Context, conversation, or state reference:** What reference is needed, if any?
- **Excluded fields:** What should never be included because it is unnecessary, sensitive, unapproved, or outside the workflow boundary?

Example request contract section:

- **Workflow requirement:** Generate an internal support-case summary for account managers.
- **Caller assumption:** Internal dashboard service calling on behalf of an authenticated employee.
- **Method and route:** `POST /case-summary`, if the customer application exposes a service endpoint.
- **Required fields:** `account_id`, `issue_text`, `source_context_ids`.
- **Optional fields:** `user_question`, `case_priority_hint`.
- **Validation rules:** `account_id` must be present; `issue_text` must be non-empty; `source_context_ids` must reference approved sources.
- **Excluded fields:** Full customer payment details, personal credentials, production secrets, unapproved account notes.

A request contract should make implementation easier, not harder. Use clear field names and simple validation rules. Also distinguish between the customer application endpoint and the OpenAI API interface decision.

For example: the customer may expose a service endpoint such as `POST /case-summary`, while the implementation uses an OpenAI API interface behind that service boundary. The API contract should make that distinction clear when relevant.

## Slide 27/53 - Define the response

A response contract defines what the API returns. A strong response contract should include: success status code or success condition; response body; required output fields; optional output fields; expected structure or schema discipline; source, evidence, confidence, or review fields where relevant; next-step behavior for the client, downstream system, reviewer, or user; behavior when the requested output cannot be produced safely, completely, or in the required structure.

Example response fields:

| Field | Type | Required | Meaning |
|---|---|---|---|
| `issue_summary` | string | Yes | Short summary of the customer issue. |
| `urgency` | enum: low, medium, high | Yes | Operational urgency for review or triage. |
| `recommended_next_action` | string | Yes | Suggested next internal action for the account team. |
| `source_ids` | array of strings | Yes, when source grounding is used | Approved source references used to support the output. |
| `confidence_note` | string | Yes | Brief explanatory note about known uncertainty or missing context. Not a calibrated confidence score; must not replace evaluator or human-review logic. |
| `needs_human_review` | boolean | Yes | Whether a human should review before use. |
| `review_reason` | string | Required when needs_human_review is true | Why review is required. |

The response contract should not assume the model can always produce a perfect answer. Define what happens when the API cannot answer, cannot use an approved source, or cannot produce valid structure.

A useful fallback response might include: a structured failure state; a review flag; a user-safe error message; a next step for the client or reviewer.

For downstream integration, the response contract should be explicit about which fields are intended for machine consumption and which fields are intended for human review. This distinction matters for dashboards, workflow automation, logs, review queues, and customer-facing surfaces.

## Slide 28/53 - Define structured-output requirements

Structured-output requirements make the API response easier to validate, route, review, and integrate with downstream systems. The contract should state whether the implementation uses Structured Outputs for schema adherence or JSON mode plus application-side schema validation.

Use structured outputs when predictable fields are needed for: dashboards; routing; workflow automation; tool inputs; human review; downstream system processing; analytics or reporting.

Define: required fields; optional fields; data types; allowed values; field-level meaning; invalid-output behavior.

Include fields that support review and governance where relevant. For example: `source_ids`, `confidence_note`, `needs_review`, `review_reason`, `escalation_path`.

Also define what counts as structured-output failure. Examples include: missing required fields; wrong data type; invalid allowed value; unsupported claim; malformed structure; free-text output when structured output is required.

A weak requirement says: *"The API returns JSON with the summary."*

A stronger requirement says:

> "The API returns a structured object with required fields issue_summary, urgency, recommended_next_action, confidence_note, and needs_human_review. urgency must be low, medium, or high. needs_human_review must be true when source support is missing, a defined application rule or evaluator triggers review, or the response cannot be used safely."

Before scripting or implementation guidance, validate exact field names, schema examples, and structured-output behavior against current authorized documentation.

For technical implementation teams, this structured-output section should be written so it can become a schema, a validation rule set, or a set of test assertions later.

## Slide 29/53 - Define error states and status codes

An API contract is incomplete if it only describes success. Define error states before implementation begins so the client, user, downstream system, or reviewer knows what to do when something fails.

Common error states include: missing required field; invalid data type; invalid allowed value; invalid authentication, where the caller cannot be confirmed; authenticated but unauthorized request, where the caller is known but lacks permission for the action or data; unsupported input; missing context; source unavailable; unsupported workflow request; timeout; async failure; retry condition; dependency failure; structured-output failure; state mismatch; conversation-reference mismatch.

For each error state, define: the condition that triggers it; the status code or failure category, where relevant; a user-safe error message; next-step behavior for the client or reviewer.

Example error states:

**Missing required field** — Condition: `account_id` is not provided. User-safe message: "The account identifier is missing." Next step: Client should resubmit with `account_id`.

**Unauthorized account access** — Condition: Caller is authenticated but does not have permission for `account_id`. User-safe message: "You do not have access to this account." Next step: Do not return account details. Log permission failure.

**Source unavailable** — Condition: Required approved context cannot be accessed. User-safe message: "Approved source context is unavailable." Next step: Set `needs_human_review` to true or return structured failure state.

**Structured-output failure** — Condition: Required response fields cannot be produced. User-safe message: "The response could not be produced in the required format." Next step: Retry if safe or route to review.

Do not expose sensitive internal details in user-facing errors. A useful error helps the system recover without leaking private context.

Error design should also separate authentication, authorization, validation, dependency, and model-output failures. These are different engineering problems and usually have different owners, logs, and remediation paths.

## Slide 30/53 - Make the API contract specific enough to test

A vague API contract is hard to build against because it leaves too much open to interpretation.

Avoid requirements such as: "Send some text." "Return a summary." "Make a recommendation." "Use the right context." "Handle errors gracefully."

These phrases are too vague to guide implementation or testing. They do not specify the required input, output, validation rule, error behavior, or review path.

A stronger API contract specifies: expected request shape; required fields; optional fields; validation rules; response fields; structured-output requirements; error states; review behavior; examples that can be tested.

Example weak contract: *"The API should summarize customer issues and suggest what to do next."*

Example stronger contract:

> "The API accepts account_id, issue_text, and approved_context_ids. It returns issue_summary, source_ids, urgency, recommended_next_action, confidence_note, needs_human_review, and review_reason. If approved context is missing, the API must not invent source-backed claims and must set needs_human_review to true or return a structured failure state."

This version gives reviewers enough detail to check whether the API interaction is ready for implementation, needs remediation, or requires specialist review.

Clear API contracts reduce delivery risk. They help pre-sales, architecture, implementation, customer security, and production support teams work from the same expectations before the build moves forward.

## Slide 31/53 - Real-world example: Turning a vague requirement into an API contract

A partner receives this requirement: *"The API should summarize customer issues and suggest what the account team should do next."*

The customer wants the output to feed an internal dashboard where account managers can sort, filter, and review recommendations before calls.

That requirement is not yet a strong contract. It does not define: what the caller sends; which fields are required; what the response returns; what structure the dashboard needs; what happens when context is missing; what should trigger human review; what errors must be handled.

A stronger request contract might define:

- `account_id` — Required: Yes. Notes: Must reference an account the caller is allowed to access.
- `issue_text` — Required: Yes. Notes: The issue or support-note text to summarize.
- `approved_context_ids` — Required: Yes, where grounding is required. Notes: References approved account or support context.
- `user_question` — Required: Optional. Notes: Follow-up question or focus area.

A stronger response contract might define:

- `issue_summary` — Required: Yes. Notes: Concise summary of the issue.
- `source_ids` — Required: Yes, where grounding is required. Notes: Source references used to support the summary.
- `urgency` — Required: Yes. Notes: low, medium, or high.
- `recommended_next_action` — Required: Yes. Notes: Internal next step.
- `confidence_note` — Required: Yes. Notes: Short explanation of known uncertainty or missing context; not a calibrated confidence score.
- `needs_human_review` — Required: Yes. Notes: true or false.
- `review_reason` — Required: Required if needs_human_review is true. Notes: Why review is required.

It should also define error states: missing `account_id`; unauthorized access to `account_id`; missing approved context; source unavailable; invalid `urgency` value; structured-output failure.

The vague requirement has now been translated into something testable. The implementation team can see the expected inputs, required outputs, and failure cases.

This also makes the handoff clearer. Technical and customer-facing teams can explain what has been defined, what still needs validation, and which customer system dependencies remain open.

## Slide 32/53 - Recommended exercise: Define a clear interface contract

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice making the chosen interface precise enough to build against.

**Task:** Use this vague API interaction: *"The API should summarize customer issues and suggest what the account team should do next."* Convert it into a concrete interface contract with request, response, schema, structured-output, authentication, and error assumptions.

**Estimated time:** 8–10 minutes

**Suggested output and reflection:** Request, response, schema, structured-output, and error section of the Core Interface and API Contract Plan.

**Optional stretch:** Add one validation rule, one unauthorized-access error, and one structured-output failure state.

## Slide 33/53 - Knowledge check

**A partner writes this handoff note: "The API should turn a project update into a task list for the team tracker." What is missing before an implementation team can build and test it?**

- **What the caller sends, which task fields the API must return, what structure the tracker expects, and what happens when the update is incomplete or invalid.** ✓ Correct
- The exact model version, SDK, hosting environment, and development tools engineers will use for the first build.
- The broader rollout approach, including pilot timing, adoption goals, success reporting, and how managers will communicate the finished workflow to teams.
- The final tracker experience, including the screen layout, button labels, notification wording, and how users will visually review completed tasks.

A strong handoff defines what the caller sends, what the API returns, what structure the output must follow, and what should happen when something goes wrong. Without those details, the handoff is still too vague to build or test.

## Slide 34/53 - Summary

In this module, you turned interface decisions into contract details. A strong API contract defines the request, response, structured-output expectations, error states, and failure behavior clearly enough for another team to build and test.

The key practice is to write API contracts that reduce ambiguity across architecture, implementation, validation, customer review, and handoff.

## Slide 35/53 - Introduction (Module: Add verification and error tests)

An API contract is only useful if the team can verify that it behaves as expected.

In this module, you'll turn the API contract into success tests, error tests, structured-output tests, and state-behavior tests. These tests help capture evidence about what the API interaction does correctly, what can fail, and what still needs review before the work moves forward.

By the end of the module, you should be able to connect each contract requirement to evidence that another technical stakeholder can inspect.

## Slide 36/53 - Define success tests

A success test proves that the API behaves as expected under valid conditions. It should test one or more requirements from the API contract.

For each success test, define: the valid request; required fields present; expected status code or success condition; expected response body; required output fields; structured-output schema adherence, where required; expected state or conversation behavior, where relevant; expected tool-result handling, where relevant; expected client or downstream-system next step.

Example success test:

- **Test:** Valid support summary request
- **Request:** `account_id`, `issue_text`, and `approved_context_ids` are present and valid.
- **Expected result:** Response includes `issue_summary`, `urgency`, `recommended_next_action`, `confidence_note`, and `needs_human_review`.
- **Structured-output expectation:** `urgency` is low, medium, or high; `needs_human_review` is true or false.
- **What it proves:** The API can return the required fields for a valid request.
- **What it does not prove:** It does not prove error handling, permission behavior, scale, or production readiness.

A success test is only one part of verification. The plan also needs tests for error handling, failure behavior, permissions, and any structured-output or state assumptions.

Write each success test so it can later become a manual test, automated test, API client test, integration test, or validation check.

## Slide 37/53 - Define error and failure tests

Error and failure tests prove whether the API behaves predictably when something is missing, invalid, unsupported, or unsafe.

Include tests for: missing required field; invalid authentication; authenticated but unauthorized request; invalid data type; invalid allowed value; unsupported input; missing context; unavailable source; out-of-scope request; timeout or retry assumption; structured-output failure; state or conversation mismatch; tool error or tool unavailable, where relevant; approval-required condition, where relevant.

Example error test — **Missing account_id**: Request: `issue_text` is present, but `account_id` is missing. Expected result: API returns a defined missing-field error or structured failure state. What it proves: The API validates required fields before attempting the workflow. What it does not prove: It does not prove permission behavior or structured-output success.

Example permission test — **Authenticated but unauthorized account**: Caller is authenticated but does not have permission to access `account_id`. Expected result: API does not return account data and returns a user-safe unauthorized message. What it proves: The contract separates authentication from authorization. What it does not prove: It does not prove the customer's full access-control implementation.

Separating these tests prevents a common mistake: assuming that a successful happy path proves the API is ready.

Error tests also help surface ownership questions. Some failures are handled by the application, some by the API service, some by customer access-control systems, and some by later validation or observability plans.

## Slide 38/53 - Test state, streaming, async, retry, and idempotency assumptions

Some API contracts need additional behavior tests beyond the basic success and error paths.

For stateless interactions, test whether the request includes enough context to stand alone. A stateless request should not rely on hidden previous turns unless the API contract says it does.

For stateful interactions, test whether expected context is retained, referenced, or unavailable in the way the plan expects. Also test what happens when the conversation reference is missing, expired, or mismatched.

For streaming behavior, identify how partial-output success or failure would be recognized at a planning level. If the final response must be structured, define when the structure is validated.

For async behavior, define how completion, progress, failure, timeout, or retry should be checked.

For retry-sensitive workflows, identify whether repeat requests could duplicate work, messages, records, or customer-visible actions.

Example state test — **Conversation-reference mismatch**: Request: User asks a follow-up question, but the conversation reference points to the wrong case. Expected result: API asks for clarification or returns a structured state-mismatch error instead of using incorrect context. What it proves: The contract handles state mismatch safely.

Example retry test — **Duplicate request after timeout**: Request: Client resends the same request after timeout. Expected result: The API does not create duplicate dashboard entries or duplicate customer-visible actions. What it proves: The contract identifies idempotency expectations for retry-sensitive behavior.

Keep these tests at API contract verification depth. You are defining what needs to be checked, not designing queue implementation, session storage, or monitoring infrastructure.

These tests help reveal hidden assumptions early. A workflow that looks simple in the happy path may become more complex when you test state mismatch, retries, partial output, timeout, or unavailable dependencies.

## Slide 39/53 - Capture verification evidence

Verification evidence should be clear enough for another technical stakeholder to inspect. The customer expects the output to feed an internal dashboard.

Capture: test command, request, or test description; expected response; actual response; pass, fail, or needs-review result; what the result proves about the contract; what the result does not yet prove; open question, owner, or validation need created by the result.

Use this simple evidence format:

- **Test name:** Valid support summary request
- **Request summary:** `account_id`, `issue_text`, `approved_context_ids` present
- **Expected response:** All required summary fields returned in valid structure
- **Actual response:** Required fields returned; `review_reason` omitted when `needs_human_review`=false
- **Result:** Pass
- **Proves:** Basic success response meets contract
- **Does not prove:** Permission behavior, source unavailability, scale, production monitoring
- **Open question:** Validate exact structured-output behavior before implementation

This prevents overclaiming. Contract verification proves the contract behaves as tested. It does not prove scale, resilience, security posture, production monitoring readiness, or full governance readiness.

This evidence supports better technical review because it shows what has been tested without overstating readiness. It can inform recommendations, test planning, and acceptance criteria for the next stage of work.

## Slide 40/53 - Real-world example: From contract to verification evidence

A support-summary API contract requires: `account_id`, `issue_text`, `approved_context_ids`. It must return: `issue_summary`, `urgency`, `recommended_next_action`, `confidence_note`, `needs_human_review`. The customer expects the output to feed an internal dashboard.

A strong verification plan should include:

**Success test:** Valid request includes `account_id`, `issue_text`, and `approved_context_ids`. The response returns every required field in the expected structure.

**Missing-field test:** Request omits `account_id`. The response returns a defined missing-field error or structured failure state.

**Authentication test:** Request has invalid authentication. The response does not process the request and returns a user-safe authentication error.

**Authorization test:** Caller is authenticated but does not have permission for the account. The response does not return account details.

**Unsupported-context test:** Approved context is missing or unavailable. The response does not invent source-backed claims and sets `needs_human_review` to true or returns a structured failure state.

**Structured-output test:** The response must follow the required schema when a structured result is returned. The test also covers refusal, incomplete output, and other defined non-schema paths; the system should return a controlled failure state or route for review.

**Review-trigger test:** If source evidence is missing or a defined application rule or evaluator triggers review, `needs_human_review` should be true and `review_reason` should explain why.

A weak plan only tests the happy path. A strong plan tests the contract.

This is the level of evidence a technical stakeholder can use to decide whether the contract is ready for implementation, needs remediation, or requires a deeper review in security, retrieval, tool design, evals, or production readiness.

## Slide 41/53 - Recommended exercise: Turn a contract into verification tests

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice turning a contract into a verification plan.

**Task:** Use the contract you created earlier, or use the support-summary contract from the real-world example, to write success, error, structured-output, and state-behavior tests.

**Estimated time:** 8–10 minutes

**Suggested output and reflection:** Verification section of the Core Interface and API Contract Plan.

**Optional stretch:** Add a test for retry behavior, duplicated requests, or state mismatch.

## Slide 42/53 - Knowledge check

**A team tests a support-summary API contract. One valid request returns all required fields in the expected structure. The contract also says the workflow must handle missing required fields, unauthorized account access, unavailable approved sources, invalid structured output, and stale conversation references when follow-up state is used. What should the Core Interface and API Contract Plan say? Select the strongest answer.**

- "Record the contract as partially verified. Prioritize source-unavailable and invalid-output tests first because permission and state behavior depend on customer systems."
- "Record the success path as verified. Mark the remaining behaviors as implementation risks and assign them to later security, retrieval, and state reviews."
- "Record the output structure as verified. Add a broader eval set later to check summary quality, source relevance, tone, latency, and production readiness."
- **"Record the success path as verified. Add tests for missing fields, unauthorized access, source unavailability, invalid structured output, and stale state where state is in scope."** ✓ Correct

A passing success test proves only the happy path. The plan should record that evidence, then identify which required contract behaviors are still unverified. Missing-field, permission, source-unavailable, structured-output, and state-behavior tests should be added when those behaviors are part of the contract. Broader quality, latency, and production-readiness checks may matter later, but they do not replace verification of the contract's required success and failure behavior.

## Slide 43/53 - Summary

In this module, you learned how to turn API contract requirements into verification tests and evidence.

One successful test does not prove readiness. A strong verification plan includes happy-path tests, error tests, permission tests, structured-output tests, and state-behavior tests where relevant.

State clearly what the evidence proves, what it does not prove, and what still needs review before build, pilot, or deployment.

## Slide 44/53 - Introduction (Module: Complete the Core Interface and API Contract Plan)

Now you'll bring your interface, contract, behavior, error, and verification decisions together into one reviewable handoff artifact.

In this module, you'll complete the Core Interface and API Contract Plan. The goal is not to finalize implementation details. The goal is to make the API interaction clear enough for implementation, testing, documentation, and technical review.

Use the plan to align the customer workflow need, technical design assumptions, validation evidence, and open implementation questions before the work moves into build, review, or handoff.

## Slide 45/53 - Assemble the plan

The Core Interface and API Contract Plan brings together the decisions you have developed across the course.

Your plan should include: workflow requirement; recommended inference interface (Responses API, Chat Completions API, or another validated current inference interface); state approach (stateless or application-managed context, chained Responses, or the Conversations API used with Responses); interface rationale; state and context assumptions; tool, streaming, async, retry, or idempotency assumptions; structured-output requirement; request method, route, headers, authentication assumption, and body; input schema; output schema; error states and status codes; verification tests; open implementation questions.

Use this concise template to assemble the plan:

- **Workflow requirement** — What workflow does this API interaction support?
- **Recommended inference interface** — Which inference interface is the strongest starting point, and why?
- **Interface and state rationale** — How do the inference interface and state approach support workflow, context, tools, structured output, streaming, async, or verification needs?
- **State and context assumptions** — What context must be supplied or retained? What privacy, ownership, or retention questions exist?
- **Tool, streaming, async, retry, or idempotency assumptions** — What behavior assumptions must be visible before implementation?
- **Structured-output requirement** — Which mechanism is planned—Structured Outputs or JSON mode with application validation? What schema and non-schema response paths must be handled?
- **Request contract** — What does the caller send?
- **Response contract** — What does the API return?
- **Error states** — What can go wrong, and what should happen next?
- **Verification tests** — What tests prove the contract behaves as expected?
- **Open implementation questions** — What must be confirmed before build, recommendation, or broader use?

The plan should be useful for handoff. Another technical stakeholder should be able to see what is ready, what is assumed, what is blocked, and what still needs validation by product, security, data, engineering, or customer stakeholders.

## Slide 46/53 - Prepare the plan for handoff

A handoff-ready plan should be clear, concise, and specific enough for other technical stakeholders to use.

It should help implementation, testing, documentation, and review teams understand what has been decided, what is assumed, what still needs validation, and what should happen next.

Use these principles to make the plan easier to review and act on:

- **Keep it concise** — A handoff-ready plan should be detailed enough to guide implementation, but not overloaded with unvalidated implementation details.
- **Use clear field names** — Field names should make sense to another technical stakeholder. Avoid vague names like `output`, `data`, or `result` when the workflow needs specific fields.
- **Use examples** — Examples make the contract easier to test. Include one success example and at least one failure example.
- **Name assumptions** — Mark assumptions clearly. For example: "Assumption: account context will be supplied by the calling application."
- **Avoid unvalidated product details** — Do not hardcode model names, SDK versions, endpoint behavior, pricing, or capability claims unless they have been validated against approved current sources.
- **Identify what must be confirmed** — A plan can still be useful even when some details are unresolved. Name the open questions instead of hiding them.
- **Connect the contract to later technical decisions** — Contract requirements may affect model, capability, latency, cost, output format, security review, retrieval design, tool design, validation, or production-readiness decisions.

For example:

> "The dashboard requires a structured response with low-latency behavior and strict review fields. These contract requirements may affect model and capability selection, structured-output validation, retrieval design, and production monitoring assumptions."

A strong handoff plan gives the next team a clear starting point. A weak handoff plan forces the next team to rediscover basic assumptions during implementation.

## Slide 47/53 - Check product facts and volatile details

API products and interfaces evolve. A strong Core Interface and API Contract Plan separates durable design logic from details that must be validated before implementation.

**Durable design logic includes:** the workflow requirement; the need for structured output; whether state is required; whether tools are required; what request fields are needed; what response fields are needed; what error states must be handled; what tests must prove.

**Volatile details may include:** exact interface names; supported capability combinations; SDK examples; streaming behavior; async behavior; structured-output options; product limits; model names; endpoint behavior; pricing; current availability.

Before scripting or implementation guidance, validate: current interface names; supported capabilities; SDK examples; structured-output options; state behavior; streaming or async behavior; sample schemas; status-code guidance.

Keep volatile product details in updateable notes rather than the durable core course narrative. This keeps the plan accurate and maintainable.

A useful plan statement might say:

> "Recommendation is an interface-planning assumption, not a final implementation claim. Validate current Responses API structured-output and tool behavior in official documentation before build."

Naming validation dependencies makes the plan more credible. It is clearer to state what must be checked in current documentation than to make implementation claims that could become outdated or incorrect.

## Slide 48/53 - Real-world example: Reviewing the plan for implementation readiness

A partner prepares a Core Interface and API Contract Plan for the support-summary workflow.

The plan includes:

- **Recommended interface:** Responses API, pending current documentation validation
- **Rationale:** The workflow needs structured output and possible ticket-status tool use
- **State assumption:** Follow-up continuity may require a stateful pattern
- **Request fields:** `account_id`, `issue_text`, `approved_context_ids`
- **Structured output fields:** `issue_summary`, `urgency`, `recommended_next_action`, `confidence_note`, `needs_human_review`
- **Error states:** missing input, invalid authentication, unauthorized account access, unsupported context, source unavailable, invalid structured output
- **Verification tests:** success, missing field, unauthorized access, source unavailable, structured-output failure, review-trigger behavior
- **Open questions:** current interface support, state behavior, source access, exact schema implementation

This plan is useful because it makes the interface rationale, request shape, response shape, structured-output requirement, error behavior, and verification evidence visible.

It is not a final production design. It does not prove: scale; resilience; security posture; production monitoring; full governance readiness; complete tool implementation; customer legal or compliance approval.

It gives the next technical stakeholders a clear contract to build, review, test, and refine.

The plan helps translate a customer workflow into buildable, reviewable assumptions. It gives technical stakeholders a clearer way to communicate what is known, what is assumed, and what still needs validation before the work moves forward.

## Slide 49/53 - Recommended exercise: Finalize the Core Interface and API Contract Plan

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Consolidate prior interface, contract, schema, error, and verification decisions into a handoff-ready plan.

**Task:** Use the plan sections you developed earlier in the course, or use the support-summary example as your starting point, to finalize the Core Interface and API Contract Plan. Confirm the interface recommendation, rationale, request and response assumptions, structured-output requirements, error states, verification tests, open implementation questions, and next validation step.

**Estimated time:** 8–10 minutes

**Suggested output and reflection:** A finalized Core Interface and API Contract Plan that supports implementation, testing, documentation, and handoff.

**Optional stretch:** Sketch an OpenAPI-style schema for the endpoint at a lightweight level. Do not require full OpenAPI authoring or tooling in this course.

## Slide 50/53 - Knowledge check

**Which Core Interface and API Contract Plan is strongest for handoff?**

- Use the Conversations API as the inference interface for any support workflow where follow-up questions might happen.
- Use Responses API to summarize support cases; the dashboard can define fields later.
- **Use the Responses API, pending validation, with a defined state approach, schema behavior, errors, tests, and open questions.** ✓ Correct
- Use the current chatbot interface; the build team can define errors during implementation.

This is the strongest plan because it separates the inference interface from state design, defines what the API should receive and return, includes schema and non-schema failure behavior, and names what still needs validation before handoff.

## Slide 51/53 - Summary

In this module, you finalized a Core Interface and API Contract Plan for handoff. A defensible plan should explain the interface recommendation, define the contract clearly, show how behavior will be verified, and identify open product, implementation, or governance questions before the work moves forward.

The finished plan should be practical enough to support architecture review, implementation planning, technical alignment, and delivery handoff.

## Slide 52/53 - Recap

In this course, you compared the Responses API and Chat Completions API as inference interfaces, examined the Conversations API as persistent state infrastructure used with Responses, and considered how interface and state choices affect context, tools, structured outputs, errors, retries, and verification.

You also practiced turning a workflow requirement into a Core Interface and API Contract Plan. This plan defines what the API should receive, what it should return, how failures should be handled, and what evidence is needed to verify the interaction.

The main takeaway is to make interface and contract decisions clear before implementation begins. Clear contracts reduce ambiguity, improve testing, and make handoff easier.

## Slide 53/53 - Congratulations

Congratulations, you've completed this course!

You can now use a Core Interface and API Contract Plan to make interface and contract assumptions visible before technical decisions are finalized.

A clear API contract does not replace engineering judgment, current product documentation, security review, or production-readiness work. It gives those stakeholders a clearer starting point by defining the API interaction, assumptions, expected behavior, and verification evidence.

Use this plan to support better API design, testing, documentation, and handoff.
