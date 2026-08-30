# AI Infrastructure & Implementation

## Slide 1/35 - Title

AI Infrastructure & Implementation

Created July 2026

## Slide 2/35 - Introduction

Customers often start with the outcome they want from AI: faster support, better knowledge access, automated workflows, or AI built into a product or process.

But an AI outcome also raises practical questions. Where will the application run? Where will model inference occur? What data or tools might it need? What constraints could affect whether the idea is feasible?

This course gives you a simple infrastructure recognition lens, so you can notice those questions early and know when deeper technical, security, governance, or implementation expertise should be involved.

## Slide 3/35 - Overview

AI infrastructure can sound technical, but this course keeps the focus practical. You do not need to design a system or recommend an architecture.

Instead, you will learn how to notice the early feasibility signals that may affect whether an AI workload is feasible: what the AI needs to do, what information it may need, where the application and model inference run, who operates each component, and how data moves between them.

That recognition lens can help you ask better questions, avoid jumping to a solution too early, and know when deeper technical, security, governance, or implementation expertise should be involved.

## Slide 4/35 - What you'll learn

By the end of this course, you'll be able to:

- Describe four deployment questions at a high level: application location, model-inference location, operational ownership, and data movement.
- Recognize practical trade-offs across performance, cost, governance, data control, and operational responsibility.
- Distinguish training from inference in plain language.
- Recognize basic AI hardware terms, including CPU, GPU, NPU, and accelerator.
- Identify three common feasibility constraints: latency, volume, and data and privacy.
- Apply a simple infrastructure recognition lens to a short workload description without recommending an architecture.

Let's get started!

## Slide 5/35 - Introduction (Where AI systems run)

An AI solution can combine components that run in different places. An application may run in a customer's cloud while model inference is provided through an OpenAI-hosted service. Another solution may use a model that supports customer-run inference on controlled infrastructure, or keep some processing on a device because of connectivity or latency.

In this module, you'll learn basic hardware terms and a four-question deployment framework: where the application runs, where model inference occurs, who operates each component, and how data moves between them.

## Slide 6/35 - Basic AI hardware terms

Before examining where application and inference components run, it helps to recognize a few hardware terms.

You do not need to become a hardware expert. You only need to understand what these terms generally refer to when they appear in customer or technical conversations.

**CPU**

A CPU, or central processing unit, is a general-purpose processor. It handles many everyday computing tasks and is common across almost all computers and servers.

**GPU**

A GPU, or graphics processing unit, is commonly used for AI training and large-scale inference because it can process many operations in parallel. GPUs are often important for workloads that require significant compute.

**NPU**

An NPU, or neural processing unit, is often used in consumer or edge devices for local AI processing. For example, a phone, laptop, or specialized device may include an NPU to support certain AI tasks on the device.

**Accelerator**

A broad term for specialized hardware that helps certain workloads run more efficiently. GPUs and NPUs are examples of accelerators.

The key idea is simple: AI workloads can require different kinds of compute depending on what the system needs to do, how quickly it needs to respond, where the application and inference components run, and how much usage it needs to support.

## Slide 7/35 - The four deployment questions

An AI solution can include components that run in different places. To understand deployment clearly, consider four separate questions rather than relying on one environment label.

Keeping these questions separate prevents a common mistake: assuming that the application, model inference, data, and operations all sit in the same environment.

**1. Application location**

Where does the user-facing application or workflow component run?

It may be an OpenAI-hosted workspace, a customer application in a public or private cloud, an on-premises application, or software on a device.

Application location describes the experience or software the user interacts with. It does not, by itself, tell you where model inference occurs.

**2. Model-inference location**

Where is a trained model used to process inputs and generate outputs? Inference may be provided through an OpenAI-hosted service, or it may be run by the customer or a hosting provider for a model that supports that deployment path.

Do not assume that an application running in the customer's cloud also means the customer is operating the model.

**3. Operational ownership**

Who sets up, monitors, maintains, secures, and supports each component? The application, integration, model service, data stores, and device components may have different owners.

More customer-operated components usually create more operational responsibility. Confirm who owns updates, monitoring, incident response, and ongoing support.

**4. Data movement**

What information moves between the user, application, model service, tools, and storage? Where is it processed or stored, and which permissions, retention rules, or review steps apply?

A solution can cross more than one location. The data path must be understood separately from the application and inference locations.

For example, a retailer may run a support application in its own cloud while using OpenAI-hosted model inference. The application location is customer cloud; the model-inference location is OpenAI-hosted. The customer still needs to understand the data path and the responsibilities on each side.

The map below shows the four deployment questions to consider separately, followed by a simple example.

**Diagram:** Four boxes labeled Application location, Model-inference location, Operational ownership, and Data movement. Below, an "Example — Data exchange" pair shows Customer-cloud application (Customer-operated) on the left and OpenAI-hosted inference (OpenAI-operated) on the right, connected by a bidirectional arrow.

## Slide 8/35 - Practical trade-offs across deployment choices

Deployment trade-offs come from the combination of application location, inference location, data movement, and operational ownership—not from one environment label.

A useful first comparison looks at four areas:

**Performance and latency**

Response time and reliability can depend on the application, model-inference service, network path, workload, and hardware. A real-time interaction may have different needs from a background document review process.

**Cost and capacity**

Hosted services can use service-based or usage-based costs. Customer-run inference can require compute, storage, operations, maintenance, and engineering investment. Compare the full cost and capacity profile rather than a single cost component.

**Governance and data control**

Data movement, processing location, storage, permissions, retention, and review requirements can shape the path. Verify these details against current product and customer requirements.

**Operational ownership**

The customer, partner, OpenAI, or another provider may operate different components. More control over one component can bring more responsibility for setup, monitoring, updates, incident response, and support.

## Slide 9/35 - Deployment configurations: real-world examples

Here are four configurations that show why the deployment questions must be separated.

**OpenAI-hosted workspace**

Employees use an OpenAI-hosted workspace for document and knowledge work. The product experience and model inference are provided through the hosted service. The customer still needs to decide how the service fits its workflow, access rules, and review practices.

**Customer-cloud application with OpenAI-hosted inference**

A retailer runs a support application in its own cloud and sends approved requests to an OpenAI-hosted model service. The retailer operates the application and integration; OpenAI operates the hosted model service. Data moves between those components.

**Customer-controlled application with customer-run inference**

An organization runs an application and an open-weight model on infrastructure it controls. The organization is responsible for the compute environment, model serving, monitoring, updates, and ongoing support.

**Edge application with split processing**

A field tool runs on a device and keeps some workflow data local, but uses remote model inference when connectivity is available. The team must clarify which steps happen locally, which happen remotely, and how the workflow behaves when the connection is unavailable.

These examples are configurations, not mutually exclusive environment labels. A single solution may combine a customer-run application, OpenAI-hosted inference, local device processing, and customer-controlled data stores.

Use the four deployment questions to describe the configuration, then compare its trade-offs before recommending a path.

## Slide 10/35 - Knowledge check

**Question:** Which statement best describes this configuration? A retailer runs a support application in its own cloud and sends requests to an OpenAI-hosted model service.

- Data movement does not need to be considered because the model service is hosted.
- Both the application and model inference run in the customer's cloud.
- **The application runs in the customer's cloud, while model inference is OpenAI-hosted. (Correct)**
- The retailer must operate the model hardware because it owns the application.

**Explanation:** Application location and model-inference location are separate. A customer-cloud application can use OpenAI-hosted inference.

## Slide 11/35 - Summary

An AI solution can include components that run in different places. Start by answering four separate questions: where the application runs, where model inference occurs, who operates each component, and how data moves between them.

Those choices interact with performance, cost, governance, data control, and operational responsibility. A customer-cloud application can still use OpenAI-hosted inference, so avoid treating one environment label as the full architecture.

## Slide 12/35 - Introduction (Understanding what training and inference mean in AI)

Two terms often appear in AI infrastructure conversations: training and inference.

They sound technical, but the basic distinction is straightforward:

- Training is about how a model learns or is adapted.
- Inference is about using a trained model to produce an output.

In this module, you'll learn how to use these terms accurately and avoid a common misconception: not every AI project requires training a new model.

## Slide 13/35 - Understanding "training" in an AI context

Training is the phase where a model learns patterns from data.

During training, the model is created or adapted so it can perform a task more effectively. This usually requires significant compute and happens before the model is used in a live product or workflow.

Training can involve very large datasets and significant infrastructure. It may also involve more targeted adaptation, depending on the method and use case.

Many customer AI experiences use an already trained model. They may need the right business context, approved data sources, retrieval, configuration, or workflow design rather than full model training from scratch.

That distinction matters. When someone says, "We need to train a model," they may not always mean full model training. They may mean that they need the AI system to understand their business context or behave appropriately for a specific workflow.

A useful clarification is:

> Do we need to train or adapt a model, or do we need to use an already trained model with the right context?

## Slide 14/35 - Understanding "inference" in an AI context

Inference is the phase where a trained model is used to produce an output from an input.

Every time a user asks an AI assistant a question, uploads a document for summarization, asks for a draft, or sends information to an AI-enabled application, the model is performing inference.

During inference, the model uses what it has already learned to generate an output from the input and context it receives.

Inference happens every time the model is used. The application sending the request can run somewhere different from the infrastructure performing inference, so response time, network path, scale, and cost often matter.

For example, a customer-facing support assistant may need to answer many users quickly. An internal document summarization tool may process longer files but tolerate slower responses. A background workflow may run in batches without needing immediate output.

Most AI experiences that users interact with are inference experiences.

## Slide 15/35 - Why the distinction matters

Training and inference raise different questions. Training questions are usually about how a model learns, is adapted, or changes behavior before use. Inference questions are about how a trained model performs when people or systems use it.

This distinction affects several practical considerations:

**Cost and compute**

Training and inference can have different cost, compute, and operational patterns.

**Operational ownership**

A customer may operate its own application while another provider operates the model-inference service. Customer-run inference is a separate path that depends on the model, infrastructure, and support responsibilities involved.

**Implementation path**

Some customer needs may be met by adding the right business context to an already trained model. Others may require deeper technical work.

**Communication accuracy**

It is important to avoid implying that every AI project requires training a new model.

When the terminology is unclear, ask what the customer is trying to achieve. They may need training, but they may also need retrieval, configuration, context, workflow design, or an already trained model used in the right way.

This helps you keep early conversations focused on the actual workload before assuming that a new model, a specific product, or customer-run inference is required.

## Slide 16/35 - Training and inference: real-world examples

**Training or adaptation example**

A healthcare operations team has a large set of labeled historical support tickets. A project team uses that dataset to adapt a model so it becomes better at recognizing common ticket categories and patterns.

In this example, the model behavior is being changed using data before it is used in a live workflow. This points to training or adaptation.

**Inference example**

An employee opens an AI assistant and asks it to summarize a policy document. The model uses what it has already learned, along with the user's input and available context, to generate a summary.

In this example, the model is producing an output from an input. This is inference.

**Context example**

A company connects an AI assistant to approved policy documents so employees can ask questions about internal guidance.

This may not require training a new model. The main need may be giving the AI-supported experience access to the right context, sources, and permissions.

## Slide 17/35 - Knowledge check

**Question:** A user asks an AI assistant to summarize a policy document. The trained model produces a response from the user's input. What is this an example of?

- Training
- On-prem deployment
- **Inference (Correct)**
- Hardware acceleration

**Explanation:** Inference happens when a trained model is used to produce an output from an input.

## Slide 18/35 - Summary

Training and inference describe different parts of how AI systems work. Training is about how a model learns or is adapted before use. Inference is what happens when a trained model produces an output from an input.

Many AI use cases do not require training a new model. They may need the right context, approved sources, permissions, configuration, or workflow design.

## Slide 19/35 - Introduction (Feasibility constraints)

An AI use case may sound feasible at first, but implementation can become more complex when you consider response time, usage volume, data sensitivity, privacy expectations, and operating requirements.

In this module, you'll learn three common feasibility constraints: latency, volume, and data and privacy.

## Slide 20/35 - Latency in AI

Latency is how long the system takes to respond. Some AI experiences need fast responses because the user is waiting. Others can run in the background without interrupting the user's work.

**For example**

- Voice assistants often need fast responses because the interaction is live.
- Live chat support usually needs quick replies because a customer is waiting.
- Autocomplete or in-product suggestions may need to appear almost immediately.
- A scheduled summary or batch document review may tolerate slower processing.

Latency can be affected by model choice, output length, workload complexity, system design, data retrieval, tool use, and network conditions. You do not need to solve latency questions yourself. You should be able to recognize when response time may matter.

A useful question is:

> Does the user need an immediate response, or can the work happen in the background?

## Slide 21/35 - Volume in AI

Volume is how many requests, users, documents, messages, or tasks the system needs to handle. Higher volume can affect cost, capacity, throughput, reliability expectations, and operating requirements.

**For example**

- An internal assistant used by a small team has one volume profile.
- A customer-facing feature used by millions of end users has a very different volume profile.
- A tool that processes ten documents a day has different needs from one that processes thousands of documents per hour.
- A weekly report generator has a different cadence from a live customer support assistant.

Volume is shaped by the number of users, frequency of use, input size, output size, and workload cadence.

A useful question is:

> How many users, requests, documents, or tasks does the system need to handle, and how often?

## Slide 22/35 - Data and privacy in AI

Data and privacy constraints involve what information the workload uses, where it can be processed, who can access it, and what requirements apply. This matters because AI workloads may involve sensitive, regulated, proprietary, or customer-specific information.

**Examples may include**

- Internal policy assistants.
- Customer support systems.
- Legal document review.
- Healthcare workflows.
- Financial analysis.
- Employee or customer data workflows.

Data and privacy considerations may affect where the application runs, where model inference occurs, how information moves between components, what information can be used, which users can access it, how long data is retained, and which controls or approvals are required.

For customer-facing conversations, avoid making assumptions about privacy, retention, residency, compliance, or plan-specific details.

Those details should be verified against current approved sources before any commitment is made.

Your role is to recognize when data and privacy may affect feasibility and when the right expert needs to be involved.

## Slide 23/35 - Constraints usually appear together

Latency, volume, and data/privacy constraints often appear together.

A customer-facing assistant may need to respond quickly, serve many users, and use sensitive customer data.

That single workload raises latency, volume, and data/privacy considerations at the same time.

Another example: An internal legal document review process may not need instant responses, but it may involve sensitive information, long documents, access controls, retention expectations, and review steps.

The same workload can also raise operational ownership questions.

A customer may operate the application while another provider operates model inference, or it may choose more customer-operated components. Each choice changes who owns setup, monitoring, updates, incident response, and support.

Your role is to identify what matters and what needs to be clarified before deeper design or implementation decisions are made.

In later role-based work, this same recognition may help you qualify whether an opportunity needs technical validation, security review, deployment planning, or customer governance input before it moves forward.

## Slide 24/35 - Knowledge check

**Question:** Match each workload example to the feasibility constraint it most clearly raises.

- A support assistant must respond quickly, serve many users, and use customer data → **Combination of constraints (Correct)**
- A workflow uses sensitive customer records → **Data and privacy (Correct)**
- A voice assistant needs to respond while the user is speaking → **Latency (Correct)**
- A customer-facing application may receive millions of requests → **Volume (Correct)**

All pairs matched correctly!

## Slide 25/35 - Summary

Feasibility depends on more than whether an AI capability is possible. Response time, usage volume, data sensitivity, privacy expectations, and operating requirements can all shape what is practical.

These constraints often appear together, so a useful first step is to identify what matters and what still needs to be clarified.

## Slide 26/35 - Introduction (How infrastructure shapes implementation feasibility)

You've now explored deployment questions, training and inference, basic hardware terms, and common feasibility constraints.

This module brings those ideas together. You'll look at how the type of AI use case, the data it needs, and the customer's governance expectations can shape implementation feasibility.

## Slide 27/35 - AI workloads have different infrastructure needs

AI infrastructure decisions should start by understanding the workload, not by choosing a preferred technology path too early.

In this context, a workload means the task, or set of tasks, the AI system is expected to handle. This might include answering questions, summarizing documents, classifying requests, generating content, processing voice, reviewing code, or supporting a workflow across systems.

The infrastructure considerations may depend on questions such as:

- Who will use the AI system?
- What task does the system need to support?
- Does the system need to respond immediately or run in the background?
- What information does the system need to access?
- How many users, requests, documents, or tasks must it support?
- Where does the application or user experience run?
- Where does model inference occur?
- How does data move between the application, model service, tools, and storage?
- Who will operate, monitor, and maintain each component?

The same AI capability can require different infrastructure considerations depending on the customer context.

That is why OpenAI solution paths should be considered in relation to the workload, not chosen only because a product surface or single environment label sounds familiar.

For example, summarizing documents for a small internal team is different from summarizing documents for a regulated, customer-facing process with strict access, privacy, and audit expectations.

## Slide 28/35 - Data access, context, and governance considerations

Many AI workloads depend on stored information. That information may include documents, knowledge sources, application data, logs, user inputs, outputs, or workflow records.

In enterprise settings, this is part of the broader context the AI may need to support real work. Context is what the AI needs to know about the business, workflow, data, systems, policies, and permissions.

Data access and context considerations may affect:

- What information the AI system can access.
- Where information is stored or processed.
- Who can access it.
- Which permissions or approval steps apply.
- How long information may need to be retained.
- What governance, privacy, or auditability requirements apply.

These questions matter because AI value often depends on the right context. But context has to be handled responsibly.

For example, an internal support assistant may be more useful if it can access approved policy documents. However, the organization still needs to control which sources are used, who can see which information, and how the workflow is reviewed.

## Slide 29/35 - How constraints connect

Infrastructure considerations rarely appear in isolation.

Here are a few examples:

- A real-time assistant may raise latency considerations.
- A high-use customer application may raise volume considerations.
- A workflow using sensitive information may raise data and privacy considerations.
- A solution with more customer-operated components may raise additional operational ownership considerations.
- A training or adaptation workload may raise different compute and data considerations from an inference workload.

Understanding how these considerations connect helps you recognize why AI implementation can vary across use cases.

A simple customer request such as "We want an AI assistant" is not enough to determine feasibility.

You need to understand what the assistant will do, where the application runs, where model inference occurs, how data moves, how fast it must respond, how many people will use it, and what controls or review expectations apply.

## Slide 30/35 - Simple enterprise operating lens

As AI becomes part of enterprise workflows, three operating concepts can help structure the conversation: context, runtime, and observability. Operational ownership and governance should remain separate questions.

**Context:** What does the AI need to know?

This includes the business, workflow, data, systems, policies, permissions, and operating context.

**Runtime:** Where does the AI operate?

Separate where the application runs, where model inference occurs, which tools or systems are involved, and how data moves between them.

**Observability:** How can the organization monitor and improve the workflow?

This includes visibility into activity, performance, errors, and opportunities for improvement.

You do not need to design the operating model in this course. Focus on recognizing these as early feasibility signals.

Operational ownership and governance are separate questions. Clarify who operates each component and which permissions, approvals, retention rules, and human-review steps apply.

A useful way to apply the lens is:

- **Context** — What information does the AI need?
- **Runtime** — Where do the application and model inference run, and how does data move between them?
- **Observability** — How will the organization monitor and improve what happens?

**Diagram:** Three boxes side by side: Context (hexagon-cluster icon) — "What AI knows"; Runtime (arrow icon) — "Where AI works"; Observability (magnifying-glass icon) — "How work is monitored."

This lens helps connect infrastructure to real enterprise work.

As you continue through PartnerU, you will see the same questions appear in product, solution-pattern, technical, and deployment conversations: what the AI needs to know, where the application and model inference run, how data moves, who operates each component, and how activity is monitored and improved.

## Slide 31/35 - Recommended exercise: Recognize infrastructure considerations

This is an optional practice activity to help you apply what you just learned.

**Purpose**

Help you apply the course concepts to short AI workload examples.

**Task**

Review the three workload examples below. For each one, identify:

- The application location and model-inference location,
- Who operates each component and how data moves between them,
- Whether the example primarily involves training, inference, adding context, or a combination,
- The main feasibility constraint or combination of constraints.

**Workload example 1**

A company gives employees access to an OpenAI-hosted AI workspace so they can summarize internal documents and draft communications.

**Workload example 2**

A retailer runs an AI assistant inside its own customer support platform. The application runs in the retailer's cloud, uses an OpenAI-hosted model service for inference, must respond quickly to many customers, and may retrieve approved order information.

**Workload example 3**

A field technician uses an AI-enabled mobile tool in remote locations with unreliable connectivity. The application and approved reference data are on the device, and model inference runs locally on edge hardware.

**Estimated time**

5 minutes

**Suggested output and reflection**

Complete a short categorization using this pattern:

- Application location:
- Model-inference location:
- Operational owner and data movement:
- Training, inference, or adding context:
- Main feasibility constraint:

Then ask yourself: "Which deployment details would need to be clarified before a technical team could design this properly?"

## Slide 32/35 - Knowledge check

**Question:** A customer-facing assistant must respond quickly, serve many users, and use approved customer data. Which answer best describes the infrastructure considerations?

- The only consideration is latency because users need fast replies.
- **The workload may involve latency, volume, data access, and governance considerations together. (Correct)**
- The workload does not raise infrastructure considerations because it is an assistant.
- The only consideration is volume because many users may access the assistant.

## Slide 33/35 - Summary

Infrastructure conversations should start with the workload: what the AI needs to do, who will use it, what information it needs, and how the solution's components will be deployed and operated.

Application location, model-inference location, data movement, operational ownership, latency, volume, and data and privacy considerations can change the implementation path.

A simple recognition lens can help structure early conversations: what the AI needs to know, where the application and model inference run, how data moves, who operates each component, and how activity will be monitored and improved.

## Slide 34/35 - Recap

In this course, you learned how to separate application location from model-inference location, how training differs from inference, and why hardware, data movement, operational ownership, latency, volume, data, and privacy can affect feasibility.

The key takeaway is simple: infrastructure conversations should start with the workload. What does the AI need to do, what information does it need, where does the application run, where does model inference occur, how does data move, who operates each component, and what still needs to be clarified before design decisions are made?

## Slide 35/35 - Congratulations

Congratulations, you've completed this course!

You can now use a practical infrastructure recognition lens when reviewing AI workload examples: identify the application location, model-inference location, operational owner and data path, the type of AI work involved, and the feasibility constraints that may matter most.

Use this lens to ask better early questions, avoid jumping to a solution too quickly, and recognize when technical, security, governance, or implementation expertise should be involved.
