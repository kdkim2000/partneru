# AI Applications & Technologies

## Slide 1/26 - Title

AI Applications & Technologies

Created July 2026

## Slide 2/26 - Introduction

This course gives you an application-pattern lens for the broader PartnerU journey: how to recognize what AI is doing in a workflow, connect that pattern to possible OpenAI paths, and clarify what needs to be understood before a solution is recommended.

Customers often describe outcomes, not AI categories: faster answers, better summaries, useful content, code support, or workflow automation. This course helps you translate those asks into clearer application patterns without jumping too quickly to a product recommendation.

## Slide 3/26 - Overview

In this course, you'll learn a practical map of common AI applications and technologies, including generative AI, RAG, agentic AI, and AGI.

The focus is recognition: what the AI is doing, whether grounding may be needed, and which solution decisions should be separated next—user or product surface, capability or architecture, and deployment or operations. You will not design the full solution here; your job is to describe the application shape clearly and avoid overclaiming.

## Slide 4/26 - What you'll learn

By the end of this course, you'll be able to:

- Explain generative AI in plain language.
- Recognize common patterns, including text generation, summarization, classification, image generation, code assistance, and retrieval-grounded answers.
- Explain RAG conceptually and why grounding may matter.
- Separate user or product surface, capability or architecture, and deployment or operations when describing an application shape.
- Use careful language for agentic AI and AGI while clarifying what to ask next.

Let's get started!

## Slide 5/26 - Introduction (Generative AI and common application patterns)

When customers talk about AI applications, they often describe the result they want rather than the underlying pattern.

A customer might say:

- "We want help writing customer emails."
- "We need to summarize long reports."
- "We want to sort incoming support requests."
- "We need product images for campaigns."
- "We want to help developers move faster."
- "We need answers from our internal documents."

Each request points to a different kind of AI activity. In this module, you'll learn common application patterns in plain language. The goal is not to design or implement the application. The goal is to recognize what the AI is being asked to do.

## Slide 6/26 - Generative AI in plain language

Generative AI creates new content. That content might be text, images, code, audio, or a structured response. A user provides an input, such as a question, instruction, file, image, or business context. A model then produces an output based on that input.

For example:

A sales representative gives meeting notes and asks for a follow-up email.

A support manager gives a set of ticket summaries and asks for common themes.

A designer gives a description and asks for image concepts.

A developer gives natural-language instructions and asks for draft code or a test.

An analyst gives a document and asks for a shorter summary.

In all of these cases, the AI is not only retrieving a fixed answer from a database. It is generating a new output.

Generative AI is often used for drafting, rewriting, summarizing, answering, analyzing, creating, coding, and assisting workflows. This is why it can show up across many business functions.

But generated content can also be plausible without being correct or fully supported. A response may sound confident even when it is missing important context, using outdated information, or making an unsupported inference.

That is not a reason to avoid the technology entirely. It is a reason to ask better questions:

- What information should the AI use?
- What output should it produce?
- Who will review the output?
- What level of accuracy or grounding does the workflow require?

In this course, keep the focus at the application level. You do not need to explain generation techniques, model architecture, or implementation design.

## Slide 7/26 - Six common application patterns

Many customer requests can be understood through six common AI application patterns. These patterns describe what the AI is doing in the workflow.

Use this map to recognize the type of AI activity behind a customer request.

**Diagram:** Six-box grid labeled "What is the AI doing in the workflow?": Text generation, Summarization, Classification, Image generation, Code generation, Retrieval-grounded answers.

**Text generation**

Text generation means AI produces or rewrites text.

This can include drafts, messages, ideas, explanations, responses, outlines, emails, job descriptions, proposals, FAQs, or internal communications.

Example: A marketing team asks AI to draft three versions of a product announcement for different audiences. The pattern is text generation because the AI is producing new written content.

**Summarization**

Summarization means AI condenses longer information into a shorter version while preserving the main meaning. This can include meeting summaries, report summaries, document summaries, call summaries, research summaries, or executive briefings.

Example: A customer success manager asks AI to summarize a long account history into the main risks and next steps before a renewal meeting. The pattern is summarization because the AI is shortening and organizing existing information.

**Classification**

Classification means AI assigns a label or category to information.

The label might be sentiment, intent, topic, priority, risk level, product area, customer type, or request category.

Example: A support team asks AI to label incoming tickets as "billing," "technical issue," "account access," or "product feedback." The pattern is classification because the AI is sorting information into categories.

**Image generation**

Image generation means AI creates or edits images based on text or image inputs.

This can include concept images, campaign visuals, design variations, illustrations, mockups, or edits to an existing image.

Example: A brand team asks AI to generate visual concepts for a seasonal campaign based on a creative brief. The pattern is image generation because the AI is producing or modifying visual content.

**Code generation**

Code generation means AI writes, explains, modifies, reviews, or tests code based on natural-language instructions or existing code context.

This can include drafting functions, explaining errors, suggesting tests, reviewing code, refactoring, or helping developers understand a codebase.

Example: An engineering team asks AI to create test cases for a function and explain why the current code is failing. The pattern is code generation or code assistance because the AI is working with software development content.

**Retrieval-grounded answers**

Retrieval-grounded answers mean AI answers using relevant information retrieved from a knowledge source.

The knowledge source might be customer documents, internal policies, product information, release notes, knowledge bases, support articles, or approved business guidance.

Example: An employee asks, "What is our travel reimbursement policy?" and the AI answers using the company's approved policy documents.

The pattern is retrieval-grounded answers because the answer should be based on retrieved source information, not only the model's general knowledge.

## Slide 8/26 - Pattern Combinations in AI Workflows

A single workflow may use more than one AI application pattern. This is important because customers often describe a complete workflow, not a single AI task. If you force the workflow into only one category, you may miss what the AI is actually doing.

For example, a customer support assistant may:

- Retrieve product documentation.
- Generate an answer for the customer.
- Classify the request type.
- Summarize the conversation for the support team.
- Route complex cases to a human.

That is not just one pattern. It combines retrieval-grounded answers, text generation, classification, and summarization. It may also include a routing step, and routing describes what happens next in the workflow, not the type of AI activity itself.

At this stage, your job is not to design the full workflow. Your job is to describe the AI activity clearly. This gives later product and role-based conversations a clearer starting point, because different combinations of patterns may point to different OpenAI capabilities or solution paths.

A helpful question is: What is the AI being asked to produce, shorten, sort, create, code, or answer from source material?

**Real-world example**

A customer says:

> "We want AI to help our support team handle customer questions faster."

That statement is too broad on its own. It could mean many things.

A clearer application-pattern reading might be:

> "The customer wants AI to retrieve relevant product information, generate a draft answer, classify the request type, and summarize the interaction for the support team."

This is stronger because it identifies what the AI is doing.

It also makes the next questions easier to see:

- Which product information should the AI use?
- Which request categories matter?
- Which answers can be sent directly?
- Which answers need human review?
- What should happen when the retrieved information is missing or unclear?

## Slide 9/26 - Knowledge check

**Q:** A customer wants AI to read incoming support tickets and label each ticket by request type. Which application pattern is most directly involved?

- "Code generation, because the AI changes software code."
- **"Classification, because the AI assigns each ticket a category."** ✓ Correct
- "Text generation, because the AI drafts a new customer response."
- "Image generation, because the AI creates a visual output."

*Explanation: Classification is the pattern where AI assigns a label or category to information. In this case, the AI is sorting tickets by request type.*

## Slide 10/26 - Summary

Generative AI creates new content from an input, such as a question, instruction, file, or business context.

Common application patterns describe what the AI is doing in the workflow. The same customer request may involve one pattern or combine several, especially when the workflow includes source material, generated outputs, labels, summaries, or human review.

## Slide 11/26 - Introduction (Retrieval-augmented generation at a conceptual level)

Customers and partners may use the acronym "RAG" directly. A customer might say:

- "We need RAG for our internal knowledge base."
- "Can AI answer questions from our policy documents?"
- "We need answers based on our latest product information."
- "We don't want the AI making up answers from general knowledge."

These are common signals that the customer may need retrieval-grounded answers.

In this module, you'll learn what retrieval-augmented generation means at a conceptual level, why customers use it, and what it does not guarantee.

## Slide 12/26 - What RAG means

RAG stands for retrieval-augmented generation. In plain language, RAG combines two actions:

**Retrieval**

Finding relevant information from a knowledge source.

**Generation**

Using that information to produce a response.

A simple way to understand it is:

A user asks a question. A system retrieves relevant information from an approved source. The model uses that retrieved information to generate an answer.

This simple flow shows RAG as retrieval plus generation.

The knowledge source may include:

- Customer documents.
- Company policies.
- Product guides.
- Release notes.
- Knowledge-base articles.
- Approved business guidance.
- Other maintained or approved sources.

The term matters because customers may say "we need RAG" when they really mean:

"We need answers grounded in our own information."

That is the practical meaning to listen for.

At this level, you do not need to explain embeddings, vector databases, chunking, indexing, or retrieval configuration. Those are implementation topics. The recognition skill is simpler: notice when a customer wants generated answers to be based on specific source material.

## Slide 13/26 - Why customers use RAG

Customers often use RAG when general AI knowledge is not enough. A base model may be useful for many general tasks, but customer workflows often depend on specific, current, or approved information.

That information may live inside the customer's documents, systems, policies, or product materials. In later courses, you'll see this need appear across product surfaces and application designs—for example, in ChatGPT, an application built with the API, or an agentic workflow. The starting question is the same: what source information should the AI rely on?

RAG can help in several situations:

**Customer-specific knowledge**

A customer may need answers based on information that is specific to their organization.

Example: An HR team wants employees to ask questions about internal benefits policies. The answers should come from approved company policy documents, not generic HR guidance.

**Current information**

A customer may need answers based on information that changes over time.

Example: A product team wants internal teams to ask questions about the latest release notes. If the product changes frequently, the system needs access to maintained source material.

**Grounding**

RAG can reduce the chance that the model fills gaps with unsupported information because the answer is grounded in retrieved content.

This does not mean every answer will be perfect. It means the application has a way to bring relevant source material into the response.

**Transparency support**

Depending on the design, retrieval-grounded answers may make it easier to connect a response back to source material.

Example: An internal assistant answers an employee's policy question and points to the relevant policy section for review.

This can help users understand where the answer came from and when they may need to check the source directly.

## Slide 14/26 - What RAG does not guarantee

RAG is useful, but it is not a complete accuracy, safety, or governance solution.

It helps ground answers in relevant information, but several things still matter.

**RAG does not guarantee correctness**

A retrieval-grounded answer can still be wrong, incomplete, or misleading.

For example, the system might retrieve the wrong document section, miss an important exception, or generate an answer that overstates what the source says.

**Source quality matters**

If the source material is outdated, incomplete, conflicting, or wrong, the generated answer may also be poor.

A model cannot reliably produce a strong business answer from weak or unreliable source material.

**Retrieval quality matters**

The system must retrieve the right information for the model to use.

If the relevant policy, product note, or customer document is not retrieved, the generated answer may not have the context it needs.

**Review still matters**

High-stakes, sensitive, regulated, or customer-facing workflows may still require evaluation and human review.

For example, an AI answer about an internal travel policy may be lower risk than an answer about a legal interpretation, medical decision, financial recommendation, or customer commitment.

A safe way to explain RAG is:

"RAG can help ground answers in relevant source information, but it does not guarantee correctness by itself. The source material, retrieval step, and review expectations still matter."

## Slide 15/26 - Knowledge check

**Q:** A customer says employees need answers based on approved internal policy documents that change over time. Which statement is most accurate?

- **"RAG can ground answers in approved sources, but review still matters."** ✓ Correct
- "RAG removes the need to maintain accurate source documents."
- "RAG is mainly used to create visual policy examples."
- "RAG makes every policy answer correct without added review."

*Explanation: RAG can help retrieve relevant source information before generating an answer, but it does not guarantee correctness by itself.*

## Slide 16/26 - Summary

RAG means retrieval plus generation: relevant information is retrieved, then a model uses that information to generate a response.

RAG is useful when answers need to be based on customer-specific, current, or approved information. It helps with grounding, but it does not remove the need for strong source material or review where the workflow requires it.

## Slide 17/26 - Introduction (From application shape to solution decisions)

Once you can recognize the AI application pattern, the next step is to separate three decisions that are easy to collapse into one. This is not the same as making a final recommendation.

At this stage, ask:

- Where will the person or workflow primarily operate?
- What capabilities or architecture does the workflow require?
- Where will the application and model inference run, who will operate each component, and what controls will apply?

A customer may combine choices across these layers. In this module, you'll use them to describe an application clearly without treating product surface, capability, and deployment as the same decision.

## Slide 18/26 - Three decisions to separate

An application pattern tells you what the AI is doing. It does not, by itself, determine the product surface, capability design, or deployment model. Keep three decisions separate.

**User or product surface**

Ask: Where will the person or workflow primarily operate?

- ChatGPT Chat for collaborative thinking and creation.
- ChatGPT Work for delegated knowledge work.
- Codex for software engineering work.
- An application or process built with the OpenAI API for embedded or custom experiences.

**Capability or architecture**

Ask: What must the system do?

- Generate, summarize, classify, create images, or assist with code.
- Retrieve source information or return structured outputs.
- Use apps or tools, coordinate multiple steps, execute code, or automate part of a workflow.

**Deployment and operations**

Ask: Where will the application and model inference run, who will operate each component, how will data move, and what identity, permission, approval, retention, logging, and human-review controls will apply?

At this level, distinguish four common arrangements:

- OpenAI-hosted model inference: OpenAI serves the model through ChatGPT or the OpenAI API.
- Customer-cloud application: The customer application runs in the customer's cloud, while model inference may still be OpenAI-hosted.
- Third-party hosting service: Another provider operates a supported model or service. Provider-specific terms, controls, data paths, and support must be verified.
- Customer-run open-weight model: The customer or its chosen provider operates supported open-weight models on infrastructure it controls. Do not assume that proprietary OpenAI models used through ChatGPT or the OpenAI API are available for self-hosting.

A customer may combine choices across the three layers. Treat them as questions to clarify, not as mutually exclusive paths.

A customer-cloud application may still use OpenAI-hosted inference; customer-run deployment applies to supported open-weight models, not proprietary OpenAI models.

## Slide 19/26 - Signals that shape the decisions

Use the application pattern as the starting point, then clarify each decision layer.

**User or workflow**

Ask: Who is doing the work, and where should the experience live?

The answer may point toward different paths:

- Collaborative knowledge work may point toward ChatGPT Chat.
- Delegated knowledge work may point toward ChatGPT Work.
- Software engineering may point toward Codex.
- An embedded or custom experience may point toward an application built with the API.

These are recognition cues, not final recommendations.

**Required capabilities**

Ask: What must the system do?

The workflow may need:

- Generation
- Summarization
- Classification
- Image work
- Code assistance
- Retrieval-grounded answers
- Tool use
- Multi-step coordination

The same capability can appear across more than one product surface.

**Application, inference, and operations**

Ask:

- Where does the application run?
- Where does model inference occur?
- Who operates each component?
- How does data move?
- Which identity, permissions, approvals, retention, logging, and human-review controls apply?

A customer-cloud application can still call OpenAI-hosted inference. Customer control of the application does not mean the customer is hosting a proprietary OpenAI model.

**Grounding and source ownership**

Ask: What information does the AI need, which sources are approved, and who keeps them current?

A good recognition statement might sound like:

"This workflow combines retrieval-grounded answers and summarization. The first user experience may be in ChatGPT, while a later portal experience may be built with the API. The portal could run in the customer's cloud while model inference remains OpenAI-hosted. Before recommending a solution, we need to clarify source ownership, data flow, permissions, review points, and current product availability."

## Slide 20/26 - Examples of application shape and solution decisions

The same application pattern can lead to different choices across the three layers. Use the examples below to keep those choices separate.

**Delegated knowledge-work example**

A finance team wants AI to prepare a first draft of a month-end review from approved reports and a standard template.

The workflow may involve:

- Application patterns: Retrieval-grounded answers, summarization, and text generation.
- Additional capabilities: Multi-step coordination and artifact creation.
- User or product surface: ChatGPT Work, because the team wants to delegate a body of knowledge work and review a finished artifact.
- Deployment and operations considerations: Data permissions, workspace controls, approvals, and human review.

**Customer-cloud application example**

A product team wants AI-generated support answers inside its customer portal.

The solution may involve:

- Application patterns: Retrieval-grounded answers, classification, and text generation.
- User or product surface: An application built with the OpenAI API.
- Deployment: The portal runs in the customer's cloud, while model inference remains OpenAI-hosted.
- Deployment and operations considerations: Data flow, permissions, source quality, human review, and provider-specific controls.

**Customer-run open-weight example**

A customer requires model inference to run on infrastructure it controls.

The solution may involve:

- Application patterns: Summarization, classification, or retrieval-grounded answers.
- Deployment requirement: A supported open-weight model running on customer-controlled infrastructure, or a verified third-party hosting service.
- Important distinction: This does not mean that proprietary OpenAI models accessed through ChatGPT or the OpenAI API can be self-hosted.

**Depth boundary**

Detailed product fit, architecture, provider selection, pricing, and implementation planning are outside the scope of this course.

Your role is to identify the three decision layers, clarify what still needs to be validated, and involve the appropriate product or technical experts before any commitment is made.

## Slide 21/26 - A note on agentic AI and AGI

You may hear the terms "agentic AI" and "AGI" in customer conversations, internal conversations, or public discussions. These terms require careful, bounded language.

**Agentic AI**

Agentic AI is often used to describe AI systems that can work toward a goal by planning steps, using tools, coordinating actions, or contributing to larger workflows.

For example, a simple AI interaction might answer one question. An agentic workflow may involve several steps: gathering information, using a tool, drafting an output, checking progress, and asking for approval when needed.

Do not use "agentic" as a generic synonym for "advanced AI." The key idea is that the AI is doing more than producing a single response. It may be helping move work forward across steps or tools.

A helpful clarifying question is:

> "When you say agentic, what actions do you expect the AI to take, what tools would it use, and where should human oversight happen?"

That question keeps the conversation practical and avoids exaggerating what the technology can do.

**AGI**

AGI stands for artificial general intelligence.

Learners may hear AGI in relation to OpenAI's mission and long-term research direction. In customer conversations, treat AGI as a long-term research goal—not a current product label, deployment path, or customer solution.

Careful language:

- Do not describe today's products or customer applications as AGI.
- Do not promise AGI capabilities in customer workflows.
- Do not use AGI as a shortcut for "very capable AI."
- Keep the conversation focused on the actual workflow and application pattern.

## Slide 22/26 - Recommended exercise: Application-pattern analysis

This is an optional practice activity to help you apply what you just learned.

**Purpose**

This exercise helps you practice identifying the application pattern, grounding need, and three solution decisions in a realistic customer context.

**Task**

Review the customer context below.

A customer's HR operations team receives repeated manager questions about internal leave policies, onboarding steps, and employee documentation. Managers currently search through policy documents or ask HR business partners for help. The HR team wants AI to provide plain-language answers based on approved internal policy documents. For sensitive questions, they want managers to be directed to HR for review. The customer also mentions that, later, they may want the experience inside their manager self-service portal.

Apply the application-pattern lens:

- What workflow is the customer trying to improve?
- Which AI application pattern, or combination of patterns, is involved?
- Are retrieval-grounded answers likely needed? Why or why not?
- Which user or product surface, or combination of surfaces, may fit the workflow?
- What capabilities or architecture does the workflow require?
- What deployment and operations questions should be clarified before making assumptions?

**Estimated time**

4-5 minutes

**Suggested output**

Write a short application-pattern assessment using this structure:

> "The workflow is [workflow]. The likely AI application pattern is [pattern or combination of patterns]. Retrieval-grounded answers [are / are not] likely needed because [reason]. The likely user or product surface is [surface], while the required capabilities include [capabilities]. The deployment and operations questions to clarify are [questions]. The next person or source needed for validation is [owner or source]."

**Example response**

> "The workflow is manager access to HR policy information. The likely AI application pattern combines retrieval-grounded answers, text generation, and possibly classification for sensitive questions that should be directed to HR. Retrieval-grounded answers are likely needed because responses should come from approved internal policy documents, not general knowledge. The initial user or product surface could be ChatGPT for direct employee use, while a later manager-portal experience could be built with the API. The required capabilities include retrieval, generation, permissions-aware access, and escalation to a human. The deployment and operations questions include where the portal and model inference will run, who maintains the source documents, how data moves, and where human review is required. Product and technical owners should validate the final surface and operating model."

## Slide 23/26 - Knowledge check

**Question:** A customer runs a support application in its own cloud and uses the OpenAI API for model responses. Which statement is most accurate?

- Using the API removes the need to clarify data flow, permissions, or human review.
- Because the application runs in the customer's cloud, the customer is self-hosting a proprietary OpenAI model.
- A customer-cloud application must use a customer-run open-weight model.
- **Application hosting and model inference are separate decisions: the application can run in the customer's cloud while model inference remains OpenAI-hosted. (Correct)**

**Explanation:** Application hosting and model inference are separate. A customer application can run in the customer's cloud while calling OpenAI-hosted model inference through the API. Customer-run open-weight models are a different deployment arrangement.

## Slide 24/26 - Summary

Application patterns describe what the AI is doing in a workflow. Solution routing requires three separate decisions: user or product surface, capability or architecture, and deployment or operations. A customer may combine choices across those layers.

A customer-cloud application can still use OpenAI-hosted model inference. Customer-run deployment applies to supported open-weight models or other verified arrangements—not automatically to proprietary OpenAI models used through ChatGPT or the OpenAI API. At this level, identify the questions, and verify current product, provider, and control details before making commitments.

## Slide 25/26 - Recap

AI application conversations are clearer when you focus on what the AI is doing in the workflow. Use the application-pattern lens to recognize whether AI is generating text, summarizing information, classifying content, creating images, assisting with code, or answering from retrieved source material. If a workflow combines patterns, name the combination.

Use RAG language carefully. RAG can help ground answers in customer-specific or approved information, but it does not guarantee correctness by itself.

Then separate three decisions: where the workflow operates, what capabilities it needs, and where the application and inference run. A customer-cloud application may still use OpenAI-hosted inference; customer-run deployment does not mean self-hosting proprietary OpenAI models. Stay at recognition depth and verify details before making commitments.

## Slide 26/26 - Congratulations

Congratulations, you've completed this course!

You can now use the application-pattern lens to make AI conversations clearer. Keep asking: What workflow is the customer trying to improve? What is the AI being asked to do? Does the answer need customer-specific grounding? Where should the person or workflow operate? What capabilities are required? Where will the application and model inference run, who will operate each component, and what still needs validation?

As you continue through PartnerU, this lens will help you connect customer workflows to possible OpenAI solution paths, use case patterns, and role-based next steps while keeping the conversation grounded in what the customer needs and what still needs clarification.

**Course completed**

Next up in OpenAI Foundational Knowledge: **AI Infrastructure & Implementation** (Course, 40 min) — Unlock the essentials of AI infrastructure and implementation with a practical, jargon-light approach. Discover how to spot early feasibility signals, understand the difference between training and inference, and get familiar with key hardware terms like GPU, TPU, and NPU. Explore the trade-offs between cloud, on-prem, and edge environments, and learn how latency, volume, and data privacy shape real-world AI deployments. Use a simple recognition lens to ask the right questions early, ensuring you know when to involve technical, security, or governance experts for successful AI outcomes.
