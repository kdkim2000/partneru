# Early Opportunity Progression Application

## Slide 1/13 - Title

Early Opportunity Progression Application

Created July 2026

## Slide 2/13 - Introduction

Early opportunities are decision points, not handoffs. A customer may bring urgency, internal pressure, and a belief that AI could help—but the evidence may still be incomplete.

In this course, you'll practice working through that ambiguity in a live AI role-play with a customer stakeholder at Riverton Mutual Insurance.

Your task is to clarify the workflow, test the business problem, identify who owns the outcome, and avoid jumping from interest to product recommendation.

By the end, you'll recommend whether the opportunity should progress toward Stage 1, based on qualification evidence, readiness signals, the likely AI application pattern, and a credible next step.

## Slide 3/13 - Overview

Your objective is to determine whether a single early AI opportunity at Riverton Mutual Insurance is ready to progress to Stage 1.

By the end of the scenario, you should be able to explain:

- What business problem the customer is trying to solve.
- Which workflow or business process is affected.
- Who is impacted and who owns the outcome.
- What value might be created if the problem is addressed.
- What evidence supports progression.
- What still needs validation.
- What next step should happen.

Keep the objective simple: progress the opportunity to a credible Stage 1 readiness recommendation. A credible recommendation does not need perfect information. It needs enough evidence to justify structured follow-up, plus a clear view of what is still unknown.

## Slide 4/13 - How the AI role-play works

You will complete two short role-play activities with Leon Whitaker, VP of Claims Operations at Riverton Mutual Insurance.

In each activity:

- Read the setup first.
- Respond as a partner seller or solution advisor.
- Keep your responses concise and customer-focused.
- Do not try to solve every issue in one answer.
- Let Leon's latest concern guide your response.

The AI character will close the conversation when you have addressed the main goal of the activity.

As you respond, stay focused on the customer's workflow, the evidence you have, and the evidence you still need. Your job is not to pitch the most impressive solution. Your job is to determine what the opportunity is actually ready for.

When Leon asks for a recommendation, avoid jumping straight to a product.

First clarify the workflow, stakeholder need, qualification evidence, and readiness signals.

Then separate three seller decisions:
- Where the person or workflow should primarily operate
- What capabilities or architecture the workflow requires
- How the solution must be deployed, controlled, and reviewed

The starting surface may be ChatGPT, Codex for software engineering, or an application or process built with the API. Capabilities such as retrieval, structured extraction, connected tool use, or multi-step agentic work—and operating choices such as hosted, embedded, or open-weight deployment—must be validated rather than treated as peer product paths.

Further discovery or a technical or deployment handoff may be the right next step.

When Leon raises concerns about governance, value, ownership, or readiness, respond at the seller level.

Do not move into architecture, deployment design, admin configuration, authentication, permission models, legal advice, compliance design, or ROI guarantees.

Before you begin the role-play activities, download the Riverton Mutual Seller Guide.

The Seller Guide is a companion aid. It summarizes the Riverton customer context, the five qualification signals, workflow and stakeholder prompts, seller-level routing cues across user or product surface, required capability or architecture, and deployment and operations, readiness considerations, and a simple structure for making a Stage 1 recommendation.

**Attachment:** S7-1.3 OpenAI Partner University _ Early Opportunity Progression Application Course _ Seller Guide.pdf (270.6 KB)

Use this guide during both scenario activities to stay anchored in the customer context, seller-level response boundaries, and the evidence needed to recommend a credible next step.

## Slide 5/13 - Meet the customer: Riverton Mutual Insurance

Riverton Mutual Insurance is a fictional mid-sized commercial property and casualty insurer serving regional businesses across the Midwest and Southeast United States.

The company has grown quickly after expanding its commercial property coverage for logistics companies, regional retailers, and light manufacturing businesses. That growth has increased pressure on the claims organization.

Riverton's claims team is now dealing with:

- Higher claim volume after severe weather events.
- Slower first-pass claim review.
- Inconsistent triage between regional claims teams.
- Adjusters spending too much time assembling claim context before deciding next steps.
- Leadership pressure to reduce backlog before the next storm season.

Riverton has expressed interest in "using AI in claims," but the opportunity is not yet clearly framed. Your job is to move from that broad interest signal to a clearer opportunity point of view.

## Slide 6/13 - Meet your customer stakeholder: Leon Whitaker

You will speak with Leon Whitaker, VP of Claims Operations at Riverton Mutual Insurance.

Leon owns claims intake, early triage, and adjuster productivity. He is pragmatic and direct.

He is interested in AI, but he does not want a broad transformation program that takes months before the claims team sees practical value.

**Leon cares about:**

- Reducing backlog during claim spikes.
- Improving consistency in early triage.
- Helping adjusters start with better claim context.
- Keeping qualified human review and accountability for high-stakes insurance decisions, including final coverage, liability, payment, and exception decisions. OpenAI Usage Policies prohibit automating high-stakes insurance decisions without human review.
- Understanding where review, controls, and approval points need to remain visible in the claims workflow.
- Understanding what a realistic first pilot could look like.

Leon is not the final technical decision-maker. If the opportunity progresses, he will need to involve claims systems, data, security, and legal stakeholders. For this course, you only speak with Leon.

## Slide 7/13 - Before the conversation

You are about to meet with Leon Whitaker, VP of Claims Operations at Riverton Mutual Insurance.

Leon is interested in using AI to improve claims operations, but the opportunity is still broad. Your job is to clarify whether there is a real business problem, a specific workflow, a practical first use case, and enough evidence to justify moving toward Stage 1.

Treat this as a discovery and qualification conversation, not a quick product-routing exercise. A customer saying "AI sounds useful" is not enough.

Look for evidence that the problem is specific, the workflow is real, the impact matters, the use case can be framed, and the customer is willing to take a next step.

In this conversation, focus on gathering evidence. Try to clarify:

- What is happening today in the claims workflow.
- Who is affected by the problem.
- What the problem costs in time, quality, speed, risk, or customer experience.
- What better would look like.
- Which first use case is narrow enough to validate.
- Who else would need to be involved if the opportunity progresses.
- What next step Leon is willing to commit to.

Do not try to design the full solution. Your goal is to gather enough evidence to make a recommendation.

## Slide 8/13 - Scenario: Early AI Opportunity Discovery at Riverton Mutual (AI Role-Play)

**Character:** Leon Whitaker, VP of Claims Operations, Riverton Mutual Insurance

**Scenario setup:** A partner solution advisor meets Leon Whitaker, VP of Claims Operations at Riverton Mutual Insurance, to qualify an early AI opportunity in claims intake and triage. Learners practice consultative discovery, testing business problem clarity and readiness, and recommending a realistic Stage 1 next step without jumping into premature product or technical design.

**Conversation transcript:**

**Leon Whitaker:** Hi there! As the VP of Claims Operations at Riverton Mutual Insurance, I'm currently dealing with some significant challenges. We're facing a claims backlog, inconsistent triage processes, and adjusters spending too much time on context assembly. With the storm season approaching, there's a real urgency to address these issues. How do you think we might tackle this?

**Seller (me):** Thanks for sharing that, Leon. Before I suggest anything, I'd like to understand the workflow better. Can you walk me through what happens today from the moment a claim comes in to when an adjuster starts working it? I'm especially curious where the triage inconsistency shows up and what "assembling context" actually involves for your adjusters.

**Leon Whitaker:** Sure, when a claim comes in, it first goes through intake where packets are often incomplete. This leads to delays as adjusters need to gather additional information. Triage inconsistency arises because regional teams apply different practices, making it hard to categorize claim severity uniformly. Adjusters then spend a lot of time assembling context from various sources like claim notes, emails, attachments, and policy references before they can decide on the next steps. This is where we see significant slowdowns.

**Seller (me):** That's helpful context. In terms of impact, do you have a sense of how much time adjusters lose per claim assembling that context, or how the backlog is affecting cycle time or customer experience? And who feels this most today—adjusters, regional managers, or customers waiting on claims?

**Leon Whitaker:** The backlog and context assembly slow down the first-pass review, leading to rework and escalation pressure. While I don't have exact numbers, this affects cycle time and customer experience negatively. Adjusters and regional managers feel the pressure most, but ultimately, it's the customers who experience delays in their claims being processed.

**Seller (me):** Understood. If we narrowed this to a first, testable step—rather than trying to fix the whole intake-to-triage process at once—would it make more sense to start with helping adjusters assemble claim context faster, or with standardizing triage severity classification across regions? And separately, I want to be clear: any final coverage, liability, payment, or exception decision would still need qualified human review—we wouldn't automate that. Does that align with how you'd want to pilot this?

**Leon Whitaker:** Absolutely, any high-stakes decisions must remain under human review. For a pilot, starting with helping adjusters assemble claim context faster could provide immediate relief and improve productivity. Standardizing triage can follow once we have a better handle on the intake process. This approach aligns well with our need for a practical, incremental improvement.

**Seller (me):** That's a good place to start. As we think about next steps, if this moves forward, who else on your side would need to be involved—claims systems, data, security, or legal—especially to confirm data access and review requirements? And would you be open to a short follow-up working session with those stakeholders to validate the details before we go further?

**Leon Whitaker:** Yes, for this to move forward, we'd need involvement from claims systems, data, security, and legal teams to ensure data access and compliance with review requirements. I'm open to sponsoring a follow-up session with these stakeholders to validate the details and ensure we're aligned before proceeding further.

**Coaching feedback: Good job!**

You ran a focused, consultative discovery that stayed aligned to the customer's priorities.

- Probed deeply into workflow, impact, and roles before suggesting any solution path.
- Explicitly framed a narrow, testable first use case around context assembly.
- Secured agreement on stakeholders and a concrete follow-up working session.

Areas to improve:
- Ask for even rough metrics to quantify cycle time and backlog impact.
- Briefly restate the validated problem to confirm shared understanding before proposing next steps.

## Slide 9/13 - Build your readiness point of view

Pause and organize what you heard from Leon. Use the five qualification signals:

1. **Business problem clarity** ✓ (Click to complete)
2. **Stakeholders identified** ✓ (Click to complete)
3. **Initial AI use case framed** ✓ (Click to complete)
4. **Customer engagement signal** ✓ (Click to complete)
5. **Early value hypothesis** ✓ (Click to complete)

For each signal, decide whether the evidence is:

- **Strong** — Clear enough to support Stage 1 progression.
- **Developing** — Directionally useful, but needs more validation.
- **Missing** — Not yet supported by the conversation.

You do not need perfect evidence. You need enough credible clarity to decide whether structured opportunity development is justified.

Before you return to Leon, prepare a short point of view:

- Should this opportunity progress to Stage 1?
- What should the first pilot focus on?
- Why is that the right first step?
- What user or product surface, required capability or architecture, and deployment and operations can you justify from the evidence?
- What still needs validation?
- What should Leon agree to do next?

## Slide 10/13 - Prepare your recommendation

You will now return to Leon Whitaker with your recommendation. Your task is to explain whether Riverton Mutual's claims opportunity should progress to Stage 1. Keep the recommendation practical, evidence-based, and focused on what should happen next.

Use this structure:

- **Recommendation** — Should this opportunity progress to Stage 1?
- **Evidence** — Which qualification signals support your recommendation?
- **Seller-level route** — What user or product surface should Riverton explore first, what capabilities or architecture may be required, and what deployment and operating requirements still need validation?
- **Why this route** — Why does this route fit the problem, evidence, value, and risk better than broader or higher-risk alternatives?
- **Value** — What claims outcome could improve if this works?
- **Validation** — What still needs to be checked before deeper solution design?
- **Next step** — What should Leon, the partner team, and OpenAI do next?

A strong recommendation explains what to pursue first and what not to pursue yet. Choose the path you can defend with evidence from discovery.

**For example:** A claims intake and triage assist workflow might be a credible first focus if the evidence shows adjusters are spending too much time assembling claim context and triage is inconsistent across regions. But do not assume the product path before the evidence supports it.

At seller level, separate three routing decisions:

- **User or product surface:** where the person or workflow will primarily operate.
- **Required capability or architecture:** what the system must do.
- **Deployment and operations:** how the solution will run and be controlled.

Then determine whether multiple components are needed and what progression motion the evidence supports.

| Routing hierarchy | Option for consideration | Seller-level guidance |
| --- | --- | --- |
| 1. User or product surface | ChatGPT | May fit when claims employees will primarily perform the work in ChatGPT. Determine which interaction pattern fits the workflow: Chat for collaborative thinking, drafting, review, and refinement; ChatGPT Work for delegated, multi-step knowledge work where available. Validate access, context, controls, approval boundaries, and human-review needs. |
| | An application or process built with the API | May fit when intelligence must be embedded in a claims system, application, or operational workflow. Validate system ownership, integration needs, data access, output requirements, and evaluation before confirming the route. |
| | Codex | Specialized for software engineering. Consider it only when the customer problem concerns software delivery or SDLC transformation; it is not the default for a claims operations problem. |
| 2. Required capability or architecture | What the system must do | Identify required capabilities such as retrieval, extraction and structuring, classification and routing, review, connected tool use, and multi-step work. Agentic behavior is a capability requirement—not a separate product route. Validate permissions, approvals, human review, and workspace configuration. |
| 3. Deployment and operations | Where and how the solution will run and be controlled | Validate hosting, runtime, control, residency, offline operation, customization, infrastructure, permissions, retention, logging, and human-review requirements. An open-weight model is one deployment option, not a peer product surface. Explore it only when Riverton has validated a relevant self-managed or infrastructure requirement and compared available hosted controls. |

| Follow-on decision | Guidance |
| --- | --- |
| Combined solution | More than one surface or capability may be needed—for example, employee-facing ChatGPT plus an API-based workflow. Do not use "hybrid" as the answer until the components, responsibilities, and operating requirements are clear. |
| Progression motion | Recommend further discovery, technical validation, deployment validation, or a specialist handoff when any routing layer remains unclear—especially data, systems, governance, ownership, permissions, human review, or operating requirements. |

Do not finalize architecture or implementation details. At this stage, your role is to recommend a clear next step, not design the full solution.

## Slide 11/13 - Scenario: Stage 1 Readiness Recommendation for Riverton Claims AI (AI Role-Play)

**Character:** Leon Whitaker, VP of Claims Operations, Riverton Mutual Insurance

**Scenario setup:** A partner solution advisor returns to Riverton Mutual's VP of Claims Operations to recommend whether a claims AI opportunity should progress to Stage 1. Learners practice turning ambiguous AI interest into a focused, evidence-based recommendation around a claims intake and triage assist workflow, including seller-level routing, validation gaps, and a concrete next step.

**Conversation transcript:**

**Leon Whitaker:** Hello! I'm eager to hear your recommendation on whether we should move forward with the claims AI opportunity toward Stage 1. Could you provide a clear, evidence-based perspective on this?

**Seller (me):** Yes—based on our conversation, I recommend progressing this to Stage 1. Here's why: the business problem is clear (incomplete intake packets, inconsistent regional triage, and adjusters losing significant time assembling context before they can act), the impact is real even without hard numbers (slower cycle time, rework, and customer delays), and you've identified a narrow, testable first use case: helping adjusters assemble claim context faster, rather than tackling full triage standardization at once. You've also named the stakeholders who'd need to be involved—claims systems, data, security, and legal—and agreed to a follow-up working session with them. That's enough credible evidence to justify structured next steps, even though we don't have exact metrics yet.

**Leon Whitaker:** Thank you for the clear recommendation. Could you elaborate on how the proposed claims intake and triage assist workflow would operate at a seller level? Also, what governance or human-review needs should we be aware of as we move forward?

**Seller (me):** At a seller level, I'd separate this into three things we still need to validate rather than lock in today. First, the user surface—likely ChatGPT for adjusters to collaboratively pull together and review claim context, though if this eventually needs to be embedded directly into your claims system, an API-based workflow might fit better; we'd need to confirm that with your systems team. Second, the required capability—this looks like retrieval and structuring of claim notes, emails, attachments, and policy references, not full automation of decisions. Third, deployment and operations—we'd need to validate data access, permissions, logging, and where human review sits in the workflow before anything is built. On governance: any final coverage, liability, payment, or exception decision must stay with a qualified human reviewer—OpenAI's Usage Policies require that for high-stakes insurance decisions, and this pilot wouldn't touch that boundary. The next step I'd recommend is a working session with your claims systems, data, security, and legal stakeholders to validate data access and review requirements before we scope anything further.

**Leon Whitaker:** That sounds like a solid plan. I agree that a working session with our claims systems, data, security, and legal teams is the right next step to validate data access and review requirements. Let's schedule that session to ensure we're aligned and ready to move forward.

**Coaching feedback: Good job!**

You clearly met the Stage 1 recommendation goals with a concise, evidence-based narrative.

- Clearly stated a ready-to-progress Stage 1 recommendation tied to discovery evidence.
- Defined a narrow, low-risk first workflow focused on adjuster context assembly.
- Identified governance and human review needs and proposed a concrete validation session.

Areas to improve:
- Reference potential outcome metrics to strengthen the business impact case.
- Clarify ownership for the proposed working session within Riverton's organization.

## Slide 12/13 - Capture your Stage 1 recommendation snapshot

Before you finish, capture the recommendation you would share with your partner team or OpenAI counterpart.

Keep this concise. This is a snapshot, not a business case or implementation plan. Use one or two short bullets for each section.

**Stage 1 recommendation snapshot**

1. **Readiness recommendation:** ✓ (Click to complete) — Is the opportunity ready, conditionally ready, or not yet ready to progress toward Stage 1?
2. **Workflow and problem:** ✓ (Click to complete) — What workflow did Leon describe, and what problem is creating business pressure?
3. **Evidence and gaps:** ✓ (Click to complete) — What evidence supports progression? What is still missing or needs validation?
4. **Likely first route:** ✓ (Click to complete)
   - What user or product surface should Riverton explore first?
   - What capability or architecture may be required?
   - What deployment and operating requirements still need validation?
   - For example, the recommendation may point to ChatGPT, Codex for a software-engineering problem, an application or process built with the API, a combined solution, a specialist handoff, or further discovery.
5. **Next step:** ✓ (Click to complete) — What should happen next, who should be involved, and what should the next conversation validate?

**Final recommendation sentence**

Use this structure:

"Based on what we heard, I recommend [ready / conditionally ready / not yet ready] for Stage 1 because [evidence]. The next step should be [specific action] to validate [most important open question]."

## Slide 13/13 - Wrap up (Summary)

Strong AI opportunities are built on evidence, not enthusiasm. Before recommending a solution, clarify the workflow problem, business outcome, stakeholder owner, and signals that show whether the opportunity is worth progressing.

A credible Stage 1 recommendation does not need perfect information. It should state whether the opportunity is ready, conditionally ready, or not yet ready; name the evidence that supports progression and what still needs validation; and recommend a focused workflow plus the seller-level route the team can defend across user or product surface, required capability or architecture, and deployment and operations.

Keep the recommendation seller-level, specific, and useful beyond the conversation. It should be clear enough for a partner account team, solution advisor, partner manager, or OpenAI counterpart to use as the starting point for structured Stage 1 planning.

**Course completed**

**Next up in OpenAI Consultative Solutions Practitioner:** OpenAI Consultative Solutions Practitioner - Final Exam (Course, 2 min)

Master the art of identifying, qualifying, and advancing real-world AI opportunities with a consultative approach. Learn to recognize strong signals of customer commitment, frame high-impact use cases, and separate evidence from assumptions for business value. Explore how to map solution routes, validate vertical context, and tailor recommendations for complex industries—all while keeping workflow, stakeholder, and governance needs at the center. Build confidence in guiding customers from early discovery through validation, ensuring every step is grounded in practical readiness and measurable outcomes.
