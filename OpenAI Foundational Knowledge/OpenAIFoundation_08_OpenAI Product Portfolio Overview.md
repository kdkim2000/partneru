# OpenAI Product Portfolio Overview

## Slide 1/46 - Title

OpenAI Product Portfolio Overview

Created July 2026

## Slide 2/46 - Introduction

Organizations use AI in different ways. Some want to help employees work more effectively. Others want to build AI into products and services, support software delivery, automate workflows, or meet specific deployment requirements.

This course gives you a practical map of how OpenAI capabilities support different kinds of customer work, so you can connect customer needs to possible OpenAI paths without jumping straight to a product recommendation.

## Slide 3/46 - What you'll learn

By the end of this course, you'll be able to:

- Describe the three independent portfolio decision layers: user or product surface, capability or architecture, and deployment and operations.
- Explain where ChatGPT Chat, ChatGPT Work, Codex, and applications or processes built with the API fit at the surface layer.
- Recognize capabilities and interfaces—such as Apps, Workspace Agents, voice, image generation, and deep research—that can extend a surface.
- Apply a simple portfolio mapping framework to connect a customer workflow to surface, capability, and deployment decisions.
- Identify the questions that still require product, technical, security, governance, or deployment validation.

Let's get started!

## Slide 4/46 - Introduction (Understanding the OpenAI Portfolio)

OpenAI's portfolio is easier to understand when you separate three different decisions: where people or workflows operate, what capabilities the system needs, and how the solution runs and is controlled.

This module gives you a first look at those layers across employee-facing work, embedded product experiences, software delivery, agentic capabilities, and deployment requirements.

## Slide 5/46 - Why different technologies exist

Different OpenAI technologies exist because organizations solve different problems in different ways.

For some customers, the first priority is helping employees complete everyday work such as researching, drafting, analyzing, and preparing deliverables.

For others, the priority is building AI directly into a product, service, or internal application.

Engineering teams may need AI support across the software development lifecycle.

Operations teams may want AI to coordinate steps across tools and systems.

Some organizations may also have deployment requirements that influence where and how AI can operate.

As AI adoption expands, the value is not only in giving individuals a productivity tool.

More mature organizations look for ways to embed intelligence into workflows, systems, teams, governance, and operating models. That means different technologies may play different roles in how work gets done.

A helpful way to think about the portfolio is to ask:

- What customer workflow or outcome are we trying to improve?
- Where will the person or workflow primarily operate?
- What capabilities or architecture must the system use?
- Does the work require collaboration, delegated multi-step execution, tools, or approvals?
- Where and how must the solution run, be controlled, and be monitored?

Those questions help move the conversation from "Which product should we use?" to a clearer map of the workflow, surface, capabilities, and operating requirements.

They also keep the portfolio connected to customer value: the right combination depends on the work, the user experience, what the system must do, and how it must be operated.

## Slide 6/46 - The three portfolio decision layers

The OpenAI portfolio includes product surfaces, capabilities, and deployment or operating choices. These are related, but they are not peer routes.

**ChatGPT**

ChatGPT Chat and ChatGPT Work are user-facing experiences for knowledge work. Chat is collaborative: people explore, draft, critique, and refine with AI. Work is built for delegation: people define an outcome, provide context and boundaries, and review completed or review-ready work.

**API**

An application or process built with the API is the surface when an organization needs intelligence embedded in a product, internal system, customer experience, or operational workflow it controls.

**Codex**

Codex is the dedicated surface for software engineering work, including planning, implementing, testing, reviewing, debugging, documenting, and maintaining software.

**Capability or architecture**

Describes what the system must do. Examples include Apps and tools, Workspace Agents, retrieval, structured outputs, code execution, automation, and human approval steps.

**Deployment and operations**

Describes where and how the solution runs and is controlled. Examples include hosted or embedded operation, local or cloud environments, identity, permissions, approvals, retention, logging, human review, and—where appropriate—customer-run open-weight models.

A simple way to remember the portfolio is:

- User or product surface: Where will the person or workflow primarily operate?
- Capability or architecture: What must the system do?
- Deployment and operations: Where and how will it run and be controlled?
- Agentic behavior: Treat it as a capability that can appear within ChatGPT Work, an API-built process, or another suitable surface—not as a separate product route.
- Open-weight models: Treat them as one deployment option to validate, not as the default answer to every control, privacy, or residency requirement.

A single customer solution may combine one or more surfaces with several capabilities and a distinct deployment and operating model. Keep these decisions separate before deciding how they fit together.

## Slide 7/46 - Related capabilities and interfaces

Across these layers, OpenAI offers capabilities and interfaces such as voice, image generation, deep research, Apps (formerly connectors), and Workspace Agents.

These extend a product surface or support a workflow; they are not separate portfolio routes by themselves.

**For example**

- Voice is an existing interface for supported experiences such as customer support, field work, live translation, or hands-free workflows.
- Image generation may support visual creation, ideation, campaign work, or other creative workflows.
- Deep research may support more complex research and synthesis tasks.
- Apps (formerly connectors) can help AI work with approved tools or knowledge sources, depending on the product, plan, workspace settings, permissions, and admin controls.
- Workspace Agents can support shared, repeatable workflows that use context, tools, schedules, triggers, and oversight where the plan and workspace configuration allow.

At the Foundation level, you do not need to memorize feature or availability details. Product names, access, and behavior can change, so validate current documentation before making a commitment.

**For example**

A customer-facing support experience might combine an API-built application, agentic capabilities, and voice.

An employee workflow might use ChatGPT Chat or Work with Apps and deep research.

The surface and capabilities still need a separate deployment and operating decision.

## Slide 8/46 - Understanding how intelligence operates across the portfolio

As organizations expand AI adoption, four concepts help explain how intelligence operates across the portfolio: context, runtime, observability, and governance.

In this course, runtime is shorthand for where and how a workflow executes. It is distinct from the user or product surface and from the capabilities the workflow uses.

Context means what the AI knows about the business. This may include company knowledge, files, data, policies, workflows, systems, permissions, or other relevant information.

Runtime means where and how AI does work across a ChatGPT experience, an application, an engineering environment, tools, systems, or a customer-operated environment.

Observability means monitoring and tracing AI activity so the organization can understand what the system is doing, what it can access, how it is performing, and what outcomes or errors are occurring.

Governance means the policies, roles, permissions, approval boundaries, review requirements, and accountability that determine how AI may be used.

You do not need to design the technical architecture in this course. The point is to recognize that context and runtime describe how work is performed, observability provides visibility, and governance sets the rules and responsibilities.

Use this map to keep monitoring separate from policy and control.

**Diagram:** A hierarchy diagram. Top row: three boxes — User or product surface, Capability or architecture, Deployment and operations. These three connect down to a bottom row of four boxes: Context ("What AI knows"), Runtime ("Where and how work executes"), Observability ("Monitoring and tracing"), Governance ("Policies, access, approvals, accountability").

## Slide 9/46 - Real-world example

A regional insurance provider wants to improve how teams use AI across the business.

Customer service teams want faster access to policy information so they can respond more confidently.

Engineering teams want help maintaining legacy applications.

Product teams want to explore AI-powered experiences inside digital customer channels.

At first, the organization may describe this as one broad goal: "We want to use AI." But the work is not all the same.

The customer service need points first to a ChatGPT surface—Chat for collaborative assistance or Work for delegated knowledge work—plus capabilities such as Apps, retrieval, or Workspace Agents.

The engineering need points to Codex. The product-team need points to an application or process built with the API.

The challenge is not choosing one peer category for the whole organization. It is mapping each workflow across surface, capability or architecture, and deployment and operations.

Recognize that the same organization can use different surfaces and capabilities while applying consistent operating and governance requirements.

## Slide 10/46 - Knowledge check

Match each example to the portfolio layer or role it represents.

- "Voice, image generation, and deep research" → **Capabilities or interfaces that can extend a surface (Correct)**
- "ChatGPT Chat, ChatGPT Work, Codex, or an application built with the API" → **User or product surface (Correct)**
- "A customer-run open-weight model" → **A deployment option to validate within deployment and operations (Correct)**
- "Hosted or embedded operation, identity, permissions, approvals, retention, logging, or human review" → **Deployment and operations (Correct)**
- "Apps and tools, Workspace Agents, retrieval, structured outputs, code execution, or automation" → **Capability or architecture (Correct)**

**All pairs matched correctly!**

## Slide 11/46 - Summary

OpenAI's portfolio is easier to map when you separate user or product surface, capability or architecture, and deployment and operations.

ChatGPT Chat, ChatGPT Work, Codex, and API-built applications describe where people or workflows operate. Apps, Workspace Agents, retrieval, voice, and other capabilities describe what the system can do.

A useful first step is to ask what work matters, where the experience should live, what capabilities are required, and how the solution must run, be controlled, and be monitored.

## Slide 12/46 - Introduction (identifying workflow indicators)

You've built a high-level map of the OpenAI portfolio. Now, let's make that map more practical. Customer requests are not always precise. A customer may say they want to improve productivity, build an AI feature, support developers, or automate a process.

In this module, you'll learn to identify indicators in the customer's workflow: who is involved, where the experience belongs, what the system must do, and what operating requirements apply.

At this stage, focus on spotting clues that point to the relevant surface, capability or architecture, and deployment and operations.

## Slide 13/46 - Identify indicators: AI for people and teams

Some AI opportunities are mainly about helping employees complete everyday work. These opportunities often involve employees using AI directly to research, summarize, draft, analyze, or prepare materials.

The AI experience usually lives in a workspace where the employee can ask questions, provide context, upload or reference information, and refine the output.

**Typical indicators**

- Employees are the primary users
- The work involves research, analysis, writing, communication, or decision support.
- Productivity and knowledge work are primary goals.
- The AI experience helps people complete work directly.

**Most relevant user or product surface**

ChatGPT is often the relevant surface when employees need to interact with AI directly. Chat fits collaborative thinking and creation; ChatGPT Work fits delegated knowledge work with a defined outcome, context, boundaries, and review standard.

For example, a marketing manager who wants to summarize notes and iteratively draft an update may start in Chat. If the manager delegates a multi-step campaign briefing and expects a review-ready artifact, Work may be the better surface to explore.

## Slide 14/46 - Identify indicators: AI inside products and applications

Some AI opportunities are not about giving employees a separate AI workspace. Instead, the organization wants AI to appear inside a product, service, portal, or internal application.

In these situations, the user may not think of the experience as "using AI." They simply interact with a more helpful product or workflow.

**Typical indicators**

- AI is embedded into software.
- Users interact through an existing product, application, portal, or service.
- The organization wants to design a custom user experience.
- AI becomes part of the product journey.

**Most relevant user or product surface**

An application or process built with the API is often the relevant surface when the organization wants intelligence inside a product, application, operation, or customer experience it controls.

For example, a software company wants users to receive AI guidance while completing setup inside its platform. The user stays inside the product, and the company controls the experience. Those indicators point toward an API-built experience to explore first.

## Slide 15/46 - Identify indicators: AI for software delivery

Engineering workflows have their own needs. Software teams work across codebases, development tools, testing processes, documentation, review cycles, and maintenance work.

These opportunities are not just about generating text or improving general productivity. They are about helping engineering teams move software delivery work forward.

**Typical indicators**

- Development or engineering teams are the primary users.
- Work involves coding, testing, debugging, review, documentation, maintenance, or modernization.
- The focus is software delivery outcomes.
- Engineering productivity is a key objective.

**Most relevant user or product surface**

Codex is often the relevant surface when the workflow centers on software engineering.

**For example**

An engineering team wants help writing tests, reviewing code changes, and understanding an older codebase.

The work is inside the software development lifecycle, so Codex is the surface to explore first; supporting capabilities and controls still need separate validation.

## Slide 16/46 - Identify indicators: AI that performs work

Some opportunities move beyond a single prompt and response. The customer may want AI to gather information, coordinate multiple steps, use approved tools, prepare an output, or ask for approval before taking action.

These are signs that an agentic approach may be relevant.

**Typical indicators**

- Information must be gathered from more than one place.
- The work involves multiple steps.
- AI needs to coordinate actions or move a task forward.
- The workflow may involve tools, systems, approvals, or handoffs.

**Relevant capability or architecture**

Agentic capabilities may be relevant when AI needs to pursue a goal across multiple steps, tools, systems, or approvals.

They can operate within ChatGPT Work, an API-built process, or another suitable surface.

**For example**

An operations team wants AI to check approved information, prepare a summary, update a ticket, and ask a manager for approval before sending a response.

Those clues point to agentic capabilities, but they do not by themselves determine the product surface or deployment model.

## Slide 17/46 - Identify indicators: AI with deployment flexibility

Sometimes the most important clues are about deployment and operations rather than the user surface or capability.

Requirements around infrastructure, operational ownership, privacy, latency, identity, retention, logging, or data movement can shape which operating options are realistic.

**Typical indicators**

- Infrastructure requirements influence the decision.
- Operational requirements affect deployment options.
- Environment control is important.
- The customer may need to operate more of the environment directly.
- Technology selection includes deployment considerations.

**Relevant decision layer**

These clues belong to deployment and operations.

Customer-run open-weight models may be one option to evaluate, but hosted or embedded approaches may also meet the requirement.

**For example**

A customer says the AI capability must run in an environment they control directly. That is an important operating requirement, but it is not enough for a final recommendation. The team must clarify where the application runs, where model inference occurs, who operates each component, and how data moves.

## Slide 18/46 - Real-world example

A product team wants to add AI help inside an existing customer portal. The team says, "We want customers to ask questions and get help without leaving the portal."

Look at the indicators:

- The users are customers.
- The experience lives inside an existing product.
- The organization wants to control the user experience.
- The work is part of a customer journey.

Those clues point toward an application or process built with the API as the most relevant surface. If the journey requires retrieval, tool use, or multi-step execution, those are separate capability decisions.

Now compare that with a different request: "Our customer success managers need help researching accounts and preparing follow-up notes."

In that case, the users are employees and the work happens in ChatGPT.

Chat may fit collaborative preparation; Work may fit delegated, multi-step preparation.

Small changes in the users, work, and experience can change the surface. Capability and deployment decisions still need to be made separately.

## Slide 19/46 - Knowledge check

Match each workflow clue to the most relevant first decision.

- "Environment control is a primary requirement" → **Deployment and operations; evaluate hosted, embedded, and customer-run options separately (Correct)**
- "Customers need AI assistance inside an existing software product" → **An application or process built with the API (Correct)**
- "Employees need to collaborate with AI on research and drafting, or delegate a defined knowledge-work outcome" → **ChatGPT Chat or ChatGPT Work, depending on the interaction (Correct)**
- "Engineers need help testing and modernizing application code" → **Codex (Correct)**
- "A workflow spans multiple steps and approved tools" → **Agentic capability or architecture; the surface is still a separate decision (Correct)**

**All pairs matched correctly!**

## Slide 20/46 - Summary

Clues in the workflow help you map three different decisions. Employee knowledge work may point to ChatGPT Chat or Work.

Embedded product experiences may point to an API-built application. Software engineering may point to Codex. Multi-step tool use points to agentic capability or architecture, while environment control points to deployment and operations.

Small changes in users, work, experience, or operating requirements can change one layer without determining the others.

## Slide 21/46 - Introduction (How surfaces, capabilities, and operating choices combine)

So far, you've explored the three portfolio decision layers and where common surfaces and capabilities fit. Now, let's look at how they can work together. In real organizations, a single business problem may involve employees, customers, engineering teams, workflows, tools, and deployment requirements.

In this module, you'll explore how surfaces, capabilities, and operating choices combine in a broader solution. Focus on the role each layer plays rather than forcing one product or capability to solve everything.

## Slide 22/46 - One problem, multiple technologies

Many organizations begin by asking, "Which product do we need?"

In practice, business problems often involve multiple users, systems, workflows, and objectives. One customer goal may require several product surfaces, capabilities, and operating choices.

**For example:** A company may want to improve customer support.

That single goal could involve:

- Employees who need faster access to approved information.
- Customers who need help inside a digital product.
- Engineering teams that maintain the support platform.
- Agentic capabilities that gather information, use tools, or update systems.
- Governance requirements that set permissions and approvals, plus observability that helps monitor activity.

No single surface or capability has to solve every part of the problem. Different layers can support different parts of the same workflow or broader strategy.

Portfolio thinking helps you avoid forcing a technology choice too early.

Start by separating the customer goal into workflows, then map the user or product surface, required capabilities, and deployment and operating requirements for each.

A single customer problem can involve several workstreams and decision layers. This map shows why one product should not be forced across the whole workflow.

**Diagram:** A hierarchy diagram. Top: "Business problem." This connects down to three stacked layer boxes: (1) User / product surface — containing ChatGPT Chat, ChatGPT Work, Codex, API-built experience; (2) Capability / architecture — containing Apps and tools, Workspace Agents, Retrieval, Code execution, Automation, Approvals; (3) Deployment / operations — containing Hosted / embedded, Local / cloud, Identity, Permissions, Retention, Logging, Observability, Governance, Human review.

## Slide 23/46 - Employee productivity patterns

Employee productivity opportunities often involve more than a direct AI interaction.

Employees may use AI to:

- Research information
- Analyze content
- Create drafts
- Access organizational knowledge
- Support decision-making
- Prepare materials for review

ChatGPT may be the visible starting surface. Chat supports collaborative work, while ChatGPT Work supports delegated knowledge work. Additional capabilities may support the broader workflow.

**For example**

A consulting firm wants employees to prepare client deliverables more efficiently.

Consultants need to research information, analyze documents, generate draft materials, and prepare client-ready outputs. Leadership initially assumes the solution is simply giving employees AI access.

Further discussion reveals that employees may also need organizational knowledge, automated research, and repeatable ways to prepare common deliverables.

The workflow may therefore use Apps, deep research, Workspace Agents, or other capabilities, subject to current product and workspace settings.

Recognize that an employee workflow can combine one surface with several capabilities and a separate operating model.

## Slide 24/46 - Customer-facing AI patterns

Customer-facing opportunities often look different from employee productivity opportunities.

Common characteristics include:

- AI is delivered through a product or service.
- Customers interact with an existing experience.
- AI supports the customer journey.
- The technology operates behind the scenes.
- User experience is a primary consideration.

For example, a software company wants customers to receive AI-powered assistance while using its platform.

The objective is not to send customers to a separate AI tool. The objective is to improve the experience inside the product itself.

That difference matters. The user or product surface may shift from ChatGPT to an application built with the API because the organization wants AI inside an experience it controls. Retrieval, tool use, or multi-step execution are separate capability decisions.

Recognize the surface distinction between AI used directly by employees and AI embedded in products and services.

## Slide 25/46 - Organization-wide AI patterns

Many organizations pursue multiple AI initiatives at the same time.

Different teams may focus on:

- Employee productivity.
- Customer experiences.
- Software delivery.
- Workflow automation.
- Deployment flexibility.
- Governance and monitoring.

Understanding the portfolio helps explain how product surfaces, capabilities, and operating choices support different parts of the same strategy.

As adoption grows, organizations evaluate business context, runtime, observability, and governance separately.

Context and runtime shape how work is performed; observability provides monitoring and tracing; governance sets policies, permissions, and accountability.

At this stage, you do not need to design the complete solution. Your goal is to recognize when several layers may contribute to the same business outcome.

## Slide 26/46 - Knowledge check

A company wants employees to prepare internal reports faster, customers to get help inside its product, and engineers to modernize the platform. What is the best portfolio-first interpretation?

- "Wait for a full technical architecture before identifying any likely surface or capability."
- "Choose API for everything because customers are involved."
- "Choose ChatGPT for everything because employees are involved."
- **"Treat this as multiple workflows, then map each one across user or product surface, capability or architecture, and deployment and operations." (Correct)**

**Correct!** The business problem spans employee work, customer experience, and software delivery. Portfolio thinking separates the workflows and then maps each one across the three decision layers.

## Slide 27/46 - Summary

Customer problems often involve more than one product surface, capability, or operating choice. A single business goal may include employee work, customer-facing experiences, engineering workflows, automation, governance, observability, and deployment considerations.

Portfolio thinking separates the work into clearer parts, so each layer supports the part of the solution where it fits best.

## Slide 28/46 - Introduction (Recognizing Common Solution Paths)

You already learned how to spot individual clues, such as who uses AI, what work is happening, and where the experience lives. Now you'll group those clues into common solution patterns. Many AI opportunities have a familiar shape: employee productivity, customer experiences, software delivery, workflow automation, or deployment and operating requirements.

In this module, you'll practice recognizing those patterns and then mapping the relevant surface, capabilities, and operating choices.

## Slide 29/46 - Recognize pattern: Employee productivity and knowledge work

The first common pattern is employee productivity and knowledge work.

This pattern appears when an organization wants employees to work faster, improve output quality, find information more easily, or reduce time spent on repetitive knowledge tasks.

**Common pattern clues**

- Employees interact directly with AI.
- Work involves research, analysis, writing, communication, or decision support.
- Access to knowledge is important.
- Productivity improvements are a primary outcome.
- The organization may want repeatable ways of working across teams.

**Potential surfaces and capabilities**

- ChatGPT Chat or ChatGPT Work, depending on whether the work is collaborative or delegated
- Apps, deep research, Company Knowledge, or other approved context capabilities
- Workspace Agents or other agentic capabilities where enabled

**For example**

A consulting firm wants teams to prepare client deliverables more efficiently. Chat may support collaborative research and drafting; Work may support a delegated, multi-step deliverable. Apps, organizational knowledge, deep research, or Workspace Agents may contribute, subject to current product and workspace settings.

The solution pattern is employee productivity and knowledge work; surface, capability, and operating choices are mapped separately.

## Slide 30/46 - Recognize pattern: Customer experiences

The second common pattern is customer experience.

This pattern appears when an organization wants AI to improve how customers interact with a product, service, portal, or support journey.

**Common pattern clues**

- AI supports customers rather than internal employees.
- The experience is delivered through a product, application, service, or portal.
- AI becomes part of the customer journey.
- User experience is a primary consideration.
- The organization may want the AI to take action or coordinate steps inside the experience.

**Potential surfaces and capabilities**

- An application or process built with the API
- Agentic capabilities, retrieval, or tools where the workflow requires them
- Voice, image generation, or other interfaces and capabilities that fit the experience

**For example**

A software company wants customers to complete onboarding faster inside its platform. The user surface may be an API-built experience.

Retrieval, voice, or agentic capabilities may be added if the workflow requires information access, multiple steps, or tool use.

The pattern is customer experience. The API-built surface does not determine every capability or operating choice.

## Slide 31/46 - Recognize pattern: Software delivery and engineering acceleration

The third common pattern is software delivery and engineering acceleration.

This pattern appears when the organization wants to improve how engineering teams plan, build, test, review, document, modernize, or maintain software.

**Common pattern clues**

- Engineering teams are the primary users.
- Work focuses on software delivery.
- Activities include coding, testing, debugging, review, documentation, maintenance, or modernization.
- Engineering productivity and delivery speed are important outcomes.
- The organization may be looking beyond code generation toward broader software lifecycle support.

**Potential surfaces and capabilities**

- Codex
- API-built integrations or supporting systems where needed
- Code execution, review, automation, and other engineering capabilities

**For example**

An enterprise engineering team wants to modernize a legacy application while keeping quality high.

Codex may be the primary surface for engineering work, while supporting integrations, tests, review steps, and operating controls depend on the workflow.

The pattern is software delivery and engineering acceleration; supporting capabilities and operations are separate decisions.

## Slide 32/46 - Recognize pattern: Workflow automation and agentic work

The fourth common pattern is workflow automation and agentic work.

This pattern appears when the organization wants AI to move work forward across multiple steps, tools, systems, or approvals.

**Common pattern clues**

- Work spans multiple steps.
- Information must be gathered or coordinated.
- AI may prepare outputs, update systems, or trigger next steps.
- Human oversight or approval may still be required.
- The workflow involves handoffs, tools, systems, or repeatable processes.

**Potential surfaces and capabilities**

- ChatGPT Work, an API-built process, or another suitable user or product surface
- Workspace Agents or other agentic capabilities
- Tools, retrieval, automation, approvals, and human review

**For example**

An operations team wants to reduce manual effort in a vendor review process.

The team first chooses where the workflow will operate, then identifies the agentic capabilities, tools, approval points, and operating controls needed to complete the work responsibly.

The pattern is workflow automation and agentic work. Agentic behavior is a capability, not a separate product route.

## Slide 33/46 - Recognize pattern: Flexible deployment requirements

The fifth common pattern is deployment and operating requirements.

This pattern appears when infrastructure, model inference location, operational ownership, data movement, identity, permissions, retention, logging, or control requirements shape the solution.

**Common pattern clues**

- Deployment considerations influence solution design.
- Infrastructure requirements affect technology choices.
- Environment control is important.
- Operational requirements shape decisions.
- The customer may need to operate more of the environment directly.

**Deployment and operating options to validate**

- OpenAI-hosted inference used by a ChatGPT or API-based experience
- Customer applications running in the customer's cloud or another approved environment
- Customer-run open-weight models, where supported and appropriate

**For example**

A regulated organization wants to explore AI for internal analysis, but operating requirements are central.

The team must separate where the application runs, where model inference occurs, who operates each component, and how data moves before deciding whether a hosted, embedded, or customer-run option fits.

This pattern defines how the solution runs and is operated, not the user experience or its capabilities.

## Slide 34/46 - Real-world example

A financial services organization wants to improve how employees access information, how customers receive support, and how internal processes are managed.

**Different stakeholders describe different needs**

- Relationship managers want faster access to account and policy information.
- Customers need better support inside a digital portal.
- Operations teams want to reduce manual handoffs in review processes.
- Technology leaders want to understand whether deployment requirements affect the solution path.

**This is not one isolated clue. It is a set of solution patterns**

- Faster employee information access points to an employee productivity and knowledge work pattern.
- AI support inside the digital portal points to a customer experience pattern.
- Reducing manual handoffs points to a workflow automation and agentic work pattern.
- Deployment questions point to a flexible deployment requirements pattern.

Once you recognize the patterns, map each one across user or product surface, capability or architecture, and deployment and operations.

## Slide 35/46 - Knowledge check

Match each scenario to the most relevant solution pattern.

- "An engineering group wants to modernize legacy applications and improve testing and review" → **Software delivery and engineering acceleration (Correct)**
- "A company wants customers to get AI-powered guidance inside an existing portal" → **Customer experiences (Correct)**
- "A customer says infrastructure control and operating environment requirements are central to the solution" → **Flexible deployment requirements (Correct)**
- "An operations team wants AI to gather information, prepare a summary, update a record, and request approval" → **Workflow automation and agentic work (Correct)**
- "A team wants employees to research, summarize, draft, and prepare internal reports more efficiently" → **Employee productivity and knowledge work (Correct)**

**All pairs matched correctly!**

## Slide 36/46 - Summary

Common solution paths often have recognizable patterns: employee productivity, customer experiences, software delivery, workflow automation, and flexible deployment requirements.

These patterns are broader than a single product choice. They combine clues about users, workflows, outcomes, experience location, and operating constraints.

Recognizing the pattern helps identify the surface, capabilities, and operating choices worth exploring, plus the questions that still need validation. It also prepares you for later PartnerU courses where these patterns become more specific use cases, customer conversations, technical decisions, and deployment considerations.

## Slide 37/46 - Introduction (Bringing it together: a workflow-first approach)

You've explored the OpenAI portfolio, the three decision layers, how they combine, and the solution patterns they often support. Now, you'll bring that thinking together into a simple workflow-first approach.

In this module, you'll practice moving from the customer problem and workflow to the user or product surface, required capabilities, and deployment and operating requirements.

## Slide 38/46 - Start with the customer problem

Technology discussions often begin with products. More effective conversations usually begin with the problem the customer is trying to solve.

Before mapping the portfolio, first understand the business need behind the request. This keeps the discussion focused on outcomes rather than jumping directly to a product, capability, or deployment assumption.

Start with questions such as:

- What problem is the customer trying to solve?
- What business outcome are they pursuing?
- Why is this important now?

Then move to the workflow itself:

- What work needs to happen?
- What outcome is being pursued?
- Where does friction exist today?

Similar product requests may be driven by very different business problems. The same customer problem may also support more than one surface, capability set, or operating model.

Understanding the customer problem and workflow often provides more insight than starting with a technology label.

## Slide 39/46 - Understand who performs the work

Different users often require different experiences.

Consider who is involved in the workflow:

- Employees
- Customers
- Engineering teams
- Operational teams
- Administrators or reviewers
- Leaders or decision-makers

The people involved often influence the user or product surface.

**For example**

Employees may use ChatGPT Chat for collaborative work or ChatGPT Work for delegated knowledge work.

Customers inside a product may require an API-built experience.

Engineers may use Codex.

Operations teams with multi-step processes may need agentic capabilities, but that does not determine the surface by itself.

Do not assume every user needs the same interface. Identify who performs the work, then choose the surface before mapping capabilities and operating requirements.

## Slide 40/46 - Understand where the experience lives

The next question is where the person or workflow primarily operates.

- ChatGPT Chat or ChatGPT Work
- An application or process built with the API
- Codex and its supported engineering surfaces
- A supported web, mobile, desktop, or embedded surface within those product paths

This matters because the surface is a distinct decision from the capabilities the system uses and the environment in which it operates.

**For example**

- If employees need collaborative thinking, drafting, or analysis, ChatGPT Chat may be relevant; if they delegate a defined multi-step outcome, ChatGPT Work may be relevant.
- If AI needs to appear inside an existing customer portal, an application or process built with the API may be relevant.
- If developers need support inside software engineering workflows, Codex may be relevant.
- If work needs to move across tools or systems, add the required agentic capabilities after selecting the surface.
- If environment control is a major requirement, evaluate deployment and operating options separately, including hosted, embedded, and customer-run approaches.

The surface narrows the experience decision, but it does not determine capability or deployment by itself.

## Slide 41/46 - Consider possible technology paths

A simple framework can keep solution thinking organized:

**Customer problem and workflow → User or product surface → Capability or architecture → Deployment and operations**

Use the framework like this:

1. Customer problem and workflow: What work must improve, and what outcome matters?
2. User or product surface: Where will the person or workflow primarily operate?
3. Capability or architecture: What must the system do, access, or coordinate?
4. Deployment and operations: Where and how will it run, be controlled, and be monitored?

This framework moves from the work to three independent portfolio decisions without treating products, agentic capabilities, and deployment options as peer routes.

Then check four operating concepts:

**Context** — What information and business knowledge does the AI need?

**Runtime** — Where and how will the workflow execute?

**Observability** — How will activity, performance, and outcomes be monitored and traced?

**Governance** — Which policies, permissions, approvals, review points, and accountabilities apply?

**For example**

A healthcare organization wants to improve how employees prepare patient-support documentation. Initial conversations focus on "using AI," but the workflow raises separate surface, capability, and operating questions.

The discussion evolves from a product request into a workflow evaluation exercise.

ChatGPT Chat or Work may be the employee surface. Apps, retrieval, or agentic capabilities may provide approved context and multi-step support.

Deployment, permissions, observability, governance, and human review still require separate validation.

You are not making a final recommendation. You are creating a first-pass map and identifying what needs product, technical, security, governance, or deployment validation.

## Slide 42/46 - Recommended exercise: Mapping a Workflow to the Portfolio

This is an optional practice activity to help you apply what you just learned.

**Purpose**

Practice mapping a workflow across the user or product surface, capability or architecture, and deployment and operations.

**Task**

Review the short workflow examples below.

For each one, identify:

- The primary workflow and desired outcome.
- Who performs or receives the work.
- The most relevant user or product surface.
- The capabilities or architecture the workflow may require.
- The deployment and operating requirements that still need validation.

Use these examples:

- Employees researching and preparing internal reports.
- Customers receiving AI assistance inside a software product.
- Engineers modernizing legacy applications.
- Teams automating a multi-step operational process.

**Estimated time**

6-8 minutes

**Suggested output and reflection**

Create a simple table with six columns: Workflow and outcome, Users, User or product surface, Capability or architecture, Deployment and operations, and Open questions.

After completing the table, ask yourself: "Did I start with the work, or did I jump straight to a product?"

## Slide 43/46 - Knowledge check

A customer says, "We need AI to help customers complete complex account-update requests inside our existing portal." Which first-pass mapping best separates the portfolio layers?

- **"An API-built application, with agents if the workflow requires multiple steps." (Correct)**
- "A customer-run open-weight model only, because customer data may be involved in the workflow."
- "Codex only, because the portal is software that engineering teams may maintain."
- "ChatGPT only, because the request includes a conversational interaction with the user."

**Correct!** The existing portal points to an API-built surface. Multi-step work, tools, and approvals are capability decisions; privacy, identity, retention, logging, and operating-environment requirements must be evaluated separately.

## Slide 44/46 - Summary

A workflow-first approach helps you move from a broad AI request to a structured portfolio map.

Use the sequence Customer problem and workflow → User or product surface → Capability or architecture → Deployment and operations to separate where work happens, what the system must do, and how it will run and be controlled.

At this stage, the aim is recognition, not a final recommendation. Use the map to identify likely options and the product, technical, security, governance, or deployment questions that remain.

## Slide 45/46 - Recap

OpenAI's portfolio supports different kinds of work through distinct layers. ChatGPT Chat supports collaborative knowledge work, ChatGPT Work supports delegated knowledge work, Codex supports software engineering, and applications or processes built with the API support embedded and custom experiences.

Capabilities such as Apps, Workspace Agents, retrieval, voice, and automation can extend those surfaces. Deployment and operations determine where and how the solution runs, is controlled, and is monitored.

The main habit is to start with the customer's work, then map the user or product surface, capability or architecture, and deployment and operating requirements separately.

## Slide 46/46 - Congratulations

Congratulations, you've completed this course!

Use the portfolio map as a workflow-first starting point in customer conversations. Start with the work, then separate the user or product surface, required capabilities, and deployment and operating requirements.

You do not need to recommend a full solution at this stage. Your goal is to identify likely options, understand how the layers can combine, and know what still needs validation before anyone commits to a solution.

**Course completed**

**Next up in OpenAI Foundational Knowledge:** ChatGPT Essentials (Course, 58 min)

ChatGPT Essentials unlocks the power of conversational AI for everyday productivity, guiding users through practical workflows like research, drafting, analysis, and collaboration. Discover how to craft clear prompts, leverage ChatGPT's features for both individual and workplace use, and understand the differences between ChatGPT, the OpenAI API, and Codex. Explore real-world examples, learn best practices for responsible adoption, and build confidence with hands-on exercises and safe-use guidance. Whether you're new to AI or helping teams adopt smarter ways of working, this content empowers you to get more done—thoughtfully, securely, and with human judgment at the center.
