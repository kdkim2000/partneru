# Model and Capability Selection for API Solutions

## Slide 1/36 - Title
Model and Capability Selection for API Solutions
Created July 2026

## Slide 2/36 - Introduction

Model and capability choice is a deployment decision that starts from the workflow, not from the newest or most capable model on the catalog. This course produces a **Model and Capability Selection Rationale** that explains the recommended pattern, the rejected alternatives, the tradeoffs, the risks, and the validation questions that remain before build.

## Slide 3/36 - What you'll learn

- Define the task and capability requirements a workflow actually needs.
- Use the current official model catalog to build a dated shortlist of candidates.
- Compare shortlisted candidates against the workflow's real requirements.
- Reject candidates that are unnecessarily complex or uneconomic for the task.
- Produce a complete Model and Capability Selection Rationale.

## Slide 4/36 - Introduction (Module: Define task and capability requirements)

Selection starts with translating the customer's problem into a technical task: what input and output the workflow expects, what context is required, and what the risk profile and validation need look like.

## Slide 5/36 - Classify the task

Task classification is the first selection filter.

| Task type | Definition | Example API behavior |
|---|---|---|
| Generate | Produce new text, code, or content | Draft a reply, write a summary paragraph |
| Summarize | Condense existing content | Shorten a long ticket thread into a summary |
| Classify | Assign a label from a fixed set | Route a support message to a category |
| Extract | Pull specific fields from unstructured input | Pull order number and issue type from a message |
| Reason | Multi-step inference over inputs | Determine root cause from multiple signals |
| Transform | Convert one structured format to another | Convert free text into a JSON schema |
| Retrieve | Bring in external knowledge before responding | Look up policy documents before answering |
| Act through a tool | Call an external system/function | Look up an order status via a tool call |
| Support live/multimodal interaction | Real-time, streaming, or multimodal exchange | Voice assistant handling a live customer call |

When a workflow combines multiple task types, identify the primary output first by asking: "What must the API return or cause for the workflow to continue?" Map that primary output to its core task type.

- Weak task statement: "The API should understand customer messages."
- Strong task statement: "The API should classify each customer message into one of five fixed categories and return a structured label."

## Slide 6/36 - Define technical requirements

- **Input/output modality** — what forms of input and output the task requires (text, image, audio, structured data).
- **Reasoning depth** — how much multi-step inference the task requires.
- **Required context** — how much prior conversation, document, or retrieved content must be available.
- **Output structure** — whether the response must be free text or a structured/validated object, e.g.:

```json
{"routing_label": "delivery_issue", "priority": "high", "reason": "...", "needs_review": true}
```

- **Latency tolerance** — how quickly the workflow needs a response.
- **Throughput/scale** — expected request volume.
- **Reliability requirement** — how consistently the workflow needs valid, usable output.
- **Contract and interface requirements** — whether the workflow needs the Responses API, Chat Completions, or persisted Conversations state.

**Strong technical requirements summary (support-message classification example):**

| Task | Input | Output | Context | Reasoning depth | Latency | Throughput | Reliability | Review | Product validation |
|---|---|---|---|---|---|---|---|---|---|
| Classify | Customer message text | Structured label + priority + reason | Minimal (single message) | Low | Near real-time | High volume | High | On low-confidence cases | Confirm structured output support and rate limits |

## Slide 7/36 - Define risk and review requirements

- **Sensitive data** — does the task involve PII or regulated data?
- **Human-review need** — which outputs require a human check before acting?
- **Safety boundary** — what outputs or actions must never happen automatically?
- **Quality threshold** — what accuracy or consistency is acceptable?
- **Validation approach** — useful evidence types include representative success cases, edge cases, known failure cases, high-risk examples, and structured-output checks.
- **Data access/permission boundary** — what systems or data the model/tool may touch.
- **Governance/approval expectation** — who signs off before production use.
- **Observability evidence** — what should be logged and monitored per pattern:
  - Classification: label distribution, confidence, review-trigger rate.
  - Retrieval: source documents returned, grounding accuracy.
  - Tool use: call success rate, error rate, latency per call.
  - Realtime: session duration, dropped-connection rate, fallback rate.

Example risk/review summary: "Messages flagged as high-priority or low-confidence route to human review; no automated customer-facing action is taken without that check."

## Slide 8/36 - Real-world example: Defining capability requirements before choosing a model

Retail support-message classification workflow.

| Requirement | Detail |
|---|---|
| Business outcome | Faster, more consistent ticket routing |
| Workflow task | Classify inbound message and assign routing label |
| Input | Free-text customer message |
| Output | Structured label, priority, reason, needs_review flag |
| Modality | Text only |
| Reasoning need | Low to moderate |
| Context need | Single message, no history required |
| Latency and throughput | Near real-time, high volume |
| Quality threshold | High accuracy on common cases |
| Review need | Low-confidence and high-priority cases |
| Validation evidence | Representative and edge-case message sets |
| Product validation | Confirm structured-output and rate-limit behavior |

Selection takeaway: the likely first pattern is structured classification, not the most advanced model available. Retrieval, tool use, realtime interaction, or optimization techniques may become relevant later, but only if evidence shows the baseline pattern is insufficient.

## Slide 9/36 - Recommended exercise: Shortlist and compare model candidates

Example workflow: an IT helpdesk triage API that returns `issue_category`, `urgency`, `recommended_queue`, and `needs_review`.

Task: shortlist 2-3 current model candidates with exact IDs, sources, and a checked date, then compare them against task fit, modality, interface, context, output, operational, cost, and safety/review requirements.

Estimated time: 8-10 minutes.

## Slide 10/36 - Knowledge check

**A team has defined a structured classification workflow, and the current model catalog shows several compatible candidates. What is the best next step?**

- Default to the flagship model.
- Choose the model with the oldest, most-documented code samples.
- Choose the lowest-price candidate.
- **Run the same representative cases against the shortlisted candidates and compare task quality, schema behavior, review triggers, latency, and cost per successful task.** ✓ Correct

Correct! A current shortlist narrows the options, but task-specific evals provide the evidence needed for a defensible decision. The comparison should use predefined criteria and the same representative cases wherever possible.

## Slide 11/36 - Summary

At this stage, the rationale should record: candidate model IDs, source pages, verified date, pass criteria, representative test cases, the recommendation, the rejected candidates, and any volatile facts that need rechecking. Next: stress-testing cost, latency, reliability, safety, and operating assumptions.

## Slide 12/36 - Introduction (Module: Build and evaluate a current model shortlist)

Model selection is a current, evidence-led comparison — not a permanent ranking. The goal is to identify the least complex current candidate that meets the defined thresholds.

## Slide 13/36 - Build a current model shortlist

A shortlist is a filtered candidate set. For each candidate, record the exact model ID, the official source, the date checked, and the requirement or evidence that justifies inclusion.

| Filter category | What to assess | Exclude/hold when |
|---|---|---|
| Task and modality fit | Does the model support the required input/output types? | Modality unsupported |
| Interface and capability fit | Does it support the required API surface/features? | Feature unavailable |
| Context and output fit | Can it meet context length and structured-output needs? | Output cannot be validated |
| Operational fit | Does it meet latency/throughput needs? | Fails latency/throughput requirement |
| Cost inputs | Is total cost per successful task acceptable? | Cost exceeds budget with no offsetting benefit |
| Evaluation readiness | Can it be tested with representative cases? | No way to evaluate before commitment |

Models change regularly — update the shortlist for each new workflow rather than reusing an old one.

## Slide 14/36 - Avoid model-selection shortcuts

Shortcuts to avoid:

- Choosing the newest or most capable model by default.
- Choosing the lowest listed price without checking total cost per successful task, which includes input/output usage, failed attempts, retries/repair calls, additional model or tool calls, human correction/review, and operational overhead.
- Treating general benchmarks as proof for a specific workflow.
- Reusing an old implementation choice without rechecking it.
- Comparing candidates under different test conditions.
- Failing to record the exact tested model identity.

Selection principle: **"Choose the least complex candidate that meets the predefined quality, safety, latency, and task-economics thresholds."** If no candidate meets thresholds, improve the baseline, revisit requirements, or defer — don't force a selection.

## Slide 15/36 - Compare shortlisted models against the workflow

Distinguish must-have requirements (e.g., required modality, required structured output) from selection preferences (e.g., slightly lower latency, marginally lower cost).

**Example model comparison matrix:**

| Requirement | Candidate A | Candidate B | Candidate C | Decision implication |
|---|---|---|---|---|
| Text I/O + structured output | Supported | Supported | Not supported | Remove Candidate C |
| Inference interface | Compatible | Compatible | Compatible | No differentiator |
| Context/output requirements | Meets | Meets | N/A | — |
| Latency/volume | Marginal | Meets | N/A | Retain B with conditions |
| Cost inputs | Higher | Lower | N/A | Favor B |
| Additional capability | Unneeded | Unneeded | N/A | No credit given |
| Operational complexity | Higher | Lower | N/A | Favor B |

Decision positions: Retain / Retain with conditions / Remove / Defer. A "provisional lead" is not proof of an eval — carry validation questions forward.

## Slide 16/36 - Real-world example: Compare shortlisted models

Retail support-routing example needing `routing_label`, `priority`, `reason`, `needs_review` fields.

Shared case set and pass criteria: correct routing on common and edge cases, valid fields/allowed values, reliable review triggers, acceptable latency, acceptable total cost per successful task.

**Illustrative (fictional) results:**

| Candidate | Accuracy | Latency | Cost per successful task | Decision |
|---|---|---|---|---|
| A | High | Slower | Higher | Retain with conditions |
| B | High | Meets threshold | Lowest | **Recommended baseline** |
| C | Lower | Meets threshold | Lower | Remove (fails accuracy) |

Candidate B is recommended as the baseline because it meets all thresholds and has the strongest total cost per successful task.

Example recommendation statement: "Candidate B is recommended as the current baseline based on comparable test results against the shared case set."

What would change the recommendation: a shift in required accuracy, a change in volume driving different cost tradeoffs, new modality needs, or updated pricing/limits.

Selection takeaway: a defensible model recommendation is a dated conclusion from comparable task evidence, not a permanent ranking.

## Slide 17/36 - Recommended exercise: Match workflows to capability patterns

Example workflow: an IT helpdesk triage API that returns `issue_category`, `urgency`, `recommended_queue`, and `needs_review`.

Task: shortlist 2-3 current model candidates with exact IDs, sources, and a checked date, then compare them against task fit, modality, interface, context, output, operational, cost, and safety/review requirements.

Estimated time: 8-10 minutes.

## Slide 18/36 - Knowledge check

**A team has defined a structured classification workflow, and the current model catalog shows several compatible candidates. What is the best next step?**

- Default to the flagship model.
- Choose the model with the oldest, most-documented code samples.
- Choose the lowest-price candidate.
- **Run the same representative cases against the shortlisted candidates and compare task quality, schema behavior, review triggers, latency, and cost per successful task.** ✓ Correct

Correct! A current shortlist narrows the options, but task-specific evals provide the evidence needed for a defensible decision. The comparison should use predefined criteria and the same representative cases wherever possible.

## Slide 19/36 - Summary

At this stage, the rationale should record: candidate model IDs, source pages, verified date, pass criteria, representative test cases, the recommendation, the rejected candidates, and any volatile facts that need rechecking. Next: stress-testing cost, latency, reliability, safety, and operating assumptions.

## Slide 20/36 - Introduction (Module: Add risk, cost, and validation logic)

The goal of this module is to stress-test the recommendation against cost, scale, latency, reliability, safety, and validation needs. This is not building a detailed pricing model, an eval suite, a security architecture, or a monitoring plan — it is naming the assumptions and evidence still needed.

## Slide 21/36 - Cost and scale assumptions

Cost means comparing total cost per successful task using dated price inputs.

Starting questions: What is the request volume? Is it steady or bursty? What are typical input/output lengths? Is retrieval, tool use, realtime, or multimodal support needed? Is a uniform capability level required across all requests, or can routine and edge cases be routed differently? How might volume grow after a pilot?

| Estimation category | Why it matters |
|---|---|
| Request volume | Drives total cost and throughput needs |
| Input length | Affects token cost and latency |
| Output length | Affects token cost and latency |
| Tool or retrieval usage | Adds cost and complexity per request |
| Latency need | Constrains model/pattern choice |
| Expected growth | Affects whether current choice remains viable |
| Success rate, retries, rework | Hidden cost driver often missed |

Do not add a higher-capability/cost model, retrieval, tools, or specialized/optimized approaches before the baseline has been validated.

Example cost/scale note: "At current pilot volume, Candidate B's total cost per successful task is lowest among tested candidates; this should be rechecked if volume grows 10x."

Handoff implication: cost and scale should be recorded as validation questions, not fixed commitments.

## Slide 22/36 - Latency and reliability assumptions

**Latency** is how quickly the workflow needs a usable response. **Reliability** is how consistently the workflow receives valid, usable output.

Workflow expectation types: synchronous, streaming, asynchronous, timeout, retry, fallback, valid structured output, review/escalation, and a clear error state.

Questions to ask about latency: What is the maximum acceptable response time? Does the interaction need to stream? What happens on timeout?

Reliability definitions by pattern:
- Structured classification: consistent valid labels and low review-trigger rate.
- Retrieval-supported: consistent grounding in the correct source documents.
- Tool-enabled: consistent successful tool calls with graceful failure handling.

Example latency/reliability note: "Responses must return within 2 seconds at the 95th percentile; failed calls fall back to a default queue with a flagged review."

Handoff implication: flows into contract, validation, and observability work. Signals to track include latency, timeout rate, structured-output validity, retry rate, review-trigger volume, fallback use, and failure categories.

## Slide 23/36 - Safety and validation assumptions

Validation means identifying the evidence needed before trusting a selection — not designing a full eval suite, guardrails, moderation, or monitoring system.

Failure-mode considerations by pattern:
- Structured classification: mislabeling, low-confidence cases treated as confident.
- Retrieval-supported: citing the wrong or outdated source.
- Tool-enabled: calling the wrong tool or acting on stale data.

Validation evidence: representative success cases, edge cases, known failure cases, high-risk examples, structured-output checks, human review of ambiguous outputs, baseline comparison, latency/throughput checks, and product-fact validation.

Notes: human review triggers should be explicit; security/data sensitivity should be flagged early; product facts (pricing, limits, capabilities) should be validated against official documentation, not assumed.

Example safety/validation note: "All high-priority and low-confidence classifications route to human review before any customer-facing action."

Handoff implication: routes open questions to security/data handling, retrieval design, tool design, evals/guardrails, observability, or production readiness.

## Slide 24/36 - Real-world example: Stress-testing cost, latency, safety, and validation assumptions

Retail seasonal-peak routing scenario.

Weak initial recommendation: "Use a high-capability model for every message, with a detailed explanation each time."

**Stress test:**

| Dimension | Stress-test question | Why it matters |
|---|---|---|
| Cost | What is total cost per successful task at peak volume? | High-capability model for every message multiplies cost |
| Output length | Is a detailed explanation needed for every message? | Longer output increases cost and latency without added value |
| Latency | Does response time hold at peak volume? | Peak load may violate latency requirements |
| Reliability | Does the model behave consistently at scale? | Untested at true peak conditions |
| Safety | Are high-risk cases still flagged for review? | Full automation risks unreviewed high-priority misses |
| Validation | Has this been tested against representative peak-season cases? | Off-season testing may not reflect peak behavior |
| Fallback | What happens if the model or a dependency fails at peak? | No fallback risks a full outage during peak |

Stronger selection note: use the structured classification baseline with concise required fields, reserving detailed explanations only for flagged review cases.

Tradeoff takeaway: added capability, length, or complexity must be justified by evidence tied to the workflow's actual needs.

## Slide 25/36 - Recommended exercise: Stress-test a selection rationale

IT helpdesk routing scenario with an over-engineered proposed recommendation: using the most advanced model for all requests, generating a long explanation, and adding speculative retrieval.

Task: answer cost and scale, latency, reliability, safety and review, pattern fit, and product validation questions about the proposal.

Estimated time: 8-10 minutes. Optional stretch: add a fallback/downgrade strategy.

## Slide 26/36 - Knowledge check

**A partner recommends using a high-cost model with long explanations and retrieval for every request in a high-volume support-routing API, even though the workflow only needs short structured fields. What is the strongest critique?**

- **The recommendation is incomplete because added cost, latency, retrieval, and output length are not justified.** ✓ Correct

Correct! A defensible rationale should name the cost, scale, latency, reliability, safety, and validation assumptions that support the selected pattern. More complexity should be justified by evidence.

## Slide 27/36 - Summary

The rationale should name what is known, what is assumed, and what evidence is still needed for cost, scale, latency, reliability, safety, and validation. It should also name tradeoffs, review triggers, fallback questions, and product facts to validate before build or recommendation.

## Slide 28/36 - Introduction (Module: Complete the Model and Capability Selection Rationale)

This module brings together workflow requirements, the model shortlist, comparisons, and stress-tested assumptions into the final course artifact: a customer-ready technical rationale recording the current shortlist, verified sources/date, eval evidence, the recommendation, rejected candidates, tradeoffs, volatile product facts, risks, and the next review area.

## Slide 29/36 - Build the rationale

The Rationale is a decision artifact — not a product tour, a model ranking, a final architecture, or a production plan.

| Section | What to capture |
|---|---|
| Workflow task | The specific task the API must perform |
| Business outcome or customer value signal | Why this matters to the customer |
| Input and output modality | What forms of input/output are required |
| Required capabilities | Reasoning depth, context, structure, etc. |
| Relevant contract and interface requirements | API surface, state handling |
| Candidate capability patterns | Patterns considered (classification, retrieval, tool use, etc.) |
| Recommended pattern | The selected candidate and why |
| Rejected alternatives and rationale | Other candidates and why they were not chosen |
| Cost-latency-scale-reliability-safety-review tradeoffs | Key tradeoffs behind the recommendation |
| Risks | Known risks and mitigations |
| Validation questions | What still needs to be tested or confirmed |
| Next review area | What should be revisited next |

Example concise rationale statement: "Model Candidate B is recommended as the current baseline for structured message classification based on comparable evaluation results against the shared test case set."

## Slide 30/36 - Make the rationale defensible

- Use the current model catalog without treating it as a permanent ranking.
  - Weak: "Use the best available model."
  - Strong: "As of [date checked], Candidate B is the recommended baseline based on current catalog and test results."
- Use durable decision criteria: task type, modality, reasoning need, context requirement, output structure, latency tolerance, throughput, cost/scale, reliability, safety/review, operational risk, validation evidence.
- Isolate volatile product facts from decision logic.
  - Decision logic: "The workflow requires structured output with low latency."
  - Product fact to validate: "Confirm current pricing and rate limits for Candidate B before build."
- Name what must be confirmed before build: model/API-surface support, structured-output behavior, modality support, tool/retrieval capability, pricing/usage, limits/rate-limits, safety/data-handling, latency/throughput/reliability, and review/escalation ownership.
- Identify deeper review areas: security/data, retrieval, tool design, evals/guardrails, observability, optimization.
- Identify interface assumptions that affect the selection.
- Explain what would change the recommendation:
  - If routing depends on approved policies → add retrieval.
  - If routing depends on live order data → add tool use.
  - If quality fails the baseline → move to stronger capability or optimization.
  - If latency fails at peak → simplify the approach or add a fallback.
  - If sensitive data is involved → pause for a data-handling review.

## Slide 31/36 - Real-world example: Turning selection logic into a customer-ready recommendation

Retail high-volume triage scenario, with each rationale section filled in:

| Section | Example content |
|---|---|
| Workflow task | Classify inbound support message and assign routing label |
| Business outcome | Faster, more consistent ticket routing at peak volume |
| Input/output modality | Text in, structured JSON out |
| Required capabilities | Low-to-moderate reasoning, structured output |
| Contract/interface requirements | Responses API with structured output |
| Candidate capability patterns | Structured classification (baseline); retrieval and tool use considered and deferred |
| Recommended pattern | Model Candidate B, structured classification |
| Rejected alternatives | Candidate A (higher cost, no added accuracy); Candidate C (fails accuracy/modality) |
| Tradeoffs | Lower cost and latency vs. slightly less detailed explanations |
| Risks | Misrouting on ambiguous edge cases |
| Validation questions | Peak-volume latency, pricing/limits recheck |
| Next review area | Retrieval for policy-dependent routing if accuracy requirements rise |

- Weak recommendation: "Use the flagship model because the workflow is important."
- Strong recommendation: "Use Model Candidate B as the current baseline because it met every required threshold with the strongest total task economics among the candidates tested, as of [date checked]."

## Slide 32/36 - Recommended exercise: Finalize the Model and Capability Selection Rationale

Task: consolidate all prior decisions into the final rationale for the retail support-routing example, confirming all 12 structure sections.

Estimated time: 8-10 minutes. Optional stretch: add a benchmark/evaluation question.

## Slide 33/36 - Knowledge check

**A partner's Model and Capability Selection Rationale includes the workflow requirements, current shortlist, recommended candidate, and expected tradeoffs. However, it does not explain why the other candidates were rejected or identify which product facts must be checked again. What is the most important improvement? Select the strongest answer.**

- **Add the rejected candidates and supporting rationale, then record the model details, pricing, limits, and availability that must be revalidated.** ✓ Correct
- Remove the dated shortlist so the rationale remains valid if model names or pricing change.
- Add a longer description of every available model so the reader can compare the full catalog.
- Replace the current recommendation with the most capable candidate to reduce the chance of future changes.

Correct! A defensible rationale should explain both the recommendation and the rejected alternatives. It should also separate durable decision logic from product facts that may change and must be revalidated before build.

## Slide 34/36 - Summary

In this module, you consolidated your course decisions into a Model and Capability Selection Rationale. A strong rationale captures the workflow task, business outcome, required capabilities, contract and interface requirements, candidate patterns, recommended pattern, rejected alternatives, tradeoffs, risks, validation questions, and next review area.

A strong rationale is more than a recommendation. It is the evidence-backed explanation of why the pattern fits the workflow, why alternatives are not the right first choice, what assumptions or risks remain, what product facts must be checked, and what evidence would validate or change the recommendation.

## Slide 35/36 - Recap

In this course, you practiced model and capability selection as deployment judgment. You learned how to define workflow requirements, build a dated shortlist from current official guidance, compare model candidates, and assess total task economics, latency, reliability, safety, and operating risk.

When a team asks which model or API capability to use, start with the workflow. Filter the current catalog, test comparable candidates against predefined criteria, and select the least complex option that meets the required threshold.

The rationale is not the final build specification; it is the decision artifact that explains why a capability pattern fits the workflow and what must be validated next.

## Slide 36/36 - Congratulations

Congratulations, you've completed this course!

You can now create a Model and Capability Selection Rationale that explains why a recommended pattern fits the workflow, why alternatives are not the right first choice, what assumptions must be validated, and what review area comes next.

**Next up in API Deployment Practitioner:** API Security, Data Handling, and Access Controls (Course, 48 min) — Unlock practical, real-world skills for evaluating API security, data handling, and access controls before deployment. Learn to map data flows, classify sensitivity, apply data minimization, and distinguish authentication from authorization while ensuring secrets are protected and permissions follow least privilege. Master the art of defining approval gates, auditability, and remediation actions, and bring it all together with a concise API Security and Data Handling Review that makes risks and next steps visible for any workflow. Build the judgment to spot blockers, document evidence gaps, and confidently recommend whether to proceed, conditionally advance, remediate, or escalate—empowering safer, smarter API launches.
