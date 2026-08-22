# Prompt Design, Evals, Moderation, Guardrails, and Human Review

## Slide 1/52 - Introduction

Prompt Design, Evals, Moderation, Guardrails, and Human Review

This course treats prompt behavior, evaluations, moderation, guardrails, structured outputs, and human review as deployment controls that shape how an API behaves in production, not just as isolated technical features.

You will learn how to define expected API behavior, test it against realistic and edge cases, identify failure categories, and use evidence to recommend release, remediation, pause, or escalation.

By the end of the course, you will build an API Behavior Validation and Guardrail Plan — a handoff artifact showing tested controls, ownership, open risks, and release decisions.

## Slide 2/52 - Introduction (Module: Add moderation and application safety checks)

Add moderation and application safety checks

This module introduces moderation and application-level safety checks as complementary controls. OpenAI moderation models cover documented harmful-content categories, but they are one signal among several. Application-specific checks are needed for authorization, customer policy, source approval, sensitive context, misuse detection, and downstream actions that moderation does not cover.

## Slide 3/52 - What moderation covers

What moderation covers

OpenAI's moderation models classify content against a defined set of harmful-content categories (for example: violence, self-harm, sexual content, hate, and harassment).

Moderation is a signal that flags content matching these documented categories. It does not understand your business rules, your customers' policies, your data-access rules, or your workflow-specific risks.

## Slide 4/52 - What moderation does not cover

What moderation does not cover

Moderation does not verify:

Whether the requester is authorized for the action.
Whether the request violates a customer-specific or company-specific policy.
Whether the source content used to answer is approved or trustworthy.
Whether the context is sensitive for reasons outside standard harm categories (e.g., legal, financial, health-adjacent workflows).
Whether the request is a misuse pattern specific to your product.
Whether a downstream action (e.g., issuing a refund, changing access, sending an email) is safe to execute automatically.

## Slide 5/52 - Pair moderation with application-specific checks

Pair moderation with application-specific checks

Because moderation only covers documented harmful-content categories, teams must add deterministic, application-specific checks for:

Authorization: Does this user/role have permission for this action or data?
Customer policy: Does this comply with the specific customer's or organization's rules?
Source approval: Is the underlying information from an approved, trusted source?
Sensitive context: Does this topic require extra caution even if not classified as harmful (e.g., medical, legal, financial specifics)?
Misuse patterns: Is this request part of a known abuse or misuse pattern for this product?
Downstream actions: Should this action require confirmation, additional validation, or human review before executing?

Moderation is one signal. Application-specific, deterministic checks close the gaps moderation cannot address.

## Slide 6/52 - Knowledge check

**Question:** A team relies only on OpenAI's moderation model to decide whether an API response is safe to send to a customer. What is the biggest risk with this approach?

- Moderation is too slow to run in production.
- Moderation only covers documented harmful-content categories and misses authorization, policy, source, and workflow-specific risks. **✓ Correct**
- Moderation cannot be used with structured outputs.
- Moderation requires human review for every request.

Moderation is one signal that flags documented harmful-content categories. It does not check authorization, customer policy, source approval, sensitive context, misuse patterns, or downstream actions — those require application-specific deterministic checks.

## Slide 7/52 - Real-world example: Moderation is not enough

Real-world example: Moderation is not enough

An internal HR-assistant API answers employee questions about benefits using approved HR documents.

Moderation correctly blocks a request containing harassment language. However, moderation does not catch:

A request asking the assistant to disclose another employee's personal benefits information (an authorization violation).
A request asking about a benefit that does not exist in the approved source documents (an unsupported-claim risk).
A request from a manager attempting to use the assistant to make an employment decision (a misuse pattern requiring escalation).

The team adds application-specific checks: an authorization check tied to employee ID, a source-grounding check requiring citations from approved documents, and a workflow boundary that refuses to support employment decisions.

## Slide 8/52 - Recommended exercise: Identify moderation gaps

Recommended exercise: Identify moderation gaps

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice identifying risks that moderation does not cover and designing application-specific checks to close those gaps.

**Task:** Consider an API that helps customers request refunds. List at least four risks moderation would miss (e.g., authorization, refund-policy compliance, fraud patterns, downstream action safety) and describe an application-specific check for each.

**Estimated time:** 8–10 minutes

**Suggested output and reflection:** A short list mapping each moderation gap to a corresponding application-specific check, for later inclusion in the API Behavior Validation and Guardrail Plan.

## Slide 9/52 - The confidence_note caution

The confidence_note caution

Some APIs include a model-authored `confidence_note` field explaining why an answer might be uncertain.

Important: a `confidence_note` is explanatory text, not a calibrated confidence score. It should never be used alone as a trigger for a low-confidence workflow path.

Instead, pair it with at least one of:

Source evidence (e.g., whether citations/sources were found).
A deterministic rule (e.g., missing required fields).
A validated evaluator that has been tested against known cases.
Human review.

## Slide 10/52 - Summary

Summary

In this module, you learned that OpenAI moderation models cover documented harmful-content categories but are only one signal. Application-specific deterministic checks are required to cover authorization, customer policy, source approval, sensitive context, misuse patterns, and downstream actions. You also learned that a model-authored `confidence_note` is explanatory text, not a calibrated score, and must be paired with other evidence before being used as a workflow trigger.

## Slide 11/52 - Introduction (Module: Add guardrails)

Add guardrails

This module covers guardrails: deterministic or rule-based checks layered around model behavior to enforce boundaries that moderation and prompting alone cannot guarantee.

## Slide 12/52 - What a guardrail is

What a guardrail is

A guardrail is a deterministic check — a rule, validator, or filter — applied before or after a model call to enforce a boundary the model itself might not reliably respect.

Guardrails do not rely on the model to police itself. They exist because prompts, even well-designed ones, do not provide guaranteed enforcement.

## Slide 13/52 - Types of guardrails

Types of guardrails

Input guardrails: Checks applied to what enters the model (e.g., blocking disallowed request types, validating required fields, restricting inputs by role).
Output guardrails: Checks applied to what the model returns (e.g., verifying claims cite approved sources, blocking disallowed action types, checking for policy compliance).
Structural guardrails: Enforce format and schema compliance (e.g., required fields present, valid enum values, correct data types).
Behavioral guardrails: Enforce workflow-boundary rules (e.g., refuse to bypass authorization, refuse to provide unsupported medical/legal/financial advice as final).

## Slide 14/52 - Knowledge check

**Question:** Why are guardrails necessary even when the prompt already instructs the model on what not to do?

- Guardrails make the prompt shorter.
- Prompt instructions alone do not guarantee enforcement; guardrails provide deterministic checks that catch cases where the model doesn't follow instructions. **✓ Correct**
- Guardrails replace the need for moderation.
- Guardrails are only needed for structured outputs.

Prompt instructions describe desired behavior but cannot guarantee it. Guardrails add deterministic enforcement, catching violations the model may still produce despite instructions.

## Slide 15/52 - Designing a guardrail set

Designing a guardrail set

To design an effective guardrail set:

Identify the workflow boundary: What must never happen (e.g., bypassing authorization, giving unsupported advice as final, exposing restricted data)?
Map each boundary to a specific check: Each guardrail should map to a specific risk, not be a vague catch-all.
Decide where the check runs: Input-side, output-side, or both.
Decide the failure behavior: Block, ask for clarification, escalate to human review, or return a structured refusal.
Test the guardrail against both normal and adversarial cases.

## Slide 16/52 - Real-world example: Guardrails for a benefits-eligibility API

Real-world example: Guardrails for a benefits-eligibility API

An API answers employee questions about benefits eligibility using approved policy documents.

The team designs these guardrails:

Input guardrail: Reject requests asking about another employee's specific eligibility unless the requester has HR authorization.
Output guardrail: Require that any eligibility determination cite a specific policy source; if no source is found, return `needs_review: true` instead of a final answer.
Structural guardrail: Validate that the response always includes `answer`, `source_ids`, and `needs_review` fields in the correct format.
Behavioral guardrail: Refuse to state a final eligibility determination for edge cases not explicitly covered by policy; route those to human review instead.

## Slide 17/52 - Recommended exercise: Design a guardrail set

Recommended exercise: Design a guardrail set

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice mapping workflow boundaries to specific, testable guardrails.

**Task:** For an API that helps customers cancel a subscription, identify at least three workflow boundaries (e.g., must not cancel without identity verification, must not offer unauthorized discounts, must not bypass a required retention-offer step) and design a guardrail for each, including where it runs and its failure behavior.

**Estimated time:** 8–10 minutes

**Suggested output and reflection:** A guardrail table (boundary → check → location → failure behavior) for inclusion in the API Behavior Validation and Guardrail Plan.

## Slide 18/52 - Summary

Summary

In this module, you learned that guardrails are deterministic checks layered around model behavior to enforce boundaries prompting alone cannot guarantee. Guardrails can apply to inputs, outputs, structure, or behavior, and each should map to a specific workflow risk with a defined failure behavior (block, clarify, escalate, or refuse).

## Slide 19/52 - Introduction (Module: Add structured-output validation)

Add structured-output validation

This module covers structured-output validation: verifying that model responses conform to an expected schema so that downstream systems can rely on the output's shape and content.

## Slide 20/52 - Why structured-output validation matters

Why structured-output validation matters

When an API returns structured fields (e.g., `answer`, `source_ids`, `confidence_note`, `needs_review`), downstream systems depend on those fields being present, correctly typed, and internally consistent.

A malformed or incomplete structured output can silently break downstream automation, even if the answer content itself looks reasonable.

## Slide 21/52 - What to validate

What to validate

Required fields: Are all required fields present?
Types and formats: Are values the correct type (string, boolean, enum, array)?
Internal consistency: Does `needs_review: true` come with a `review_reason`? Does a refusal come without a populated `answer`?
Enum compliance: Are categorical fields limited to the allowed set of values?
Non-empty constraints: Are fields like `source_ids` populated when required (e.g., whenever a factual claim is made)?

## Slide 22/52 - Knowledge check

**Question:** An API returns `needs_review: true` but leaves `review_reason` empty. What is the correct response?

- Accept the output since `needs_review` is set correctly.
- Treat this as a structured-output validation failure, since the fields are internally inconsistent. **✓ Correct**
- Ignore `review_reason` since it is optional.
- Escalate directly to the customer.

Internal consistency is part of structured-output validation. A `needs_review: true` flag without a populated `review_reason` is a validation failure — the output does not give a human reviewer enough information to act.

## Slide 23/52 - Handling validation failures

Handling validation failures

When structured-output validation fails, teams should define a specific failure path rather than passing the malformed output downstream:

Retry: Re-run the request, optionally with clarified instructions.
Fallback: Return a safe default or a structured refusal.
Escalate: Route to human review if retry/fallback are not appropriate.
Log: Record the failure for monitoring and pattern detection.

## Slide 24/52 - Real-world example: Structured-output validation for a claims-support API

Real-world example: Structured-output validation for a claims-support API

An API returns structured fields: `status`, `next_step`, `source_ids`, `needs_review`, `review_reason`.

During testing, the team finds:

Most responses validate correctly.
One case returns `status: "approved"` with no `source_ids`, which should never happen for a factual claim.
Another case returns `needs_review: true` with an empty `review_reason`.

The team adds a validation rule: any `status: "approved"` response must include at least one `source_id`, and any `needs_review: true` response must include a non-empty `review_reason`. Failing responses are retried once, then routed to human review if the failure repeats.

## Slide 25/52 - Recommended exercise: Define structured-output validation rules

Recommended exercise: Define structured-output validation rules

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice defining validation rules that catch structurally malformed or internally inconsistent outputs.

**Task:** For an API returning `answer`, `source_ids`, `confidence_note`, `needs_review`, and `review_reason`, write at least three validation rules that check required fields, types, and internal consistency. Define a failure-handling behavior (retry, fallback, escalate, or log) for each.

**Estimated time:** 8–10 minutes

**Suggested output and reflection:** A validation-rule table for inclusion in the API Behavior Validation and Guardrail Plan.

## Slide 26/52 - The confidence_note caution (revisited)

The confidence_note caution (revisited)

As a reminder: a model-authored `confidence_note` is explanatory text, not a calibrated confidence score. Structured-output validation should never treat `confidence_note` alone as sufficient grounds for triggering or skipping a review path — it must be paired with source evidence, a deterministic rule, a validated evaluator, or human review.

## Slide 27/52 - Summary

Summary

In this module, you learned to validate structured outputs for required fields, correct types, internal consistency, and enum compliance, and to define failure-handling behavior (retry, fallback, escalate, log) so malformed outputs never silently reach downstream systems.

## Slide 28/52 - Introduction (Module: Add human review)

Add human review

This module covers human review: how to define when a human should review a model's output before it is finalized, delivered, or acted upon.

## Slide 29/52 - When human review is needed

When human review is needed

Human review is needed when:

Confidence or evidence is insufficient (e.g., missing sources, ambiguous requests).
The action has significant consequences (e.g., financial, legal, safety, access-related).
The case falls outside tested/expected patterns (an edge case).
A guardrail or structured-output check flags the output for review.
Policy requires human sign-off for a category of decision (e.g., regulated industries).

## Slide 30/52 - Designing a review trigger

Designing a review trigger

An effective human-review trigger includes:

The specific condition (e.g., missing source, low-confidence flag, restricted-data request).
The reviewer role responsible (e.g., policy owner, security reviewer, workflow owner).
The information the reviewer needs (e.g., the original request, the model's draft answer, the reason flagged).
The expected reviewer action (approve, edit, reject, escalate further).

## Slide 31/52 - Knowledge check

**Question:** A team defines a human-review trigger but does not specify who the reviewer is or what information they receive. What is the main risk?

- The API will run slower.
- The review trigger will fire too often.
- Without a defined reviewer role and required information, flagged cases may go unreviewed or be reviewed without enough context to make a sound decision. **✓ Correct**
- Structured-output validation will fail.

A review trigger is only effective if it specifies who reviews, what information they need, and what action is expected. Without these, flagged cases risk being ignored or mishandled.

## Slide 32/52 - Real-world example: Human review for a contract-support API

Real-world example: Human review for a contract-support API

An API drafts responses to internal questions about vendor contracts, citing specific contract clauses.

The team defines this human-review trigger: any response involving contract terms with financial exposure above a threshold, or any response where no matching clause is found, is routed to a legal reviewer with the original question, the model's draft answer, the relevant contract sections, and the reason for the flag. The reviewer can approve, edit, or reject the draft before it reaches the requester.

## Slide 33/52 - Recommended exercise: Design a human-review workflow

Recommended exercise: Design a human-review workflow

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice designing a complete human-review trigger with a defined reviewer, required information, and expected action.

**Task:** For an API that drafts customer-facing responses to billing disputes, define at least two human-review triggers (e.g., dispute amount above a threshold, no matching billing record found). For each, specify the reviewer role, the information provided, and the expected action.

**Estimated time:** 8–10 minutes

**Suggested output and reflection:** A human-review trigger table for inclusion in the API Behavior Validation and Guardrail Plan.

## Slide 34/52 - Summary

Summary

In this module, you learned to identify when human review is needed (insufficient evidence, high-consequence actions, edge cases, or policy requirements) and how to design an effective review trigger that names the reviewer, required information, and expected action.

## Slide 35/52 - Introduction (Module: Connect controls to release decisions)

Connect controls to release decisions

This module covers how to connect evals, moderation, guardrails, structured-output validation, and human review into evidence that supports a specific release decision.

## Slide 36/52 - From controls to a release decision

From controls to a release decision

Individual controls (evals, moderation, guardrails, structured-output checks, human review) each produce evidence. A release decision should be based on the combined evidence, not any single control in isolation.

Common release recommendations:

Ready: All critical cases pass with no blocking gaps.
Ready with conditions: Release is scoped (e.g., internal pilot only) with monitoring and defined pause/escalation triggers.
Remediate before launch: Blocking gaps must be fixed first.
Pause: Release should not proceed until specific issues are resolved.
Escalate: The decision requires input from security, legal, policy, or another owner.

## Slide 37/52 - Real-world example: Combining evidence into a release decision

Real-world example: Combining evidence into a release decision

An API for internal expense-policy questions has: passing normal-case evals, a moderation check that blocks unsafe content, a guardrail requiring source citations, structured-output validation passing in all but one edge case, and a human-review trigger for missing-source cases.

Because one structured-output edge case is unresolved and reviewer capacity is untested, the team recommends "Ready with conditions": release to an internal pilot only, with monitoring of structured-output failures and reviewer load, and a pause trigger if either exceeds a defined threshold.

## Slide 38/52 - Knowledge check

**Question:** All of an API's evals pass, but the team has not yet defined who owns human review for flagged cases. What is the most defensible release recommendation?

- Ready, since the evals passed.
- Ready with conditions, since evals are the most important control.
- Remediate before launch or escalate, since a required control (review ownership) is undefined. **✓ Correct**
- Pause monitoring until after launch.

Passing evals alone is not sufficient evidence for release if a required control — such as review ownership — is undefined. An undefined ownership gap should block release or be escalated, not be treated as a minor condition.

## Slide 39/52 - Define pause, escalation, improvement, and retest triggers

Define pause, escalation, improvement, and retest triggers

After release, monitoring may show that the API is not behaving as expected. The team should decide in advance what happens when that occurs, rather than waiting for a failure pattern to appear in production or during a pilot.

Use the trigger areas below to make the post-release response path concrete.

Define:

**Pause triggers:** When should rollout pause? For example: unsafe responses, recurring unsupported claims, malformed output reaching users, or missed review triggers.
**Escalation triggers:** When should the issue go to security, privacy, legal, policy, platform, system owner, or workflow owner?
**Improvement loop:** Who reviews issues, which signals are reviewed, what gets updated, and how changes are tested before redeployment.
**Retest triggers:** Which tests must be rerun after changes to the prompt, model, or other behavior-affecting components?

## Slide 40/52 - Real-world example: Release decision for a policy-support API

Real-world example: Release decision for a policy-support API

An internal policy-support API answers employee policy questions using approved sources and returns structured fields: `answer`, `source_ids`, `confidence_note`, `needs_review`, and `review_reason`.

Pre-launch validation shows:

Normal policy questions pass.
Unsafe requests are refused.
Missing-source cases now trigger review.
Structured-output checks pass for most cases.
One edge case still returns a low-confidence answer without enough explanation.
Reviewer overrides are higher than expected during pilot testing.

The release gate allows an internal pilot only. The team monitors structured-output failures, missing-source volume, human-review triggers, unsupported-claim reports, low-confidence outputs, and reviewer overrides.

If unsupported customer-facing claims recur or review triggers are missed, rollout must pause and the issue must escalate to the policy owner.

The learner should notice that the recommendation is not "release" or "do not release" in isolation. It is a scoped decision based on evidence, known gaps, conditions, monitoring signals, owners, and pause triggers.

## Slide 41/52 - Recommended exercise: Make a release-gate recommendation

Recommended exercise: Make a release-gate recommendation

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice turning validation evidence into a launch-readiness recommendation, release gate, and monitoring plan.

**Example workflow:** Employee software-access API

Validation results show:

Supported access-policy questions passed 18 of 20 normal cases.
Missing-context cases correctly asked for clarification.
Restricted-dataset cases triggered review in 7 of 8 tests.
One restricted-dataset case produced a low-confidence answer without setting `needs_review` to true.
Structured-output validation passed in all but one malformed-output test.
No test showed the API provisioning access directly.
The policy owner has not yet approved the reviewer override process.

**Task:** Review the behavior evidence and decide whether the API should release, release with conditions, remediate before launch, pause, or escalate. Then define the release gate, monitoring signals, pause conditions, escalation path, and retest triggers.

**Estimated time:** 8–10 minutes

**Suggested output and reflection:** Release gate, monitoring, escalation, and improvement-loop section of the API Behavior Validation and Guardrail Plan.

## Slide 42/52 - Knowledge check

**Question:** A team wants to release an internal pilot. Validation shows normal cases pass, but two sensitive cases missed the human-review trigger. The review owner is not yet confirmed. What is the strongest recommendation?

- Ready with conditions because only sensitive cases failed.
- Ready because normal cases pass.
- Remediate or pause until review behavior and ownership are fixed. **✓ Correct**
- Escalate to production monitoring after launch.

Missed review triggers in sensitive cases are not minor gaps. The team should fix the behavior and confirm ownership before the API moves forward, even for an internal pilot.

## Slide 43/52 - Summary

Summary

In this module, you connected validation evidence to release gates, monitoring signals, pause triggers, escalation paths, and retest triggers.

The key takeaway is that release decisions should be evidence-led. A successful demo or passing normal-case test is not enough.

Teams need to understand what passed, what failed, what remains unresolved, who owns each issue, and what must be retested when behavior-affecting changes occur.

## Slide 44/52 - Introduction (Module: Complete the API Behavior Validation and Guardrail Plan)

Complete the API Behavior Validation and Guardrail Plan

Now you'll bring the course decisions together into one reviewable handoff artifact.

In this module, you'll complete the API Behavior Validation and Guardrail Plan by consolidating prompt behavior, structured-output expectations, eval coverage, moderation checks, guardrails, human-review triggers, pre-launch behavior evidence, release recommendation, monitoring signals, owners, escalation paths, open risks, and retest triggers.

The purpose is not to prove that the API is risk-free. The purpose is to make expected behavior, test coverage, safety controls, release conditions, unresolved risks, ownership, and improvement assumptions clear enough for implementation, review, and handoff.

## Slide 45/52 - Build the plan

Build the plan

The API Behavior Validation and Guardrail Plan should show how the team will validate API behavior before launch and continue improving it after release.

Your plan should cover five areas:

**Workflow and expected behavior**
Workflow boundary, prompt purpose, expected answer behavior, clarification behavior, refusal behavior, escalation behavior, structured-output behavior, and failure examples.

**Eval criteria and test coverage**
Success criteria, representative test cases, failure categories, and pass/fail or acceptance thresholds where appropriate.

**Controls and review path**
Moderation or safety checks, guardrail rules, structured-output validation rules, human-review triggers, review owner, and escalation path.

**Pre-launch evidence and release recommendation**
Evidence reviewed, passing cases, failed cases, unresolved cases, blocking gaps, required remediation, release recommendation, and release conditions.

**Monitoring, retesting, and ownership**
Monitoring signals, pause or escalation conditions, retest triggers after behavior-affecting changes, eval owner, human-review owner, remediation owner, escalation owner, open risks, and handoff notes.

Use these five areas as one connected release-control plan, not five separate checklists. An effective plan should make API behavior testable before launch, show how unsafe or uncertain behavior will be handled, and name who owns review, remediation, escalation, and retesting after release.

## Slide 46/52 - Make the plan handoff-ready

Make the plan handoff-ready

The plan should be clear enough that a technical reviewer, workflow owner, security reviewer, policy reviewer, or customer stakeholder can understand what has been validated and what still needs a decision.

Use a final handoff check:

**Keep behavior clear**
Make the workflow boundary, prompt behavior, structured-output requirements, and failure examples specific enough to test.

**Tie evals to evidence**
Connect eval criteria to expected behavior, failure categories, and release-gate evidence.

**Tie controls to risks**
Tie each moderation check, guardrail, structured-output rule, human-review point, or escalation path to a specific workflow risk, failure category, or release gate.

**Name owners**
Identify owners for eval review, human review, remediation, retesting, escalation, and unresolved risks.

**Keep assumptions visible**
Identify what must be validated after prompt, model, source, retrieval, tool, schema, policy, guardrail, or review-threshold changes.

**Avoid overclaiming**
Do not imply that evals, moderation, guardrails, structured outputs, or human review eliminate risk. They reduce and manage risk when they are designed, tested, owned, and monitored.

The completed plan should also support one of the five recommendations: Ready, Ready with conditions, Remediate before launch, Pause or Escalate.

## Slide 47/52 - Real-world example: Completed plan excerpt

Real-world example: Completed plan excerpt

An internal policy-support API answers employee questions using approved policy sources. The API returns structured fields: `answer`, `source_ids`, `confidence_note`, `needs_review`, and `review_reason`.

A completed plan excerpt would look like this:

| Plan section | Example entry |
|---|---|
| Workflow boundary | Answer employee policy questions using approved internal sources. Do not provide legal advice, bypass policy, or answer unsupported questions as final. |
| Prompt behavior | Answer supported questions, ask for missing details, refuse unsafe requests, and trigger review for sensitive, unsupported, or low-confidence outputs. |
| Structured output | Required fields: answer, source_ids, confidence_note, needs_review, review_reason. |
| Eval coverage | Normal cases, missing-context cases, unsafe requests, unsupported-source cases, structured-output failures, and human-review trigger cases. |
| Controls | Source-use guardrail, structured-output validation, safety check, low-confidence review trigger, escalation to policy owner. |
| Evidence reviewed | Normal cases pass; unsafe requests refuse; missing-source cases trigger review; one edge case still needs explanation improvement. |
| Recommendation | Ready with conditions for internal pilot only. |
| Conditions | Monitor low-confidence outputs, reviewer overrides, missing-source events, and malformed outputs. |
| Retest triggers | Rerun relevant tests after prompt, policy source, output schema, guardrail, or review-threshold changes. |
| Owners | Eval owner: implementation team. Review owner: policy owner. Escalation owner: policy and security lead. |
| Open risk | Reviewer override process needs confirmation before broader rollout. |

This plan is handoff-ready because it shows what was tested, what controls exist, what release scope is allowed, what conditions apply, who owns review, and what must be retested.

## Slide 48/52 - Recommended exercise: Finalize the API Behavior Validation and Guardrail Plan

Recommended exercise: Finalize the API Behavior Validation and Guardrail Plan

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Consolidate your behavior, validation, guardrail, review, release, and ownership decisions into one deployment-ready plan.

**Task:** Use the plan sections you developed earlier in the course, or use this employee software-access workflow as your starting point:

An API answers employee questions about software access using approved IT policy sources, returns structured fields, refuses requests to bypass access controls, and routes sensitive, unsupported, or low-confidence answers to review.

As you complete the plan, focus on five areas:

Expected behavior: What should the API do, what should it not do, and what structured output should it return?
Validation coverage: What eval cases prove the API can handle normal requests, edge cases, failures, risky inputs, malformed outputs, and review-triggering cases?
Controls and review path: What moderation checks, guardrails, structured-output checks, human-review triggers, and escalation paths are required?
Release decision: What pre-launch evidence supports the recommendation: ready, ready with conditions, remediate before launch, pause, or escalate?
Ownership and retesting: Who owns review, remediation, escalation, monitoring, and retesting? What changes require validation to be rerun?

**Estimated time:** 8–10 minutes

**Suggested output and reflection:** A completed API Behavior Validation and Guardrail Plan that is clear enough for implementation, review, and release decision-making.

## Slide 49/52 - Knowledge check

**Question:** Which validation plan is most handoff-ready?

- A plan with pass rates and release conditions, but no failed-control next steps.
- A plan with structured outputs and review triggers, but release based on normal cases.
- A plan with behavior, evals, controls, release decision, owners, risks, signals, and retest triggers. **✓ Correct**
- A plan with prompt behavior, eval cases, and guardrails, but no owners or retest triggers.

The correct option is strongest because it connects behavior, tests, controls, release decision, ownership, open risks, monitoring, and retesting into one usable handoff. The other plans include useful pieces, but each leaves out something needed for deployment review, such as ownership, failed-control behavior, retest triggers, or release evidence beyond normal-case success.

## Slide 50/52 - Summary

Summary

In this module, you finalized the API Behavior Validation and Guardrail Plan.

A defensible plan should make API behavior evidence-led, reviewable, and actionable. It should show what the workflow is allowed to do, how the API should behave at boundaries, which risks require review or escalation, which release recommendation the evidence supports, and what must be retested when behavior-affecting changes occur.

## Slide 51/52 - Recap

Recap

In this course, you treated prompt behavior, evals, moderation, guardrails, structured outputs, and human review as deployment controls. You learned how to define expected API behavior, test it against realistic cases, identify failure categories, and use evidence to recommend release, remediation, pause, or escalation.

The key habit is evidence-led validation. Before an API reaches users, teams should know what the workflow can do, how it should respond at boundaries, which risks need review, and what must be retested after behavior changes.

Use this validation plan as a handoff artifact for tested controls, ownership, open risks, and next decisions.

## Slide 52/52 - Congratulations

Congratulations, you've completed this course!

You can now use your API Behavior Validation and Guardrail Plan to support safer API deployment decisions.

In future API solution design work, use this plan to define expected behavior, create eval coverage, add guardrails and review triggers, interpret validation evidence, make release recommendations, and identify what must be monitored or retested before broader rollout.

**Course completed**

Next up in API Deployment Practitioner: "DevOps, Observability, and Production Readiness for APIs" (Course, 46 min) — Unlock the secrets to deploying APIs that are truly ready for production—not just working locally. Learn how to define environment, configuration, and release assumptions, set up robust observability with health, usage, and cost signals, and plan for real-world failure handling and support ownership. Build an actionable API Production Readiness Checklist that covers deployment context, validation evidence, monitoring signals, operational response, and ownership—so every release is safe, supportable, and decision-ready.
