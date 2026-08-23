# Model Selection and Solution Patterns

## Slide 1/50 - Title

Model Selection and Solution Patterns

Created July 2026

## Slide 2/50 - Introduction

When a customer asks, "Which model should we use?", the best answer usually starts with the workflow, not the model name.

The stronger starting point is the task shape: what work the AI must perform, how often it runs, what output is needed, what risk or review requirements apply, and what evidence would make a recommendation credible.

This course helps you make practical model-selection and solution-pattern recommendations for API-led opportunities. You'll learn to look at the task, output, context, risk, tradeoffs, and validation evidence before suggesting a model class, solution path, or pattern.

## Slide 3/50 - What you'll learn

By the end of this course, you'll be able to:

- Explain why model selection should start with task shape and workflow context.
- Distinguish common model classes by practical strengths and tradeoffs.
- Identify the decision drivers that affect API model selection.
- Distinguish the primary user or product surface—ChatGPT Chat, ChatGPT Work, Codex, or an application or process built with the API—from capability or architecture and deployment or operations decisions.
- Map common customer needs to repeatable solution patterns.
- Identify the eval evidence needed to validate a model-selection and solution-pattern recommendation.
- Decide when to route, validate, or escalate an early technical recommendation.

Let's get started!

## Slide 4/50 - Introduction (Module: Start with task shape, not model name)

Before comparing models, define the work the AI system must perform.

This module introduces task shape: a practical way to describe the task pattern, required output, context needs, and risk or review signals behind a customer request. Task shape helps you avoid jumping too quickly from a broad workflow label to a model class, product path, or implementation pattern.

The key question for this module is: What exactly must the AI produce, who or what uses that output next, and what must be reviewed before anyone relies on it?

## Slide 5/50 - What task shape means

A customer request often arrives as a broad label: contract review, claims review, support triage, procurement intake.

That label is a useful starting point, but it usually hides several different jobs the AI system might perform.

Task shape describes the actual work the AI needs to do inside the workflow. It captures the action the system takes, the information it needs, the output it must produce, who or what uses that output next, and what level of risk or review applies.

That is why model selection should not start with the newest or most powerful model. It should start with the task, workflow, data, risk level, success criteria, and operating context.

Once those are clear, you can make a stronger recommendation about the model class, solution path, pattern, and validation evidence.

A useful task-shape statement names the work, the inputs or context, the expected output, the user or downstream system, and any important review or success requirements.

For example, a vague request like "We need support-ticket triage" becomes clearer when expressed as a task shape: The AI reads incoming support tickets, classifies issue type and urgency, retrieves approved troubleshooting or policy guidance when needed, and routes ambiguous, sensitive, or high-priority cases to a human queue with a short rationale.

That statement reveals classification, retrieval-grounded support, escalation logic, and review criteria. Those details affect the model class, solution pattern, eval evidence, and escalation needs.

## Slide 6/50 - Common task patterns

A task pattern is a recognizable type of work the AI performs inside a workflow.

Task patterns help you look inside a broad customer request and see what the AI may actually need to do. That matters because different kinds of work can point to different output requirements, model classes, solution patterns, review needs, and eval evidence.

For example, "Procurement intake" may sound like one workflow, but it could include several task patterns. The AI might classify the request, extract vendor details, answer policy questions from approved guidance, check a system, and route exceptions for human review.

Use task patterns as a practical conversation aid. The goal is not to label every task perfectly. The goal is to ask better questions before recommending a model class or solution path.

Common task patterns include:

- Summarization and synthesis
- Classification and routing
- Extraction and structuring
- Drafting and rewriting
- Reasoning and analysis
- Retrieval-grounded answering
- Tool-using workflow support
- Multimodal understanding
- Voice or real-time interaction
- Code or developer workflow support
- Moderation and safety filtering

A single customer workflow may include more than one task pattern. When that happens, separate the patterns before recommending a model class or solution path.

## Slide 7/50 - Output requirements shape the decision

After you understand the task pattern, clarify what the AI must produce. Output requirements determine how the result will be used, reviewed, and validated.

A customer may say they want "analysis," but the required output could be a short narrative summary, a structured table, a classification label, a decision-support note, a cited answer, a tool call, a generated file, a voice response, a code change, or a safe refusal with escalation.

Those outputs have different technical implications.

For example, a claims-review workflow could require a plain-language summary for an adjuster, structured extracted fields for a claims system, a risk classification for routing, or a cited policy explanation for review. Each output requires different thinking about model class, prompt design, retrieval, structured output, tool use, evals, and human review.

Strong early questions include:

- What does the next person or system need to do with the AI output?
- What format does the output need to be in?
- Will the output be requested again in the future, if so how often/repeatable?

If the output only informs a human, a natural-language response may be enough. If it drives a workflow, updates a system, or triggers an action, the workflow needs more structure, validation, and review.

## Slide 8/50 - Risk and review shape the decision

After you understand the task pattern and output, consider what could happen if the AI output is wrong, incomplete, unsupported, or acted on without review.

Risk matters because it changes what the recommendation needs to include.

A higher-risk workflow does not simply need a more capable model. It usually needs stronger validation, clearer human review, safer escalation behavior, and more careful ownership.

Risk is higher when the AI output is customer-facing, uses regulated or sensitive data, runs at high volume, affects legal, financial, medical, security, or employment decisions, triggers system actions, writes back to another system, or operates with limited human review.

For example, an AI system that drafts an internal summary may only need human review for quality. An AI system that updates a procurement system or prepares a claim-decision note needs more careful validation, approval rules, logging, and escalation.

At this point in the course, you do not need to design the full governance model.

You do need to recognize the practical implication: the higher the risk, the more your recommendation should explain what must be tested, reviewed, approved, or escalated before the customer relies on the workflow.

## Slide 9/50 - Real-world example

A customer says: "We need a model to help with contract review."

That sounds specific, but it is still a workflow label. In a procurement context, "contract review" could mean several different tasks.

- The AI might summarize commercial terms so a procurement manager can understand the contract quickly.
- It might extract obligations, renewal dates, payment terms, or required actions into structured fields.
- It might compare clauses against an approved policy or playbook.
- It might flag unusual clauses for legal review.
- It might draft negotiation notes for a business stakeholder using approved guidance.
- It might route contracts to the right review queue based on value, exception type, or risk.

Each task shape changes the recommendation:

- Extraction points toward structured outputs.
- Policy comparison points toward approved sources and retrieval-grounded behavior.
- Routing points toward classification logic and escalation rules.
- Negotiation notes point toward careful human review before use.

A stronger response to the customer is not: "use this model."

A stronger response is: "Contract review can involve several different task shapes. Before recommending a model class, I'd want to confirm whether we are summarizing, extracting structured fields, comparing against policy, routing exceptions, drafting negotiation support, or combining several of those steps."

That answer gives the customer confidence that your recommendation will be based on workflow fit rather than model popularity.

## Slide 10/50 - Recommended exercise: Decompose the task shape

This is an optional practice activity you can complete to apply what you just learned.

**Purpose:** Practice turning a broad customer workflow request into a clearer task-shape note before considering model class, solution path, or pattern.

**Task:** Use the customer request below: "We need AI support for claims review."

Reflect on what you would need to understand before making a model-selection recommendation. Consider whether the AI is being asked to summarize information, extract structured fields, compare information against policy, classify risk, draft review notes, route exceptions, or support another task.

Write a short task-shape note that captures:

- The likely task pattern or combination of task patterns
- The required output
- The context or source information the AI may need
- One risk or review signal
- One missing technical question you would ask before recommending a model class or solution path

**Estimated time:** 2–3 minutes

Suggested output and reflection: Create a short task-shape note that clarifies what the AI is being asked to do and what still needs to be understood before model selection.

## Slide 11/50 - Knowledge check

**Question:** A customer asks, "Which model should we use for claims review?" Which next question best keeps the conversation workflow-first?

- How many people will attend the implementation meeting?
- Which exact model names are already approved?
- **What does claims review need to do?** ✓ Correct
- Can we use the newest model available?

Model selection starts with the task, output, workflow context, and review needs. A model name is useful only after the work is clear enough to evaluate fit.

## Slide 12/50 - Summary

You can now turn a broad workflow label into a task-shape statement.

Task shape helps you identify the work the AI performs, the information it needs, the output it must produce, who or what uses that output, and what risk or review requirements apply. A broad request such as "claims review" or "contract review" can hide several different task patterns, and each pattern may point to different model classes, solution paths, eval evidence, and escalation needs.

In the next module, you will use task shape to compare model classes and decision drivers.

## Slide 13/50 - Introduction (Module: Understand model classes and decision drivers)

Once you understand the task shape, you can begin comparing model classes and the tradeoffs that matter.

This module uses durable model-class language rather than exact model IDs. That matters because model names, availability, pricing, and capability details can change. Model-class language helps you explain the type of capability a workflow needs in a way that stays useful over time.

The key question for this module is: Which model class is most plausible based on the task shape, reasoning need, context, latency, cost, risk, and evidence required?

## Slide 14/50 - Durable model classes

A model class is a stable category of capability. It helps you discuss model fit without relying on a specific model name from memory.

Use model classes as starting hypotheses, not final answers. The recommendation still needs to be tested against the workflow, constraints, and eval evidence.

Use model class only for model categories. Evaluate related capability or architecture choices such as retrieval, ranking, tool use, and agentic orchestration and deployment or operations choices such as hosting, identity, permissions, approvals, retention, and logging as separate decisions. These layers interact, but they should not be presented as one peer list.

Decision category and practical use in a workflow:

- **Reasoning-oriented models** — Useful when the task requires multi-step analysis, planning, ambiguity handling, policy interpretation, technical reasoning, or judgment-heavy work.
- **General-purpose models** — Useful for broad language tasks such as drafting, summarization, rewriting, classification, and everyday workflow support.
- **Efficient models** — Useful when speed, cost, and scale matter and the task is relatively stable, simple, or high volume.
- **Multimodal models** — Useful when the workflow involves images, documents, screenshots, audio, or mixed inputs and outputs.
- **Audio or real-time models** — Useful for speech, transcription, streaming, voice interaction, and low-latency conversational experiences.
- **Embedding models** — Useful for semantic search, retrieval, similarity comparison, clustering, and organizing knowledge for later use.
- **Capability or architecture: moderation and safety filtering** — Useful when the workflow needs to identify unsafe, sensitive, disallowed, or escalation-worthy content.
- **Capability or architecture: tool use** — Useful when the workflow needs to call functions, use APIs, retrieve information, perform calculations, or coordinate actions across systems.
- **Model or deployment option: open models** — Useful when hosting, customization, deployment environment, infrastructure, policy, latency, or cost structure constraints require evaluation.
- **Capability or architecture: retrieval and ranking** — Retrieval returns candidate results for a query; ranking or reranking orders those candidates by relevance before downstream use.

The goal is not to memorize this table. The goal is to use it as a conversation aid.

For example, if the customer needs high-volume ticket classification with clear categories, an efficient model may be a plausible starting point.

If the workflow requires ambiguous policy interpretation and exception handling, a reasoning-oriented model may be more plausible.

If the task depends on approved internal documents, the model class alone is not enough; retrieval or another context pattern may also be needed.

## Slide 15/50 - Reasoning depth

Reasoning depth describes how much planning, analysis, or multi-step problem solving the task requires. Not every workflow needs a reasoning-oriented model class.

Simple summarization, rewriting, formatting, and stable classification may work well with a general-purpose or efficient model class, especially when the output is short, categories are clear, and the workflow runs at high volume.

Deeper reasoning becomes more important when the task involves incomplete inputs, competing constraints, policy interpretation, technical analysis, planning across several steps, or judgment about whether to escalate.

It may also matter when the model uses tools in sequence and needs to decide what to do next.

The practical question is not: "Can a stronger model do this?"

The better question is: "Does this workflow justify deeper reasoning based on the task, risk, and evidence required?"

That question helps you avoid defaulting to the most capable model when a simpler model class may be faster, cheaper, easier to validate, and sufficient for the workflow.

## Slide 16/50 - Latency, cost, and scale

Latency is the time it takes for the system to respond. Cost is the resource impact of running the workflow. Scale is how often the workflow runs and how many users, documents, requests, or actions it must support.

These drivers matter most when the workflow is frequent, user-facing, or operationally embedded.

A high-volume support triage workflow may need fast, consistent classification more than deep reasoning on every ticket.

A low-volume legal review workflow may tolerate slower responses if deeper reasoning and stronger evidence are needed.

When latency, cost, or scale is important, ask what can be simplified. Choose the output contract from downstream requirements. When a reliable structured contract is required, use Structured Outputs with an appropriate JSON Schema.

Evaluate operational cost at the level of the successful task including retries, human correction, tool use, and downstream rework — not token count or nominal token price alone.

The workflow may benefit from an efficient model class, shorter inputs, structured outputs, routing simple cases differently from complex cases, caching repeated results, or redesigning the workflow so only the hard cases require deeper reasoning.

A strong recommendation explains this tradeoff clearly. It does not assume that the most capable model is always the best operational fit.

## Slide 17/50 - Context and knowledge requirements

Context is the information the AI system can use to complete the task. In enterprise workflows, context may include company knowledge, documents, policies, records, systems, permissions, business rules, and operating context.

Some tasks can be completed from the user's prompt alone. Others require current, private, or approved business information.

If the model needs information outside the prompt, model choice alone will not solve the problem.

For example: A procurement policy assistant may need approved policy documents, current spending thresholds, vendor status, user permissions, and exception rules. That need may point toward retrieval-grounded answering, tool use, application integration, or a hybrid pattern. The model class still matters, but the context pattern may matter just as much.

A useful distinction is: What can the model handle from the prompt, and what must the customer provide through approved context, retrieval, tools, or connected systems?

That distinction helps you avoid recommending a "better model" when the real gap is missing context.

## Slide 18/50 - Structured output, tool use, and risk

Structured outputs help the system return information in a consistent format that downstream systems, people, or workflows can reliably use.

Tool use is relevant when the model must retrieve information, call an API, search a file, perform a calculation, check a system, or trigger an action.

Tool use increases responsibility. As soon as a workflow can take action rather than only produce text, the recommendation should account for permission boundaries, approval rules, error handling, observability, evals, and escalation planning.

A workflow that only drafts a result for human review has a different risk profile from one that updates a procurement system automatically.

## Slide 19/50 - Real-world example

A customer says: "We need to categorize thousands of inbound support messages by topic and urgency."

A weak recommendation would immediately choose the strongest model available. A better recommendation depends on the workflow.

If the categories are clear, the inputs are short, and the output is a simple structured label, an efficient model class may be a strong starting point.

The main drivers may be consistency, latency, cost, and performance at scale.

If the messages are ambiguous, include multiple issues, require account context, or depend on current policy rules, the recommendation changes.

The workflow may need a reasoning-oriented model class, retrieval-grounded support, tool access, or escalation logic for uncertain cases.

The decision should be validated with representative examples. If an efficient model handles typical and ambiguous tickets well enough, it may be the better operational fit. If it misses urgent or sensitive cases, the evidence may justify a different model class, a routing pattern, stronger review gates, or escalation.

## Slide 20/50 - From workflow to model-class shortlist

This visual shows how to move from a customer workflow to a model-class shortlist.

Start with the task shape: what the AI must do, what output is required, what context it needs, and what risk or review requirements apply.

Then use decision drivers such as reasoning depth, latency, cost, scale, context, structured output, tool use, and risk to narrow the options.

The goal is not to choose a final model. The goal is to identify a plausible shortlist, define what needs validation, and recognize when escalation may be needed.

A strong early recommendation explains which model class looks most plausible, what alternative may also be worth comparing, what tradeoff matters most, and what evidence would validate the recommendation.

## Slide 21/50 - Recommended exercise: Shortlist a model class

This is an optional practice activity you can complete to apply what you just learned.

**Purpose:** Practice using decision drivers to form an early model-class hypothesis without treating it as a final model recommendation.

**Task:** Use the workflow below: A support organization receives thousands of inbound messages each day. The team wants AI to classify each message by topic and urgency so it can be routed to the right queue. Most messages are short and straightforward. Some are ambiguous, contain multiple issues, depend on account-specific policy, or include sensitive language that may require escalation.

Reflect on which model class or combination of model classes may be a reasonable starting point. Consider the tradeoffs that matter most for this workflow, such as reasoning depth, latency, cost, scale, structured output reliability, context needs, and escalation behavior.

Write a short model-class tradeoff note that captures:

- One likely model class or model-class combination
- One possible alternative
- Two or three decision drivers that matter most
- One tradeoff you would want to validate
- One type of evidence that would help confirm or challenge the recommendation

**Estimated time:** 2–3 minutes

Suggested output and reflection: Create a short model-class tradeoff note that explains your starting hypothesis, alternative, key tradeoff, and validation need.

## Slide 22/50 - Knowledge check

**Question:** Match each workflow need to the most relevant model class or capability.

- Safety filtering before review → **Moderation or safety-focused capability** ✓ Correct
- High-volume simple classification → **Efficient model** ✓ Correct
- Search across approved internal documents → **Embedding or retrieval-supporting capability** ✓ Correct
- Ambiguous policy interpretation → **Reasoning-oriented model** ✓ Correct
- Document image understanding → **Multimodal model** ✓ Correct

All pairs matched correctly!

## Slide 23/50 - Summary

You can now explain model-class fit as a hypothesis, not a final answer.

Durable model-class language helps you discuss capability without relying on exact model names or version memory. Decision drivers then help you test that hypothesis against the workflow. Reasoning depth, latency, cost, scale, context, structured output, tool use, risk, and eval needs can all change what "best fit" means.

A strong early recommendation names a plausible model class, a reasonable alternative, the tradeoff that matters most, and the evidence needed to validate the choice.

## Slide 24/50 - Introduction (Module: Compare solution paths and patterns)

A model recommendation is stronger when it fits the right solution path and workflow pattern.

This module introduces solution-path comparison and common API-led solution patterns. These are routing tools, not extra models to memorize. They help you decide where the work should happen and how the AI capability may appear inside the workflow.

The key question for this module is: Which solution path and pattern best fit the workflow, users, systems, context, actions, review needs, and validation requirements?

## Slide 25/50 - When API model selection is the right next step

API model selection becomes relevant when the customer needs to prioritize either speed or intelligence embedded into software, products, operations, or customer experiences.

In an API-led path, the model is part of a larger system.

The surrounding application controls how users interact with the capability, what context is passed to the model, what output format is required, which tools or systems may be used, and what happens after the model responds.

API model selection is often the right next step when the customer needs a custom user experience, product integration, backend workflow automation, structured outputs, tool use, system actions, or production-scale application behavior.

For new custom API projects, use the Responses API as the default starting primitive, then validate the required inputs, context, tools, output contract, state, review, and evaluation evidence against current API documentation.

For example: If the customer needs high-volume ticket classification with clear categories, an efficient model may be a plausible starting point.

An API-led opportunity also needs clear ownership for implementation, evals, monitoring, and ongoing improvement. At this course depth, your job is to identify those dependencies early, not to design the full system.

## Slide 26/50 - When another solution path may fit better

Do not compare products, capabilities, and deployment choices as one peer list. Separate three decisions before recommending a model class or API-led pattern.

1. User or product surface — where will the person or workflow primarily operate?
   - ChatGPT Chat supports collaborative thinking, drafting, analysis, and refinement with the user.
   - ChatGPT Work supports delegated, multi-step knowledge work when the user defines an outcome, context, constraints, and review standard.
   - Codex supports delegated software-engineering work.
   - An application or process built with the API supports embedded and custom AI experiences.

2. Capability or architecture — what must the system do? Examples include: retrieval, Structured Outputs, tool use, agentic orchestration or automation, multimodal or Realtime interaction.

3. Deployment and operations — where and how will it run and be controlled? Consider hosting or embedding: identity, permissions, approvals, human review, retention, logging, model-hosting constraints.

A combined solution may span more than one surface or capability, but "agents," "open models," and "hybrid" should not be treated as peer user surfaces. Use the three layers to explain the role of each decision and what still needs validation.

Visual diagram: "Customer workflow need" flows down into three parallel boxes — "Where will it operate? (User or product surface)", "What must it do? (Capability or architecture)", and "How will it run and be controlled? (Deployment and operations)" — which all flow down into a shared box: "A solution may span all three layers."

## Slide 27/50 - Common API-led solution patterns

Once an API-led path looks like the right option, use solution patterns to describe how the AI capability will show up in the workflow.

A solution pattern is a repeatable way that AI supports a workflow.

It is not a final architecture. It is a practical description of the work the AI performs and the surrounding capabilities that may be needed.

Common API-led patterns include text generation, structured extraction, classification and routing, retrieval-grounded answering, summarization and synthesis, multimodal understanding, voice or real-time assistance, tool-using workflows, moderation and safety filtering, and human-in-the-loop review.

Each pattern carries different implications:

- Structured extraction needs predictable fields and format checks.
- Retrieval-grounded answering needs approved sources and grounding tests.
- Tool-using workflows need permission boundaries and error handling.
- Human-in-the-loop review needs clear criteria for what humans approve, reject, or escalate.

The point of naming the pattern is to make those implications visible before the team moves deeper into design.

## Slide 28/50 - Pattern combinations

Many customer workflows require more than one pattern. When patterns combine, identify the role of each step and how the output of one step supports the next.

Procurement intake may combine classification to identify the request type, structured extraction to capture vendor and purchase details, retrieval-grounded answering to check policy, tool use to check vendor status, and human review for exceptions.

Customer-support triage may combine classification, retrieval-grounded answer suggestions, escalation routing, and moderation for sensitive content.

Employee policy support may combine retrieval-grounded answering, cited outputs, and human escalation for sensitive or ambiguous topics.

A pattern combination should not read like a loose list of capabilities. It should explain the workflow sequence. For each step, ask what the AI produces, what context or tool it needs, what could go wrong, what evidence would validate it, and where human review or escalation belongs.

## Slide 29/50 - Real-world example

A customer says: "We want to improve procurement intake for business users."

This request gives you a workflow area, but not yet a full recommendation. Procurement intake may involve collecting missing details, checking policy, identifying approval requirements, looking up vendor status, and routing exceptions.

A practical starting recommendation may be: to build the workflow as an application or process using the API — potentially alongside another user surface — when it must connect to procurement systems, produce structured outputs, draw on approved policy context, and route exceptions for human review.

A concise early recommendation could be: "The primary surface appears to be an application or process built with the API, potentially combined with another user surface. The workflow may need classification, structured extraction, retrieval from approved procurement guidance, tool use for vendor or approval data, and human review for exceptions. Before recommending a model class or pattern, validate which systems are in scope, which policy sources are approved, whether the AI can only read information or also trigger updates, and which exceptions require human approval."

That answer does not overpromise. It gives a direction, explains why, and names what still needs validation.

## Slide 30/50 - Recommended exercise: Route the workflow in three layers

This is an optional practice activity you can complete to apply what you just learned.

**Purpose:** Practice separating the user or product surface, capability or architecture, and deployment or operations decisions before shaping a model-class and pattern recommendation.

**Task:** Use the workflow below: A claims-processing application needs AI support. The workflow may include classifying claim type, extracting structured fields from claim documents, retrieving approved policy rules, preparing a short review note, and routing exceptions to a human review queue. The customer has not yet confirmed which systems are in scope, which policy sources are approved, or whether the AI can only prepare information for review versus update downstream systems.

First identify the primary user or product surface: ChatGPT Chat, ChatGPT Work, Codex, or an application or process built with the API. Then identify the capability or architecture pattern, the deployment and operations constraints, and any combined path across those layers.

Write a short routing and pattern note that captures:

- The primary user or product surface
- A likely solution pattern or pattern combination
- One reason the surface and capability combination may fit the workflow
- One deployment or operations question that would affect the recommendation

**Estimated time:** 2–3 minutes

Suggested output and reflection: Create a short routing and pattern note that names the primary surface, the capability or architecture pattern, any deployment or operations constraint, and the main validation question.

## Slide 31/50 - Knowledge check

**Question:** A customer wants AI embedded into a claims-processing application. It must classify claim type, extract fields, retrieve policy rules, and route exceptions to human review. What is the strongest early pattern recommendation?

- An open-model deployment decision made before the workflow and control requirements are clear
- Codex as the primary surface for the claims-processing workflow
- ChatGPT Chat as the only surface, with no application integration
- **An application or process built with the API, using classification, structured extraction, retrieval, and human review** ✓ Correct

The user or product surface is an application or process built with the API. Classification, structured extraction, and retrieval are capability or architecture decisions; human review, model hosting, and operational controls are deployment and operations decisions. The recommendation still needs validation before implementation.

## Slide 32/50 - Summary

In this module, you learned to start with the solution path, not the API model.

In the future, remember to first decide where the work should happen: ChatGPT Chat, ChatGPT Work, Codex, or an application or process built with the API. Then consider the capabilities, architecture, deployment, and operating choices required. Agentic behavior, open-model constraints, and combined solutions belong within those later decisions.

You also learned to describe API-led needs as solution patterns or pattern combinations. This keeps your recommendation tied to the workflow and makes your choices easier to explain.

## Slide 33/50 - Introduction (Module: Validate recommendations with eval evidence)

A model-selection and solution-pattern recommendation should be supported by evidence, especially when the workflow is complex, high-volume, customer-facing, or risk-sensitive.

This module introduces lightweight eval evidence. An eval is a structured way to test whether a model class, prompt approach, retrieval strategy, structured output, or tool-use pattern is likely to perform well enough for a specific workflow.

This course keeps evals at model-selection depth. You are not building a full eval program. You are identifying the evidence needed to support, revise, or escalate an early recommendation.

## Slide 34/50 - Why model selection needs evidence

A demo can show what is possible. Lightweight eval evidence helps show whether a recommendation is likely to work for the actual workflow.

Model selection should not rely only on intuition, preference, a single impressive answer, or the assumption that a more capable model will always be the best fit.

Representative examples help teams compare model classes, prompt approaches, retrieval strategies, structured output designs, tool-use behavior, safety behavior, latency, and cost.

The practical question is: "Is this recommendation good enough for this workflow, or do we need a different model class, pattern, safeguard, or escalation path?"

Evidence also helps you communicate responsibly. Instead of saying "this model should work," you can say what has been tested, what performed well, where the recommendation is still uncertain, and what should be validated next.

## Slide 35/50 - Define two or three success criteria

Success criteria describe what "good enough" means for the workflow. Choose two or three criteria that would meaningfully affect the recommendation. The criteria should come from the task shape, output requirements, risk level, and how the result will be used.

For a procurement intake workflow, classification accuracy, format compliance, and escalation behavior may matter more than writing style.

For a retrieval-grounded policy answer, groundedness, completeness, and cited support may matter more.

For a voice interaction, latency and turn-taking quality may be critical.

Avoid choosing too many criteria at this stage. A long list can make the eval feel precise while hiding the real decision. The best criteria are the ones that help you decide whether to support the recommendation, revise it, test an alternative, add safeguards, or escalate.

## Slide 36/50 - Draft a small eval seed set

An eval seed set is a small group of test cases that represents the workflow well enough to compare options.

A useful seed set includes normal cases and difficult cases.

The difficult cases matter because they reveal whether the recommendation can handle ambiguity, missing information, sensitive inputs, high-risk exceptions, required output formats, retrieval needs, and tool-use requirements.

For example: If you are testing support-ticket triage, do not only test clean tickets with obvious categories. Include tickets with multiple issues, unclear urgency, missing information, sensitive content, and cases that should be escalated.

A small representative eval set is more useful than a large vague one. The goal is not to prove perfection. The goal is to gather enough evidence to decide whether the starting recommendation is credible or whether another path should be tested.

## Slide 37/50 - Decide what evidence means

Before reviewing results, decide how you will interpret them. This prevents the team from overreacting to one strong answer or ignoring a meaningful failure.

For each recommendation, define what would support it, what would weaken it, and what would require escalation.

A recommendation may be supported if the model handles typical cases consistently, follows the required output format, and escalates high-risk cases correctly.

It may be weakened if the model performs well on easy examples but fails ambiguous cases, uses unsupported information, misses required fields, or handles escalation inconsistently.

Evidence should point to a responsible next step. That next step may be to recommend the starting approach, gather more targeted examples, test another model class, revise the pattern, add human review, or escalate to a specialist.

## Slide 38/50 - Real-world example

A team is choosing between an efficient model class and a reasoning-oriented model class for support-ticket triage.

The efficient model class may be faster and more cost-effective if tickets fit clear categories and the output is a simple structured label.

The reasoning-oriented model class may perform better when tickets are ambiguous, contain multiple issues, require policy interpretation, or need reliable escalation decisions.

A useful eval seed set would include simple tickets, ambiguous tickets, missing-information tickets, urgent tickets, and tickets that require escalation.

If the efficient model handles the representative set well enough, it may be the better operational recommendation.

If it fails on ambiguous or high-risk cases, the team may need a reasoning-oriented model, routing logic, stronger review gates, or a different pattern.

The recommendation should be based on performance against the workflow, not on assumptions about speed, cost, or capability.

## Slide 39/50 - Recommended exercise: Define eval evidence

This is an optional practice activity you can complete to apply what you just learned.

**Purpose:** Practice identifying lightweight evidence needed to validate an early model-selection and solution-pattern recommendation.

**Task:** Use the workflow below: A support team wants AI to triage inbound support tickets. The workflow should classify ticket topic and urgency, identify tickets that need escalation, and produce a structured routing label. The team is considering a model class that may work well for simple, high-volume routing, but some tickets may be ambiguous, urgent, missing information, or sensitive.

Reflect on what evidence would help you decide whether the starting recommendation is credible. Consider what "good enough" would mean for this workflow and what kinds of cases would test the recommendation fairly.

Write a short eval evidence note that captures:

- Two success criteria
- Three to five eval seed cases you would want represented
- One type of result that would support the recommendation
- One type of result that would weaken the recommendation
- One type of result that would require escalation or specialist review

**Estimated time:** 3–4 minutes

Suggested output and reflection: Create a short eval evidence note that defines how you would test whether the model-selection recommendation is credible enough to move forward.

## Slide 40/50 - Knowledge check

**Question:** A model performs well on easy examples but misses ambiguous requests and high-risk exceptions. What should you do next?

- Remove the high-risk examples from the eval set.
- Move to a multimodal model even if the task is text-only.
- **Treat the failures as routing evidence.** ✓ Correct
- Recommend it because the average result is strong.

Ambiguous and high-risk examples are exactly where eval evidence matters. Use the failures to gather more evidence, test alternatives, add safeguards, or escalate before recommending the approach.

## Slide 41/50 - Summary

In this module, you learned that model-selection and solution-pattern recommendations need evidence, not preference.

Lightweight eval evidence helps compare model classes, prompts, retrieval strategies, structured outputs, tool behavior, safety behavior, latency, and cost. In this course, the goal is not to build a full eval program. The goal is to identify enough evidence to support, revise, or escalate an early recommendation.

Good eval evidence includes typical cases and harder cases. The harder cases often reveal whether the recommendation is ready to move forward.

## Slide 42/50 - Introduction (Module: Apply the model-selection decision logic)

This module brings the course decision logic together.

You'll practice deciding the next responsible technical step for an early model-selection recommendation: whether to route toward a starting path, validate more evidence, or escalate for specialist review. The key question is: What can you responsibly recommend now, and what still needs validation?

## Slide 43/50 - Four-part model-selection decision structure

A strong early model-selection recommendation answers four questions. Use the structure below as a reference for organizing technical judgment.

- **Task shape and output requirements** — Clarifies the workflow label, likely task patterns, required output, context needs, risk signals, review needs, missing questions, and success criteria. Guiding question: What is the AI being asked to do?
- **Model class and decision drivers** — Clarifies the likely model class or classes, possible alternatives, reasoning depth, latency, cost, context, structured output, tool use, risk, and eval needs. Guiding question: Which model class is a plausible starting hypothesis, and what tradeoff matters most?
- **Solution routing and pattern** — Clarifies the primary user or product surface; capability or architecture requirements; deployment and operations constraints; selected pattern or pattern combination; why the route may fit; and what needs validation. Guiding question: Where should the person or workflow operate, what must the system do, and how will it run and be controlled?
- **Eval evidence and escalation** — Clarifies success criteria, representative seed cases, support signals, weakness signals, and escalation signals. Guiding question: What evidence is needed before the recommendation becomes customer-facing or implementation-ready?

Use this structure to prepare better questions and clearer handoffs. Do not use it to make unsupported product, pricing, compliance, security, architecture, implementation, availability, or exact-model claims.

## Slide 44/50 - How to use the decision structure in technical conversations

The four-part decision structure helps slow down model-selection conversations when stakeholders move too quickly from a customer need to a model name.

Use it to clarify: what the workflow needs, what the AI must produce, which model class is plausible, which solution path or pattern may fit, which tradeoffs matter most, what evidence supports or weakens the recommendation, and what must be validated before the recommendation moves forward.

For example, if a customer asks: "Which model should we use for supplier onboarding?"

Do not start with a model name. First clarify the workflow: what information is collected, which policy sources are approved, whether the AI reads or writes to systems, what human approval is required, and what eval evidence would show that the workflow is reliable enough.

The goal is not to fill in a document. The goal is to make a clearer, safer, and more technically defensible recommendation.

## Slide 45/50 - Boundary language for early recommendations

An early model-selection recommendation should be clear about its boundaries.

Use language like: "Based on the workflow described, this looks like a starting model class and solution pattern to validate, not a final implementation recommendation."

Or: "This recommendation identifies a plausible path and the evidence still needed. Product, security, data, compliance, architecture, or implementation details may require specialist review before customer-facing use."

Avoid language that makes the recommendation sound more final than it is.

Do not present an early recommendation as: a confirmed architecture, a production implementation plan, a security or compliance approval, a pricing or availability commitment, an exact model selection, a benchmark result, a full eval plan, a detailed API, tool-use, or integration design, or a customer-ready implementation specification.

## Slide 46/50 - Recommended exercise: Route, validate, or escalate

This is an optional practice activity you can complete to apply what you just learned.

**Purpose:** Practice choosing the next responsible technical step when a workflow has important unknowns.

**Task:** Use the workflow below: A customer says: "We want to automate supplier onboarding. The workflow includes collecting vendor details, checking policy requirements, preparing a decision-support note for review, and updating our procurement system."

The customer has not yet confirmed: which procurement systems are in scope, which policy sources are approved, whether the AI can only read information or also write back to systems, which steps require human approval, what eval criteria would prove the workflow is reliable enough, and who owns monitoring and improvement after launch.

Reflect on the next responsible technical step. Choose one of the following responses:

- Route: Make a starting path and pattern recommendation.
- Validate: Gather more evidence before recommending.
- Escalate: Bring in specialist review before continuing.

Then write a brief decision note that includes:

- Your chosen response
- One reason for that response
- One technical question you would ask next

**Estimated time:** 3–5 minutes

Suggested output and reflection: Create a brief decision note that explains whether you would route, validate, or escalate, and what you would ask next.

## Slide 47/50 - Knowledge check

**Question:** Match each item to the decision area where it belongs.

- Primary user or product surface, capability or architecture, deployment and operations, and pattern combination → **Solution path and pattern** ✓ Correct
- Plausible model class, alternative, decision drivers, and tradeoff → **Model class and decision drivers** ✓ Correct
- Success criteria, seed cases, support signals, weakness signals, and escalation signals → **Eval evidence and escalation** ✓ Correct
- Workflow label, task pattern, required output, context need, and risk signal → **Task shape and output requirements** ✓ Correct

All pairs matched correctly!

## Slide 48/50 - Summary

You can now apply model-selection decision logic to an early technical recommendation. A strong recommendation starts with task shape, compares plausible model classes, considers the right solution path and pattern, and names the evidence needed before the recommendation moves forward.

When the workflow is clear enough, route toward a starting model class, solution path, or pattern. When evidence or requirements are missing, validate before recommending. When product, security, data, compliance, architecture, or implementation details require specialist input, escalate.

The four-part decision structure from this module can help organize that thinking. It is not a separate artifact to complete. The goal is to make a clearer, safer, and more technically defensible recommendation.

## Slide 49/50 - Recap

In this course, you've learned that model-selection judgment depends more on routing, tradeoffs, validation, and escalation than on memorizing every model or product detail. Start with the task shape, use durable model-class language, and compare factors such as reasoning depth, latency, cost, context, tool use, structured outputs, risk, and eval needs.

As you take this learning forward, separate your solution routing into three decisions: the primary surface, the required capabilities or architecture, and the deployment and operations model.

Use repeatable solution patterns to describe how the system could work, validate recommendations with lightweight eval evidence, and escalate questions when specialist review is needed.

## Slide 50/50 - Congratulations

Congratulations, you've completed this course!

You now have a practical decision process for moving from a broad customer need to a more credible model-selection and solution-pattern recommendation.

Before selecting a model, question the right thing first: what work the AI must do, what output it must produce, and what would make the recommendation credible.

Use that approach in your next customer conversation, solution review, discovery moment, or implementation handoff.

Course completed. Next up in OpenAI Technical Practitioner: "Platform Capabilities and Developer Tools" (Course, 58 min) — Unlock the art of building AI-powered solutions by focusing on what workflows actually need, not just what's on a feature list. Learn to map platform capabilities like APIs, retrieval, tool use, agentic orchestration, evals, and developer tools to real business problems, always weighing tradeoffs, dependencies, and validation points. Practice making clear, defensible recommendations by starting with workflow roles, choosing the smallest responsible capability set, and escalating questions that require specialist review. By the end, you'll confidently select and combine platform building blocks to deliver practical, scalable, and right-sized solutions for any workflow.
