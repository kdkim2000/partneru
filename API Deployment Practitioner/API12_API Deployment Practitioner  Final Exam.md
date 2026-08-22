# API Deployment Practitioner - Final Exam

## Slide 1/2 - Title

API Deployment Practitioner - Final Exam

## Slide 2/2 - Assessment

This is a multi-question final assessment covering the API Deployment Practitioner pathway.

**Question 1:** What evidence best proves that a minimal local API works?

- A project plan with no executed tests
- A model-generated description of the API
- **Successful and failed request tests showing the expected status codes and response bodies** ✓ Correct
- A screenshot of the code editor

Working evidence comes from running the API and verifying both normal and error behavior. A code listing or plan alone does not prove runtime behavior.

*[Source: API Deployment Foundations]*

**Question 2:** Why should authentication examples use safe placeholders instead of real secrets?

- To avoid testing error cases
- To make the API respond faster
- **To prevent credentials from being exposed in code, documentation, or evidence** ✓ Correct
- To eliminate authorization checks

API keys and other secrets must be handled through controlled mechanisms. Examples and evidence should prove the pattern without leaking usable credentials.

*[Source: API Deployment Foundations]*

**Question 3:** What is the strongest starting point for an API solution architecture?

- A preferred model name
- A list of every available API feature
- A complex reference architecture copied from another customer
- **The customer problem, workflow, desired outcome, boundaries, and constraints** ✓ Correct

Architecture decisions should follow the work the solution must support. Clear boundaries and constraints help the team choose the minimum useful pattern and identify open decisions.

*[Source: API Solution Architecture]*

**Question 4:** Why should an architecture brief include what the solution will not do?

- To guarantee that requirements never change
- To remove the need for testing
- **To make scope and assumptions explicit and prevent unsupported expansion** ✓ Correct
- To avoid defining success

Exclusions are part of a usable boundary. They help stakeholders distinguish current scope from future possibilities and identify items that require validation.

*[Source: API Solution Architecture]*

**Question 5:** What should determine the choice of inference interface and state approach for an API workflow?

- **Workflow needs for state, tools, streaming, asynchronous behavior, and output structure** ✓ Correct
- The interface with the longest name
- Alphabetical order
- A rule that every new solution must use the same interface

Responses API and Chat Completions are inference interfaces; Conversations can provide persistent state when used with Responses. Choose the inference interface first, then the state approach, based on workflow and contract needs.

*[Source: API Contracts and Core Interfaces]*

**Question 6:** What belongs in an API contract?

- Only the user-interface design
- Only the model name
- A guarantee that the service will never fail
- **Request fields, response shape, authentication assumptions, structured-output requirements, and error behavior** ✓ Correct

A contract makes expected interaction testable for implementers and consumers. It includes normal behavior and defined failure behavior.

*[Source: API Contracts and Core Interfaces]*

**Question 7:** What should happen before selecting a model or advanced capability?

- Skip requirements and optimize after launch
- Add an agent to every workflow
- Select the most expensive model
- **Define the task, modality, context, quality, latency, cost, scale, safety, and review requirements** ✓ Correct

Capability selection is a requirements decision. Clear criteria allow the team to compare simpler and more complex patterns and validate the recommendation.

*[Source: Model and Capability Selection for API Solutions]*

**Question 8:** A team proposes Deep Research, image generation, or model optimization for a workflow that a simple API call may already satisfy. What should it do first?

- **Confirm that the specialized pattern solves a real workflow need and that its evidence, risks, tradeoffs, and validation burden are justified** ✓ Correct
- Skip simpler alternatives because they are less impressive
- Launch all three patterns and let users decide
- Select the most advanced pattern to avoid future redesign

Specialized patterns should be chosen only when the workflow and evidence justify their added complexity. Teams should compare simpler options and define source, rights, safety, review, and validation requirements before proceeding.

*[Source: Deep Research, Images, Distillation, and Specialized API Pattern Fit]*

**Question 9:** What is the difference between authentication and authorization?

- Authorization always happens before identity is known
- They are two names for encryption
- Authentication defines output schemas; authorization measures latency
- **Authentication verifies identity; authorization determines permitted actions or resources** ✓ Correct

Secure APIs must establish who or what is making a request and what that identity is allowed to do. Both should be designed with least privilege.

*[Source: API Security, Data Handling, and Access Controls]*

**Question 10:** Why is data minimization important?

- It guarantees perfect model accuracy
- It means all API responses must be short
- **It limits collection and processing to the data needed for the approved workflow** ✓ Correct
- It removes the need for access controls

Data minimization reduces unnecessary exposure and helps align processing, logging, and retention with the solution's purpose.

*[Source: API Security, Data Handling, and Access Controls]*

**Question 11:** When is retrieval the right pattern?

- **When the workflow needs current or domain knowledge from approved sources that the model should access at request time** ✓ Correct
- When no authoritative sources exist
- When permission boundaries should be ignored
- When a model-only answer already meets the need reliably

Retrieval is justified by a knowledge-access requirement. A model-only or structured-output pattern may be sufficient when no external source is needed.

*[Source: Context, Data, and Retrieval for Grounded API Solutions]*

**Question 12:** What should a team test in a retrieval-grounded solution?

- **Missing, conflicting, outdated, unauthorized, and irrelevant sources plus unsupported output claims** ✓ Correct
- Only the user-interface colour
- Only the average response length
- Only whether any text is returned

Retrieval quality depends on source readiness, permissions, search behavior, and grounded generation. Tests must cover important failure modes as well as successful queries.

*[Source: Context, Data, and Retrieval for Grounded API Solutions]*

**Question 13:** When should an API workflow call a tool?

- To avoid defining an input schema
- When no system owner exists
- Whenever the prompt contains more than one sentence
- **When the workflow needs controlled access to external data or an action that the model cannot perform by text generation alone** ✓ Correct

Tool use should serve a specific system interaction. The tool contract must define purpose, inputs, outputs, permissions, validation, and errors.

*[Source: Tool Use, Actions, and Agentic API Workflows]*

**Question 14:** What is the safest rule for choosing between a model-only, tool-calling, and agentic pattern?

- **Choose the simplest pattern that can complete the approved workflow safely and reliably** ✓ Correct
- Let the model expand its own permissions
- Use unrestricted tools to reduce design work
- Always choose the agentic pattern

More autonomy increases control and validation burden. The workflow should become agentic only when multi-step goals, state, handoffs, or cross-system actions justify it.

*[Source: Tool Use, Actions, and Agentic API Workflows]*

**Question 15:** What makes an eval useful as a release gate?

- **It uses representative success, edge, misuse, and failure cases with explicit pass criteria** ✓ Correct
- It asks reviewers whether they like the model
- It contains one impressive example
- It tests only the happy path

A release gate needs repeatable evidence about expected behavior and important risks. Test coverage and criteria should connect directly to the workflow.

*[Source: Prompt Design, Evals, Moderation, Guardrails, and Human Review]*

**Question 16:** When should human review be triggered?

- **When the output or proposed action is high impact, uncertain, policy-sensitive, or outside an approved boundary** ✓ Correct
- After every harmless formatting change
- Never if a guardrail exists
- Only when the API returns a server error

Human review is a targeted control. It should focus attention where errors or actions have meaningful consequences and where judgment or approval is required.

*[Source: Prompt Design, Evals, Moderation, Guardrails, and Human Review]*

**Question 17:** Which signals are core to API observability?

- Only model output length
- **Health, availability, usage, latency, errors, logs, traces, and alerts with named review ownership** ✓ Correct
- Only monthly cost
- Only user sign-ins

Observability helps teams understand service behavior, diagnose failures, and respond. Signals need owners and an incident route to become operationally useful.

*[Source: DevOps, Observability, and Production Readiness for APIs]*

**Question 18:** What should a production-readiness plan include for failure handling?

- **Known failure modes, response actions, graceful degradation, rollback, escalation, and support ownership** ✓ Correct
- A promise that failures will not occur
- No customer communication path
- Automatic retries without limits

Production systems need a defined response when dependencies, models, data, or infrastructure fail. The plan should protect users and make recovery accountable.

*[Source: DevOps, Observability, and Production Readiness for APIs]*

**Question 19:** When is a realtime, voice, image, or multimodal pattern justified?

- Whenever a non-text feature is available
- **When the user and workflow need that modality and the team can meet latency, consent, accessibility, privacy, fallback, and safety requirements** ✓ Correct
- When a text workflow already fully meets the need
- Before the interaction flow is defined

Modality should follow the workflow, not novelty. Non-text experiences add interaction and operational considerations that must be designed and tested.

*[Source: Realtime, Voice, and Multimodal API Experiences]*

**Question 20:** A deployment case has unresolved access controls, incomplete eval evidence, and no incident owner. What is the strongest recommendation?

- Add more features before reviewing readiness
- Release immediately because the prototype works
- Remove the gaps from the documentation
- **Remediate the gaps before release, with named owners and evidence requirements for each blocker** ✓ Correct

Unresolved access controls, incomplete eval evidence, and missing incident ownership are release blockers. The strongest recommendation is to remediate them before release and name the evidence and owners needed to change that decision.

*[Source: API Deployment Practice Application]*
