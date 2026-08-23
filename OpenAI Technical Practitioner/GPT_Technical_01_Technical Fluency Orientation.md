# Technical Fluency Orientation

## Slide 1/37 - Title

Technical Fluency Orientation

Created July 2026

## Slide 2/37 - Introduction

Technical fluency helps you move from product familiarity to practical solution judgment. It helps you connect customer workflows to credible solution paths, ask better implementation questions, recognize tradeoffs earlier, and know when a specialist needs to validate the next step.

This course is not a product deep dive. You will not leave as an expert in every OpenAI product, model, architecture pattern, or governance control. You will instead leave with a practical orientation: Enough judgment to ask better questions, make a credible early route, and avoid overclaiming.

The central question for this course is: How do I route a technical opportunity responsibly before I over-design it, overclaim it, or hand it to the wrong team?

## Slide 3/37 - What you'll learn

By the end of this course, you'll be able to:

- Explain how technical fluency and computational thinking support partner solution work.
- Distinguish product familiarity from practical technical judgment.
- Use a three-axis routing model to distinguish the user or product surface, the required capability or architecture, and the deployment and operating approach.
- Identify the baseline concepts that shape solution routing, including context, data flow, runtime, tools, evals, governance, and observability.
- Ask stronger early technical questions before solution design or handoff.
- Create a role-specific Technical Fluency Navigator for future customer or implementation conversations.

## Slide 4/37 - What you'll produce

Near the end of this course, you will have the optional opportunity to start a lightweight Technical Fluency Navigator.

Your Navigator is a lightweight thinking aid you can use before customer conversations, solution reviews, technical discovery sessions, or implementation handoffs. It's comprised of role considerations, early routing cues, discovery questions and escalation signals.

You will optionally create your own Navigator further into this course and can then reuse or expand it whenever you prepare for future customer or implementation conversations.

Let's get started!

## Slide 5/37 - Introduction (Module: Map the technical solution landscape)

Before you can route a technical opportunity, you need a practical map of the decisions that shape a solution.

This module introduces a three-axis routing model for deciding a technical OpenAI solution at orientation depth. The goal is not to learn every feature. The goal is to separate where the work happens, what the system must do, and how it will run and be controlled.

The key question to think about is: What user or product surface, capability or architecture, and deployment and operating approach are most plausible for this workflow?

## Slide 6/37 - Why technical fluency matters

Before you can map your own technical solution landscape, you need to understand why technical fluency matters in the first place.

Technical fluency is important because many customer conversations start with a broad request. You might hear: "We want an AI assistant for our operations team.", "Can we automate this workflow?", or "Should this be in ChatGPT or built with the API?"

A product-aware response may jump straight to a feature, product surface, or model name.

But a more technically fluent response slows down just enough to understand the workflow, data, users, constraints, risks, and success criteria.

- **Product familiarity:** Means knowing what OpenAI products are called and what they can generally do.
- **Practical technical judgment:** Means knowing which questions determine fit, which tradeoffs matter, and what must be validated before a recommendation becomes credible.
- **Computational thinking:** Means logical step-by-step understanding of a problem, what information is needed, what data we have access to, and weighing up different options available - picking the most appropriate.

Use this comparison to show the difference between knowing product names and applying technical judgment in a customer conversation.

Visual diagram: Product familiarity (naming relevant products, naming relevant features) sits above Practical technical judgment (users, data → workflow → consider: constraints, risks, success criteria, tradeoffs, validation needs, escalation points).

## Slide 7/37 - Three decision axes for early technical judgment

Before you compare possible solutions, separate three decisions that are often blurred together. Use these axes to organize early technical judgment.

- **User or product surface:** Where will the person or workflow primarily operate? At orientation depth, the main starting surfaces are ChatGPT, Codex, and an application or process built with the API. Within ChatGPT, Chat supports collaborative thinking and creation, while Work supports delegated knowledge work.
- **Capability or architecture:** What must the system do? Examples include Apps and tools, Workspace Agents, retrieval, structured outputs, code execution, and automation.
- **Deployment and operations:** Where and how will the solution run and be controlled? Consider local or cloud operation, hosted or embedded experiences, identity, permissions, approvals, retention, logging, human review, and whether a customer-run open-weight model needs evaluation.

A technically fluent conversation asks:

- Where will the person or workflow primarily operate?
- What must the system do?
- Where and how will it run and be controlled?

Use the three axes to keep product surfaces, capabilities, and deployment choices distinct while you build one coherent route.

These axes help you avoid jumping straight to a product name. They keep the conversation focused on where the work should happen, what the system must do, and how it will be operated and controlled.

## Slide 8/37 - Start with the workflow, not the product

An effective route separates three decisions rather than treating products, capabilities, and deployment choices as peers.

A customer need rarely maps to a single product or path. The same business outcome may combine ChatGPT or Codex, an application or process built with the API, one or more capabilities, and an operating model. A combined solution is the result of decisions you make across the axes—not a separate peer route.

Start with the workflow, then make a preliminary decision on each axis before comparing fit, readiness, and escalation signals.

Use the table below to map the workflow across all three axes. Within the ChatGPT surface, distinguish Chat for collaborative work from Work for delegated knowledge work; keep Codex for software engineering and the API for embedded or custom experiences.

Treat the combined route as a starting hypothesis until the workflow, capability needs, deployment constraints, operating controls, and success criteria are clear.

- **User or product surface** — Correct question: Where will the person or workflow primarily operate? — Orientation examples: ChatGPT Chat or Work; Codex; an application or process built with the API
- **Capability or architecture** — Correct question: What must the system do? — Orientation examples: Apps and tools; Workspace Agents; retrieval; structured outputs; code execution; automation
- **Deployment and operations** — Correct question: Where and how will it run and be controlled? — Orientation examples: Local or cloud; hosted or embedded; identity; permissions; approvals; retention; logging; human review; customer-run open-weight model evaluation where relevant

## Slide 9/37 - Recognize early fit signals

Use fit signals to decide where the technical conversation should start.

Early fit signals are clues in the customer's workflow—not final recommendations. Use them to identify a plausible starting point on each routing axis decision.

The goal is not to solve the architecture in the first few minutes. Listen for where the work should happen, what the system must do, and which operating constraints could change the route.

These are fit signal examples for each OpenAI solution:

**Surface fit signals**

- ChatGPT Chat: The user needs to explore, draft, critique, or refine interactively.
- ChatGPT Work: The user can define an outcome, context, constraints, approval boundaries, and a review standard for delegated knowledge work.
- Codex: The work centers on software engineering, repositories, tests, review, debugging, or documentation.
- Application or process built with the API: Intelligence must be embedded into a product, system, workflow, or custom experience.

**Capability or architecture fit signals**

The workflow needs approved context, retrieval, structured output, code execution, tools, actions, automation, or agentic coordination.

**Deployment and operations fit signals**

- Identity, permissions, approvals, retention, logging, human review, hosting, or operating ownership could change the recommendation.
- A customer-run open-weight model is being considered because of a specific deployment requirement—not simply because the data is sensitive.

## Slide 10/37 - Avoid common routing mistakes

Early routing mistakes usually happen when teams pick a solution path before they understand the workflow.

This can happen when a familiar product or capability becomes the default answer: "Use ChatGPT," "build it with the API," "make it agentic," or "try Codex." Any of these may be relevant, but they answer different kinds of questions and should follow discovery.

Watch for these patterns:

- Treating ChatGPT, Codex, the API, agentic capabilities, open-weight models, and combined designs as one list of equivalent routes.
- Selecting ChatGPT without distinguishing collaborative Chat from delegated Work.
- Treating agents or automation as a product surface rather than a capability or architecture choice.
- Treating an open-weight model as a user surface rather than a model and deployment decision.
- Choosing a surface before defining the required context, tools, actions, and output.
- Ignoring permissions, approvals, retention, logging, human review, or operating ownership until late.
- Calling a combined solution "hybrid" without explaining the decision on each axis.

Instead of immediately routing to a specific product, ask: What workflow are we solving, where should the person or process operate, what must the system do, and how will it be controlled?

## Slide 11/37 - Recommended exercise: Real-world signal sort

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Practice using early customer signals to identify a plausible starting solution path without treating that route as a final recommendation.

**Task:** Review the customer signals below. For each one, write: the most plausible user or product surface (ChatGPT Chat, ChatGPT Work, Codex, or an application or process built with the API); one capability or architecture the workflow may require; one deployment and operations question that could change the recommendation.

A scenario may not determine all three axes. Record what is unknown rather than forcing a route.

Customer signals:

- "Our analysts need faster ways to summarize internal policies and draft decision notes."
- "We want AI-generated responses inside our customer support product."
- "Our engineering teams lose time on review prep, tests, debugging, and documentation."
- "We want a system that checks records, drafts a response, asks for approval, and updates a ticket."
- "We have strict hosting requirements and want to evaluate model options inside our own infrastructure."

Suggested output or reflection: Your own three-axis routing notes for the customer signals.

Estimated time: 5 minutes.

## Slide 12/37 - Knowledge check

**Question:** Match each customer need to the strongest preliminary routing cue.

- Permissions, approvals, logging, retention, and human review → **Deployment and operations decision** ✓ Correct
- Retrieval, structured output, tool use, or automation → **Capability or architecture decision** ✓ Correct
- Delegated creation of a review-ready policy brief from approved sources → **ChatGPT Work** ✓ Correct
- Interactive policy Q&A and drafting with the user closely involved → **ChatGPT Chat** ✓ Correct
- Tests, documentation, and pull-request support → **Codex** ✓ Correct
- AI-generated output inside a customer-facing product → **Application or process built with the API** ✓ Correct

All pairs matched correctly!

## Slide 13/37 - Summary

Technical routing starts with the workflow—not a list of products.

Separate three decisions: where the person or workflow will operate, what the system must do, and how it will run and be controlled.

Your combined route is a hypothesis to test—not a solution to defend.

## Slide 14/37 - Introduction (Module: Build the baseline technical mental model)

Technical fluency improves when you have a simple mental model for how AI solutions work inside real workflows.

This module introduces four discovery layers—user or workflow, context and data, runtime and tools, and governance and observability. Use them to gather evidence within the three-axis routing model, not as a replacement list of product routes.

The key question to think about is: Which discovery layer is least clear, and how could that uncertainty affect the surface, capability, or deployment and operations decision?

## Slide 15/37 - Four layers for early technical judgment

In early customer conversations, the question is rarely just, "Which product should we use?" Before recommending a solution, it helps to understand the people involved, the information required, how the work will happen, and what will be needed to manage the outcome over time.

One way to organize that thinking is through four baseline layers:

1. **User or workflow:** Who needs help? What work is being done? What output is required? What is the specific business problem? Is it repeatable or a one-off?
2. **Context and data:** What does the AI need to know, retrieve, access, or respect? Do we have representative, current, and usable data? Labels are target annotations used for a defined task; data cleanliness, completeness, and formatting are separate quality dimensions.
3. **Runtime and tools:** Where does the work happen? Which systems or tools are used? What actions are allowed?
4. **Governance and observability:** How will the organization monitor, control, evaluate, and improve the solution?

These layers help you avoid incomplete recommendations. They're designed as practical thinking tools, not architecture jargon. They'll also help you ask better questions before a solution path becomes a recommendation.

These discovery layers support the three routing axes: they help you identify the likely surface, required capabilities, and deployment or operating controls without treating those decisions as peers.

## Slide 16/37 - APIs, applications, and workflows

At a high level, an API allows one software system to communicate with another.

In simple terms, an application sends a request: the information, instruction, and parameters the AI service needs. The service returns a response: the output the application can display, store, route, or pass to another system.

At this orientation depth, you do not need to design the API call.

You need to recognize when this request-response pattern is needed because AI must operate inside another system or workflow.

This is important because many AI opportunities are not simply about giving employees a place to interact with AI directly.

Instead, the goal is often to embed AI into an existing product, application, business process, or customer experience.

When this happens, the AI may operate largely behind the scenes. The user may not even realize that AI is involved.

A system collects information, sends it to an OpenAI-powered service, receives a response, and then uses that response as part of the workflow.

For example, imagine a customer support platform. When a support ticket is created, the system could send the ticket details, account information, and relevant knowledge-base content to an OpenAI-powered backend. The AI might generate a draft response, identify the likely issue category, or suggest next actions. The result is then presented to the support agent, who reviews and decides what to send to the customer.

A similar pattern appears in many business workflows:

- A customer onboarding system generates personalized onboarding plans.
- A document-management system extracts key information from contracts.
- A CRM system prepares account summaries before customer meetings.
- A compliance platform reviews documents and flags potential exceptions.
- A customer-facing application provides intelligent recommendations or guidance.

In each case, the AI is supporting the workflow from within an existing system rather than through a standalone chat interface.

You do not need to understand how to build or design APIs in this course. At this stage, it is enough to recognize when a customer needs AI embedded into a product or workflow rather than accessed directly by employees.

A useful question to ask is: "Does the user need to work directly with AI, or does another system need to use AI as part of a larger workflow?"

The answer often helps determine whether the conversation should begin with ChatGPT, the API, or a combination of both.

## Slide 17/37 - Context shapes quality

AI quality depends heavily on context. Context is the information the AI uses to understand the task, the user's intent, the business situation, and any constraints around the work.

It may include:

- User-provided details
- Retrieved knowledge
- Connected systems
- Files and documents
- Structured data
- Tool outputs
- Policies and operating rules
- Permissions and access boundaries

A useful technical question to remember is: "What information does the system need, where does it come from, who is allowed to access it, and how will accuracy be checked?"

Even a powerful AI model can produce poor results if it is working with the wrong information.

A solution that lacks the right context may sound convincing but still provide inaccurate answers, use outdated information, reference the wrong policy, or miss important business requirements.

For example, imagine an HR assistant answering employee questions. If the assistant only has access to public company information and not the latest HR policies, it may provide answers that are incomplete or outdated.

Similarly, a customer-support assistant may perform poorly if it cannot access current product documentation, account information, or recent support history. The model itself may be capable, but it is missing the context needed to answer correctly.

A finance team might ask AI to prepare a risk-review summary. If the system cannot access the relevant customer documents, policy requirements, or committee guidelines, the output may omit critical information needed for decision-making.

This is why strong technical conversations focus not only on what the AI should do, but also on where the information will come from and how it will stay accurate over time.

For example:

- A policy assistant may need approved policy documents, clear user permissions, and a review process for sensitive questions.
- A support assistant may need access to product documentation, ticket history, and customer account information.
- A sales-preparation assistant may need CRM records, call notes, account plans, and renewal history.
- A contract-review workflow may need access to approved templates, legal guidance, and relevant contract documents.

In each case, the quality of the outcome depends heavily on the quality of the context.

A stronger technical conversation asks:

- Where will the information come from?
- How will it stay current?
- Who is allowed to access it?
- How will the output be reviewed or validated?

The goal is not simply to give AI more information. The goal is to provide the right information, from the right sources, to the right users, in a way that supports trustworthy results.

## Slide 18/37 - Evals and guardrails matter early

The gap between a demo that worked once and a system you can deploy with confidence is whether you define "good" and "consistent" before trusting the output.

This is why evals and guardrails belong at the start, not bolted on after the first failure - or worse, as part of a customer service recovery after it silently fails for multiple calls.

**Evals:** Structured ways to test whether an AI-supported solution behaves as expected. A simple eval might check whether the system gives complete answers, follows the required format, uses the right source material, avoids unsupported claims, or handles edge cases appropriately. In a customer-facing workflow, evals may also test whether outputs are accurate enough, consistent enough, and safe enough before they reach users.

**Guardrails:** Controls that shape how the system behaves. They help define what the system can do, what it should not do, what kind of output it should produce, and when it should refuse, escalate, or ask for human review. Guardrails may also relate to data access, tool use, output format, approval rules, policy boundaries, or human oversight.

While you don't need to design evals or guardrails in this course, you do need to recognize that they are not late-stage add-ons.

Start evaluation with representative, labeled examples that reflect the workflow and expected outcomes. Labels are target annotations—not a measure of cleanliness. Any training or fine-tuning decision requires a separate, use-case-specific data strategy and specialist validation.

They influence:

- Which solution path is credible.
- Whether the workflow can be safely tested.
- What confidence is needed before launch.
- What evidence specialists need before deeper design.
- Whether the customer is ready to scale beyond a pilot.

## Slide 19/37 - Recommended exercise: Spot the assumptions before you recommend a path

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Practice using the baseline technical mental model to identify what you know, what you are assuming, and what you would need to clarify before making an early technical recommendation.

**Task:** Use this sanitized workflow example: "A customer wants AI to help field teams prepare for customer meetings faster."

Before identifying a route, pause and reflect on the request through the four discovery layers. Which layer is least clear? What is one question you would ask next before identifying a likely user or product surface, capability or architecture, and deployment and operating approach?

The four technical layers are:

- **User or workflow:** Who would use this, what work are they trying to complete, and what would a good output look like?
- **Context and data:** What information would the AI need? Where might that information come from? What access, permission, or accuracy questions would you need to ask?
- **Runtime and tools:** Where might the work happen? Would the AI only help the user reason and draft, or would it need to use tools, retrieve information, update systems, or trigger actions?
- **Governance and observability:** What would need to be reviewed, monitored, approved, or escalated before this workflow could be trusted in a customer environment?

**Estimated time:** 6–8 minutes

Suggested output and reflection: Write a reflection with one short sentence for each layer. End with one of these statements: "I would not recommend a path yet because…", "The first thing I would validate is…", or "The assumption I would be most careful about is…"

## Slide 20/37 - Knowledge check

**Question:** Match each question to the discovery layer or routing axis it belongs to.

- "Where and how will it run and be controlled?" → **Deployment and operations decision** ✓ Correct
- "Which records can it access?" → **Context and data discovery layer** ✓ Correct
- "Can it update a ticket?" → **Runtime and tools discovery layer** ✓ Correct
- "How will failures be monitored?" → **Governance and observability discovery layer** ✓ Correct
- "What must the system do?" → **Capability or architecture decision** ✓ Correct
- "Where will the person or workflow primarily operate?" → **User or product surface decision** ✓ Correct
- "Who will use the assistant?" → **User or workflow discovery layer** ✓ Correct

All pairs matched correctly!

## Slide 21/37 - Summary

Strong technical discovery separates evidence-gathering from routing.

Use the four discovery layers to understand the workflow, context, tools, actions, controls, and evidence. Then use the three routing axes to identify the likely surface, capability or architecture, and deployment and operating approach.

When any layer or axis is unclear, ask a better question before strengthening the recommendation.

## Slide 22/37 - Introduction (Module: Use technical judgment to route, validate, and escalate)

Technical fluency is useful only if it improves the quality of decisions.

In this module, you'll learn how to approach technical conversations with confidence. You'll practice identifying likely solution options, understanding the tradeoffs involved, and knowing when more information or specialist support is needed.

The key question to think about is: What can I confidently recommend today, and what still needs to be validated before the solution can move forward?

## Slide 23/37 - Separate recommendation from validation

Early technical conversations often require you to say something useful before every detail is known. That is normal. The risk is sounding more certain than the evidence allows.

A technically fluent partner can make a useful recommendation while still being honest about what remains unknown. This means separating a likely starting direction from a fully validated solution.

Think about three levels of confidence:

- **Level 1: Preliminary solution path recommendation** — A likely starting direction based on what is currently known.
- **Level 2: Validated architecture recommendation** — A solution that has been reviewed in more detail, with key technical assumptions validated.
- **Level 3: Deployment-ready implementation plan** — A solution that is ready for implementation, with requirements, approvals, integrations, and operational details defined.

In most early customer conversations, your focus should be on Level 1.

For example, imagine a customer explaining that support agents spend too much time searching across multiple knowledge sources before responding to customers.

Based on that information, you might say: "This appears to be an employee-facing knowledge workflow, so ChatGPT looks like a reasonable starting direction. Before confirming that recommendation, we would want to understand where the information lives, how agents access it today, and whether there are any security or approval requirements that affect the workflow."

Notice what happened: the partner made a recommendation, but they did not claim that the solution was fully designed. They explained their reasoning and identified what still needs validation.

Similarly, if a customer wants AI embedded into a customer-facing application, you might say: "This may point toward an API-based solution because the AI needs to operate inside an existing product experience. Before confirming that path, we would need to understand the application architecture, data requirements, user experience expectations, and any integration constraints."

In both examples, the partner provides a useful direction without overstating certainty.

That is the goal of Level 1 thinking: identify the most likely starting path, explain why it appears relevant, and clearly state what still needs to be validated before moving forward.

## Slide 24/37 - Tradeoffs that shape decisions

Technical recommendations often involve tradeoffs. A tradeoff is simply a choice between competing priorities. Improving one thing may make another thing more difficult, expensive, or complex.

For example, a solution that is quick to launch may offer less customization. A highly tailored solution may provide more control, but require more implementation effort.

A workflow with more automation may reduce manual work, but increase the need for monitoring, approvals, and exception handling.

Consider a customer who wants AI to help support agents answer questions faster. One option might be to start with ChatGPT because it can be deployed quickly and allows teams to begin testing workflows. Another option might be to build a deeper integration into the support platform. That could create a more seamless experience for agents, but would require additional technical work, integration planning, and ongoing support.

Neither option is automatically right or wrong. The best choice depends on the customer's priorities.

As you evaluate opportunities, listen for the tradeoffs that could change the route. Some tradeoffs are about how the solution is experienced:

- **Speed versus control:** How quickly does the customer want to move? How much customization, governance, or operational control do they need?
- **Quality versus cost/responsiveness:** How accurate, consistent, or deeply reasoned do outputs need to be? What cost, latency, or performance constraints apply?
- **Automation versus oversight:** What should the AI do independently, and where should people review, approve, or intervene?
- **Simplicity versus integration depth:** Can the workflow be supported in an existing interface, or does it require deeper connections to systems, tools, data sources, or business processes?

Other tradeoffs are about whether the solution can be operated responsibly:

- **Data access and security:** What data does the solution need, who can access it, and what security or privacy requirements apply?
- **Governance and reliability:** How will the customer make sure the solution behaves consistently, follows policy, and can be monitored or audited?
- **Maintainability and ownership:** Who will maintain the solution after launch, update instructions or integrations, monitor performance, and respond when something changes?
- **Implementation maturity:** Does the customer have the technical environment, ownership model, and operational readiness to support the path they are considering?

You do not need to resolve every tradeoff in this course. At this stage, your job is to notice which tradeoffs could affect the route and name what needs validation before the recommendation becomes stronger.

For example, instead of saying: "This is definitely the right solution." A stronger response might be: "This appears to be a reasonable starting path, but we still need to validate the integration requirements and approval process."

That approach allows you to provide useful guidance without making claims that the evidence does not yet support.

## Slide 25/37 - Know when to involve specialists

In early technical conversations, you are not expected to answer every detailed technical question yourself.

Your role is to identify likely solution paths, recognize where additional validation is needed, and involve the right people when the conversation reaches areas that require deeper expertise.

A good rule of thumb is to involve specialists when the opportunity introduces significant uncertainty, technical complexity, or requirements that need expert review.

Some common situations include:

- **Data and compliance considerations:** Bring in specialists when the workflow may involve sensitive data, regulated information, data residency requirements, customer privacy concerns, or unclear data ownership.
- **System and action considerations:** Bring in specialists when the AI may access production systems, update records, trigger actions, send customer-facing communications, or influence important business decisions.
- **Security and permission considerations:** Bring in specialists when identity management, permissions, access controls, approval rules, audit requirements, or tool boundaries need to be defined.
- **Architecture and integration considerations:** Bring in specialists when the solution depends on complex integrations, retrieval systems, grounding strategies, custom application design, agentic workflows, or unclear implementation ownership.
- **Product or policy questions:** Bring in specialists when customers ask about product behavior, availability, roadmap, security, privacy, compliance, or policy details that require authoritative confirmation.

For example, imagine a customer wants an AI assistant that can retrieve customer information, update records in multiple systems, and automatically send follow-up emails.

At a high level, you may be able to identify this as an agentic workflow. However, questions about permissions, approvals, system access, audit requirements, and operational controls would likely require deeper technical review.

A useful response might be: "This looks like a promising direction, but we should validate the system access, approval requirements, and security controls with the appropriate specialists before finalizing the recommendation."

## Slide 26/37 - Real-world example: from vague request to technical route

A customer says: "We want an AI assistant for our operations team."

At first, this sounds like a clear request. But it could point to several different solution paths.

A weak response would be: "Use ChatGPT" or "Build an agent." Both responses move too quickly. They name a solution before the workflow is understood.

A stronger response would be: "That could mean a few different things. Let's clarify how the operations team would use it."

The partner might then ask:

- "Which operations workflow are you trying to improve?"
- "Who would use the assistant day to day?"
- "What information would the assistant need?"
- "Should it only answer questions, or should it take action?"
- "Which systems are involved?"
- "Which outputs would need review or approval?"
- "What data, security, or governance requirements should we understand?"

As the conversation continues, the route becomes clearer across the three axes.

If the operations team needs to explore, summarize, or draft interactively, ChatGPT Chat may be the most plausible surface. If the team can define an outcome, context, constraints, and a review standard for delegated knowledge work, ChatGPT Work may be more appropriate.

If intelligence must be embedded inside an operations platform, an application or process built with the API may be the plausible surface. Retrieval, tools, approvals, or automation are then capability and architecture decisions—not separate product routes.

Deployment and operations still need validation, including data access, permissions, hosting, approvals, logging, human review, and ownership.

A credible early recommendation might sound like: "Based on what we know so far, ChatGPT Chat or Work may be a plausible surface if employees will perform the work directly in ChatGPT. An application or process built with the API may be more appropriate if the work must happen inside the operations platform. Before recommending a design, we should validate the required capabilities and the deployment and operating controls."

This response is stronger because it does not pretend the answer is obvious. It gives the customer a useful starting direction while making clear what still needs to be validated.

## Slide 27/37 - Recommended exercise: Make a recommendation without overclaiming

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Practice turning an early customer signal into a useful Level 1 recommendation that names a likely starting path, identifies a tradeoff, and makes clear what still needs validation.

**Task:** Review this sanitized customer request: "We want AI to help our customer success team spot renewal risks, prepare account summaries, recommend follow-up actions, and update CRM notes after review."

Before making a recommendation, write a short response using the prompts below.

- **User or product surface:** Where should the person or workflow primarily operate: ChatGPT Chat, ChatGPT Work, Codex, or an application or process built with the API? Why?
- **Capability or architecture:** What must the system do—for example, retrieve approved context, produce structured output, use tools, coordinate approvals, or automate steps?
- **Deployment and operations:** What must be validated about identity, permissions, hosting, CRM write-backs, approvals, logging, retention, human review, ownership, or support?
- **Tradeoff and escalation:** Which tradeoff could change the recommendation, and which specialist should validate it?

**Estimated time:** 5–7 minutes

Suggested output and reflection: Write a three- to four-sentence response you could say in an early customer conversation. Use this structure: "Based on what we know, ___ is the most plausible surface because ___. The workflow may require ___ as a capability or architecture choice. Before recommending a design, we should validate ___ in deployment and operations. I would involve ___ to confirm ___."

## Slide 28/37 - Knowledge check

**Question:** A customer says: "We want AI to review vendor-risk information and update our procurement records automatically." Which response shows the strongest technical judgment?

- Choose a customer-run open-weight model for this because the data being handled may be sensitive.
- Select ChatGPT Work immediately because the request includes multiple steps.
- **Separate surface, capability or architecture, and deployment and operations decisions, then validate data access, permissions, review, auditability, and escalation.** ✓ Correct
- Treat "agentic" as the product route and design the automation now.

This is strongest because the request combines a possible user surface, automation capabilities, sensitive information, and system write-backs. The team should separate the three decisions and validate access, permissions, review requirements, auditability, and escalation before recommending a design.

## Slide 29/37 - Summary

A strong early technical recommendation should do three things: name the likely user or product surface, identify the required capability or architecture, and explain which deployment and operating assumptions still need validation.

This helps you avoid two common mistakes: staying too vague to be useful, or sounding more certain than the evidence allows.

When the route is not final, state what is plausible on each axis, what assumptions you are making, and what must be checked next.

## Slide 30/37 - Introduction (Module: Build your Technical Fluency Navigator)

Throughout this course, you have practiced separating the decisions that shape a technical route, asking discovery questions, recognizing tradeoffs, and spotting when specialist validation is needed. You will now bring those skills together in a lightweight Technical Fluency Navigator that helps you answer four practical questions:

- What kind of conversation am I preparing for?
- What user or product surface is plausible?
- What capabilities or architecture must the system use?
- What deployment and operations assumptions or escalation signals matter?

The goal is not to capture every detail. Use the Navigator as a thinking aid before customer conversations, solution reviews, technical discovery sessions, or implementation handoffs. It is not a final recommendation, architecture document, or implementation plan.

## Slide 31/37 - Choose what your Navigator should help you do

Technical fluency looks different depending on your role.

A technical pre-sales specialist, solution consultant, solution architect, implementation practitioner, and developer-oriented builder may all need technical fluency, but they use it in different moments.

Start by completing this sentence: **My role most often needs technical fluency when…**

Here are some example answers to this question across different roles:

- **Technical pre-sales:** My role most often needs technical fluency when I need to explain likely surface, capability, and deployment choices, identify fit signals, and route an opportunity responsibly.
- **Solution consultant:** My role most often needs technical fluency when I need to translate a workflow challenge into useful technical discovery questions.
- **Solution architect:** My role most often needs technical fluency when I need to identify constraints, assumptions, risks, and validation requirements.
- **Implementation practitioner:** My role most often needs technical fluency when I need to prepare readiness discussions, implementation planning, or handoff conversations.
- **Developer or FDE-style builder:** My role most often needs technical fluency when I need to connect platform capabilities and solution patterns to a practical implementation approach.

Next, choose the one or two conversation types where your Navigator would be most useful:

- Early customer discovery
- Solution-path routing
- Technical pre-sales or solution review
- Implementation handoff
- Developer or Codex opportunity
- Security, governance, or data-readiness discussion

Finally, mark your current confidence as Low, Medium, or High in each area:

- Distinguishing ChatGPT Chat, ChatGPT Work, Codex, and API-built applications or processes as user or product surface choices
- Identifying required capabilities or architecture, such as retrieval, tools, structured outputs, code execution, Workspace Agents, or automation
- Asking deployment and operations questions about identity, permissions, approvals, retention, logging, human review, hosting, and ownership
- Naming tradeoffs and knowing when to involve a specialist

Use one Low or Medium area to decide what your Navigator should help you strengthen first.

## Slide 32/37 - Use a simple Navigator structure

Your Technical Fluency Navigator should be short enough to use before a real conversation. To do this, you need to use a structure that incorporates four sections.

**1. My role and conversation focus**

This is an extension of what you've just learned about technical fluency across different roles. Capture the situation where you most often need technical judgment.

To do so, use these prompts:

- My role most often needs technical fluency when…
- The conversations I support most often are…
- The stakeholders I usually need to help are…

**2. Three-axis routing cues**

Use this section to keep the three decisions distinct. Your notes are starting points for better discovery—not final recommendations.

- **User or product surface** — Use when the workflow suggests: ChatGPT Chat for interactive collaboration; ChatGPT Work for delegated knowledge work; Codex for software engineering; an application or process built with the API for embedded or custom experiences — Question to ask before routing: Where will the person or workflow primarily operate?
- **Capability or architecture** — Use when the workflow suggests: Apps and tools; Workspace Agents; retrieval; structured outputs; code execution; automation — Question to ask before routing: What must the system do?
- **Deployment and operations** — Use when the workflow suggests: Local or cloud; hosted or embedded; identity; permissions; approvals; retention; logging; human review; customer-run open-weight model evaluation where relevant — Question to ask before routing: Where and how will it run and be controlled?

**3. Discovery questions I reuse**

Keep only a few questions that you would actually use.

- **Workflow and outcome:** What work is being improved, who performs it, what output is required, and what outcome matters?
- **User or product surface:** Where should the person or workflow primarily operate?
- **Capability or architecture:** What context, tools, outputs, actions, or coordination does the system require?
- **Deployment and operations:** Where and how will the solution run, be controlled, reviewed, monitored, and supported?

**4. Tradeoffs and escalation signals**

Use this section to remind yourself when a route may need more validation.

Common tradeoffs include: speed versus control, quality versus cost or latency, automation versus oversight, simplicity versus integration depth.

Escalate or involve a specialist when the opportunity includes:

- Sensitive or regulated data
- Security, privacy, compliance, or residency questions
- System write-backs or customer-facing actions
- Complex integrations or unclear architecture
- Tool permissions, approval rules, or auditability needs
- Unclear evals, monitoring, ownership, or support model

A useful final line for your Navigator is: "Based on what I know, the likely surface is ___, the workflow may require ___, and I need to validate ___ in deployment and operations before treating the route as a recommendation."

## Slide 33/37 - Recommended exercise: Create your own one-page Technical Fluency Navigator

This is an optional practice activity you can complete to reinforce what you just learned.

**Purpose:** Consolidate the course's core technical-fluency habits into a role-specific Technical Fluency Navigator. You can use your completed Navigator to prepare for real conversations, identify plausible starting paths, ask stronger discovery questions, and recognize when tradeoffs or specialist validation could change the route.

**Task:** Create a short Navigator using the four sections from the previous card:

1. **My role and conversation focus** — Complete the sentence: My role most often needs technical fluency when…
2. **Three-axis routing cues** — Write one preliminary note for each axis: the likely user or product surface, the required capability or architecture, and one deployment and operations question.
3. **Discovery questions I reuse** — Write one question for the workflow and outcome, then one for each routing axis.
4. **Tradeoffs and escalation signals** — Write two tradeoffs you want to remember and two situations where you would involve a specialist.

Keep your Navigator brief. Aim for one page or less.

**Estimated time:** 5–7 minutes

Suggested output and reflection: Create a private one-page Navigator or write a short reflection using these prompts: "The conversation I most want to be ready for is…", "The three discovery questions I want to remember are…", "The tradeoff I am most likely to miss is…", "The situation where I should involve a specialist is…"

## Slide 34/37 - Knowledge check

**Question:** You are preparing for a customer call. The customer wants "AI automation" but has not explained the workflow, data sources, user group, or approval needs. What is the strongest next step?

- Ask which model the customer wants to use.
- **Clarify the workflow, then separate the user or product surface, capability or architecture, and deployment and operations decisions before routing.** ✓ Correct
- Recommend an agent because automation usually means agentic work.
- Recommend ChatGPT because it is the fastest place to start.

The strongest next step is to clarify the workflow and separate the three routing axes. Technical fluency starts with understanding what the work is, where it should happen, what the system must do, and how it will be controlled before recommending a route.

## Slide 35/37 - Summary

Your Technical Fluency Navigator brings together the core habits of technical fluency: separating user or product surface, capability or architecture, and deployment and operations decisions; asking stronger discovery questions; recognizing tradeoffs; and knowing when specialist validation is needed.

Keep it lightweight. A useful Navigator does not need to include every concept from the course. It only needs to help you prepare for real conversations, ask better questions, and avoid turning an early route into an unsupported recommendation.

As your experience grows, you can continue updating it with deeper implementation, architecture, governance, and solution-design knowledge.

## Slide 36/37 - Recap

Technical fluency is not about memorizing products, architectures, or implementation details. It is about understanding enough to ask better questions, recognize important tradeoffs, and know when additional validation is needed.

In this course, you learned how to route AI opportunities by separating three decisions: the user or product surface, the required capabilities or architecture, and the deployment and operating approach. You also explored how context, data, tools, evals, governance, and observability shape those decisions.

You also learned how to use the Technical Fluency Navigator to organize your thinking, identify gaps across the three axes, and prepare for stronger conversations with customers, technical teams, and specialists.

## Slide 37/37 - Congratulations

Congratulations, you've completed this course!

You now have a practical framework for approaching technical conversations with confidence. You do not need to be the deepest technical expert in the room. Your role is to understand the workflow, identify what matters, recognize what still needs validation, and involve the right people when needed.

Before your next customer conversation, solution review, or implementation discussion, open your Technical Fluency Navigator and ask yourself:

- What problem is the customer trying to solve?
- What information, systems, or tools are involved?
- What implementation details still need validation?
- Who should help answer the remaining questions?
