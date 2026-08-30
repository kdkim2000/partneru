# Core AI & Machine Learning Fundamentals

## Slide 1/39 - Title

Core AI & Machine Learning Fundamentals

Created July 2026

## Slide 2/39 - Introduction

This course gives you a practical vocabulary for understanding AI and machine learning terms in partner and customer conversations.

You'll build enough fluency to connect core concepts to OpenAI capabilities, real workflows, and later PartnerU learning—without going into implementation detail.

## Slide 3/39 - Overview

Terms like AI, machine learning, deep learning, neural networks, and models show up often in customer and partner conversations.

In this course, you'll learn how those terms relate, what "a model" can mean in different contexts, and how to describe AI capabilities clearly.

You'll also practice a simple communication habit: Describe the capability first, and verify specific model names when they matter. That habit helps keep conversations accurate as products and model options evolve.

## Slide 4/39 - What you'll learn

By the end of this course, you'll be able to:

- Explain how AI, machine learning, deep learning, and neural networks relate.
- Distinguish a trained AI model from a specific named model option.
- Describe inputs, outputs, and context at a high level.
- Recognize terms like transformer, foundation model, and frontier model.
- Describe model capability first and verify model names before making commitments.
- Recognize supervised, unsupervised, and reinforcement learning at a terminology level.
- Apply the vocabulary to a short system description without implementation detail.

Let's get started!

## Slide 5/39 - Introduction (How core AI terms relate)

AI, machine learning, deep learning, neural networks, and large language models are related, but they are not interchangeable.

This module gives you a simple hierarchy you can reuse when customers or internal teams use "AI" loosely. This isn't a memory test. The goal is to understand the relationship between the terms well enough to clarify what someone means.

## Slide 6/39 - The AI, ML, deep learning, and neural network hierarchy

**Artificial intelligence, or AI, is the broadest term**

AI refers to machines or software performing tasks that appear intelligent—things like understanding language, recognizing patterns, making predictions, planning, or generating content.

**Machine learning, or ML, is a subset of AI**

Machine learning refers to systems that learn patterns from data instead of relying only on fixed rules. For example, a machine learning system could learn from historical examples to identify patterns or make predictions.

**Deep learning is a subset of machine learning**

Deep learning uses neural networks with many layers to learn complex patterns from large amounts of data. It's important because many modern AI capabilities rely on it, including language, image, audio, and multimodal systems.

**Neural networks are model structures made up of connected layers**

They are commonly used in deep learning and help systems learn patterns from data. You do not need to understand the technical mechanics of neural networks in this course. For now, just know that neural networks are a structure used by many deep learning systems.

A simple way to remember the hierarchy is:

- AI is the broad category.
- Machine learning sits inside AI.
- Deep learning sits inside machine learning.
- Neural networks are the structure deep learning commonly uses.

The diagram below shows how these terms relate. The key point is that they are connected, but they do not all mean the same thing.

**Diagram:** Nested concentric circles showing (outer to inner): Artificial Intelligence (AI) — Broadest field; Machine Learning (ML) — Learns from data; Deep Learning — Uses layered models; Neural networks — a common model structure used in deep learning.

## Slide 7/39 - Why the hierarchy matters in partner conversations

Customers can use the word "AI" to mean many different things.

A customer might say:

> "We already use AI for fraud screening."

That could mean several things. They might be referring to fixed business rules, a machine learning classifier, a generative AI workflow, or a combination of different systems.

At this stage, don't correct the customer or prove you know the exact terminology. Your goal is to clarify what they mean so the next conversation is more useful.

A helpful response might be:

> "When you say AI for fraud screening, are you referring to fixed rules, a model that learns from historical data, or a newer generative AI workflow?"

That kind of question keeps the conversation grounded. It also helps you avoid assuming that every AI use case involves the same technology or implementation path.

## Slide 8/39 - Where large language models fit

Large language models, often called LLMs, are one important type of AI model.

An LLM is a type of deep learning model trained to process and generate language.

LLMs are behind many familiar generative AI experiences, including chat, drafting, summarization, reasoning support, and content generation.

Some modern LLMs are multimodal, meaning they can work with more than one type of input—such as text, images, or audio—depending on the model and product.

You'll hear about LLMs often because many modern AI experiences use language as the way people interact with intelligence at work.

Users might ask a question, request a summary, draft a response, or analyze information. But LLMs are not the whole of AI.

Many AI systems do not center on language generation.

Some systems classify transactions, detect patterns, recommend items, analyze images, process audio, or support decision workflows. Some systems combine multiple AI capabilities.

A customer-facing clarification could sound like:

> "LLMs are one important type of AI model, especially for language-based tasks. They are not the whole field of AI."

## Slide 9/39 - Knowledge check

**Q:** Which of the following statements about LLMs are accurate based on the text?

- "AI, machine learning, deep learning, and neural networks are separate terms with no relationship."
- "Large language models are outside AI because they focus mainly on language tasks."
- "Machine learning is the broadest category, and AI is a smaller type within machine learning."
- **"AI is the broadest category. Machine learning sits inside AI, deep learning sits inside machine learning, and neural networks are a common structure used in deep learning."** ✓ Correct

*Explanation: This correctly places the terms in a simple hierarchy and keeps them from being used interchangeably.*

## Slide 10/39 - Summary

Several common AI terms are connected, but they do not mean the same thing. AI is the broadest category. Machine learning is a subset of AI. Deep learning is a subset of machine learning. Neural networks are structures commonly used in deep learning.

LLMs are an important type of AI model, especially for language-based work. Some modern LLMs are also multimodal and can work with inputs such as text, images, or audio, depending on the model and product. LLMs are still not the whole field of AI.

The most important partner habit is clarification. When someone says "AI," listen for what they actually mean before assuming which technology or solution path is involved.

## Slide 11/39 - Introduction (What "a model" means)

"Model" is one of the most important words you will hear in AI conversations. It is also one of the easiest words to misunderstand because people use it in more than one way.

A customer might use "model" to mean an AI system generally. A technical team may use "model" to mean a specific named option selected in a product or API. This module helps you recognize which meaning is being used.

## Slide 12/39 - One word, two common meanings

Generally, a model is a trained system that maps inputs to outputs based on patterns it has learned.

For example, a model might receive a piece of text and generate a summary.

It might receive an image and identify what is in it. It might receive structured data and classify a record.

In a more specific product or platform conversation, "model" can also mean a named model option used in a product, interface, or API configuration.

Be mindful that two people may use the same word differently.

A customer might ask:

> "Which model should we use?"

They might mean:

- What kind of AI system do we need?
- Which named model option should our developers configure?
- Which model is available in a product experience?
- Which model best fits a cost, latency, reasoning, or multimodal requirement?

Before answering, listen for the meaning. A useful clarifying question is:

> "When you say model, do you mean the AI system generally, or a specific model option you are using?"

## Slide 13/39 - Inputs, outputs, and context

At a high level, models receive inputs, process them, and produce outputs. Inputs are what the model receives.

Inputs may include text, images, audio, structured data, instructions, examples, uploaded files, or information made available through an approved workflow or connection.

Outputs are what the model produces.

Outputs may include text, summaries, classifications, recommendations, images, audio, or tool-use requests that a connected product or workflow may turn into actions within the right boundaries.

Context is the information the model uses to shape its response.

Context may include:

- The user's instructions
- Documents or examples
- Conversation history
- Connected data
- Workflow information
- Organizational knowledge
- Policies
- Permissions
- Details from connected systems

This affects business conversations. A model does not automatically know a customer's private documents, internal policies, product catalog, or workflow rules. That information must be provided through the right product setup, approved connection, retrieval method, or workflow.

Frame it like this to customers:

> "The model can use relevant customer information when it is provided through the right setup."

This is one reason workflow context matters. Before discussing a product or model, clarify what information the AI needs, where that information comes from, and who should be allowed to use it.

Avoid saying:

> "The model already knows your business."

That wording can overstate what the model has access to and create confusion about data, permissions, and governance.

## Slide 14/39 - Model versus product, platform, or API surface

Let's get clear on some more distinctions.

**Model**

The trained system that processes inputs and generates outputs.

**Product or workspace**

The user-facing experience where people interact with AI.

**API surface**

The developer-facing interface used to build AI into products or workflows.

ChatGPT is an example of a product experience where users can interact with AI through natural language and supported tools.

The same product or API surface may support different models.

The same model may also be available through different experiences, depending on product, plan, configuration, or availability.

You do not need to understand API configuration, endpoint selection, or implementation details in this course. The key is to avoid confusing the model with the experience or interface where the model is used.

This distinction also helps you understand where different OpenAI capabilities may fit.

ChatGPT, Codex, and applications built with the API may expose or use models differently. Agent capabilities and the decision to deploy open-weight models are separate considerations that depend on the workflow and operating environment.

## Slide 15/39 - Knowledge check

**Q:** A customer asks, "Which model will our employees use in ChatGPT?" What should you clarify first?

- **"Whether they mean a trained AI system, a specific named model option, or ChatGPT as the product experience."** ✓ Correct
- "Whether ChatGPT automatically has access to every internal business document."
- "Whether their employees know how to build a model from the beginning."
- "Whether all AI systems use the same model architecture and learning method."

*Explanation: This separates the model from the product experience and helps you avoid answering a different question than the customer intended.*

## Slide 16/39 - Summary

"Model" means two related but different things.

In a general AI conversation, a model is a trained system that maps inputs to outputs. In a product or platform conversation, "model" may refer to a specific named option.

It is also important to separate the model from the product or API surface where it is used. This helps keep customer questions clear and reduces assumptions about access, availability, or implementation.

## Slide 17/39 - Introduction (Model vocabulary partners may hear)

You may hear model vocabulary that sounds technical: transformer, foundation model, and frontier model.

In this course, you only need recognition-level understanding. These terms describe different dimensions of a model. They are not synonyms, and they should not be used interchangeably.

## Slide 18/39 - Transformer

A transformer is a way of structuring a model. It is not a product. It is not a specific named model. It describes something about how a model is built.

Transformers are important because they helped enable major progress in language, code, and multimodal AI systems.

Many modern AI systems use transformer-based approaches or ideas that build on them.

For partner conversations, the main point is simple:

"Transformer" tells you something about model architecture. It does not tell you whether the model is the right fit for a customer use case.

## Slide 19/39 - Foundation model

A foundation model is a general-purpose AI model that adapts to support many different tasks.

This term describes breadth of use.

A foundation model supports tasks such as generating text, summarizing information, analyzing data, answering questions, supporting coding workflows, or working with other capabilities depending on the product or system it is part of.

Foundation models are significant because they can often be adapted or directed for different business workflows.

They may be used through prompting, tools, retrieval, fine-tuning, or product-specific workflows.

But "foundation model" does not automatically mean OpenAI. It also does not automatically mean the model is the best fit for every customer use case.

A simple way to frame this is:

"Foundation" points to breadth of use. It does not make the model a customer-ready solution by itself.

## Slide 20/39 - Frontier model

A frontier model is a point-in-time label for a model considered among the most capable available when the comparison is made.

This term describes current capability level.

Customers ask about frontier models when they want the latest capability, stronger reasoning, advanced performance, or support for more complex work.

The important point is that "frontier" is a moving label. Which models are considered frontier can change as new models are released and capabilities improve.

That makes verification important.

Before naming a specific frontier model in a customer-facing commitment, use current official sources.

## Slide 21/39 - Keeping the terms separate

These three terms describe different things:

**Transformer**

How the model is built.

**Foundation model**

How broadly the model can be used or adapted.

**Frontier model**

How advanced or capable the model is at a given time.

They are not interchangeable.

A model could be described by more than one of these terms, but each term answers a different question.

When a customer uses one of these terms, clarify which dimension they are asking about:

- Are they asking about architecture?
- Are they asking about breadth of use?
- Are they asking about current capability?
- Are they asking which model option should be used in a specific product or technical setup?

That clarification keeps the conversation accurate without requiring you to go into implementation detail.

## Slide 22/39 - Knowledge check

**Q:** Match each term to what it describes.

- "Foundation model" → **How broadly a model can be used or adapted** ✓ Correct
- "Transformer" → **How a model is built** ✓ Correct
- "Frontier model" → **How advanced or capable a model is at a given time** ✓ Correct

*All pairs matched correctly!*

## Slide 23/39 - Summary

The main takeaway is that these three terms—transformer, foundation model and frontier model—answer different questions.

When a customer uses one of them, clarify what they are asking about before moving toward a product or model recommendation.

## Slide 24/39 - Introduction (Describe capability first, verify names when needed)

A lot of things change over time: model names, model families, recommended choices, pricing, availability, and product support to name a few.

That creates a communication risk. If you lead with a specific model name too early, your language may become brittle or inaccurate. If you describe the needed capability first, your explanation stays more durable and more connected to the customer's actual problem.

This module introduces a practical habit: Describe capability first. Verify exact model names when they matter.

## Slide 25/39 - Why this habit matters

Customers usually care less about the name of a model than about what the AI system needs to do.

They may need a model that can summarize a large volume of customer feedback. They may need stronger reasoning for multi-step analysis.

They may need a cost-optimized option for a high-volume workflow. They may need multimodal capability, such as working with both text and images.

Those are capability needs.

Capability-first language helps you keep the conversation focused on the work being supported, not just the technology label.

It also leaves room for technical validation when exact choices matter.

A useful partner standard is:

Be specific when specificity is required. Stay capability-led when the exact name is not the point.

## Slide 26/39 - Capability-first examples

Here are examples of capability-first language.

Instead of saying: "We should use this exact model for summarizing all customer feedback."

Say: "We need a model suited for summarizing high volumes of customer feedback. We should verify the exact model option before making a recommendation."

Instead of saying: "This named model is always best for reasoning."

Say: "This workflow may require stronger reasoning for multi-step analysis. We should confirm the best current model option for that requirement."

Instead of saying: "Use the cheapest model."

Say: "This looks like a high-throughput workflow, so cost and latency will matter. We should look for a cost-optimized model that still meets the quality requirement."

Instead of saying: "This model can handle everything."

Say: "The workflow may need multimodal capability, such as processing both text and images. We should confirm which current model options support that requirement."

Capability-first language does not make the conversation vague. It makes the conversation more accurate. It focuses on what the customer needs before locking into a named model.

## Slide 27/39 - When exact model names matter

**Sometimes exact model names do matter**

- When a developer is implementing or configuring a system.
- When pricing, cost, throughput, latency, or availability is being discussed.
- When a partner is making a specific commitment to a customer.
- In technical documentation that must remain accurate over time.

Use exact model names when they are required for:

- Code or configuration
- Pricing or commercial discussion
- Availability or plan guidance
- Customer commitments
- Implementation documentation
- Formal solution recommendations

When exact names matter, verify them against current official sources before committing.

A helpful way to think about it is:

Capability-first language is good for discovery and early explanation. Exact model names require verification before commitment.

## Slide 28/39 - Recommended exercise: Rewrite model-specific language

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice converting model-name-first statements into capability-first language that stays accurate as products and model options evolve.

**Task**

Review each statement below. Rewrite it so it focuses on the capability needed, not an unnecessary model-name commitment. Then note whether the exact model name would need to be verified before use.

- "We should use the latest model for every customer support workflow."
- "This named model is the best choice for every summarization use case."
- "The customer needs this exact model because their documents are long."
- "This workflow just needs the cheapest model."

**Estimated time**

5 minutes

**Suggested output and reflection**

For each statement, write a capability-first version and add one sentence explaining when you would verify the exact model name.

Example rewrite: "The customer support workflow might need a model that can summarize customer conversations accurately and handle the expected volume. Let's verify the exact model option before making an implementation or pricing recommendation."

## Slide 29/39 - Knowledge check

**Q:** Which statement is the best example of capability-first model language?

- **"This workflow needs reliable summarization at high volume; we should verify the exact model option."** ✓ Correct
- "This workflow should start with a model name before the customer need is clearly understood."
- "This workflow does not require model verification because documentation details matter less."
- "This workflow should use the newest model because newer models are always the safest choice."

*Explanation: This statement focuses on the capability required and includes the right verification habit before making a specific commitment.*

## Slide 30/39 - Summary

Remember this communication habit: describe capability first, then verify exact model names when needed.

Capability-first language keeps the conversation focused on what the customer needs the AI system to do. Exact model names still matter for implementation, pricing, availability, and formal commitments.

The key is knowing when to stay capability-led and when to verify a specific model option before giving guidance.

## Slide 31/39 - Introduction (How Systems Learn)

You may hear people describe different ways AI systems learn.

This module introduces three common terms at recognition depth only:

- Supervised learning
- Unsupervised learning
- Reinforcement learning

You do not need to design a training pipeline or explain detailed learning mechanics. You just need to recognize the basic difference between these terms when they appear in customer, partner, or technical conversations.

## Slide 32/39 - Supervised learning

Supervised learning uses examples with known answers.

The system learns from input-output pairs. That means it sees examples where the correct label, category, or value is already known.

A simple analogy is a learner practicing with an answer key. The learner sees the question, checks the correct answer, and gradually learns the pattern.

For example, a supervised learning system might learn from historical records where each example includes both the input and the known outcome.

Over time, the system learns patterns that help it classify or predict new examples.

A simple one-liner is this:

"Supervised learning is useful when examples and expected outputs can be clearly defined."

## Slide 33/39 - Unsupervised learning

Unsupervised learning looks for patterns in data without a provided answer key.

At a high level, the system groups, clusters, or identifies structure in unlabeled data.

The system is not being shown the correct answer for each example. Instead, it is looking for patterns that may be useful.

For example, an unsupervised learning system might group similar items together based on patterns in the data. The value is in discovering structure, not predicting a known label.

Think of it like exploring a city without a map and gradually noticing neighborhoods or routes.

Try explaining it like this:

"Unsupervised learning is useful when the goal is to discover structure or patterns, not predict a known answer from labeled examples."

## Slide 34/39 - Reinforcement learning

Reinforcement learning improves through feedback over a sequence of actions.

The system learns which actions lead to better outcomes over time. This is different from learning from a static set of labeled examples.

The system is improving behavior based on feedback from actions and outcomes—like learning through trial and adjustment.

Reinforcement learning is often associated with control problems, sequential decision-making, and systems where actions affect future states.

Here's how you could frame it:

"Reinforcement learning is about improving behavior through feedback over time, not simply learning from a fixed dataset."

## Slide 35/39 - Recognizing mixed systems

Real AI systems may combine multiple approaches. A system may use one approach during development, another approach for refinement, and additional processes for evaluation, safety, or product behavior.

In customer conversations, you do not need to force every system into one pure category.

Instead, focus on the main learning idea being discussed.

A useful question is:

"Is the system learning from labeled examples, finding patterns without labels, or improving through feedback over time?"

That question helps you recognize the difference without overreaching into technical design. It also reminds you that real customer solutions may combine several techniques or portfolio components, so the right next step is often clarification rather than a quick label.

## Slide 36/39 - Knowledge check

**Q:** Match the concepts related to problem-solving steps and understanding customer solutions:

- "Improves behavior through feedback over time" → **Reinforcement learning** ✓ Correct
- "Finds patterns without a provided answer key" → **Unsupervised learning** ✓ Correct
- "Combines more than one approach in a real system" → **Mixed system** ✓ Correct
- "Learns from examples with known answers" → **Supervised learning** ✓ Correct

*All pairs matched correctly!*

## Slide 37/39 - Summary

The main takeaway is that "learning" can mean different things in AI. Some systems learn from examples where the expected answer is known. Others look for patterns in data without an answer key. Some improve through feedback over time.

In partner conversations, you do not need to classify every system perfectly. What matters is recognizing the kind of learning being discussed and asking the right follow-up questions when clarification is needed.

## Slide 38/39 - Recap

In this course, you built a practical vocabulary for core AI and machine learning concepts.

You learned how AI, machine learning, deep learning, neural networks, and LLMs relate. You also practiced using "model" carefully: it can mean a trained AI system, or a specific named option in a product, platform, or API.

You also reviewed terms like transformer, foundation model, and frontier model, and recognized supervised, unsupervised, and reinforcement learning at a high level.

## Slide 39/39 - Congratulations

Congratulations, you've completed this course!

You now have a shared vocabulary for discussing AI concepts more clearly in partner and customer conversations.

As you continue through PartnerU, use this foundation to listen for what someone means, stay at the right level of detail, and connect AI capabilities to real workflows without moving too quickly to a specific model, product, or solution path.

The main habit to carry forward: clarify what people mean, describe the capability needed, and verify exact model names when details matter.
