# Deep Research, Images, Distillation, and Specialized API Pattern Fit

## Slide 1/42 - Title

Created July 2026

## Slide 2/42 - Introduction

Specialized API patterns can unlock powerful workflows—but only when the workflow truly needs them.

This course introduces specialized API pattern selection as fit and validation judgment. You'll learn how to decide when Deep Research through the Responses API, image understanding, image generation or editing, distillation, or optimization approaches are justified beyond standard API patterns.

These specialized API patterns are builder and integration choices. They can help organizations embed intelligence into products, operations, and customer experiences where standard patterns are not enough. But they also add validation burden, operational complexity, data and rights questions, review needs, and escalation responsibilities.

## Slide 3/42 - What you'll learn

By the end of this course, you'll be able to:

- Assess whether a specialized API pattern is justified by workflow need, evidence, tradeoffs, and validation burden.
- Evaluate Deep Research as a Responses-based pattern for source quality, approved data/tools, traceability, synthesis risk, long-running execution, and review ownership.
- Evaluate image understanding, generation, and editing workflows for fit, surface choice, rights, accessibility, safety, review needs, and approved use.
- Decide whether distillation or optimization is justified after simpler improvements and baseline evidence are considered.
- Produce a Specialized API Pattern Fit Assessment with alternatives, tradeoffs, validation conditions, risks, exclusions, and recommendation.

## Slide 4/42 - What you'll produce

Your course output is a Specialized API Pattern Fit Assessment.

Your assessment will include:

- Workflow need and standard-pattern alternative
- Candidate specialized pattern
- Pattern-specific fit evidence
- Adjacent pattern dependencies
- Data, quality, rights, safety, and governance considerations
- Tradeoffs and operational complexity
- Validation and escalation plan
- Risks, exclusions, and recommendation

You'll optionally build toward this assessment by completing recommended exercises across the course. The exercises are not submissions or graded activities. They are practice opportunities to help you apply the decision logic.

Let's get started!

## Slide 5/42 - Introduction (Module: Evaluate Deep Research workflows)

Some workflows require more than a quick answer. They require gathering information from multiple sources, comparing evidence, resolving conflicts, synthesizing findings, and producing an output that a human can review.

That is where Deep Research may be relevant. In this module, you'll evaluate Deep Research as a specialized Responses-based pattern.

Focus on workflow fit, source and tool selection, prompt completeness, background execution, validation, review ownership, and whether the current model and tool guidance has been verified immediately before publication or customer recommendation.

## Slide 6/42 - Key definitions

Before you start to evaluate Deep Research, there are some common definitions you need to be aware of.

These terms will help you move through the course:

**Standard API pattern**

A common solution approach such as model-only generation, structured output, retrieval-grounded response, tool or action workflow, agentic workflow, realtime or multimodal experience, or a hybrid of these. Standard does not mean basic. It means the solution can be achieved without adding a specialized capability or optimization layer.

**Specialized API pattern**

A more targeted approach used when a standard pattern is not enough. In this course, specialized patterns include Deep Research through the Responses API, image understanding, image generation and editing, distillation, optimization, and other OpenAI-confirmed specialized patterns.

**Deep Research workflow**

A documented product pattern built through the Responses API. A Deep Research workflow uses the Responses API to support multi-step research tasks that require source gathering, synthesis, evidence review, traceability, and human review. It is most relevant when a standard response or simple retrieval-grounded answer is not enough because the workflow must search or browse across approved source types, compare evidence, handle conflicts, and produce a reviewable output.

**Image understanding or vision workflow**

Uses an image as input so the model can analyze visual information and return text, structured output, or a review-support signal. Examples include interpreting a screenshot, reviewing a product photo for listing quality, extracting visible details from a document image, identifying visual issues in an uploaded asset, or summarizing what a diagram appears to show.

**Image generation or editing workflow**

Creates a new image or changes an existing image. Examples include product-visual drafts, design concepts, diagram drafts, internal visual guides, edited reference images, or visual assets for review.

**Combined visual workflow**

Some customer workflows include both image understanding and image generation or editing. Treat these as connected but separate steps, not as one undifferentiated Images category. For example, a retail workflow might analyze uploaded product photos for listing quality and also generate internal draft visuals for merchandising review. The analysis step is an image understanding workflow. The draft-visual step is an image generation or editing workflow.

**Validation burden**

The additional proof required before a specialized pattern can be recommended responsibly. It may include source review, evals, quality thresholds, rights checks, safety review, accessibility review, cost and latency evidence, maintenance ownership, or escalation approval.

**Standard-pattern alternative**

The lower-complexity option you should consider before recommending specialization. It might be a structured output, a retrieval-grounded response, a tighter tool contract, a better prompt, a model or capability selection change, or a human-assisted workflow.

## Slide 7/42 - Understanding the Responses-based Deep Research surface

The current Deep Research implementation pattern for this course is a Responses API workflow.

You should therefore first understand the Deep Research architecture decision in this context:

The application sends a fully formed research task to the Responses API.

This enables the appropriate supported data sources and tools, and receives a research output that should include evidence or source visibility for review.

Deep Research also involves data sources and tools. A Deep Research workflow should define which source or tool types are approved for the task.

Some common source and tool decisions include:

| Source or tool area | What it is used for | What to validate |
|---|---|---|
| Web search | Gathering current public information from external sources. | Source authority, source relevance, source freshness, citation visibility, and whether public-web research is appropriate for the workflow. |
| File search | Searching approved internal or customer-provided documents through approved vector stores. | Source approval, permissions, freshness, completeness, metadata, and whether users are allowed to access the retrieved content. |
| Remote MCP servers | Searching approved private data sources through a trusted remote MCP server that implements the required search-and-fetch interface. | Trust boundary, server approval, data shared with the server, tool-call review, and whether sensitive data could be exposed. |
| Code interpreter | Analyzing data, calculations, files, or structured information as part of the research task. | Whether analysis is needed, whether input data is approved, whether outputs are reproducible enough for review, and whether the results need human validation. |

A Deep Research request uses the Responses API and must include at least one approved data source—web search, file search over vector stores, or a remote MCP server that implements the required search-and-fetch interface. Code interpreter can be added for analysis.

Other tools, including function calling, are not supported. Make sure to re-check the current official Deep Research guide immediately before publication or customer recommendation.

Deep Research tasks can take tens of minutes, so a production design should decide whether to use background mode, how completion is detected through polling or webhooks, how users are notified, what timeout behavior applies, and how cost and latency are constrained.

Background mode retains response data for roughly 10 minutes to support polling and is incompatible with Zero Data Retention (ZDR) requirements; leave it off when ZDR is required and validate current data-handling guidance before implementation.

## Slide 8/42 - Identify Deep Research workflow needs

To determine whether Deep Research would be useful, start by asking whether the workflow truly requires research-style behavior. A simple internal policy question may not need Deep Research. If the answer can be grounded in one approved policy source and returned in a clear structured format, a retrieval-grounded response may be enough.

Deep Research becomes more relevant when the user needs to search or browse across multiple approved source types, synthesize changing information, compare evidence, identify uncertainty, run analysis, and produce a reviewable output with source visibility.

Use this table to evaluate fit:

| Fit signal | What it means | Surface or tool implication | What to validate |
|---|---|---|---|
| Multi-source investigation | The workflow needs information from several source types, such as public sources, internal documents, analyst commentary, and structured data. | Consider Deep Research through the Responses API with approved source/tool configuration. | Which sources are approved, current, authoritative, and permissioned? |
| Evidence comparison | The workflow must compare claims, identify disagreements, and explain what changed. | Deep Research may be useful when synthesis requires more than retrieving one passage. | How will conflicts, missing evidence, and unsupported claims be flagged? |
| Current or changing information | The output depends on recent public or external information. | Web search may be relevant if approved for the workflow. | Which public sources are allowed, and how will source quality be reviewed? |
| Internal source synthesis | The workflow must use approved internal files, policies, notes, or knowledge bases. | File search may be relevant when sources are available in approved vector stores. | Are vector stores approved, permissioned, current, and scoped correctly? |
| Private-system context | The workflow needs information from approved private systems or services. | A remote MCP server may be relevant only when it is trusted, approved, and implements the search-and-fetch interface required for Deep Research. | What data is shared with the MCP server, and what approvals or logs are required? |
| Data analysis during research | The workflow requires calculations, comparisons, extraction, or analysis of data files. | Code interpreter may be relevant if analysis is part of the research task. | Are input files approved, and how will analysis outputs be validated? |
| Long-running research | The workflow may take minutes rather than seconds because it uses multiple steps or tools. | Background mode, webhooks or polling, timeout design, and tool-call budgets may be needed. | How will users know the job is running, completed, failed, or ready for review? |
| Reviewable output | The output informs a business decision but should not act automatically. | The response should be structured for human review, with visible evidence and uncertainty. | Who reviews the result, and what triggers escalation? |

Examples that may justify Deep Research include weekly market briefings, policy-change summaries, competitive research, technical literature reviews, vendor risk research, or multi-source customer account research.

Before recommending Deep Research, define the workflow need in one sentence:

> The user needs to synthesize [source types] using [approved tools or data sources] to produce [output] for [decision or action], and a standard pattern may be insufficient because [reason].

A strong workflow statement might be:

> "Analysts need to synthesize regulatory updates, internal policy documents, market commentary, and competitor disclosures into a weekly risk briefing for review. Deep Research through the Responses API may be relevant because the task requires multi-source source gathering, evidence comparison, conflict handling, and traceable findings, with background execution and analyst review before distribution."

## Slide 9/42 - Identify risks

Deep Research workflows can create risk because the output often looks polished, structured, and authoritative. That can be useful when the evidence is strong, but risky when the evidence is weak, outdated, incomplete, unapproved, or not visible to the reviewer.

For deployment teams, the risk is not just that the model may get something wrong.

The bigger risk is that the workflow may produce a confident synthesis that hides uncertainty, skips source conflicts, overuses tools, exposes sensitive data, or gives users an answer they treat as final before evidence has been reviewed.

Before recommending Deep Research, check whether the workflow can make evidence, uncertainty, source boundaries, tool behavior, and review needs visible.

Common risks to check for include:

| Risk area | What to watch for |
|---|---|
| Source quality and freshness | The workflow uses sources that are weak, incomplete, outdated, or not appropriate for the decision being made. |
| Unsupported or overconfident claims | The output presents conclusions as fact when the source evidence is limited, unclear, or missing. |
| Source conflicts | Different sources disagree, but the workflow does not flag the conflict or route it for review. |
| Unapproved or unverified sources | The workflow relies on sources that have not been approved by the customer, domain owner, or implementation team. |
| Traceability gaps | Important claims cannot be traced back to the source evidence used to support them. |
| Review ownership gaps | No qualified person or team is responsible for reviewing the output before it is used in a high-impact workflow. |
| Permission issues | The workflow may access, combine, or expose sources that a user or downstream system should not be able to see. |

A Deep Research workflow should not hide uncertainty. It should make uncertainty visible.

For example, if two sources disagree about a regulatory deadline, the system should not simply choose one and present it as fact.

The safer behavior is to flag the conflict, show the source or evidence references where appropriate, and route the decision to a qualified reviewer.

Likewise, if the workflow depends on internal policy, source access matters.

The system should not rely on unapproved web content when the customer's policy team has an approved source of truth. It should also respect permission boundaries: not every user should receive every source, and not every source should be available to every workflow.

## Slide 10/42 - Define validation needs

A Deep Research workflow should not be trusted just because it can produce a well-written synthesis.

Before it is recommended for a customer environment, the team needs evidence that the workflow can use the right data sources and tools, represent sources accurately, manage long-running execution, and route uncertain or high-impact outputs for review.

For deployment teams, validation is the difference between a useful research assistant and a risky black box.

The goal is to prove that the workflow can support human judgment without hiding weak evidence, source conflicts, missing information, permission issues, tool risks, or long-running failure modes.

Validation should answer three questions:

| Validation question | What it checks |
|---|---|
| Are the sources trustworthy and allowed? | Confirms that the workflow uses approved, current, relevant sources that the user is permitted to access. |
| Is the synthesis accurate and traceable? | Checks whether important claims are supported by evidence and whether conflicts or gaps are made visible. |
| Is the review process safe enough for the workflow? | Confirms who reviews the output, when escalation is required, and what the system should do when evidence is incomplete. |

When defining your own validation needs, focus on:

**Source readiness**

Which sources are approved, current, relevant, and accessible for this workflow.

**Evidence expectations**

Which claims need source references, citations, or reviewer-visible evidence.

**Output structure**

What format the research output should follow so it can be reviewed consistently.

**Uncertainty handling**

How the workflow should behave when evidence is missing, weak, outdated, or conflicting.

**Review ownership**

Who is responsible for approving, correcting, or escalating the output before it is used.

**Capability validation**

Whether the proposed implementation is supported by current official documentation and approved product guidance.

A strong validation plan should also define what "safe failure" looks like. In a research-style workflow, the best output is not always a complete answer. Sometimes the correct behavior is to stop, flag the issue, and ask for review.

For example, the workflow might return:

> "The available sources are insufficient to support this conclusion."
> "The sources conflict on this point. Human review is required."
> "This claim needs evidence before it can be included."
> "This output is a draft for analyst review, not a final recommendation."

That behavior protects trust. A research-style workflow that knows when not to answer is often more valuable than one that always produces a confident synthesis.

## Slide 11/42 - Concise deployment example: source, permission, evidence, and review controls

This simplified pseudocode example shows how the learning across this module can translate into a deployable customer pattern. It is not runnable SDK code.

The aim is to show the control flow: prepare the research task, select approved data sources and tools, run long-running work safely, require evidence, and return a review status instead of treating the output as final.

```python
# PSEUDOCODE ONLY
# Shows control flow for a Responses-based Deep Research workflow.
# It is not runnable SDK code.

current_deep_research_model = "CURRENT_SUPPORTED_DEEP_RESEARCH_MODEL_TO_VALIDATE_BEFORE_PUBLICATION"

approved_source_plan = {
    "public_web": {
        "enabled": True,
        "tool": "web search",
        "allowed_for": ["market_news", "regulatory_updates"],
        "source_quality_rule": "Use approved authoritative sources where possible."
    },
    "internal_documents": {
        "enabled": True,
        "tool": "file search over approved vector stores",
        "vector_stores": ["APPROVED_POLICY_STORE", "APPROVED_ACCOUNT_NOTES_STORE"],
        "permission_rule": "Retrieve only content the user and workflow are allowed to access."
    },
    "private_systems": {
        "enabled": False,
        "tool": "remote MCP server with search and fetch",
        "reason": "Enable only after search-and-fetch support, server trust, data sharing, and approval rules are confirmed."
    },
    "analysis": {
        "enabled": True,
        "tool": "code interpreter",
        "allowed_for": ["tables", "figures", "trend calculations"]
    }
}

request = {
    "user_role": "analyst",
    "task": "Create a weekly regional risk briefing.",
    "decision_context": "Analyst review before distribution.",
    "required_output": [
        "summary", "key changes", "evidence references",
        "source conflicts", "open questions", "review recommendation"
    ],
    "source_types_needed": [
        "regulatory_updates", "internal_policy_documents",
        "market_commentary", "competitor_disclosures"
    ]
}

def prepare_research_brief(request):
    missing_requirements = check_for_missing_constraints(request)
    if missing_requirements:
        return {
            "status": "needs_clarification",
            "questions": missing_requirements
        }
    return {
        "status": "ready",
        "brief": create_fully_formed_research_prompt(request)
    }

def validate_source_and_tool_plan(approved_source_plan, request):
    risks = []
    research_data_sources = ["public_web", "internal_documents", "private_systems"]
    if not any(approved_source_plan[source]["enabled"] for source in research_data_sources):
        risks.append("No approved Deep Research data source is enabled.")

    if "internal_policy_documents" in request["source_types_needed"]:
        if not approved_source_plan["internal_documents"]["enabled"]:
            risks.append("Internal documents are needed, but file search is not approved.")

    if approved_source_plan["private_systems"]["enabled"]:
        risks.append("MCP is enabled. Confirm search-and-fetch support, server trust, data sharing, logging, and approval controls.")

    return risks

research_brief = prepare_research_brief(request)
source_tool_risks = validate_source_and_tool_plan(approved_source_plan, request)

if research_brief["status"] == "needs_clarification":
    response = {
        "status": "needs_clarification",
        "next_step": "Ask the user or workflow owner for missing research constraints.",
        "questions": research_brief["questions"]
    }
elif source_tool_risks:
    response = {
        "status": "pause_or_escalate",
        "reason": "Source or tool plan is not ready.",
        "risks": source_tool_risks,
        "next_step": "Confirm approved sources, tool permissions, and review controls."
    }
else:
    deep_research_job = {
        "surface": "Responses API",
        "model": current_deep_research_model,
        "input": research_brief["brief"],
        "execution_mode": "background",
        "completion_handling": "polling_or_webhook",
        "tool_call_budget": "SET_MAX_TOOL_CALLS_FOR_COST_AND_LATENCY",
        "enabled_tools": [
            "web search for approved public sources",
            "file search over approved vector stores",
            "code interpreter for approved analysis tasks"
        ],
        "disabled_tools_or_sources": [
            "unapproved MCP servers",
            "unapproved source repositories",
            "sources outside the user permission boundary"
        ]
    }

    draft_result = run_deep_research_job(deep_research_job)
    evidence_check = review_evidence_and_conflicts(draft_result)

    response = {
        "status": "needs_review" if evidence_check["risks"] else "ready_for_review",
        "brief": draft_result["structured_brief"],
        "evidence_used": draft_result["evidence_references"],
        "tool_trace_for_review": draft_result["tool_trace"],
        "risks": evidence_check["risks"],
        "reviewer_action": "Verify evidence, conflicts, and permissions before distribution."
    }
```

This example shows that Deep Research is not just a model call. It is a controlled Responses-based workflow.

Before research begins, the application checks whether the task is specific enough, which sources and tools are approved, whether the user has permission to access internal sources, and whether any tool-risk questions require escalation.

Because the work may be long-running, the design uses background execution only when data-handling requirements allow, with a completion path such as polling or webhooks; when ZDR is required, it leaves background mode off and uses higher request timeouts.

After the result is produced, the output is still marked for review rather than treated as final.

The main lesson is that deployment teams should design Deep Research workflows to use approved sources, respect permissions, manage long-running execution, show evidence, log tool behavior where appropriate, and fail safely when evidence or controls are not strong enough.

## Slide 12/42 - Real-world example: Evaluating a Deep Research workflow

A financial services customer wants an API-based workflow that helps analysts synthesize regulatory updates, market commentary, internal policy documents, and competitor disclosures into a weekly risk briefing.

A weak recommendation would be:

> "Use Deep Research because the customer needs research."

That is too broad. It does not explain why the pattern is justified, what sources are allowed, what needs to be reviewed, or what simpler alternative has been considered.

A stronger recommendation starts with the workflow need.

The analysts need a weekly briefing that:

- Gathers information from multiple approved source types
- Synthesizes changes across external and internal materials
- Flags uncertainty, source conflicts, and unsupported claims
- Produces a structured briefing that can be reviewed before distribution
- Helps humans decide what needs attention, not what final action to take automatically

A standard retrieval-grounded response might be enough if the analysts only need answers from one internal policy source. But it may be insufficient if the workflow requires multi-step source gathering, cross-source comparison, evidence traceability, and human-review support.

Deep Research may be justified if the team can confirm:

- Approved source access and permission boundaries
- Source freshness and authority
- Required source references or evidence traceability
- Human review ownership
- Clear output structure
- Escalation rules for conflicting or missing evidence
- Current official documentation support for the intended implementation

The recommendation might be:

> "Deep Research through the Responses API is plausible for the weekly risk briefing, but only as a review-support pattern.
>
> Proceed with a limited prototype using approved public sources, approved internal vector stores, structured evidence references, background execution only where compatible with data-handling requirements, tool-call limits, and analyst review.
>
> Do not automate final risk decisions. Validate the current Deep Research model, supported tools, availability, limits, and data-handling guidance immediately before publication or customer recommendation."

## Slide 13/42 - Recommended exercise: Assess Deep Research fit

This is an optional practice activity to help you apply what you just learned.

**Purpose**

Practice assessing Deep Research workflow fit.

**Task**

Assess whether Deep Research through the Responses API is justified for a market-intelligence, policy-synthesis, customer-research, or technical-research workflow compared with a simpler retrieval-grounded, structured-output, or human-assisted workflow.

**Use this context**

A customer wants an API workflow that produces a weekly market-intelligence brief for regional sales leaders. The brief should synthesize industry news, customer account notes, analyst commentary, and internal sales guidance. The customer has not yet confirmed which external sources are approved, which internal documents can be searched, whether customer account notes can be used through approved vector stores or systems, who owns final review, how source conflicts should be handled, or whether the task should run in background mode.

Decide:

- What workflow need is being served?
- What standard-pattern alternative should be considered first?
- What evidence would justify a research-style pattern?
- What source-quality or traceability requirement is missing?
- What recommendation is safest right now?

**Estimated time**

8-10 minutes

**Suggested output and reflection**

Deep Research pattern assessment.

## Slide 14/42 - Knowledge check

**Question:** A customer wants a research-style workflow that summarizes regulatory updates and internal policies into a weekly executive briefing. The team has not confirmed approved sources, citation expectations, source-conflict handling, or who reviews the briefing before it is sent. What is the safest recommendation?

- Proceed because executive briefings need research support.
- Replace the briefing with generated visual summaries.
- **Defer until sources, traceability, conflict handling, and review ownership are defined.** ✓ Correct
- Use external sources only and skip internal policy content.

Research-style workflows need source quality, traceability, conflict handling, and human-review ownership before they can be recommended responsibly. Without those controls, the output may appear authoritative while hiding evidence gaps.

## Slide 15/42 - Summary

Deep Research is most useful when a task requires multi-step source gathering, synthesis, evidence review, traceability, analysis, and human decision support.

It's not justified simply because the customer asks for "research." Start with the workflow need, compare it against simpler alternatives, and identify the validation burden. A defensible recommendation should name the source requirements, review owner, traceability expectations, uncertainty handling, and escalation path.

The strongest Deep Research recommendations make evidence visible. They help humans review and decide, rather than making unsupported claims look final.

## Slide 16/42 - Introduction (Module: Evaluate Image understanding and Image generation/editing workflows)

Visual workflows can be highly valuable when the work depends on visual information, visual output, or both. The first decision is to separate the visual surface.

Image understanding, also called vision, uses an image as input so the model can analyze what is in the image and return text, structured output, or a review-support signal. Image generation and editing create or change visual output. Some customer workflows need both.

This module helps you evaluate fit, risk, and review requirements for visual workflows without combining image understanding and image generation into one undifferentiated category.

## Slide 17/42 - Understanding different image workflow types

Start by separating what the image is doing in the workflow. Not every visual workflow is the same. In some workflows, the API creates a new image. In others, it analyzes an image the user provides. In others, it supports review, quality assurance, diagramming, or internal drafting.

For deployment teams, the important question is not simply, "Can this use images?"

It is: What role does the image play in the customer workflow, and what controls are needed before the output is used?

Use this table to separate the visual need before recommending a pattern:

| Visual workflow type | Primary surface to evaluate | What the workflow is doing | Fit question to ask |
|---|---|---|---|
| Image understanding or vision | Responses API flow with image input | Analyzes an uploaded image, screenshot, product photo, document image, diagram, or other visual input and returns text, structured output, or a review-support signal. | Does the workflow need information that is only available, or best verified, from the image itself? |
| Image generation | Images API for direct generation, or Responses API image-generation tool when generation is part of a conversational, iterative, or multi-step flow | Creates a new visual from a prompt, brief, approved source material, or workflow context. | Does the workflow truly need visual output, or would a text summary, structured brief, or human-created asset be enough? |
| Image editing or transformation | Images API for direct editing, or Responses API image-generation tool when editing happens in a conversational or multi-turn interaction | Changes an existing image or creates a new image using one or more reference images. | Are the input rights, edit intent, approved use, and review criteria clear before the image is changed or reused? |
| Visual-content draft | Usually an image generation or editing surface | Produces an early visual concept for internal review, such as a product visual, campaign concept, or design direction. | Is the output clearly treated as a draft, with human review before reuse or publication? |
| Visual QA support | Usually image understanding through the Responses API flow with image input | Reviews images for quality issues, missing elements, inconsistencies, readability, or policy concerns. | What criteria determine pass, fail, needs review, or request a new image? |
| Diagram or concept generation | Usually an image generation or editing surface | Creates a draft flow, architecture sketch, journey map, process illustration, or concept diagram. | Is the diagram used for alignment and review, rather than treated as a final technical artifact? |
| Combined visual workflow | Separate the understanding step from the generation or editing step | Uses one visual step to analyze an input and another visual step to create or edit an output. | Which step is image understanding, which step is generation or editing, and what handoff, review, and approval controls sit between them? |

A visual workflow is strongest when the image changes the quality or feasibility of the work. For example, a product-photo review workflow may need image input because the image itself is the evidence. A concept-generation workflow may need image output because the team is trying to align on a visual direction.

If the same outcome can be achieved with a checklist, structured output, or text summary with lower risk and easier review, a specialized image pattern may not be justified.

Before recommending a visual workflow, define the visual role and surface in one sentence:

> The workflow needs [image understanding, image generation/editing, or both] to support [task or decision]. The understanding step should use [surface], the generation/editing step should use [surface if needed], and a simpler pattern may be insufficient because [reason].

For example:

> The ecommerce team needs image understanding to review uploaded product photos for missing angles, blurry images, and inconsistent backgrounds. The analysis step should use the Responses API flow with image input. A text-only pattern may be insufficient because the image itself is the evidence that determines whether the listing is ready for review.

This keeps the recommendation focused on workflow fit, review needs, and deployment controls—not just on using images because the workflow is visual.

## Slide 18/42 - Determining risks, boundaries and verification for Images

Visual workflows need clear boundaries before they move beyond exploration. This is especially important when the workflow creates or interprets images that could affect customer-facing content, brand decisions, product claims, accessibility, or user trust.

For deployment teams, the goal is to define three things before recommending the workflow:

- What the visual workflow is allowed to do
- What risks or review requirements apply
- How the team will verify that the workflow is safe, useful, and ready for the intended use

Use this table to structure your review:

| Area to check | What to define | Verification question |
|---|---|---|
| Brand and product accuracy | Whether outputs must follow brand rules, product details, approved backgrounds, required angles, or style guidance. | Would a reviewer be able to confirm that the image is accurate and on brand? |
| Rights and approved use | Whether the team has the right to use input images, reference materials, brand assets, generated drafts, or transformed outputs. | Are the image inputs and outputs approved for this workflow and intended use? |
| Sensitive content and consent | Whether images may include people, IDs, locations, personal data, customer assets, or other sensitive content. | Do consent, privacy, and handling assumptions need review before the workflow continues? |
| Media handling and retention | Where uploaded or generated media can be stored, who can access it, and how long it can be retained. | Are storage, access, and retention rules approved? |
| Accessibility | Whether the workflow needs alt text, readable labels, text equivalents, or a non-visual fallback. | Can users still complete the task if they cannot use or interpret the image? |
| Customer-facing use | Whether the output is an internal draft, a support aid, or a customer-facing asset. | Is human approval required before the image is published, shared, or used externally? |
| Output limitations | What the workflow must not claim, infer, generate, or decide. | Are the limits clear enough to prevent misuse or overreliance? |
| Review and escalation | Who reviews the output, what they check, and when the workflow should escalate. | Is there a clear owner for approval, correction, or rejection? |

Rights and usage are especially important. Teams need to know whether they can use the images involved in the workflow and whether generated or transformed outputs are approved for the intended purpose.

An internal creative draft has a different review burden from a product image, legal diagram, medical illustration, or customer-facing support asset.

Accessibility also needs to be designed in from the start, as with all multimodal approaches.

A visual workflow can exclude users if there is no text equivalent, alt text, readable labeling, or non-visual fallback where needed.

For image input workflows, teams should also decide what happens when the uploaded image is low quality or unavailable.

Verification should be specific. "Looks good" is not enough. Look to emulate these verification criteria examples instead:

| Workflow type | Example verification criteria |
|---|---|
| Product-content workflow | Brand fit, product accuracy, approved background, required angles, absence of misleading claims, readability at intended size. |
| Image-analysis or visual-QA workflow | Image-quality threshold, uncertainty handling, when to ask for another image, when to accept a text description, and when to route to human review. |
| Visual-support workflow | Accuracy of steps, readable labels, accessibility, approved terminology, and whether the output is clearly marked as a draft or support aid. |
| Diagram or concept workflow | Correct high-level flow, clear labels, stakeholder-review readiness, and no implication that the draft is a final technical design. |

Boundaries and verification matter because visual workflows can move quickly from useful support to real customer impact. Clear boundaries prevent the workflow from using images in ways that are unapproved, inaccessible, misleading, or too risky for the context.

Verification gives the team evidence that the workflow works as intended, handles uncertainty appropriately, and keeps the right human review in place before images are stored, shared, published, or used to influence decisions.

## Slide 19/42 - Deploying image workflows with API controls

An image workflow is not deployed as a standalone prompt. In a customer environment, it usually sits inside an application, workflow tool, content system, ecommerce platform, support system, or internal review process.

That application should control what the user can request, what inputs can be used, what the Images API is allowed to generate, where media can be stored.

What review is required before the output is reused or published.

Do not route every visual request to the same surface.

Use the Responses API flow with image input when the workflow needs to understand or analyze visual information.

Use the Images API when the workflow primarily needs direct image generation or editing. Use the Responses API image-generation tool when image creation or editing is part of a conversational, iterative, multi-turn, or broader workflow interaction.

If the workflow needs both understanding and generation, separate those steps and define the handoff, validation, and review controls between them.

For deployment teams, the pattern looks like this:

| Deployment step | What happens | Why it matters |
|---|---|---|
| User request | A user asks for a visual draft, uploads an image, or requests visual review. | Captures the workflow need and intended use. |
| Policy and permission checks | The application checks the user role, use case, rights, customer-facing status, and media-handling rules. | Prevents unapproved, restricted, or high-risk image use. |
| Prompt or input preparation | The application builds a controlled prompt or prepares an approved image input. | Keeps the model focused on the allowed task and avoids unnecessary data exposure. |
| Image API call | The application calls the current approved image capability only for the validated use case. | Embeds image capability into the customer workflow. |
| Output handling | The application stores, returns, or discards the media according to the customer's policy. | Controls access, retention, and downstream use. |
| Review and approval | The output is marked as draft, needs review, approved, rejected, or escalated. | Keeps brand, rights, accessibility, and customer-facing risk under human control. |
| Logging and monitoring | The system records metadata such as use case, status, reviewer action, and blocked requests. | Supports observability, auditability, and improvement over time. |

The most important deployment principle is that the customer application should enforce the boundary before and after the image is generated.

Before generation, the application checks whether the request is allowed. After generation, it controls whether the image can be stored, shared, reviewed, or published.

The code below shows a simplified deployment wrapper for an internal product-visual draft workflow. It is not a full production implementation.

The image-generation call is shown as a placeholder so the final SDK method and parameters can be validated against current official documentation before publication.

```python
# PSEUDOCODE ONLY
# Shows control flow for an image workflow.
# It is not runnable SDK code.

approved_image_workflows = {
    "internal_product_draft": {
        "allowed_roles": ["designer", "merchandising_lead"],
        "customer_facing_allowed": False,
        "rights_required": True,
        "accessibility_review_required": True
    }
}

request = {
    "user_role": "designer",
    "workflow_type": "internal_product_draft",
    "prompt": "Create a draft product visual for internal review.",
    "rights_confirmed": True,
    "customer_facing": False
}

workflow_rules = approved_image_workflows.get(request["workflow_type"])

if workflow_rules is None:
    response = {
        "status": "blocked",
        "reason": "Image workflow is not approved.",
        "reviewer_action": "Confirm whether this workflow should be approved."
    }
elif request["user_role"] not in workflow_rules["allowed_roles"]:
    response = {
        "status": "blocked",
        "reason": "User role is not allowed for this workflow.",
        "reviewer_action": "Check permissions before retrying."
    }
elif workflow_rules["rights_required"] and not request["rights_confirmed"]:
    response = {
        "status": "blocked",
        "reason": "Rights or approved-use confirmation is missing.",
        "reviewer_action": "Confirm rights before generating or transforming images."
    }
elif request["customer_facing"] and not workflow_rules["customer_facing_allowed"]:
    response = {
        "status": "blocked",
        "reason": "This workflow allows internal drafts only.",
        "reviewer_action": "Route customer-facing use for brand, rights, and approval review."
    }
else:
    image_draft = generate_image_with_approved_capability(
        prompt=request["prompt"]
    )

    response = {
        "status": "draft_needs_review",
        "image": image_draft,
        "allowed_use": "internal draft only",
        "reviewer_action": "Review brand fit, product accuracy, rights, accessibility, and approved use.",
        "output_limits": [
            "Do not publish externally without approval.",
            "Do not treat as a final product image.",
            "Do not store or share outside approved systems."
        ]
    }
```

This example shows that image deployment is mostly about the workflow wrapper around the model call.

The model generates the image, but the application decides whether the request is allowed, what prompt is sent, whether rights are confirmed, whether customer-facing use is blocked, and what review status comes back with the output.

That is the deployment lesson: image workflows should be controlled by policy, permissions, approved use, review status, and media-handling rules—not just by the image prompt itself.

For image analysis or visual QA workflows, the same pattern applies. The application should check whether the image input is allowed, whether the user has permission to submit or view it, whether media retention is approved, what quality threshold applies, and when the result should be routed to human review.

## Slide 20/42 - Real-world example: Evaluating an Images workflow

A retail customer wants to use an API workflow to create draft product visuals, analyze uploaded product images for listing quality, and generate visual support assets for ecommerce teams.

A weak recommendation would be:

> "Use Images because ecommerce is visual."

That recommendation is too broad. It does not separate the different visual needs or identify review requirements.

A stronger recommendation separates the workflow into parts:

**Draft product visuals**

This may be useful for internal creative exploration, but customer-facing publication requires brand, product, rights, and legal review.

**Uploaded product-image analysis**

This may be useful if ecommerce teams need help identifying missing angles, blurry images, inconsistent backgrounds, or quality issues.

The workflow should define image-quality thresholds and when to route to human review.

**Visual support assets**

These may be useful for internal guidance, such as illustrating product-photo standards or diagramming listing requirements.

The team should confirm whether the output is internal only or customer-facing.

The pattern may be justified if the team can confirm:

- The workflow truly depends on visual content or visual interpretation.
- Image rights and approved use are defined.
- Brand and human-review criteria are clear.
- Sensitive content and media-handling rules are understood.
- Accessibility requirements are met through alt text, readable labels, or non-visual fallback.
- Customer-facing use is gated by approval.

A defensible recommendation might be:

> "Use an Images workflow for internal draft visuals and visual QA support, with human review before any customer-facing use. Do not publish generated product visuals automatically. Confirm rights, brand-review criteria, accessibility expectations, and media-handling rules before expanding the workflow."

## Slide 21/42 - Recommended exercise: Evaluate Images and Image API workflow fit

This is an optional practice activity to help you apply what you just learned.

**Purpose**

Practice evaluating image workflow fit.

**Task**

Evaluate whether an Images or Image API pattern is appropriate for a product-content, visual-support, diagram-generation, visual-QA, or image-analysis workflow.

**Use this context**

A product team wants an API workflow that turns short product descriptions into draft ecommerce visuals.

Reviews uploaded product photos for listing quality, and creates internal visual guides for merchandisers.

The team has not confirmed image rights, brand review criteria, accessibility requirements, or whether generated visuals can be customer-facing.

Decide:

- Which visual workflow types are being requested?
- Which parts may be appropriate for internal use?
- Which parts require review before customer-facing use?
- What standard-pattern alternative should be considered?
- What rights, brand, accessibility, or safety requirement must be resolved?

**Estimated time**

8-10 minutes

**Suggested output and reflection**

Image pattern assessment.

## Slide 22/42 - Knowledge check

**Question:** A retail team wants to generate customer-facing product images automatically from short text descriptions. The team has not confirmed brand-review criteria, image rights, accessibility requirements, or human approval before publication. What is the safest recommendation?

- Proceed because visuals can speed ecommerce workflows.
- Exclude alt text because visual outputs do not need text support.
- Remove human review so the workflow can scale faster.
- **Use internal drafts until rights, brand review, accessibility, and approval are defined.** ✓ Correct

Image workflows can be valuable, but customer-facing visual output requires clear rights, brand, accessibility, safety, and approval controls. Internal draft use may be reasonable while customer-facing use remains gated.

## Slide 23/42 - Summary

Visual workflows are justified when the workflow depends on image input, image output, or both. Remember not to group image understanding and image generation or editing into a single decision.

A strong recommendation identifies the visual role, the correct surface, the fit signal, the standard-pattern alternative, and the review burden. Before recommending a visual workflow, clarify rights, approved use, brand review, sensitive content, accessibility, media handling, human approval, and customer-facing risk.

A visual pattern should be useful, reviewable, and safe—not simply more visually compelling.

## Slide 24/42 - Introduction (Module: Evaluate distillation and optimization patterns)

Distillation and optimization can improve an API solution, but they should not be the first answer to every quality, cost, or latency problem.

Many problems that look like customization problems are actually design problems. The prompt may be unclear. The output contract may be too loose. Retrieval may be pulling the wrong context. Tool boundaries may be ambiguous. Eval coverage may be too thin. The model or capability selection may need to be revisited. The input data may be inconsistent.

This module helps you decide whether distillation or optimization is justified by repeated quality gaps, proven performance constraints, available examples, clear eval methods, and operational ownership.

## Slide 25/42 - Start with simpler improvements

When an API workflow has quality, cost, or latency problems, it can be tempting to jump straight to distillation or deeper optimization. For deployment teams, that is usually too early.

Before distilling behavior or optimizing the system around a specialized approach, first diagnose the current workflow.

Many issues that look like customization problems are actually caused by unclear instructions, loose output structure, weak retrieval, overlapping categories, incomplete evals, or poor source data.

Consider whether a problem could be solved by one of these approaches first:

- Prompt improvement
- Output contract improvement
- Retrieval improvement
- Tool boundary improvement
- Eval coverage
- Model or capability selection revisit
- Data quality improvement
- Structured-output improvement

This matters because distillation and optimization both add deployment responsibility.

They can introduce extra cost, versioning, maintenance, data-governance requirements, evaluation burden, and operational ownership.

A specialized approach should only be considered after the existing pattern has been clearly defined, tested, and improved with simpler controls.

A useful decision rule is:

> Do not distill or optimize until the current pattern has been clearly defined, tested, and improved using simpler controls.

That does not mean distillation or optimization are rarely useful.

It means they should be evidence-led. Before recommending distillation or optimization.

The team should have baseline results, repeated failure patterns, clear eval criteria, approved data, and an owner who can maintain the resulting approach.

Use this decision ladder to check simpler improvements before recommending distillation or optimization.

**A note on fine-tuning**

Fine-tuning should not be treated as a default optimization path for new API workflows. Current availability and eligibility can vary, and OpenAI guidance may change over time.

Inference on existing fine-tuned models can continue until the underlying base model is deprecated. Before discussing fine-tuning with a customer, confirm current organization eligibility, existing fine-tuned-model use, the base-model lifecycle, and the latest official guidance.

For this course, start with simpler improvements and validate the baseline. Consider distillation or other optimization only when evidence justifies the added complexity, and route any fine-tuning question through current product validation and transition planning. Complete a final currency check immediately before publication or customer recommendation.

## Slide 26/42 - Real-world example: Avoiding premature distillation or optimization

A customer-support team has an API workflow that classifies incoming support tickets and drafts routing notes. The workflow is mostly successful, but repeated errors appear in a small number of categories, and high-volume usage is creating cost and latency pressure.

A weak recommendation would be:

> "Optimize the workflow because the output has errors and the system is expensive."

That recommendation jumps too quickly. The team first needs to understand the error pattern and the performance constraint.

Before recommending distillation or optimization, the team should diagnose the existing workflow:

- **Task definition:** Are the ticket categories clear, distinct, and stable enough to classify consistently?
- **Context and examples:** Is the model receiving the right ticket details, policy context, and examples for the task?
- **Output contract:** Does the workflow require a clear category, confidence signal, reason code, or fallback when the answer is uncertain?
- **Failure pattern:** Are the errors concentrated in specific categories, ticket types, or edge cases?
- **Evaluation baseline:** Do evals measure both category accuracy and the quality of the routing notes?
- **Performance baseline:** What are the current cost, latency, throughput, and reliability measurements?
- **Pattern choice:** Is the current model or capability pattern still appropriate for the workflow's quality, latency, and cost needs?

If the errors come from unclear categories, the team should improve the taxonomy and output schema. If the errors come from missing context, retrieval or source quality may be the issue. If the output is inconsistent, structured output may help. If cost and latency are high but quality is acceptable, optimization or distillation may be worth evaluating.

A stronger recommendation might be:

> "Do not move directly to distillation or deeper optimization yet.
>
> First clarify the ticket categories, tighten the output contract, add confidence or reason-code requirements, and create evals for classification accuracy and routing-note quality.
>
> If the workflow then meets quality targets but remains too costly or slow at expected volume, evaluate optimization or distillation with clear quality-loss thresholds, latency targets, and ownership."

That recommendation is stronger because it separates quality diagnosis from performance optimization. It also avoids optimizing a workflow before the team knows what behavior must be preserved.

## Slide 27/42 - Distillation fit

Distillation changes the cost, latency, or scale profile of a working solution by using stronger "teacher" behavior to support a smaller, faster, or lower-cost "student" approach.

For deployment teams, the important word is working.

Distillation is not the right starting point for a workflow that is still poorly defined, inconsistently evaluated, or failing for unclear reasons.

If the original workflow does not reliably produce the right behavior, distillation may simply create a faster or cheaper version of a weak solution.

Distillation becomes relevant when the team already has a validated pattern that works, but the operating profile needs to improve.

For example, a customer may have a high-quality workflow that uses a more capable model for classification, summarization, or routing, but the workflow is too expensive or too slow at production volume.

In that case, distillation may help preserve the important behavior while improving cost, latency, throughput, or operational efficiency.

This table defines more situations where distillation may be relevant, and the factors that should always be present if you're going to use distillation:

| Area to assess | Distillation may be relevant when… | Do not recommend distillation without… |
|---|---|---|
| Starting point | A larger, more expensive, or slower pattern already works. | Evidence that the current pattern produces the right behavior. |
| Goal | The team needs to make the working solution faster, cheaper, easier to scale, or easier to operate. | A clear target for what should improve, such as latency, cost, throughput, or operational simplicity. |
| Baseline behavior | The current behavior has already been validated and can act as the quality benchmark. | Baseline performance evidence from the existing workflow. |
| Evaluation method | The team can measure whether the distilled approach preserves the required behavior. | Evaluation criteria that compare the original and distilled behavior. |
| Quality threshold | The team knows what level of quality must be maintained. | Acceptable quality thresholds and a decision on what quality loss, if any, is acceptable. |
| Ownership | A team can maintain, version, retest, and monitor the distilled approach over time. | Clear maintenance and versioning ownership. |

Distillation is not a good fix for a workflow that has not yet proven what good output looks like.

If the original pattern is unstable, unclear, or poorly validated, distilling it may simply make an unreliable workflow cheaper or faster.

A distillation decision should make the tradeoff explicit. Before moving forward, the team should be able to state:

- **What behavior must be preserved:** The validated output quality or workflow behavior that the distilled approach must maintain.
- **What constraint must improve:** The cost, latency, throughput, scale, or operational issue the current pattern creates.
- **How success will be measured:** The evals and quality thresholds used to compare the original and distilled behavior.
- **What quality loss is acceptable:** The point at which the efficiency gain is no longer worth the performance tradeoff.
- **Who owns maintenance:** The team responsible for retesting when prompts, data, tools, models, or requirements change.

If these points are not defined, distillation is not deployment-ready. It may still be worth exploring, but the team should first validate the current workflow, establish a baseline, and agree how much quality can be traded for speed, cost, or scale.

Distillation usually starts with a stronger or more expensive "teacher" behavior that already works.

The team captures high-quality examples of that behavior, filters them, and uses them to train or evaluate a smaller or lower-cost "student" approach.

The simplified pseudocode below shows the decision flow: confirm the current workflow works, define what behavior must be preserved, compare a lower-cost or lower-latency candidate against the baseline, and reject the tradeoff if quality falls below threshold.

```python
# PSEUDOCODE ONLY
# Shows how a deployment team checks whether distillation is ready to validate.
# It is not runnable SDK code.

distillation_case = {
    "workflow": "support_ticket_routing",
    "teacher_pattern_validated": True,
    "constraint": "too slow or too costly at expected volume",
    "student_candidate_defined": True,
    "quality_threshold": "maintain routing accuracy within approved tolerance",
    "owner": "support_ops"
}

if not distillation_case["teacher_pattern_validated"]:
    decision = {
        "status": "do_not_distill",
        "reason": "The current workflow has not proven what good behavior looks like."
    }
elif not distillation_case["student_candidate_defined"]:
    decision = {
        "status": "defer",
        "reason": "No student candidate or lower-cost pattern has been defined."
    }
else:
    teacher_examples = collect_reviewed_teacher_outputs(
        workflow=distillation_case["workflow"]
    )

    filtered_examples = remove_unapproved_or_weak_examples(
        examples=teacher_examples
    )

    teacher_eval = run_eval(
        pattern="teacher",
        examples=filtered_examples
    )

    student_eval = run_eval(
        pattern="student_candidate",
        examples=filtered_examples
    )

    decision = compare_distillation_tradeoff(
        teacher=teacher_eval,
        student=student_eval,
        quality_threshold=distillation_case["quality_threshold"],
        target_improvement=distillation_case["constraint"]
    )
```

This example teaches that distillation is not "make it cheaper" by default. The deployer first captures examples from a validated teacher workflow, labels them with useful metadata, filters out weak examples, and then compares the student model against the teacher baseline before release.

The next deployment decision is whether the student preserves the behavior that matters. If the smaller model is faster or cheaper but fails the quality threshold, the distillation tradeoff is not acceptable.

## Slide 28/42 - Optimization fit

Optimization improves the performance of an API solution by adjusting design choices across the workflow. This might include the model, prompt, context, retrieval strategy, tool flow, output contract, latency, cost, reliability, monitoring, or evaluation loop.

For deployment teams, optimization should start with evidence. The goal is not simply to "make the workflow better."

The team needs to identify what is not meeting requirements, where the issue appears in the workflow, and what metric or behavior should improve.

Optimization is often broader than distillation. It may involve tightening the prompt, reducing unnecessary context, improving retrieval filters, changing a tool boundary, adjusting the output schema, revisiting model selection, adding caching where appropriate, or improving monitoring.

These changes can make a workflow more reliable and easier to operate, but they can also create tradeoffs.

Optimization may be justified when the team can clearly define:

| Optimization signal | What it means |
|---|---|
| Quality gap | The workflow repeatedly fails in a specific, measurable way. |
| Performance constraint | The current workflow does not meet an agreed requirement, such as response time, reliability, throughput, or output consistency. |
| Cost or scale pressure | The workflow works, but the expected usage volume makes the current design too expensive or difficult to scale. |
| Known bottleneck | The team has enough evidence to identify what part of the workflow needs improvement. |
| Baseline and evals | The team can compare the current workflow against the optimized version. |
| Ownership | A team owns testing, monitoring, maintenance, and retesting after changes. |

The key deployment question is:

> What specific behavior or metric are we improving, and how will we know the change worked?

A vague goal like "make it faster" or "make it cheaper" is not enough.

A stronger goal would be:

> Reduce average response latency for the ticket-routing workflow while maintaining routing accuracy and structured-output validity.

That makes the optimization testable. The team knows what should improve, what quality must be preserved, and what evidence is needed before the optimized workflow can be trusted.

Optimization depends on observability.

A team cannot responsibly improve latency, cost, reliability, or quality unless it can see what is happening in the workflow.

For deployment teams, observability means capturing enough operating evidence to compare the current workflow with the optimized version. That evidence may include request ID, release version, model used, latency, token or consumption signal, error category, quality status, and whether a human review or fallback was needed.

Here's a pseudocode example:

```python
# PSEUDOCODE ONLY
# Shows the kind of evidence a deployment team should log before optimizing.
# It is not runnable SDK code.

request = {
    "request_id": create_request_id(),
    "workflow": "support_ticket_routing",
    "release_version": "ticket-routing-v3",
    "pattern": "current_baseline"
}

start_time = current_time()

try:
    result = call_current_approved_workflow(
        workflow=request["workflow"],
        input_data="support_ticket_payload"
    )

    latency_ms = elapsed_time_since(start_time)

    log_event = {
        "request_id": request["request_id"],
        "workflow": request["workflow"],
        "release_version": request["release_version"],
        "pattern": request["pattern"],
        "status": "success",
        "latency_ms": latency_ms,
        "output_contract_valid": check_output_contract(result),
        "fallback_used": result.get("fallback_used"),
        "human_review_required": result.get("needs_review")
    }
except WorkflowError as error:
    latency_ms = elapsed_time_since(start_time)

    log_event = {
        "request_id": request["request_id"],
        "workflow": request["workflow"],
        "release_version": request["release_version"],
        "pattern": request["pattern"],
        "status": "error",
        "latency_ms": latency_ms,
        "error_category": classify_error(error),
        "human_review_required": True
    }

record_safe_log(log_event)
```

This second pseudocode snippet then shows how your optimization decisions should compare baseline and candidate variations:

```python
# PSEUDOCODE ONLY
# Shows how optimization decisions should compare baseline and candidate versions.

baseline_metrics = summarize_metrics(
    workflow="support_ticket_routing",
    release_version="ticket-routing-v3"
)

candidate_metrics = summarize_metrics(
    workflow="support_ticket_routing",
    release_version="ticket-routing-v4"
)

decision = compare_versions(
    baseline=baseline_metrics,
    candidate=candidate_metrics,
    target_improvement="reduce average latency",
    quality_thresholds=[
        "maintain routing accuracy",
        "maintain structured-output validity",
        "do not increase human review rate"
    ]
)
```

These examples teach that optimization begins by making the workflow measurable. The deployer records which release handled the request, which model or pattern was used, how long the call took, whether it succeeded, and whether review was needed. That evidence lets the team compare versions.

## Slide 29/42 - Choosing the right optimization path

Once the team has baseline evidence, the next question is not simply, "Should we optimize?" It is: Which part of the workflow should change, and what evidence would prove the change helped?

Use this comparison to choose the lowest-complexity path that addresses the actual constraint:

| If the problem is… | Consider first… | Consider distillation or deeper optimization only when… |
|---|---|---|
| Output is inconsistent | Tighten the prompt, output contract, structured-output schema, examples, or fallback rules. | The target behavior is clear, evals exist, and simpler controls are not enough. |
| Retrieval is weak | Improve source quality, metadata, chunking assumptions, retrieval filters, or grounding instructions. | The retrieval pattern is already validated but cost, latency, or scale remains a blocker. |
| Tool use is unreliable | Clarify tool boundaries, invocation conditions, schemas, error handling, and approval steps. | Tool behavior is stable, but the workflow needs performance or reliability optimization. |
| Latency is too high | Revisit model/capability selection, reduce unnecessary steps, simplify context, or adjust interaction flow. | Quality is already acceptable and the team has a measurable latency target. |
| Cost is too high | Review context size, model/capability choice, tool calls, duplicate work, and workflow frequency. | The current behavior works and the team needs a lower-cost approach with acceptable quality. |
| Scale is increasing | Review throughput, caching opportunities, fallback behavior, monitoring, and operational load. | The workflow is stable enough to preserve and the optimized version can be evaluated safely. |
| Quality is acceptable but the pattern is too heavy | Revisit architecture, context, tool use, and model/capability choice. | A validated stronger approach can serve as the reference for a lighter-weight path. |

The best optimization path is often the smallest change that solves the measured problem without making the workflow harder to validate, govern, or support.

A weak recommendation says:

> "Optimize the workflow."

A stronger recommendation says:

> "Reduce unnecessary context and tighten structured outputs first. If quality remains stable but latency is still above the target, evaluate a lower-latency configuration or distillation path against the current baseline. Do not proceed unless the optimized version meets the eval threshold and the support team owns monitoring and rollback."

That recommendation is more useful because it names the constraint, the first change to try, the validation condition, and the operational owner.

## Slide 30/42 - Identify tradeoffs and ownership

Distillation and optimization can improve an API solution, but they also create tradeoffs.

A specialized pattern may reduce cost but increase maintenance. It may reduce latency but lower output quality. It may improve throughput but make the system harder to explain.

It may simplify the user experience while adding complexity behind the scenes.

Before recommending distillation or optimization, identify the major tradeoffs:

| Tradeoff area | Question to ask |
|---|---|
| Quality | What quality must be preserved, and what quality loss is unacceptable? |
| Cost | What cost target must be met, and how will cost be measured? |
| Latency | What response-time target matters for the user or system experience? |
| Throughput and scale | What usage volume or concurrency requirement is driving the change? |
| Reliability | What failure modes could increase after the optimization? |
| Maintainability | Will future teams understand and support the optimized design? |
| Governance | What approvals, review points, or documentation are required? |
| Version management | How will the team track what changed and roll back if needed? |
| Evaluation burden | What evals are needed to prove the change works and continues to work? |
| Operational ownership | Which team owns monitoring, retesting, rollback, escalation, and future changes? |

Ownership is also crucial for effectively deploying specialized API patterns. An optimized pattern is not deployment-ready unless someone owns the operational loop.

Ownership should include:

| Ownership responsibility | What the owner must do |
|---|---|
| Monitor quality | Track whether the workflow continues to meet quality expectations in real use. |
| Monitor performance | Track cost, latency, throughput, reliability, and error patterns. |
| Retest after changes | Re-run evals when prompts, models, tools, source data, policies, or requirements change. |
| Manage versions | Track which version is live, what changed, and how to roll back if needed. |
| Review drift or failure patterns | Watch for repeated errors, quality decline, edge cases, or behavior that no longer matches the workflow. |
| Decide when to update or escalate | Know when to improve the workflow, pause use, roll back, or route the issue to another owner. |

A specialized optimization pattern without an owner is not ready for customer deployment.

It may still be worth exploring, but the team should first define what must be monitored, what triggers retesting, who approves changes, and how the workflow can be updated, rolled back, or escalated if performance changes over time.

## Slide 31/42 - Recommended exercise: Decide whether optimization is justified

This is an optional practice activity to help you apply what you just learned.

**Purpose**

Practice avoiding premature optimization.

**Task**

Review a quality, cost, or latency problem and decide whether to improve prompts, improve the output contract, adjust retrieval, revisit model or capability selection, evaluate distillation, optimize the workflow, or defer pending more evidence.

**Use this context**

A customer-support API classifies tickets into 18 categories and drafts routing notes. Most tickets are classified correctly, but three categories are frequently confused. The category definitions overlap, the output schema does not require confidence or reason codes, and the team has not yet built evals for category accuracy.

The workflow also has cost and latency pressure because ticket volume has increased. The team wants to optimize the workflow immediately so it can scale.

Decide:

- What simpler improvements should be tried first?
- What baseline evidence is missing?
- Which issue is a quality problem, and which issue is a performance problem?
- What eval criteria would need to exist before any optimization is recommended?
- Would distillation be justified now, or should it be deferred?
- What cost, latency, or throughput target would make optimization measurable?
- What recommendation is safest?

**Estimated time**

10-12 minutes

**Suggested output and reflection**

Optimization recommendation.

## Slide 32/42 - Knowledge check

**Question:** A team wants to optimize a ticket-classification workflow because several categories are often confused and usage volume is increasing. The category definitions overlap, there are no evals, and the output schema does not require confidence, reason codes, or fallback behavior. The team also has not measured current cost, latency, or throughput against a target. What is the strongest next step?

- Distill immediately because a smaller or faster approach will automatically fix classification quality.
- Optimize immediately because repeated errors and high usage prove the workflow needs a specialized pattern.
- **Clarify categories, tighten the output contract, add evals, measure baseline cost and latency, and define the performance target before reconsidering optimization.** ✓ Correct
- Remove category labels and use free-text routing notes only.

Optimization should not be the first response when the task definition, output contract, eval coverage, and performance baseline are incomplete. The team should first clarify the behavior, build baseline evidence, and define measurable quality and performance targets. Distillation or deeper optimization may be reconsidered only if the workflow behavior is already validated.

## Slide 33/42 - Summary

Distillation and optimization should be evidence-led decisions.

Start with simpler improvements: prompt, output contract, retrieval, tool boundaries, eval coverage, model or capability selection, data quality, and structured outputs. Then consider distillation or optimization only when the team has baseline evidence, a stable target behavior, clear evaluation criteria, approved data, and operational ownership.

A strong recommendation explains what will change, what simpler options were ruled out, what evidence supports the change, what tradeoffs it creates, and who owns maintenance over time.

## Slide 34/42 - Introduction (Module: Complete the Specialized API Pattern Fit Assessment)

You have now evaluated three major categories of specialized pattern fit: Deep Research through the Responses API, image understanding and image generation/editing workflows, and distillation and optimization patterns.

The next step is to bring that judgment together in a Specialized API Pattern Fit Assessment.

This assessment is not a product feature tour. It is a decision artifact. It should help a team decide whether to use a standard pattern, validate a specialized pattern, gather more evidence, pause or escalate, or reject the specialized pattern as unnecessary or unsupported.

## Slide 35/42 - Build the assessment

A strong Specialized API Pattern Fit Assessment answers the following questions.

**Workflow need and standard-pattern alternative**

What does the customer workflow require? Why may a standard API pattern be enough—or not enough? The standard-pattern alternative might be a structured output, retrieval-grounded response, tool workflow, agentic workflow, realtime or multimodal experience, or human-assisted process. Always consider it before recommending specialization.

**Candidate specialized pattern**

What specialized option is being considered? Examples include Deep Research through the Responses API, image understanding, image generation or editing, distillation, optimization, or another OpenAI-confirmed specialized pattern.

**Pattern-specific fit evidence**

What evidence makes this pattern relevant? Fit evidence may include source needs, visual workflow needs, repeated quality gaps, available approved examples, repeatability, cost pressure, latency pressure, scale pressure, or a performance constraint.

**Adjacent pattern dependencies**

How might this pattern depend on or combine with retrieval, tools, agents, structured outputs, realtime, voice, image, or multimodal behavior? For example, a Deep Research workflow may depend on approved web search, file search, trusted MCP, code interpreter, structured outputs, background execution, and human review. An image-understanding workflow may depend on image input, structured output, and review controls.

**Data, quality, rights, safety, and governance considerations**

What data is needed? Who has the right to use it? What quality standard applies? What safety or review concerns exist? What governance approvals may be required? This section is especially important for image workflows, research sources, and optimization data.

**Tradeoffs and operational complexity**

What cost, latency, reliability, maintenance, versioning, complexity, and support implications does the pattern introduce? Do not list only benefits. Specialized patterns often also create new operating responsibilities.

**Validation and escalation plan**

What must be tested or reviewed? Who validates it? What evidence is required? When should the decision be escalated? Validation might include source-quality review, visual review, evals, safety review, rights approval, accessibility review, cost and latency baselines, or operational-readiness review.

**Risks, exclusions, and recommendation**

What risks remain? What should the pattern not be used for? What recommendation is supported by the evidence? Make the recommendation explicit: use the standard pattern, proceed with the specialized pattern under defined conditions, defer, pause or escalate, or reject it.

## Slide 36/42 - Make the recommendation defensible

A defensible recommendation is clear about both fit and readiness.

Do not overclaim readiness. A specialized pattern can be plausible without being ready. It can be useful for an internal prototype but not customer-facing use. It can be justified for one part of a workflow but unnecessary for another.

Use these recommendation categories:

| Recommendation category | Use this when… | Example |
|---|---|---|
| Standard pattern sufficient | A standard pattern can meet the workflow need with lower complexity, lower risk, and enough quality. | A grounded structured-output workflow can answer policy questions from approved sources, so a research-style workflow is unnecessary. |
| Specialized pattern justified with validation conditions | The workflow evidence supports specialization, but specific validation, review, or governance conditions must be met. | An Images workflow is justified for internal product-visual drafts, but customer-facing use requires rights, brand, accessibility, and human approval. |
| Defer pending evidence | The pattern may be useful, but the team lacks key evidence. | Distillation may be useful, but there are not yet enough approved examples or eval results. |
| Pause or escalate | Unresolved risks require security, legal, privacy, governance, or OpenAI expert review. | A research workflow depends on unapproved sources for regulated decisions, or an image workflow uses sensitive media without retention rules. |
| Reject specialized pattern as unnecessary or unsupported | The specialized pattern does not solve a real workflow need, is not supported by the available evidence, or adds avoidable risk and complexity compared with a standard pattern. | A structured-output workflow using approved internal documents is enough for regional launch summaries, so a research-style workflow, Images workflow, or distillation is not justified. |

A strong recommendation should also explain what evidence would change the decision. This keeps the assessment practical and avoids treating "no" or "not yet" as the end of the conversation.

For example:

> "Distillation is not justified now. Revisit after the team clarifies the category taxonomy, implements structured outputs, collects at least one evaluation set, and shows repeated failures that remain after prompt and contract improvements."

## Slide 37/42 - Real-world example: Selecting the defensible specialized pattern

A global manufacturing customer asks for an "advanced API solution" to support product launch planning. The request includes market research synthesis, draft visual concepts, and automated summaries for regional launch teams.

A weak recommendation would be:

> "Use specialized API patterns for research, images, and optimization because the customer asked for an advanced solution."

That recommendation is too broad. It does not separate workflow needs, standard alternatives, fit evidence, or review conditions.

A stronger assessment would break the request into parts.

**Part 1: Market research synthesis**

This may be a Deep Research workflow if the team needs multi-source gathering, synthesis, evidence traceability, long-running research, and human review through the Responses API.

It may not be justified if approved research sources are not defined, if the task can be handled with a simple retrieval-grounded summary of internal launch documents, or if the team has not validated the current Deep Research model and supported tools.

Possible recommendation: Defer or limit until approved sources, source-reference expectations, tool configuration, background execution needs, conflict handling, model currency, and review ownership are defined.

**Part 2: Draft visual concepts**

This may be an Images workflow if the team needs visual drafts for internal creative exploration. Customer-facing use requires stronger review.

Possible recommendation: Use Images for internal drafts only, with brand, rights, accessibility, and human-review requirements before broader use.

**Part 3: Automated regional summaries**

This may not require a specialized pattern. A structured-output workflow using approved launch materials may be enough.

Possible recommendation: Use a standard structured-output and retrieval-grounded pattern unless repeated quality gaps or performance constraints appear after testing.

**Part 4: Optimization**

Optimization may be relevant only after a baseline exists. If the workflow is not built or measured yet, there is nothing reliable to optimize.

Possible recommendation: Do not optimize yet. Establish quality, cost, latency, and reliability baselines first.

The final recommendation might be:

> "Do not treat this as one advanced API solution. Use a standard structured-output pattern for regional summaries, evaluate Deep Research through the Responses API only after approved sources, source/tool configuration, background execution needs, current model guidance, and review ownership are defined, and allow image generation only for internal visual drafts with brand, rights, accessibility, and human-review controls. Defer optimization until baseline quality, cost, and latency evidence exists."

## Slide 38/42 - Recommended exercise: Finalize the Specialized API Pattern Fit Assessment

This is an optional practice activity to help you apply what you just learned.

**Purpose**

Consolidate prior pattern-fit, tradeoff, risk, validation, and recommendation decisions into a handoff-ready assessment.

**Task**

Use the assessment sections you developed earlier in the course, or use the manufacturing product-launch planning context below, to finalize the Specialized API Pattern Fit Assessment.

**Use this context**

A global manufacturing customer wants an advanced API solution for product launch planning. The workflow includes market research synthesis, draft visual concepts, automated regional summaries, and possible optimization later if the workflow becomes high volume. Approved external sources are not yet confirmed. Brand-review criteria exist but have not been translated into AI review requirements. The regional-summary workflow can likely use approved internal launch materials. No cost, latency, or quality baseline exists yet.

Confirm your assessment answers:

- Workflow need: What customer task, decision, or outcome does the workflow need to support?
- Standard alternative: What simpler API pattern could meet the need before specialization is considered?
- Specialized pattern fit: Which specialized pattern is being evaluated, and what evidence shows it may be justified?
- Dependencies and controls: What adjacent patterns, data requirements, rights, safety, governance, or quality controls matter?
- Tradeoffs: What cost, latency, complexity, maintenance, or ownership burden would the specialized pattern introduce?
- Validation plan: What must be tested, reviewed, or escalated before the pattern can be trusted?
- Risks and exclusions: What should the workflow not do, and what risks remain?
- Recommendation: Should the team use the standard pattern, proceed with validation conditions, defer pending evidence, pause or escalate, or reject the specialized pattern?

**Estimated time**

8-10 minutes

**Suggested output and reflection**

A completed Specialized API Pattern Fit Assessment with one recommendation: use the standard pattern, use the specialized pattern with validation conditions, gather more evidence first, pause or escalate, or reject the specialized pattern.

## Slide 39/42 - Knowledge check

**Question:** A manufacturing customer asks for one "advanced API solution" that combines market research synthesis, draft visual concepts, and regional launch summaries. Approved external research sources are not confirmed, visual outputs need brand and rights review, and regional summaries can likely be produced from approved internal launch documents. Which recommendation is most defensible?

- Reject the full request because some controls are unresolved.
- Build one advanced workflow and add review controls later.
- **Split the request by workflow and apply the simplest safe pattern for each.** ✓ Correct
- Use Deep Research for the entire request because one part involves market research.

The strongest answer separates the three workflow needs instead of treating them as one "advanced" solution. Regional summaries may only need a standard structured-output pattern using approved internal launch materials. Research-style synthesis should wait until approved sources and review ownership are defined. Draft visual concepts should stay internal until brand, rights, accessibility, and human-review controls are confirmed.

## Slide 40/42 - Summary

The Specialized API Pattern Fit Assessment turns an "advanced capability" request into a defensible recommendation.

A strong assessment starts with the workflow need, considers the standard-pattern alternative, identifies the candidate specialized pattern, names the fit evidence, checks adjacent dependencies, and makes risks visible. It also defines data, quality, rights, safety, governance, tradeoffs, validation, escalation, exclusions, and the recommended next step.

The goal is not to make every solution specialized. The goal is to recommend only the level of specialization that the workflow evidence, validation plan, governance needs, and operational readiness can support.

## Slide 41/42 - Recap

In this course, you practiced deciding when a specialized API pattern is justified beyond a standard API pattern.

You evaluated Deep Research through the Responses API by considering workflow fit, approved data sources and tools, source quality, evidence review, traceability, synthesis risk, long-running execution, model currency, and review ownership. You also evaluated image understanding, image generation and editing, distillation, and optimization.

You brought that judgment together in a Specialized API Pattern Fit Assessment. The key takeaway: specialized does not mean better. Specialized patterns must be justified by workflow need, fit evidence, validation requirements, and responsible operation.

## Slide 42/42 - Congratulations

Use the Specialized API Pattern Fit Assessment when a customer asks for an advanced or specialized API capability. Start with the workflow, rule out simpler alternatives, and then recommend whether to use a standard pattern, validate a specialized pattern, gather more evidence, pause or escalate, or reject the specialized pattern.

This assessment helps teams decide whether a specialized pattern is justified by workflow evidence, validation needs, governance requirements, and operational readiness. Specialized patterns should only be recommended when they add necessary value that a standard pattern cannot provide.

**Course completed**

Next up in API Deployment Practitioner: **API Deployment Practice Application** (Course, 54 min)

Step into the role of a technical partner and sharpen your deployment judgment with a hands-on, evidence-led practice scenario. Review a realistic enterprise API deployment case for Northstar Retail Group, dissecting confirmed facts, assumptions, and open questions as you diagnose architecture, contract, security, data, validation, observability, and production-readiness gaps. Work through each module to build a practical API Deployment Practice Recommendation—identifying blockers, naming owners, and recommending safe next steps. Gain the skills to separate staging success from true deployment readiness, ensuring every recommendation is grounded in clear evidence, operational visibility, and a supportable handoff.
