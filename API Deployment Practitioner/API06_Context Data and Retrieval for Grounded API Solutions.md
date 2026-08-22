# Context, Data, and Retrieval for Grounded API Solutions

## Slide 1/39 - Title
Context, Data, and Retrieval for Grounded API Solutions
Created July 2026

## Slide 2/39 - Introduction

The API lets companies build intelligence into products and workflows. When outputs depend on approved business knowledge, retrieval can help — but it is not always the right choice.

In this course, you'll learn when to use retrieval, how to assess sources and access, and how to verify grounded outputs. You'll create a Context, Knowledge Access, and Retrieval Design Plan covering key sources, risks, and open questions.

## Slide 3/39 - What you'll learn

By the end of this course, you will be able to:

- Decide when retrieval is the right solution and when a model-only, structured-output, or human-assisted pattern is sufficient.
- Identify what business knowledge the API needs, then evaluate potential sources for authority, freshness, completeness, permissions, sensitivity, and source-of-truth status.
- Explain how RAG patterns, embeddings, vector search, metadata, and filtering support retrieval-grounded responses.
- Define verification tests for missing, conflicting, or outdated sources, unsupported claims, and permission boundaries.
- Produce a Context, Knowledge Access, and Retrieval Design Plan.

## Slide 4/39 - What you'll produce

In this course, you will create a Context, Knowledge Access, and Retrieval Design Plan.

By the end of the course, your plan should help another technical stakeholder understand what knowledge the API needs, where that knowledge should come from, whether retrieval is justified, and what evidence is needed before build or handoff.

Let's get started!

## Slide 5/39 - Introduction (Module: Decide when retrieval is the right solution)

Before designing retrieval, start with the workflow. A retrieval design should answer a real knowledge need, not simply attach documents to an API because documents exist.

In this module, you'll decide whether a workflow needs retrieval, does not need retrieval, or should pause until sources, permissions, or quality are validated.

This decision matters because retrieval affects contracts, context handling, security review, evals, guardrails, observability, and production-readiness planning.

## Slide 6/39 - Identify the knowledge requirement

Start by identifying what the API needs to know to support the workflow.

A good knowledge requirement is not "connect the model to our documents." It is a clear explanation of the business knowledge the workflow depends on, why that knowledge matters, and what could go wrong if the API answered from generic or outdated information.

For example, compare these two statements:

- Too vague: "The assistant needs access to company policies."
- Stronger: "The API needs access to the current employee leave policy and regional holiday policy because it will answer employee questions about available leave, carryover rules, and escalation paths. If the answer is generic or outdated, employees may receive incorrect guidance and HR may need to correct avoidable errors."

The stronger version makes the workflow, source need, risk, and downstream impact visible.

When defining the knowledge requirement, ask: What question, decision, or workflow step requires business knowledge? What decision, answer, workflow step, or customer-facing action will the context support? What information must be accurate? What source should ground the answer? What would be risky if the answer were generic, outdated, incomplete, or unsupported? What user or system action depends on the retrieved knowledge? Does the workflow require source references, citations, or reviewable evidence? Does the workflow depend on internal policies, customer records, product guidance, contracts, procedures, or other approved business knowledge? What should the API not claim, summarize, expose, or infer from the retrieved context?

That final question is important. Context design is not only about what the API can use. It is also about the output boundary: what the API should avoid saying when the source does not support it.

**What to capture in the plan**

| Plan field | What to write |
|---|---|
| Workflow step | The specific task, user moment, or system step the API supports |
| Required business knowledge | The policy, record, document, rule, guidance, or operational context needed |
| Source expectation | The source that should ground the answer |
| Accuracy risk | What could go wrong if the output is generic, outdated, or unsupported |
| Action or decision affected | What the user or system may do based on the answer |
| Evidence need | Whether the output needs source references, review notes, or traceability |
| Output boundary | What the API should not claim, infer, expose, or summarize |

A strong knowledge requirement helps downstream teams make better decisions about security, data handling, structured outputs, retrieval, tools, evals, guardrails, observability, and production readiness. It also helps prevent premature implementation work.

If the workflow does not have a clear knowledge requirement, retrieval may be unnecessary or unsafe to recommend.

## Slide 7/39 - Decide whether retrieval is needed

Once the knowledge requirement is clear, decide whether retrieval is the right pattern.

Retrieval is useful when the workflow needs approved, current, permission-aware business knowledge at the time the API responds. But retrieval also adds complexity. It introduces source selection, access control, metadata, freshness, retrieval-quality testing, failure behavior, and maintenance responsibilities.

Use retrieval when the workflow genuinely needs it. Do not use retrieval just because it sounds more advanced.

**Retrieval is more likely to be the right solution when:** the workflow depends on specific business documents, policies, records, or approved knowledge sources; answers must cite, reflect, or be traceable to current source material; generic model knowledge is not enough; the source changes over time; the workflow requires permission-aware access to internal knowledge; the output will influence a customer-facing answer, operational decision, compliance-sensitive workflow, or system action.

For example: an API that answers employee questions about current benefits rules likely needs retrieval from approved policy sources. An API that summarizes customer account history may need retrieval or data access from approved account records. An API that answers product-support questions may need current support articles, product guidance, and source-specific freshness rules.

**Retrieval may not be the right first solution when:** the task only needs general reasoning, drafting, classification, summarization, or transformation; the user already provides all required context in the request; a structured prompt, clearer API contract, or structured-output requirement would solve the issue first; the source is not approved or not available; source quality is too weak; source ownership is unclear; permissions are unresolved; the workflow cannot tolerate missing, conflicting, or outdated source behavior.

For example: an API that rewrites a user-provided paragraph into a shorter version may not need retrieval. The user has already provided the source text. Adding retrieval could increase latency, cost, testing complexity, and permission risk without improving the output.

**Three recommendation options:**

| Recommendation | Use when | What to hand off |
|---|---|---|
| Retrieval needed | The workflow depends on approved, current, permission-aware business knowledge. | Required sources, owners, access assumptions, source readiness, retrieval assumptions, and validation tests. |
| Retrieval not needed | A model-only, structured-output, or human-assisted pattern is sufficient. | Rationale for avoiding retrieval, plus any prompt, contract, or review requirement that should be used instead. |
| Defer pending source validation | Retrieval may be useful, but source approval, quality, ownership, freshness, or permissions must be resolved first. | Open source issues, validation owners, evidence needed, and next review step. |

**Decision flow:** Does the workflow require business knowledge outside the user request? If no, retrieval may not be needed. Does the workflow depend on approved, current, or traceable source material? If yes, retrieval may be appropriate. Are the sources approved, owned, current, complete, and permissioned for this workflow? If no, defer pending source validation. Would retrieval introduce more risk or complexity than value? If yes, choose a simpler pattern or defer. Can grounded output be verified before use? If no, retrieval should not proceed without additional validation or review design.

**Design implications**

| Approach | Factors |
|---|---|
| Contracts and structured outputs | If the API must show source references, evidence fields, or review flags, the output contract may need predictable fields |
| Security and data handling | If the API uses internal records, role-based access, or sensitive sources, access assumptions must be reviewed |
| Context and state | If the workflow spans multiple turns or users, teams must define what context is passed, retained, or excluded |
| Tools and actions | If retrieved knowledge affects an action, the action boundary and approval path must be clearer |
| Evals and guardrails | Grounded output needs tests for source relevance, unsupported claims, missing evidence, and unsafe use |
| Observability and production readiness | Teams may later need visibility into retrieval failures, source freshness, latency, cost, and permission issues |

Retrieval is not just a feature choice. It is a design commitment.

## Slide 8/39 - Define knowledge access

After deciding whether retrieval may be needed, define what knowledge the API is allowed to access. Knowledge access is the boundary between useful context and uncontrolled context.

It should answer: What does the API need to know? What is it allowed to know? What should it not retrieve, expose, summarize, or infer?

This matters because enterprise knowledge is rarely one clean folder of approved content. It may include draft documents, outdated policies, confidential notes, regional exceptions, customer-specific restrictions, regulated data, and role-based access rules.

A strong retrieval design does not say "connect all documents." It identifies the approved sources that are necessary for the workflow and excludes sources that are not ready, not permissioned, not relevant, or not safe to use.

**Capture the knowledge access requirement:** Which documents, systems, records, or knowledge bases are needed? Who owns each source? Who is allowed to access each source? What permissions apply by role, region, customer, team, or system? Which sources are approved for this workflow? Which sources should be excluded, masked, or escalated? What data, source, or access constraints have already been identified in the security and data-handling review? What access must be validated before retrieval is used?

**Source decisions:**

| Source decision | Meaning | Example |
|---|---|---|
| Include | The source is relevant, approved, current enough, owned, and permissioned for the workflow. | Current employee policy page approved by HR and available to all employees. |
| Exclude | The source should not be used for this workflow. | Draft policy notes, outdated training decks, confidential leadership memos, or sources outside the user's access. |
| Validate | The source may be useful, but approval, ownership, freshness, completeness, sensitivity, or permissions are unresolved. | Regional addendum with no named owner or unclear effective date. |

**Permissions are part of the design.** Permission-aware retrieval means the system should only retrieve content the user, workflow, or service is allowed to access. Do not assume permission behavior. Validate it. Permissions may depend on: user role, department, region, customer or tenant, product line, data classification, system ownership, contractual restrictions, internal approval rules, environment (development, staging, or production).

For example, a support manager and a frontline support agent may both use the same API, but they may not be allowed to retrieve the same customer records, internal notes, or escalation histories. A field team in one region may be allowed to view regional guidance that another region should not see.

**What to hand off:**

| Plan field | What to capture |
|---|---|
| Needed source | The document, record, system, or knowledge base |
| Source owner | The team or person accountable for the source |
| Access boundary | Who or what may access it |
| Workflow approval | Whether the source is approved for this workflow |
| Sensitivity | Any sensitive, customer-specific, regulated, or confidential data concerns |
| Include / exclude / validate | The current source decision |
| Validation owner | Who confirms approval, access, freshness, or source quality |
| Output boundary | What the API must not reveal or infer from this source |

The goal is to avoid treating "more context" as automatically better. A strong knowledge access decision should make clear what the API needs to know, what it is allowed to know, and what it should not retrieve.

## Slide 9/39 - Real-world example: Retrieval fit and knowledge access

A life sciences customer wants an API that answers field-team questions using approved product guidance. Field teams need quick answers while preparing for customer conversations. The customer wants the API to respond with guidance that reflects current approved materials, regional requirements, and internal review expectations.

Retrieval is likely needed because answers must come from approved, current sources rather than generic model knowledge.

The retrieval design should identify: which product guidance is approved for field-team use; who owns the guidance; which regions each source applies to; which source version is current; whether field users have permission to access the source; which draft or outdated materials must be excluded; what metadata filters are needed, such as product, region, approval status, and effective date; what tests are needed for missing, conflicting, or outdated source content.

- Weak recommendation: "Use RAG over all product documents."
- Stronger recommendation: "Retrieval is needed for this workflow, but only approved current product guidance and validated regional addenda should be used. Draft training decks and outdated field materials should be excluded. Source owners must validate current guidance, permission boundaries, metadata fields, and source freshness before retrieval is used in a pilot."

Compare with a separate workflow: a user provides a paragraph and asks the API to rewrite it into a shorter internal summary. That second workflow may not need retrieval because the user has already supplied the needed content. Adding retrieval would increase complexity without improving the outcome. A structured-output contract or clear prompt may be enough.

**What to notice:** Retrieval fit depends on the workflow knowledge need, not on whether documents exist. The life sciences field-team workflow needs approved source grounding. The rewrite workflow does not.

## Slide 10/39 - Recommended exercise: Decide whether retrieval is needed

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice deciding whether retrieval is the right solution.

**Task:** Review the three workflow examples below. Classify each as: Retrieval needed / Retrieval not needed / Defer pending source validation. Then explain the reason.

| Workflow | Context |
|---|---|
| A. Employee policy assistant | An internal HR API will answer employee questions about leave carryover, holiday rules, and escalation paths. Answers must reflect current approved HR policies by region. |
| B. Support ticket classifier | A support API will classify incoming customer messages into fixed categories: delivery issue, refund request, damaged item, product question, or account problem. The incoming ticket text contains all information needed for classification. |
| C. Regional pricing helper | A sales-support API will answer internal questions about region-specific pricing exceptions. The customer has several pricing spreadsheets, but some are draft files, ownership is unclear, and permissions differ by region. |

**Estimated time:** 8-10 minutes.

**Suggested output and reflection:** In your own notes, identify the recommended decision, why it fits, and what must be validated or handed off.

**Optional stretch:** Add one example where retrieval would make the solution worse because sources are weak, unapproved, outdated, or permission-restricted.

## Slide 11/39 - Knowledge check

**A customer is building an internal API to answer procurement-policy questions. The available sources are a current policy approved for all employees, an unapproved draft vendor-risk addendum, and an outdated training deck. Some policy rules also vary by region. What is the strongest retrieval recommendation?**

- Use general model knowledge and user-provided details instead of retrieval.
- Retrieve all three sources and rely on ranking to prioritize the most relevant content.
- **Retrieve only the approved current policy, filter by region, exclude the outdated deck, and validate the draft before use.** ✓ Correct
- Fine-tune on all available materials and remove the need for retrieval source controls.

Correct! Procurement answers require approved, current, region-specific sources. Use the approved policy, apply regional filters, exclude outdated content, and validate the draft before use. More sources do not automatically produce better grounding.

## Slide 12/39 - Summary

In this module, you learned that retrieval design starts with the workflow knowledge need, not with the decision to "add RAG." A strong recommendation explains what business knowledge the API needs, which source should ground the answer, and what could go wrong if the output is generic, outdated, incomplete, or unsupported.

The key takeaway is that more context is not automatically better. The right context is approved, relevant, current, permissioned, and specific enough for another technical stakeholder to review.

## Slide 13/39 - Introduction (Module: Evaluate sources, RAG patterns, embeddings, and vector search)

In this module, you'll evaluate whether the sources behind a retrieval design are ready for use. That means reviewing candidate documents, records, systems, knowledge bases, or approved content sets for ownership, approval status, freshness, completeness, permissions, and maintenance needs.

By the end of the module, you should be able to decide which sources to include, exclude, or validate before implementation, and what assumptions must be handed off for review.

## Slide 14/39 - Review candidate sources

Start by identifying which sources could support the workflow knowledge need. A candidate source is not automatically an approved source. It is simply something that might help ground the API response if it passes readiness review.

Candidate sources may include: approved documents, internal knowledge bases, structured records, support articles, policies and procedures, historical examples, operational systems or structured records where access and ownership are approved.

Do not treat every available source as automatically usable. A source should be included only if it is relevant, approved, owned, current enough for the workflow, and accessible under the right permissions.

**Source review starts with the workflow.** Ask: What answer, decision, or workflow step does this source support? Is this the authoritative source for that information? Is this source approved for the intended audience and use? Does the source contain sensitive, customer-specific, regulated, or restricted data? Is the source current enough for the workflow? Who owns the source? Who can confirm whether the source may be used? Which users, services, teams, regions, or systems may access it? Should this source be included, excluded, or validated before use?

**Common source types and what to watch for:**

| Candidate source type | Useful when | Watch out for | What to validate |
|---|---|---|---|
| Approved policy documents | The workflow needs official rules or procedures. | Policies may vary by region, role, or effective date. | Owner, approval status, version, region, access permissions. |
| Internal knowledge base | The workflow needs operational guidance or support content. | Articles may be stale, duplicated, or unofficial. | Source-of-truth status, freshness, article owner, review cadence. |
| Structured records | The workflow needs account, ticket, case, product, or operational data. | Access may be role-based or system-specific. | Data owner, allowed fields, permissions, minimization, sensitivity. |
| Support articles | The workflow needs troubleshooting or customer support guidance. | Customer-facing and internal-only content may be mixed. | Audience, approval status, effective date, escalation path. |
| Historical examples | The workflow needs examples of prior handling or decisions. | Past examples may not represent current policy or approved behavior. | Quality, relevance, anonymization, approval, review owner. |
| Operational systems | The workflow needs live or structured records from business systems. | Retrieval may overlap with tool or system access decisions. | System owner, permission model, data classification, access method. |

**Include, exclude, or validate:** Include sources that are relevant, approved, owned, current enough, and permissioned. Exclude sources that are outdated, unofficial, sensitive beyond the workflow boundary, unapproved, or not relevant. Validate sources that may be useful but have unresolved ownership, approval, freshness, completeness, sensitivity, or permission questions.

**What to hand off:** Source; Source type; Workflow use; Owner; Approval status; Include / Exclude / Validate; Reason; Validation owner.

A good source inventory should make the retrieval recommendation reviewable by technical teams, source owners, security teams, and customer stakeholders. It should also make exclusions visible. Excluding the wrong source can create gaps, but including the wrong source can create risk.

## Slide 15/39 - Assess source readiness

For each candidate source, assess whether it is ready to support a grounded API workflow. Source readiness is broader than relevance. A source may contain useful information and still be unsafe or unsuitable for retrieval.

Example: A product FAQ may contain relevant language, but if it is outdated, unofficial, or not approved for customer-facing use, the retrieval recommendation should be defer pending source validation rather than retrieval needed.

**Readiness criteria:** Owner; Approval status; Freshness; Completeness; Permissions; Format; Sensitivity; Source-of-truth status; Update or refresh cadence; Review or escalation owner when source quality is unclear; Conflict-handling expectation when sources disagree.

**What each criterion means:**

| Criterion | What it means | Design question |
|---|---|---|
| Owner | The person or team accountable for the source. | Who can confirm whether this source is approved and current? |
| Approval status | Whether the source is approved for this workflow and audience. | Is this source official, draft, archived, internal-only, or customer-facing? |
| Freshness | Whether the content is current enough for the workflow risk level. | When was it updated, and how often does it change? |
| Completeness | Whether the source contains enough information to support reliable answers. | Does the source cover the expected questions, edge cases, and regional differences? |
| Permissions | Who or what is allowed to access the source. | Can this user, service, workflow, tenant, region, or role retrieve it? |
| Format | Whether the source can be reliably searched or interpreted. | Is the source structured, text-based, scanned, duplicated, fragmented, or difficult to parse? |
| Sensitivity | Whether the source contains confidential, personal, regulated, or restricted information. | Does the source need masking, exclusion, role restrictions, or escalation? |
| Source-of-truth status | Whether this is the authoritative source. | Is this the official source, or just a copy, summary, or training aid? |
| Update cadence | How the source is maintained. | Who updates it, how often, and how will retrieval reflect updates? |
| Conflict handling | What happens when sources disagree. | Which source wins, and who resolves conflicts? |

**Source readiness decisions:**

| Readiness decision | Meaning | Next step |
|---|---|---|
| Ready to include | Source is relevant, approved, owned, current enough, complete enough, and permissioned. | Include in retrieval assumptions and define metadata or filtering needs. |
| Exclude | Source should not be used because it is unapproved, outdated, irrelevant, too sensitive, or outside the access boundary. | Capture reason for exclusion. |
| Validate before use | Source may be useful but has unresolved ownership, approval, freshness, quality, format, sensitivity, or permission questions. | Name validation owner and evidence required. |

**Risk of weak source readiness:** the API retrieves outdated guidance; the API uses draft content as if it were approved; the API blends conflicting sources without explaining the conflict; the API exposes information the user should not access; the API answers confidently when the source is incomplete; the API cites a source that is relevant but not authoritative; the API produces answers that cannot be reviewed or defended.

Retrieval can improve grounding only when the retrieved sources are ready for the workflow. It does not turn weak sources into trustworthy ones.

**What to hand off:** Source; Owner; Approval status; Freshness; Completeness; Permissions; Sensitivity; Source of truth; Update cadence; Decision; Open validation.

A strong handoff does not hide uncertainty. If source readiness is unclear, the right recommendation may be to defer retrieval until the source owner, system owner, security team, privacy team, or customer stakeholder validates the source.

## Slide 16/39 - Explain RAG patterns

RAG, or retrieval-augmented generation, is a pattern where the API retrieves relevant source content and uses it to ground the model response.

**A simple RAG flow:** a user or system sends a request → the workflow identifies what source content may be relevant → the retrieval layer finds relevant content from approved sources → the retrieved content is passed as context for the model response → the model generates an answer using the retrieved context → the system returns the answer, and where required, source references, review flags, or structured fields.

The purpose of RAG is not to make every answer automatically correct. The purpose is to give the model relevant, approved context so the output can be grounded, reviewed, and tested.

**RAG design decisions require:** what source content is available; how relevant content is found; whether users have permission to access it; how source freshness is maintained; how retrieved evidence is shown, cited, or reviewed; what happens when the source is missing, conflicting, outdated, inaccessible, or low quality; whether the output should be free text, structured output, or a human-reviewed draft.

**Common RAG pattern decisions:**

| Pattern | Use when | Avoid or defer when | Validation evidence |
|---|---|---|---|
| Single-source grounding | The workflow should use one approved source of truth. | Multiple sources contain necessary exceptions or regional differences. | Tests show the API retrieves the right section of the approved source. |
| Multi-source grounding | The workflow needs to compare or synthesize across several approved sources. | Sources conflict and no conflict-resolution rule exists. | Tests cover source conflicts, source priority, and missing-source behavior. |
| Retrieval plus structured output | Retrieved evidence must feed predictable fields for downstream review, routing, or integration. | The output schema is unclear or evidence fields cannot be reliably populated. | Schema validation, source-reference checks, and unsupported-claim tests. |
| Retrieval plus human review | Output affects a customer, sensitive workflow, policy interpretation, or operational decision. | No reviewer, escalation path, or review threshold is defined. | Review criteria, escalation triggers, and evidence fields. |
| Deferred retrieval | Retrieval may help, but source quality, access, approval, metadata, or maintenance is not ready. | Stakeholders want to proceed without resolving source risk. | Open validation owners and evidence required before build. |

The pattern should match the workflow need. Do not recommend RAG just because documents exist.

**Design implications:** Output structure may need fields for answer, source references, source date, unsupported evidence, confidence flags, or review status. Access control — the retrieval layer must respect source permissions. Source maintenance — source owners may need update cadence and approval workflows. Validation — teams must test expected-source retrieval, missing sources, conflicting sources, outdated sources, unsupported claims, and permission boundaries. Handoff — the implementation team needs source decisions, metadata assumptions, and validation owners before building.

**Light structured-output example:**

```json
{
  "answer": "Draft answer grounded in approved source content.",
  "source_references": [
    {
      "source_id": "approved-policy-2026-04",
      "section": "Eligibility",
      "effective_date": "2026-04-01"
    }
  ],
  "needs_review": false,
  "missing_evidence": [],
  "open_risks": []
}
```

This is not an implementation requirement. It is a design example. The exact API surface, schema approach, source-reference behavior, and supported product capability must be validated against current official documentation before implementation.

**When not to use RAG:** the user already provides the full source content; the task is simple classification, transformation, or formatting; the source set is unapproved or outdated; permissions cannot be enforced; source conflicts cannot be resolved; the workflow cannot safely handle missing or low-quality evidence; retrieval adds latency, cost, or maintenance burden without improving the outcome.

A strong retrieval recommendation includes both the pattern and the reason simpler patterns are not enough.

## Slide 17/39 - Explain embeddings and vector search

Embeddings are numerical representations that help compare the meaning of text or other content. Vector search uses embeddings to find content that is semantically similar to a query.

In retrieval design, embeddings and vector search can help the system find relevant content even when the user's wording does not exactly match the source. For example, a user might ask about "field guidance," while the approved source uses the phrase "representative talking points." Semantic retrieval may help connect those concepts.

**Why embeddings and vector search matter:** exact keyword search can miss relevant content when different terms mean similar things. They can help with large document sets; natural-language questions; vocabulary mismatch between users and source documents; support articles with varied phrasing; policies or procedures where the same concept appears under different terms; internal knowledge bases where users do not know the official source language.

**When they may be useful:** users ask natural-language questions; relevant content may use different wording from the query; the source set is too large for simple manual selection; the workflow benefits from semantic matching; retrieval results can still be validated for authority, freshness, and permissions.

**When they may not be enough:** they do not guarantee correctness, source authority, source freshness, completeness, permission compliance, or appropriate use in a regulated or customer-specific workflow. They find potentially relevant content. They do not prove that the content is approved, current, complete, or safe to use.

**Tradeoffs and risks:** relevant but wrong source (the retrieved passage is semantically similar but not authoritative); outdated match (the retrieved passage matches the question but comes from an old version); permission issue (the retrieved content is relevant but the user should not access it); partial answer (the retrieved passage answers only part of the question); false confidence (the model uses semantically related text to generate an answer that sounds grounded but is not fully supported); metadata gaps (the retrieval layer cannot filter by region, product, source type, approval status, or effective date).

**Validation evidence:** Do retrieval results come from approved sources? Are the retrieved passages relevant to the question? Are outdated sources excluded or filtered? Are permission boundaries respected? Are metadata filters applied correctly? Are source references useful enough for review? Does the API avoid unsupported claims when the retrieved content is weak or incomplete?

**What to hand off:**

| Assumption | What to document |
|---|---|
| Why semantic retrieval may help | The wording mismatch or source-search challenge it addresses |
| What sources it applies to | Approved source set, not all available documents |
| What it does not prove | Authority, freshness, completeness, permission compliance |
| What filters are needed | Metadata such as product, region, role, date, approval status |
| What must be tested | Relevance, source quality, permission boundaries, unsupported claims |

The goal in this course is not to configure a vector database. The goal is to understand how embeddings and vector search affect the retrieval design decision.

## Slide 18/39 - Explain metadata and permission-aware retrieval

Metadata helps retrieval use the right sources for the right workflow. Metadata is descriptive information about a source. It can help the retrieval design narrow the source set before or during retrieval, so the API is not searching across irrelevant, outdated, or unauthorized content.

Metadata can identify: source type, source owner, date or version, region, product, customer, role, department, policy status, approval status, sensitivity level.

**Why metadata matters:** without metadata, retrieval may return content that is semantically similar but wrong for the workflow. For example, a field-team workflow may need sources filtered by product, region, approval status, effective date, audience, sensitivity level. If the API retrieves an outdated regional addendum or a draft training deck, the answer may look grounded while still being unsafe or inaccurate.

**Permission-aware retrieval** means the system should only retrieve content the user, workflow, or service is allowed to access. Permission assumptions must be validated before deployment. If the retrieval design cannot explain who can access which source and why, the solution is not ready for enterprise use. It may need to consider: user role, team, region, customer or tenant, department, system identity, data classification, environment, approval status, customer policy.

**Metadata is not a substitute for access control.** Metadata can help narrow retrieval, but it should not be treated as a complete access-control design by itself. A metadata field such as `sensitivity: restricted` is only useful if the surrounding system enforces what restricted access means.

Example metadata:

```json
{
  "source_id": "regional-guidance-eu-2026",
  "product": "Product A",
  "region": "EU",
  "approval_status": "approved",
  "effective_date": "2026-05-01",
  "audience": "field_team",
  "sensitivity": "internal"
}
```

This metadata can help the retrieval design choose the right source. But the implementation still needs validated permission logic, source ownership, and test evidence.

**Tradeoffs:** too broad (retrieval may include irrelevant, outdated, or unauthorized sources); too narrow (retrieval may miss useful sources and return incomplete answers); poorly maintained (metadata may become stale even if source content is updated); inconsistent taxonomy (different teams may label product, region, date, or audience differently); permission drift (user roles or source access rules may change over time).

**Validation evidence:** A user in Region A should retrieve only Region A guidance. A user without access should not retrieve restricted content. Draft content should be excluded from approved-answer workflows. Outdated sources should not be used when current sources exist. If no approved source is available, the API should not fabricate an answer. If a source conflict appears, the API should escalate or follow the defined source-priority rule.

**What to hand off:**

| Field | Why it matters | Owner or validation need |
|---|---|---|
| Product | Prevents retrieval from the wrong product source | Product or source owner confirms valid taxonomy |
| Region | Prevents use of the wrong regional guidance | Regional owner or policy owner confirms |
| Approval status | Excludes drafts or unapproved content | Source owner confirms |
| Effective date | Prevents outdated guidance from being used | Source owner confirms update cadence |
| Audience or role | Limits content by user group | Security, system owner, or business owner validates |
| Sensitivity | Identifies content needing special handling | Security, privacy, or data owner validates |

Metadata and permission-aware retrieval make the context layer more precise. They help the API use the right approved knowledge, not just any semantically similar source.

## Slide 19/39 - Real-world example: Retrieval pattern and source readiness

A life sciences customer wants an API that answers field-team questions using approved product guidance, regional policy addenda, and internal support articles. Some documents are current and approved. Others are draft materials or outdated training decks.

The retrieval design should identify: which sources to include; which sources to exclude; which sources require validation; how metadata such as product, region, approval status, and effective date should filter results; why embeddings or vector search can help find related content but cannot prove that a source is current, approved, or permissioned.

**Source readiness review:**

| Candidate source | Decision | Reason |
|---|---|---|
| Current approved product guidance | Include | It is the likely source of truth if source owner, version, audience, and permissions are confirmed |
| Regional policy addenda | Include or validate | Useful if current and approved; metadata must include region and effective date |
| Internal support articles | Validate | May help answer operational questions, but audience, approval status, and source authority must be confirmed |
| Draft field training deck | Exclude | Draft materials should not ground answers unless formally approved for this workflow |
| Outdated training deck | Exclude | Outdated sources may cause the API to generate incorrect or unsupported guidance |

**Possible RAG recommendation:** "Retrieval is needed because the field-team workflow depends on approved, current product and regional guidance. Use a retrieval pattern that grounds answers in approved product guidance and validated regional addenda. Exclude draft and outdated training materials. Add metadata filters for product, region, approval status, and effective date. Validate permission boundaries for field-team roles before implementation. Add verification tests for missing sources, conflicting guidance, outdated sources, unsupported claims, and permission boundaries."

**What to notice:** Embeddings and vector search may help retrieve relevant passages when the field team uses different wording from the official guidance. But semantic similarity does not prove that a retrieved source is approved, current, complete, or permissioned. The design still needs source readiness, metadata, permission assumptions, and verification evidence.

## Slide 20/39 - Recommended exercise: Evaluate retrieval pattern and source readiness

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice choosing a RAG and retrieval approach.

**Task:** Review the customer context and candidate sources below. Decide which sources should be included, excluded, or validated. Then choose one of the following recommendations: RAG recommended / No RAG recommended / Defer pending source readiness.

**Customer context:** A customer wants an internal API that helps support agents answer questions about warranty coverage. Agents need responses that reflect approved warranty policy, product category, region, and effective date. Some answers may be used in customer-facing replies after agent review.

| Candidate source | Notes |
|---|---|
| Current warranty policy | Owned by Legal and Support Ops. Approved for support use. Updated quarterly |
| Regional warranty addendum | Relevant by region, but the owner is unclear and one version has no effective date |
| Product support articles | Useful for troubleshooting, but some articles are internal-only and others are customer-facing |
| Archived warranty deck | Two years old. Still appears in internal search results |
| Agent notes from prior cases | May contain useful examples, but includes customer-specific details and inconsistent handling |

**Estimated time:** 10-12 minutes.

**Suggested output and reflection:** In your own notes, identify which sources to include, exclude, or validate; which metadata or permission filters matter; and who would need to validate open questions.

**Optional stretch:** Add one permission filter and one freshness rule.

## Slide 21/39 - Knowledge check

**A partner team is designing an API for internal renewal briefs using CRM notes, support summaries, account plans, and usage reports. Source review shows sensitive CRM data, draft account plans, separate source owners, and account-level access limits. Which recommendation is strongest?**

- **Use retrieval only after permissions, sensitive data handling, draft exclusions, ownership, and account filters are validated.** ✓ Correct
- Use retrieval across all sources now, and add account filters and review controls during pilot testing.
- Use only support summaries for retrieval, and ask account managers to add the other details manually.
- Avoid retrieval for renewal briefs, and ask account managers to review every source manually first.

Correct! This is strongest because retrieval may be useful, but the source and access rules are not ready yet. The team should validate permissions, handle sensitive CRM notes, exclude or approve drafts, confirm source ownership, and enforce account-level access before recommending retrieval broadly.

## Slide 22/39 - Summary

In this module, you learned how to evaluate whether candidate sources are ready to support a retrieval-grounded API workflow. You reviewed source ownership, approval, freshness, completeness, permissions, metadata, and access boundaries before choosing a RAG pattern.

You also learned that embeddings and vector search can help find relevant content, but they do not prove that a source is correct, current, approved, or safe to use.

## Slide 23/39 - Introduction (Module: Verify grounded outputs)

Retrieval-grounded output should be verified, not trusted just because the API finds documents or sounds confident. A useful answer must come from approved, relevant sources and stay within the evidence those sources support.

In this module, you'll define retrieval-specific checks: whether the API retrieves the right sources, handles missing or conflicting evidence, respects permission boundaries, and provides source references that are clear enough for review.

This is not full eval, guardrail, human-review, or production-observability design. The goal is to identify the verification evidence needed before a retrieval-grounded API design can move forward.

## Slide 24/39 - Define retrieval tests

Retrieval tests should check two things: Did the API retrieve the right source content? Did the model use that retrieved context correctly?

A weak test only asks "Was the answer right?" That is not enough for a grounded API solution. The answer may sound correct while using the wrong source, mixing outdated guidance with current guidance, exposing restricted content, or adding unsupported details.

A stronger retrieval test asks: Did retrieval return the approved source? Did the answer stay within the retrieved evidence? Did the answer avoid unsupported claims? Did the answer handle missing, conflicting, outdated, or inaccessible evidence correctly? Did the answer respect permission boundaries? Did the output include source references where required?

**What to test:**

| Test category | What it checks | Why it matters |
|---|---|---|
| Golden questions | Known questions with expected sources and expected answer behavior. | Confirms retrieval works for high-value, expected workflow questions. |
| Expected source references | Whether the answer points to the correct source, section, record, or document where required. | Makes the response reviewable and easier to validate. |
| Missing-source behavior | What happens when no approved source supports the answer. | Prevents the API from filling gaps with generic or invented content. |
| Conflicting-source behavior | What happens when sources disagree. | Prevents the API from blending conflicting guidance without escalation or source-priority logic. |
| Outdated-source behavior | Whether outdated or superseded sources are excluded or flagged. | Protects workflows where source freshness affects accuracy or risk. |
| Unsupported-claim checks | Whether the model adds claims not supported by retrieved context. | Catches a common grounded-output failure: a source-backed answer with extra unsupported details. |
| Permission-boundary behavior | Whether users or workflows only retrieve content they are allowed to access. | Protects sensitive, restricted, customer-specific, or role-specific content. |
| Source-reference or citation-quality expectations | Whether source references are specific and useful enough for review. | Supports auditability, reviewer trust, and downstream validation. |
| Metadata and filter behavior | Whether filters such as region, product, role, approval status, or effective date work as intended. | Reduces the chance of semantically similar but wrong sources being used. |
| Escalation or no-answer behavior | Whether the API refuses, asks for clarification, or escalates when evidence is insufficient. | Keeps the workflow bounded when retrieval is weak. |

**What to capture in the design plan:** Add a Retrieval verification tests section using this structure: Test case; Expected source behavior; Expected output behavior; Risk tested; Owner or reviewer. For each test, capture: the workflow question or request; the user role or access boundary; the expected approved source; any excluded source; expected source reference behavior; expected answer behavior; expected escalation, clarification, refusal, or human-review trigger; what the test proves; what remains unproven.

A retrieval test should not try to prove that the full production system is ready. It should prove that the retrieval design is ready for the next technical review.

## Slide 25/39 - Review output behavior

After retrieval tests confirm whether the right source content is available, review how the API behaves when generating the final output.

This distinction matters. A retrieval layer may find the correct source, but the model can still produce a weak answer by summarizing it incorrectly, adding unsupported details, ignoring source conflict, or exposing restricted information.

**What to review:** Does the answer use retrieved context? Does it avoid unsupported claims? Does it cite, reference, or summarize the correct source where required? Does it show uncertainty where needed? Does it escalate when sources conflict? Does it avoid using outdated or unapproved content? Does it refuse, ask for clarification, or escalate when required context is missing, inaccessible, or unsafe to use? Does it avoid exposing content the user or workflow is not allowed to access? Does the output remain useful when retrieval returns partial or low-confidence evidence?

**Common grounded-output failure modes:**

| Failure mode | What it looks like | What to do |
|---|---|---|
| Unsupported addition | The answer starts from the right source but adds a detail the source does not support. | Add unsupported-claim tests and require source-bounded output behavior. |
| Wrong-source grounding | The answer uses a semantically similar source that is not authoritative. | Strengthen source-of-truth rules, metadata filters, and source-priority logic. |
| Outdated-source use | The answer cites an old policy or archived guidance. | Add effective-date filtering and outdated-source tests. |
| Missing-source overconfidence | Retrieval returns no useful source, but the answer still sounds confident. | Require clarification, refusal, escalation, or needs_review=true behavior. |
| Weak source reference | The answer says it used "the policy" without enough detail for review. | Define source-reference expectations such as source ID, section, version, or effective date. |
| Permission leakage | The answer exposes restricted content to a user who should not see it. | Add permission-boundary tests and validate access assumptions with the appropriate owner. |
| Conflict masking | Two sources disagree, but the answer presents one blended answer without flagging conflict. | Define source-priority rules or escalation behavior. |

**Light structured-output example:**

```json
{
  "answer": "Use only source-supported content here.",
  "source_ids": ["current-policy-2026-04"],
  "source_status": "approved_current",
  "unsupported_claims_detected": false,
  "needs_review": false,
  "review_reason": null
}
```

This is a design example, not a required implementation pattern. The exact schema, source-reference behavior, and API capability details must be validated against current official OpenAI documentation before implementation.

**Design implication:** Output behavior can shape API contracts (does the output need source IDs, confidence notes, review flags, or missing-evidence fields?); structured outputs (should downstream systems receive predictable fields?); guardrails and review (what output behavior should trigger clarification, refusal, escalation, or human review?); observability (what retrieval-quality signals may need review later?); handoff (what evidence should the next technical reviewer inspect before build?).

The goal is not to prove that retrieval makes every answer correct. The goal is to identify whether the retrieval design produces reviewable, bounded, and trustworthy-enough behavior for the workflow.

## Slide 26/39 - Monitor and improve retrieval quality

Retrieval quality can change over time. Source content, metadata, permissions, and user questions can all shift after the initial design. A document that was current during planning may become outdated later, and a filter that worked for one region may fail as the workflow expands.

At this stage, keep the focus on retrieval design rather than full production monitoring. Your goal is to identify the evidence, owners, and feedback loop needed to keep retrieval quality reviewable.

**What can change after design:** new source versions are published; old source versions remain searchable; metadata is missing, inconsistent, or stale; permissions change by role, team, customer, tenant, or region; new products, policies, regions, or workflows are added; users ask questions outside the original test set; source owners change update cadence; the retrieval pattern is adjusted without retesting source behavior.

**Capture retrieval-quality review needs such as:** Retrieval failures — questions where retrieval returned the wrong source, no source, or low-quality evidence. User feedback — feedback that suggests source mismatch, missing content, outdated content, or unclear answer behavior. Wrong-source examples — cases where the retrieved content was semantically similar but not authoritative. Unsupported-claim examples — outputs that added details beyond the retrieved source. Weak source references — answers where source references were missing, vague, or not useful enough for review. Permission-boundary concerns — cases where access rules were unclear or may have been violated. Source update need — whether a source owner needs to update, approve, archive, or replace content. Metadata update need — whether filters such as region, product, effective date, role, or approval status need improvement. Retrieval owner — who reviews retrieval behavior and coordinates changes. Source owner — who maintains each source and confirms whether it remains approved.

**A change may be justified when:** multiple questions retrieve the wrong source; a high-risk question retrieves weak or outdated evidence; permission tests fail or access assumptions are unclear; source owners confirm that the source set changed; metadata no longer reflects the workflow; human reviewers repeatedly flag unsupported claims; the system cannot safely answer common workflow questions.

**What to hand off:** who owns source maintenance; who owns retrieval behavior review; what retrieval-quality evidence should be reviewed; what issues should trigger correction or escalation; what should be retested when source, metadata, permission, or retrieval assumptions change.

The practical deployment judgment is simple: retrieval is not "set and forget." It needs owners, source discipline, and enough evidence to improve the design without guessing.

## Slide 27/39 - Real-world example: Grounded output verification

A life sciences customer is testing an API that answers field-team questions using approved product guidance. During verification, the team finds two issues:

1. One answer cites the correct approved source but adds a detail that does not appear in the retrieved document.
2. Another answer uses an outdated regional addendum because the metadata filter checks only the region, not the effective date.

Both answers look grounded at first glance. Each includes a source reference. But both are still unsafe to recommend.

**The team should add retrieval tests for:** unsupported claims (the first answer used the correct source but added unsupported detail); outdated sources (the second answer used a source that should have been excluded); source-reference quality (a citation or source reference is not enough if the answer does not stay within the cited evidence); metadata filters (region alone is not enough; effective date and approval status matter); permission boundaries (field-team access may vary by role, region, product, or customer context); missing-source behavior (the API should not guess when approved guidance does not support the answer); conflict behavior (if regional guidance conflicts with product guidance, the API should follow a source-priority rule or escalate).

**A stronger verification recommendation:** "Before recommending retrieval for this workflow, test whether the API retrieves only current approved sources, filters by product, region, approval status, and effective date, avoids unsupported details, and escalates when the retrieved source does not support the answer. Source owners should validate which regional addenda are current. Permission owners should validate field-team access boundaries. The design should not proceed until unsupported-claim, outdated-source, source-reference, and permission-boundary tests pass."

A grounded answer can still be wrong. A source reference does not prove that every claim is supported. Retrieval verification must check source selection, source use, output behavior, and escalation behavior.

## Slide 28/39 - Recommended exercise: Define retrieval verification tests

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice defining retrieval verification.

**Task:** Review the workflow example below and identify retrieval verification tests that would be needed before recommending the design.

**Workflow example:** A customer wants an internal API that helps support agents answer questions about warranty coverage. The API should use approved warranty policy, product category, region, and effective date. Some answers may be used in customer-facing replies after agent review.

Candidate sources include: current warranty policy approved for support use; regional warranty addenda with mixed ownership; product support articles with both internal-only and customer-facing content; archived warranty decks; agent notes from prior cases.

**Estimated time:** 8-10 minutes.

**Suggested output and reflection:** In your own notes, identify expected retrieval behavior, expected output behavior, risk tested, and likely owner or reviewer for these cases: approved warranty question; missing regional source; archived deck appears in search; internal-only support article; conflicting warranty guidance.

**Optional stretch:** Add one test for source relevance and one test for unsupported-claim risk.

## Slide 29/39 - Knowledge check

**A partner team tests a retrieval-grounded API for warranty questions. It retrieves the current policy but adds an exception not found in that source, while still showing a source reference. Which conclusion is strongest?**

- The output is verified because the right source appeared.
- Retrieval should be removed because one answer failed.
- **The output is unverified because the exception lacks support.** ✓ Correct
- Another source must exist, so the answer is acceptable.

Correct! This is the strongest conclusion because a source reference does not prove every claim is supported. The team should treat this as an unsupported-claim failure and add tests that check whether important claims stay within the retrieved evidence.

## Slide 30/39 - Summary

In this module, you learned that grounded output must be verified at both the retrieval step and the answer step. A useful test checks whether the API retrieved approved sources, stayed within the evidence, handled missing or conflicting context, respected permissions, and produced source references that reviewers can trust.

These checks help teams decide whether the retrieval design is ready for deeper technical review.

## Slide 31/39 - Introduction (Module: Complete the Context and Retrieval Design Plan)

You've defined the knowledge need, retrieval-fit decision, access requirements, source readiness, metadata, permissions, and verification tests.

In this module, you'll turn those pieces into a handoff-ready recommendation that helps stakeholders decide whether retrieval should proceed, proceed with conditions, or pause pending validation.

## Slide 32/39 - Build the plan

The Context, Knowledge Access, and Retrieval Design Plan should bring together the full retrieval design recommendation. It should answer five practical questions: 1) What does the API need to know? 2) Where should that knowledge come from? 3) Is retrieval justified and safe enough to move forward? 4) What must be validated before build, pilot, or handoff? 5) What lab evidence and lifecycle decision support the recommendation?

**Include these sections:**

| Plan section | What to include |
|---|---|
| Workflow knowledge need | The business knowledge the workflow depends on and why generic model knowledge is not enough. |
| Retrieval-fit decision | Retrieval needed, retrieval not needed, or defer pending source validation. |
| Knowledge access requirement | Which sources, systems, documents, or records the API may use. |
| Approved sources | Sources that are relevant, approved, owned, current enough, and permissioned. |
| Sources to exclude or validate | Sources that should not be used or require review before use. |
| Source owners and approval status | Who owns each source and whether it is approved for the workflow. |
| Source freshness, quality, and completeness assessment | Whether sources are current, authoritative, complete, and maintained. |
| Access and permission assumptions | Who or what may access each source and what boundaries apply. |
| RAG pattern recommendation | The recommended retrieval pattern and why it fits the workflow. |
| Embeddings and vector search assumptions | Where semantic retrieval may help and what it does not prove. |
| Metadata and filtering assumptions | Fields such as source type, owner, version, region, product, role, approval status, and sensitivity. |
| Quality risks | Known risks such as outdated content, source conflict, unsupported claims, or low source completeness. |
| Retrieval verification tests | Tests for source relevance, missing evidence, conflicts, outdated sources, unsupported claims, permissions, and source references. |
| Retrieval governance and retrieval-quality review needs | Source owners, retrieval owners, evidence to review, and update triggers. |
| Open questions and risks | Issues that must be resolved before the recommendation can move forward. |
| Downstream constraints | Tool, action, agentic workflow, guardrail, human-review, observability, or production-readiness constraints where relevant. |

Hosted retrieval evidence and lifecycle record the vector store and file IDs, file attributes, direct search and file_search evidence, citations, filter and no-source tests, retention or expiration decision, cleanup owner, and what the evidence does and does not prove.

Include these sections only as handoff constraints; do not design the full tool plan, guardrail plan, observability plan, or production-readiness plan at this stage.

**A strong plan should be clear.** By the end of the plan, a reviewer should understand: what business knowledge the API needs; why retrieval is or is not justified; which sources should ground the workflow; which sources should be excluded or validated before use; who owns each source; who is allowed to access each source; what metadata or filters are needed to narrow retrieval; what freshness or update rules matter; what RAG pattern is recommended; where embeddings or vector search may help retrieval; what embeddings and vector search do not prove; how grounded outputs will be verified; what should happen when sources are missing, conflicting, outdated, inaccessible, or low quality; what product evidence was captured in the lab; how vector-store and file application state will expire or be deleted; which findings remain assumptions that require product, security, or customer-owner validation.

**Plan quality check:**

| Weak pattern | Why it is weak | Stronger alternative |
|---|---|---|
| Use RAG | Too vague; does not define sources, permissions, validation, or failure behavior. | Use retrieval against approved current warranty policy and validated regional addenda, with filters for product, region, approval status, and effective date. |
| Connect the knowledge base | Does not identify source owners, quality, exclusions, or access boundaries. | Include only approved support articles owned by Support Ops; exclude archived and draft content. |
| The model should cite sources | Does not define source-reference quality or unsupported-claim checks. | Return source ID, section, version, and effective date where required; test for unsupported claims. |
| Permissions will follow existing access | Assumes implementation behavior without validation. | Validate role, region, tenant, and service-account access boundaries with the system owner. |

A plan is strong when it is specific enough for another technical team to review, challenge, and validate.

## Slide 33/39 - Make the plan actionable

A retrieval plan should support a clear next step. Avoid vague recommendations such as: Use RAG; Add retrieval; Connect the knowledge base; Ground answers in company documents; Use embeddings. Those statements name a technique, not a design decision.

An actionable plan should make validation work visible: what needs to be confirmed, who owns the decision, what evidence is required, and whether the issue blocks retrieval.

| Action item | Owner | Evidence needed | Blocks retrieval? |
|---|---|---|---|
| Confirm current approved policy source | Policy owner | Approved source version and effective date | Yes / No |
| Validate role-based access | Security or system owner | Access rule by role, team, region, or tenant | Yes / No |
| Confirm metadata taxonomy | Source owner or data owner | Product, region, approval status, and effective date fields | Yes / No |
| Retest missing-source behavior | Implementation or QA owner | Test results for no-source and conflicting-source cases | Yes / No |

**Identify blockers and conditions.** A strong plan should identify any source, permission, or quality gap that must be resolved before retrieval should be used in the solution. Examples: do not include draft product guidance until the source owner approves it; do not retrieve regional policy addenda until effective dates are confirmed; do not use customer-specific case notes unless data handling, permissions, and sanitization are approved; do not expose internal-only support articles in customer-facing output; do not proceed to customer-facing pilot until missing-source and unsupported-claim behavior are tested.

This "must not proceed" section helps prevent false readiness. It also makes the plan more useful for handoff because reviewers can see what is blocking, what is conditional, and what is safe to continue.

**Use the recommendation that fits the evidence:**

| Recommendation | Use when | What the plan should say |
|---|---|---|
| Retrieval needed | The workflow depends on approved, current, permission-aware business knowledge, and enough source evidence exists to proceed to technical validation. | Name included sources, excluded sources, metadata/filter assumptions, permissions, verification tests, and validation owners. |
| Retrieval not needed | The workflow can be handled with a model-only pattern, structured-output pattern, or human-assisted workflow without adding retrieval complexity. | Explain why retrieval would add complexity or risk without improving the workflow. |
| Defer pending source validation | Retrieval may be useful, but source approval, ownership, quality, freshness, metadata, or permissions are not ready. | Name the unresolved source gaps, validation owners, evidence needed, and next review step. |

**Validate current implementation details.** Some retrieval design choices depend on current API capabilities and implementation details, including retrieval features, embeddings, vector stores, file search, SDK behavior, limits, source-reference behavior, or supported API surfaces. Before implementation, confirm those details against current official OpenAI documentation and the project's technical review process.

## Slide 34/39 - Real-world example: Retrieval design recommendation

A life sciences customer wants an API that answers field-team questions using approved product guidance. The team has reviewed the workflow and found that answers must reflect current, approved sources. Generic model knowledge is not enough. The workflow may influence customer conversations, so output behavior needs to be source-grounded and reviewable.

**A strong source decision may say:**

| Source | Decision |
|---|---|
| Current approved product guidance | Include. Approved source of truth, pending source-owner confirmation and permission validation. |
| Validated regional addenda | Include if approved and current. Needed for regional variation; must include region, approval status, and effective-date metadata. |
| Draft training decks | Exclude. Draft materials are not approved for grounding field-team answers. |
| Outdated regional addenda | Exclude or validate. Could produce incorrect guidance unless source owner confirms current status. |
| Internal support articles | Validate. May be useful, but audience, approval status, and permission boundaries must be confirmed. |

**A strong retrieval recommendation may say:** "Retrieval is needed because the workflow depends on approved, current product and regional guidance. Use a retrieval-grounded pattern with approved product guidance and validated regional addenda. Exclude draft training decks and outdated regional addenda until source owners approve them. Add metadata filters for product, region, approval status, and effective date. Validate field-team role permissions before implementation. Add verification tests for missing sources, conflicting sources, outdated sources, unsupported claims, source-reference quality, and permission boundaries."

**Action and validation needs may include:** confirm product guidance source of truth with the product or policy owner; validate current regional addenda with regional source owners; confirm field-team access with security or the system owner; confirm metadata fields with the source owner or data owner; define verification tests with the implementation or QA owner; confirm source-reference expectations with the business owner or reviewer.

**The strongest recommendation may be:** "Retrieval needed, with conditions." The core source set appears justified, but implementation should not proceed until source owners validate regional addenda, permissions are confirmed, metadata filters are defined, and retrieval verification tests are ready.

This is stronger than "use RAG over product docs" because it names why retrieval is needed, which sources are included, which sources are excluded, what must be validated, which metadata matters, which tests prove readiness, and what should not proceed yet.

## Slide 35/39 - Recommended exercise: Finalize the Context, Knowledge Access, and Retrieval Design Plan

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Consolidate prior retrieval-design decisions into a handoff-ready recommendation.

**Task:** Use the retrieval-design decisions you developed earlier in the course, or use this warranty-support workflow as your starting point: an internal API helps support agents answer warranty questions using approved warranty policy, product category, region, and effective date. Review whether the Context, Knowledge Access, and Retrieval Design Plan is specific enough for technical handoff.

**Estimated time:** 8-10 minutes.

**Suggested output and reflection:** In your own notes, check whether the plan includes: retrieval-fit decision; included sources; excluded sources; sources that require validation; source owners; validation owners; permission assumptions; retrieval assumptions; metadata and filtering assumptions; verification tests; open risks; next validation step.

**Optional stretch:** Add a maintenance or source-refresh cadence.

## Slide 36/39 - Knowledge check

**A partner team's retrieval plan says: "Use RAG across warranty documents, support articles, archived decks, and prior agent notes, cite sources, and test a few normal questions." Which critique is strongest?**

- The plan is strong because it names sources and tests.
- **The plan is incomplete because controls and owners are missing.** ✓ Correct
- The plan should launch first and improve after use.
- The plan needs fine-tuning because warranty language is specialized.

Correct! This is the strongest critique because the plan names a technique but not the required design decisions. A stronger plan defines approved sources, exclusions, owners, permissions, metadata filters, missing-source behavior, unsupported-claim tests, and validation owners.

## Slide 37/39 - Summary

In this module, you assembled the retrieval-design decisions into a handoff-ready plan. A strong plan explains why retrieval is or is not justified, which sources are included or excluded, who owns validation, what tests must pass, and which risks remain open.

The plan should support a clear recommendation: proceed, proceed with conditions, defer, or avoid retrieval.

## Slide 38/39 - Recap

In this course, you decided when retrieval is needed, when it is not needed, and when it should pause until sources, permissions, or quality are validated.

You also practiced turning a workflow need into a Context, Knowledge Access, and Retrieval Design Plan.

The main takeaway is to make retrieval decisions clear before implementation begins. Clear source, access, and verification decisions reduce ambiguity, improve testing, and make handoff easier.

## Slide 39/39 - Congratulations

Congratulations, you've completed the course!

You can now use a Context, Knowledge Access, and Retrieval Design Plan to make retrieval assumptions visible before technical decisions are finalized.

Use this plan to support better retrieval design, technical validation, governance review, and implementation handoff.
