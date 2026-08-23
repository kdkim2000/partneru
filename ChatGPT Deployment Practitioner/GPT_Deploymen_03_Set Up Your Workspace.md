# Set Up Your Workspace

## Slide 1/48 - Title

Set Up Your Workspace

Created July 2026

## Slide 2/48 - Introduction

Once an opportunity has been planned out, now the work gets more practical: the customer's ChatGPT workspace needs to be prepared to support the approved launch.

Workspace setup is not just an administrative task. It is the readiness layer that helps ChatGPT support approved workflows.

In this course, you'll use a plan-aware admin review to identify the product surface, access path, roles, groups, data and knowledge sources, app or agent permissions, monitoring evidence, and governance controls the approved workflow requires. You won't complete a click-by-click console build, but you will make the setup and validation decisions that belong in a Workspace Configuration Readiness Checklist.

## Slide 3/48 - What you'll learn

By the end of this course, you'll be able to: translate deployment requirements into workspace requirements; define workspace ownership and administrative responsibilities across identity, access, Apps, plugins, and Workspace Agents; identify user-access, SSO or SCIM provisioning, role, group, and role-based access-control requirements where they apply; evaluate readiness for approved Apps, plugins, Company Knowledge, ChatGPT Work, and Workspace Agents where the workflow depends on them; distinguish available adoption analytics from compliance or audit evidence, and document action, retention, residency, usage, and spend-control dependencies; build the key components of a Workspace Configuration Readiness Checklist.

## Slide 4/48 - What you'll produce

By the end of this course, you'll have the building blocks for a Workspace Configuration Readiness Checklist.

Your checklist will bring together ownership, access and governance requirements, knowledge, app, plugin, and Workspace Agent readiness, evidence and review needs, configuration dependencies, and outstanding setup actions for the approved workflow.

Let's get started!

## Slide 5/48 - Introduction (Module: Translating a Deployment Success Plan into workspace requirements)

Workspace setup should be driven by the approved deployment plan.

Before discussing workspace configuration, start with the practical launch context: the workflow the customer is activating, the users who need access, the information the workflow depends on, and the governance assumptions that must be validated.

In this module, you'll translate those deployment inputs into workspace requirements. This helps the team see what must be ready, what needs validation, what may block activation, and who owns the next action.

## Slide 6/48 - What workspace readiness means

Workspace readiness means the customer and partner team know what must be true before users begin working with ChatGPT on the target workflow.

Think of workspace readiness as the bridge between planning and activation:

- **Planning asks: What workflow are we launching?** — Workspace readiness asks: What users, access paths, sources, and workspace conditions does that workflow require?
- **Planning asks: What success evidence do we need?** — Workspace readiness asks: What adoption analytics, Task Insights, feedback routes, output review, or compliance evidence should be available?
- **Planning asks: What governance assumptions apply?** — Workspace readiness asks: Who validates the policy, source, app, plugin, agent, action, retention, residency, regional, or usage-control requirement?
- **Planning asks: Who owns the launch?** — Workspace readiness asks: Who owns workspace administration, source readiness, escalation, and unresolved setup actions?

Workspace readiness keeps setup connected to the deployment goal. Without that connection, setup can become a checklist of technical preferences rather than a plan that supports the customer's approved workflow.

## Slide 7/48 - Start from the approved deployment plan

Start by reviewing the planning input. This may be a Deployment Success Plan, approved customer handoff, or sanitized customer example.

Look for the information that affects setup readiness: target workflow or use case; required ChatGPT experience or product surface — such as Chat, Work, or a Workspace Agent — and whether it is enabled for the workspace and target role; target user group or cohort; launch scope; success criteria; known constraints; expected Company Knowledge, app, plugin, synced-source, or other approved-context dependencies; governance, action-approval, retention, residency, usage-control, or regional considerations already identified; business context ChatGPT needs to support the workflow, such as approved knowledge, policies, systems, or workflow guidance.

For a typical customer, the planning input includes a target workflow: legal operations specialists will prepare human-reviewed vendor-contract intake summaries from approved materials.

That single workflow already creates several workspace requirements.

The team must confirm which ChatGPT experience will support the work, whether the legal operations cohort has the right workspace and role access, how identity and provisioning will be handled, which approved sources or apps provide context, what actions are allowed, and which analytics, review, compliance, and issue evidence the customer needs.

This is why setup should not begin with product preferences. It should begin with the workflow the customer is trying to activate.

## Slide 8/48 - Translate deployment needs into workspace implications

Use a simple translation pattern:

- **Target user group identified** — Workspace implication: Access and provisioning path required. Owner: Workspace administrator or customer IT owner validates.
- **Workflow depends on internal policy documents** — Workspace implication: Knowledge source, app, plugin, or Workspace Agent readiness required. Owner: Source owner confirms content, access, and approval.
- **Regulated or sensitive workflow identified** — Workspace implication: Data-use boundary and human-review expectation required. Owner: Legal, security, or compliance owner validates.
- **Success criteria include usage and engagement** — Workspace implication: Analytics, feedback source, or review mechanism needed. Owner: Deployment owner confirms how evidence will be reviewed.
- **Workflow requires reviewable outputs** — Workspace implication: Monitoring, feedback, or issue route required. Owner: Deployment owner confirms how activity, outputs, and issues will be reviewed.

This mapping keeps the workspace conversation grounded in the deployment goal.

For example, "legal operations cohort" is not just a user group. It implies an access path, provisioning expectation, role or group decision, and support route for access issues.

Similarly, "approved contract intake materials" is not just a content note. It implies source ownership, content readiness, access validation, and a decision about whether the source is required for the first activation or can be deferred.

## Slide 9/48 - Identify configuration dependencies

A configuration dependency is anything that may affect whether the workspace can support the target workflow.

Common dependencies include: target users, workspace roles, groups, and product-surface access; identity, domain, SSO, SCIM, provisioning, deprovisioning, and user-lifecycle assumptions; workspace owner, administrator, access-control owner, app or agent owner, and analytics or compliance ownership; Company Knowledge, Apps, plugins, synced sources, or Workspace Agent dependencies; retention, deletion, data residency, inference residency, or regional requirements where relevant; sensitive-data, app-action, approval, sharing, or acceptable-use boundaries; admin enablement, publishing, logging, usage or spend controls, and other unresolved approvals.

You do not need to solve every dependency inside this course.

Your job is to make each dependency visible, assign an owner, and decide whether it must be resolved before activation or can be deferred.

Treat availability and control details as point-in-time. Validate them for the customer's plan, workspace, role, surface, and region before marking an item ready.

For a typical customer, vendor-contract summaries may depend on approved contract intake documents, policy guidance, user access, legal review expectations, and a source owner.

If any of those dependencies are unresolved, the activation team needs to know before activation begins.

## Slide 10/48 - Real-world example: From plan to workspace requirement

A deployment success plan does not automatically tell the workspace administrator what to do next.

The partner deployment team needs to translate the plan into setup requirements, validation owners, and open questions.

Here is how that might look in a real customer deployment.

A legal operations team is preparing for its first ChatGPT activation. The approved workflow is vendor-contract intake summaries. A small cohort of legal operations specialists will use ChatGPT to prepare human-reviewed summary drafts from approved contract intake documents and policy guidance.

Before activation begins, the partner deployment lead reviews the Deployment Success Plan with the workspace administrator, legal operations owner, compliance owner, and source owner.

Together, they turn the plan into a workspace readiness map:

- **First workflow: vendor-contract intake summaries** — Workspace requirement: Workspace setup must support the legal operations cohort and the approved materials needed for this workflow. Validation owner: Partner deployment lead and workspace administrator. Open question: Which workspace or access path will the cohort use?
- **First user group: legal operations specialists** — Workspace requirement: Provisioning, group access, and the user support route must be confirmed before activation. Validation owner: Workspace administrator or IT owner. Open question: Are all target users eligible for workspace access?
- **Success evidence: summary quality, user confidence, and review efficiency** — Workspace requirement: Feedback collection and review approach must be available during the first activation period. Validation owner: Business outcome owner. Open question: Who will review early outputs, user feedback, and issue patterns?
- **Governance expectation: human review before use** — Workspace requirement: User guidance and review ownership must be ready before users begin the workflow. Validation owner: Legal operations owner and compliance owner. Open question: What outputs require review before they are used in legal operations work?
- **Approved materials: contract intake documents and policy guidance** — Workspace requirement: Knowledge-source readiness must be validated before those materials support the workflow. Validation owner: Source owner. Open question: Are the materials current, approved, accessible, and appropriate for this workflow?

## Slide 11/48 - Recommended exercise: Map deployment requirements to workspace implications

This is an optional practice activity to reinforce what you just learned.

**Purpose:** This activity helps you create the first section of your Workspace Configuration Readiness Checklist by translating deployment requirements into workspace setup requirements, validation owners, readiness needs, and open questions.

**Task:** Review this customer context — the customer's Deployment Success Plan says the first ChatGPT workflow will help legal operations specialists prepare human-reviewed vendor-contract intake summaries from approved contract intake materials and policy guidance. The first 30 days should gather evidence on summary completeness, user confidence, review efficiency, and issue patterns.

Create a simple workspace-readiness map in your notes. Use one row for each deployment requirement or dependency.

Use these headings: deployment requirement; workspace implication; owner or validation owner; validation needed; readiness status, where relevant; open question or next action.

As you complete the map, consider: What does the target workflow imply for workspace readiness? What does the first user group imply for access and provisioning? What source materials need an owner and approval path? What review expectation must be validated before activation? What evidence or feedback route needs to be available during the first activation?

Estimated time: 6-7 minutes.

Suggested output and reflection: after completing your response, download the Recommended Exercise Reflection Guide for this activity ("DC3-2.6 OpenAI Partner University _ Set Up Your Workspace Course _ Reflection Guide 1.pdf", 907.3 KB). Use it to compare your response with a strong example and reflect on whether your answer is specific, grounded in the customer or workflow context, and clear about the reasoning behind your decisions.

## Slide 12/48 - Knowledge check

**Question:** A Deployment Success Plan says a legal operations cohort will prepare human-reviewed vendor-contract intake summaries from approved materials. Which workspace implication is strongest?

- Confirm broad legal-team access, workspace usage reporting, and interest in adjacent workflows before activation.
- **Confirm cohort access, source ownership, approved-use boundaries, and review expectations before activation.** ✓ Correct
- Prepare enablement materials, prompt examples, office hours, and adoption communications before activation.
- Move directly to activation because the workflow, first cohort, and intended output are already defined.

This is the strongest implication because the deployment plan creates workspace-readiness requirements: cohort access, approved source ownership, source-use boundaries, and review expectations.

## Slide 13/48 - Summary

In this module, you translated deployment goals into workspace requirements. You learned to: start from the approved Deployment Success Plan; identify target workflow, user group, launch scope, success criteria, constraints, and source dependencies; translate deployment requirements into workspace implications; identify configuration dependencies and validation owners.

You now have the first part of your Workspace Configuration Readiness Checklist: workspace requirements mapped to the deployment plan.

Next, you'll define who owns workspace readiness and administration.

## Slide 14/48 - Introduction (Module: Define workspace ownership and administrative responsibilities)

Workspace readiness depends on clear ownership. Even a well-defined deployment plan can stall if no one owns user access, workspace settings, source readiness, governance validation, or escalation.

In this module, you'll clarify who owns each workspace readiness decision before activation begins.

## Slide 15/48 - Identify workspace ownership roles

A workspace readiness plan should distinguish between several roles:

- **Business owner** — Owns the workflow outcome, business priority, and decision on whether the workspace supports the intended launch goal.
- **Deployment owner** — Coordinates launch readiness across partner and customer teams, tracks dependencies, and ensures unresolved items are visible.
- **Workspace administrator** — Manages workspace configuration, product-surface enablement, app and plugin availability, Workspace Agent controls, settings, and administrative requests.
- **Access-control owner** — Defines workspace roles, groups, and RBAC assignments for product surfaces, Apps, plugins, and Workspace Agents.
- **App or agent owner** — Owns the app, plugin, or Workspace Agent configuration; connection model; publishing; allowed actions; approval settings; and operational escalation.
- **IT or identity owner** — Confirms domain, SSO, SCIM, provisioning, deprovisioning, device, and access-path requirements where relevant.
- **Security, legal, or compliance owner** — Validates sensitive-data boundaries, app and agent action risk, policy requirements, retention, residency, Compliance API or logging needs, and approval requirements.
- **Source owner** — Confirms whether required documents, Company Knowledge, synced app content, or other approved sources are current, accessible, owned, and appropriate for the target workflow.

For smaller deployments, one person may hold more than one role. The checklist should still make each responsibility visible.

For example the legal operations lead may be both the workflow owner and business outcome owner. But workspace administration, source approval, and policy validation may still sit with different customer owners.

## Slide 16/48 - Clarify administrative responsibilities

After you identify the roles, clarify the responsibilities.

The workspace readiness plan should identify who is responsible for: user management; access management; workspace settings; governance validation; workspace and source-readiness coordination; escalation for access or setup blockers; ongoing administration.

Do not leave responsibilities implied.

If a person owns the launch but not the workspace settings, say that. If a business owner approves the workflow but not source access, say that too.

A clear checklist helps the activation team know who to contact when a setup question appears.

## Slide 17/48 - Define escalation and support ownership

Escalation ownership prevents small blockers from becoming launch delays.

Identify who should be contacted when there are blockers related to: user access or provisioning; workspace settings; regional, data residency, or inference residency questions; app, plugin, Workspace Agent, or knowledge-source access; sensitive-data or policy questions; approval delays; unclear administrative ownership.

Escalation should be practical.

The plan should tell the team who can make a decision, who can validate an assumption, and who should be involved if the issue affects policy, security, legal, or regional requirements.

## Slide 18/48 - Recommended exercise: Review workspace ownership and administrative responsibilities

This is an optional practice activity to reinforce what you just learned.

**Purpose:** This activity helps you reflect on whether ownership is clear enough for setup readiness.

**Task:** Review this customer context — the customer has confirmed the first legal operations workflow and user cohort. The legal operations lead owns the workflow outcome. The workspace administrator has not yet confirmed the access path. The policy document owner is not named. Compliance wants to review sensitive-data boundaries before activation.

Create a simple workspace-ownership map in your notes. Use one row for each ownership area or unresolved responsibility.

Use these headings: requirement or dependency; current owner, if known; missing owner or validation owner; validation needed; readiness status, where relevant; open question or next action.

As you complete the map, consider: Which owner is already clear? Which owner is missing? Who should confirm access and provisioning? Who should validate policy documents and source readiness? Who should validate sensitive-data boundaries? Who should own escalation if access, source, or approval blockers appear?

Estimated time: 6-8 minutes.

Suggested output and reflection: after completing your response, download the Recommended Exercise Reflection Guide for this activity ("DC3-3.4 OpenAI Partner University _ Set Up Your Workspace Course _ Reflection Guide 2.pdf", 907.6 KB). Use it to compare your response with a strong example and reflect on whether your answer is specific, grounded in the customer or workflow context, and clear about the reasoning behind your decisions.

## Slide 19/48 - Knowledge check

**Question:** A workspace readiness plan names the business owner but does not identify the workspace administrator, source owner, or escalation contact for access blockers. What is the main issue?

- The business owner can approve all setup actions, so that no other owners are needed.
- **The readiness plan has ownership gaps that could delay access, source validation, and setup decisions before activation.** ✓ Correct
- The course should move directly to enablement planning.
- The plan should remove governance review because the overall ownership situation is unclear.

A business owner is important, but workspace readiness also needs clear administrative ownership, source ownership, and escalation paths for setup blockers.

## Slide 20/48 - Summary

In this module, you defined workspace ownership and administrative responsibilities. You learned to: identify core workspace readiness roles; clarify administrative responsibilities; define escalation and support ownership; make ownership gaps visible before activation begins.

You now have the ownership section of your Workspace Configuration Readiness Checklist.

Next, you'll define access and governance requirements.

## Slide 21/48 - Introduction (Module: Define access and governance requirements)

Access and governance decisions shape how users engage with ChatGPT, what information they can use, and which workflows are appropriate for the first activation. These requirements should be captured as readiness assumptions to validate. They should not be treated as universal configuration rules.

In this module, you'll clarify which access and governance assumptions must be validated before activation begins.

## Slide 22/48 - Identify access requirements

Start by reviewing who needs access and what access path the target workflow requires.

Access readiness is not only about knowing the first user group.

A deployment plan may name the right cohort, but the workspace still may not be ready for those users to begin work.

Focus on reviewing: target user groups and the ChatGPT surface they need — Chat, Work, Workspace Agents, web, mobile, or desktop where applicable; workspace roles, groups, and RBAC scope for each user group; domain, SSO, SCIM, provisioning, deprovisioning, and access-support assumptions; workspace, app, plugin, and approved connected-source access path; Workspace Agent run, build, edit, publish, share, and group-access requirements where applicable; supported browser, web, mobile, desktop, device, network, or regional assumptions where relevant; any workspace, surface, role, group, app, plugin, or agent access blocker that must be resolved before activation.

Avoid assuming that "users are known" means "access is ready." Those are different readiness states.

Access is layered: a user may be provisioned into the workspace but still lack the required product surface, app, plugin, Workspace Agent, group, or action permission.

## Slide 23/48 - Identify governance requirements

Governance questions affect workspace readiness because they shape what users can do, what sources they can use, and what outputs require review.

Capture governance questions such as: organizational policies, such as acceptable-use boundaries, sharing expectations, human-review requirements, and escalation for high-impact work; data controls, such as approved inputs and sources, sensitive-data restrictions, retention and deletion, data residency, inference residency, and data-handling boundaries; compliance and oversight needs, such as legal, security, regional, Compliance API, logging, audit, and evidence-access requirements; app, plugin, and Workspace Agent controls, such as role access, end-user or shared connections, read and write actions, action approvals, parameter constraints, publishing, scheduling, triggers, and sharing limits; adoption and engagement evidence, such as available Workspace Analytics or Task Insights, plus output-quality review and customer-approved success evidence; compliance evidence and conversation or action oversight, which are separate from adoption analytics and do not by themselves prove output quality, compliance, or causal ROI; issue escalation, correction, usage or spend controls, and the owner who can pause, narrow, or disable a workflow.

These should be captured as assumptions to validate with the appropriate customer owner, not as universal ChatGPT rules.

Use only controls confirmed for the customer's current plan, workspace, role, surface, and region. Do not imply that a control exists or is enabled without current validation.

For example, one governance assumption might be: "Legal operations users must review ChatGPT-generated summaries before using them in downstream legal workflows." The checklist should identify who validates that expectation, when it must be confirmed, and how it affects activation.

## Slide 24/48 - Review regional and organizational considerations

Some deployments may include regional or organizational requirements that must be validated before activation.

Review any requirements related to: data handling; data residency; inference residency; organizational controls; regional availability, where relevant; regulated-workflow constraints, where relevant.

For each requirement, identify the customer owner responsible for validation and whether it must be resolved before activation.

Do not try to resolve these questions from memory or general assumptions.

Treat them as customer-specific readiness items that need the appropriate owner and current official documentation.

## Slide 25/48 - Connect governance to workflow behavior

Governance should not sit beside the workflow as a disconnected checklist. It should describe how the workflow will be used responsibly.

For each governance assumption, ask: Which workflow behavior does it affect? Who owns validation? When must validation happen? What launch action depends on it? What evidence, issue, or feedback should be reviewed during the first launch period?

Here's an example of how to connect governance assumptions to workflows, validators and the launch process:

- **Human review is required before summaries are used.** — Workflow behavior affected: Users must review and revise contract-summary drafts before using them in legal operations work. Validation owner: Legal operations owner and compliance owner. Launch dependency: User guidance and review process must be ready before activation.
- **Only approved policy materials may support the workflow.** — Workflow behavior affected: Users should use confirmed policy guidance and approved intake materials. Validation owner: Source owner. Launch dependency: Source readiness must be confirmed before activation.
- **Sensitive-data boundaries must be followed.** — Workflow behavior affected: Users must know what should not be entered, connected, shared, or used in the workflow. Validation owner: Legal, security, or compliance owner. Launch dependency: Acceptable-use guidance must be validated before activation.
- **App or agent write actions require bounded permission and approval.** — Workflow behavior affected: Users or agents may create or update records only within the approved scope; consequential actions require the configured confirmation or approval path. Validation owner: Workspace administrator, app or agent owner, and security or risk owner. Launch dependency: Confirm connection ownership, allowed actions, approval settings, constraints, logging, and escalation before activation.
- **Adoption and compliance evidence serve different decisions.** — Workflow behavior affected: The team reviews engagement separately from conversation or action records, output quality, and customer-approved success evidence. Validation owner: Deployment owner, analytics owner, and compliance owner. Launch dependency: Name the evidence sources, access, review cadence, and decision boundaries before activation.

This approach keeps governance connected to how ChatGPT will actually support work. It also helps the team identify which access, policy, review, and escalation decisions must be validated before activation.

## Slide 26/48 - Recommended exercise: Review access and governance requirements

This is an optional practice activity to reinforce what you just learned.

**Purpose:** This activity helps you reflect on which access, governance, regional, and organizational requirements must be validated before activation.

**Task:** Review this customer context — the customer's legal operations workflow may involve approved contract intake documents, policy guidance, and human-reviewed summary drafts. The first user cohort is known, but the access path, source approval, and sensitive-data boundaries are not fully confirmed.

Create a simple access and governance map in your notes. Use one row for each access, governance, regional, or organizational requirement.

Use these headings: requirement or dependency; workflow behavior affected; owner or validation owner; validation needed; readiness status, where relevant; required before activation?; open question or next action.

As you complete the map, consider: What access requirement must be validated for the first cohort? What human-review expectation affects the workflow? What approved-source boundary must be confirmed? What sensitive-data boundary must be validated? Are there any regional or residency considerations that require customer-owner validation? Which items are ready, need validation, blocked, or deferred?

Estimated time: 6-7 minutes.

Suggested output and reflection: after completing your response, download the Recommended Exercise Reflection Guide for this activity ("DC3-4.5 OpenAI Partner University _ Set Up Your Workspace Course _ Reflection Guide 3.pdf", 912.3 KB). Use it to compare your response with a strong example and reflect on whether your answer is specific, grounded in the customer or workflow context, and clear about the reasoning behind your decisions.

## Slide 27/48 - Knowledge check

**Question:** A legal operations team wants a Workspace Agent to use a shared app connection and update approved records. The target group is known, but publishing permission, connection ownership, allowed write actions, and approval settings are not confirmed. What should the readiness checklist say?

- Ready, because the target group and business value are known.
- Blocked permanently, because Workspace Agents cannot use apps or take actions.
- **Needs validation, because role and group access, connection ownership, action scope, approval settings, and escalation must be confirmed before activation.** ✓ Correct
- Deferred automatically, because Workspace Agent controls are always configured after launch.

The correct readiness status is: needs validation. The team must identify the app or agent owner, confirm the role and group scope, choose the connection model, bound the allowed actions, configure approvals or constraints, and name the escalation route before activation.

## Slide 28/48 - Summary

In this module, you defined access and governance requirements. You learned to: identify access requirements for target users; capture governance assumptions as items to validate; review regional and organizational considerations; connect governance expectations to workflow behavior, ownership, and launch dependencies.

You now have the access and governance section of your Workspace Configuration Readiness Checklist.

Next, you'll evaluate knowledge, app, plugin, and Workspace Agent readiness.

## Slide 29/48 - Introduction (Module: Define knowledge, app, and agent requirements)

Many ChatGPT deployment workflows depend on organizational knowledge, Apps, plugins, or Workspace Agents.

Before activation begins, the team needs to know which context and tools are required, who owns them, whether they are enabled and approved, how users or agents authenticate, and which actions are permitted.

In this module, you'll evaluate source, app, plugin, Company Knowledge, and Workspace Agent readiness without assuming that every available connection should be enabled.

## Slide 30/48 - Identify knowledge requirements

Review the target workflow and identify the information sources users may need.

As you conduct your review, make sure to consider: important information sources; frequently used content; relevant documentation; source ownership; whether the content is current and approved; whether the source is required for the first activation or can be deferred.

Don't just assume every source should be connected immediately.

Ask whether the source is required for the first activation, whether it is current, whether it has an owner, and whether it is approved for the intended workflow.

## Slide 31/48 - Identify app, plugin, and agent considerations

Start with current product terms. Apps connect ChatGPT to external tools, information, and actions.

Plugins can package one or more Apps with skills for a specific workflow. Workspace Agents can combine instructions, files, skills, tools, Apps, schedules, or triggers for repeatable work.

Some current or legacy materials may still use "connector" for a specific connection; in this course, use Apps and plugins as the primary product terms.

Determine whether the target workflow may require: the required App, plugin, Company Knowledge source, Workspace Agent, or other approved connection; availability for the customer's plan, workspace, role, surface, and region; required context, sync, files, tools, schedules, triggers, or channels; source, app, connection, agent, and publishing ownership; end-user versus shared or agent-owned authentication, least-privilege access, read and write actions, approvals, constraints, logging, and unresolved setup dependencies.

If a workflow depends on an App, plugin, Company Knowledge source, Workspace Agent, or internal system, the checklist should name the owner who will confirm availability, role and group access, connection ownership, permissions, action boundaries, logging, and whether the dependency is required for the first activation.

## Slide 32/48 - Review source, app, and agent readiness

After identifying the dependencies, assess each source, App, plugin, or Workspace Agent against two checks: knowledge-source readiness; app, plugin, and agent readiness.

These checks help you avoid two common mistakes: assuming that a useful source is ready just because it exists; assuming that an App, plugin, or Workspace Agent should be enabled just because it might be useful later.

**Knowledge-source readiness**

Knowledge-source readiness asks whether the content itself is suitable to support the target workflow.

Ask: Is the content available? Can the team access the materials that users will rely on for the first workflow? Is the content current? Are the documents, policies, templates, or examples up to date enough to support real work? Is the content approved? Has the appropriate customer owner confirmed that the material may be used for this workflow? Is the content owned? Is there a named source owner who can answer questions, approve updates, and resolve quality issues? Is the content appropriate for the target workflow? Does it help users complete the specific workflow, or is it too broad, outdated, sensitive, or unrelated?

A source is not ready simply because it exists. For example, the customer may have vendor-contract intake templates, but those templates still need a source owner to confirm that they are current, approved, accessible to the first user cohort, and appropriate for summary drafting.

A stronger readiness note would say: "Contract intake templates may support the first workflow, but they need validation. The legal operations source owner must confirm that the templates are current, approved, accessible to the first cohort, and appropriate for vendor-contract intake summaries before activation."

**App, plugin, and agent readiness**

App, plugin, and agent readiness asks whether the required component is available, enabled, approved, appropriately authenticated, and bounded for the first workflow.

Ask: Is the component needed? Does the first workflow depend on it, or can the first activation proceed with approved static or synced context? Is it available and enabled? Has the workspace administrator confirmed the plan, workspace, role, surface, regional, and group conditions for the target users? Is the connection model approved? Will each user authenticate with their own account, or will an agent-owned or shared connection be used with least privilege and a named owner? Are actions and permissions bounded? Are read and write actions, approvals, parameter constraints, publishing, schedules, triggers, sharing, logging, and escalation appropriate for the workflow?

An App, plugin, or Workspace Agent should not become a blocker unless the first workflow depends on it.

If legal summaries can begin with approved Company Knowledge, synced context, or static materials, a later contract-system action workflow can be deferred. If it is required, the checklist must confirm access, connection ownership, action scope, approvals, constraints, logging, and escalation.

A stronger readiness note would say: "A Workspace Agent that updates the contract system is under discussion, but it is not required for the first activation. Defer it until the legal operations owner confirms the need and the customer validates builder and publisher access, connection ownership, write-action approvals, constraints, logging, and escalation."

For both checks, ask whether source use, app or agent activity, actions, outputs, and issues are reviewable, and whether the source, access, app, agent, analytics, and compliance owners are clear.

## Slide 33/48 - Identify readiness gaps

A readiness gap is any unresolved condition that could prevent the workspace from supporting the target workflow with the right context, access, permissions, ownership, or review path.

These readiness gaps can affect activation even when the target workflow is clear.

Remember that not every gap has the same urgency. Some gaps must be resolved before activation.

Others should stay visible in the checklist but can be deferred because they are not required for the first workflow.

Some common gaps you might run into during your ChatGPT workspace setup include: missing or outdated source material; unclear source ownership; unapproved source or app access; unknown App, plugin, Workspace Agent, or integration availability; permissions that need validation; data-use or governance questions; dependencies that should be deferred from the first activation.

Your checklist should show which gaps matter before activation and which can wait.

For example, a customer may need approved policy guidance or synced Company Knowledge before the first legal operations activation.

A later Workspace Agent or App action that updates the contract lifecycle system may be valuable, but it can remain deferred if the initial workflow can use approved context without write access.

## Slide 34/48 - Recommended exercise: Review knowledge, app, and agent readiness

This is an optional practice activity to reinforce what you just learned.

**Purpose:** This activity helps you decide whether required sources, Apps, plugins, connections, and Workspace Agent dependencies are ready, need validation, are blocked, or can be deferred.

**Task:** Review this customer context — the customer's first workflow needs legal operations specialists to prepare vendor-contract intake summaries from approved materials. The team has contract intake templates, policy guidance, and a review checklist. The customer is considering Company Knowledge or a synced App for source access. A later Workspace Agent may update the contract system, but that write-action workflow is not required for the first activation, and its shared connection and approval settings are unresolved.

Create a simple knowledge, app, and agent readiness map in your notes. Use one row for each source, App, plugin, connection, Workspace Agent, or access dependency.

Use these headings: source, App, plugin, agent, connection, or dependency; required for the first activation?; owner or validation owner; validation needed; readiness status: Ready, Needs validation, Blocked, or Deferred; open question or next action.

As you complete the map, consider: Which sources are required for the first activation? Which source owner needs to confirm currency, approval, and access? Which source, App, sync, group-access, connection, or action dependency needs validation before activation? Which Workspace Agent, write action, shared connection, or other dependency can be deferred because it is not required for the first workflow? What owner, authentication, permission, approval, logging, or escalation question should appear in the checklist?

Estimated time: 6-7 minutes.

Suggested output and reflection: after completing your response, download the Recommended Exercise Reflection Guide for this activity ("DC3-5.5 OpenAI Partner University _ Set Up Your Workspace Course _ Reflection Guide 4.pdf", 914.6 KB). Use it to compare your response with a strong example and reflect on whether your answer is specific, grounded in the customer or workflow context, and clear about the reasoning behind your decisions.

## Slide 35/48 - Knowledge check

**Question:** A workflow depends on a policy document that is outdated and has no confirmed owner. What is the best readiness status?

- **Needs validation, because source ownership, currency, and approval must be confirmed before use.** ✓ Correct
- Deferred automatically, because all knowledge sources should wait until after activation.
- Ready, because the document exists.
- Blocked permanently, because any outdated document cannot be corrected.

The document may become usable, but it is not ready yet. The team should identify the source owner, confirm whether the content is current and approved, and decide whether it is required before activation.

## Slide 36/48 - Summary

In this module, you defined knowledge, app, and agent requirements. You learned to: identify knowledge requirements for a target workflow; capture App, plugin, Company Knowledge, connection, and Workspace Agent considerations as assumptions to validate; review source, app, plugin, connection, and agent readiness; identify readiness gaps that could affect activation.

You now have the knowledge, app, and agent readiness section of your Workspace Configuration Readiness Checklist.

Next, you'll consolidate the full checklist and assign readiness status.

## Slide 37/48 - Introduction (Module: Complete the Workspace Configuration Readiness Checklist)

You have now identified workspace requirements, owners, access and governance assumptions, and knowledge, App, plugin, connection, or Workspace Agent dependencies.

In this module, you'll consolidate those decisions into the main course output: a Workspace Configuration Readiness Checklist.

In this module, you'll clarify what is ready, what still needs validation, what is blocked, what can be deferred, and who owns the next action.

## Slide 38/48 - Review ownership

Start the final checklist review by checking ownership.

A workspace can only be ready when the right people are named for the decisions, validations, and escalations that must happen before activation. If ownership is unclear, setup work can stall even when the workflow, user cohort, and source needs are well defined.

Confirm: workspace ownership; administrative responsibilities; escalation contacts; ongoing administration ownership.

Close any unclear owner or responsibility gap.

If an owner is missing, do not mark the item ready. Mark it as needs validation or blocked, depending on whether the missing owner prevents activation.

## Slide 39/48 - Review access and governance

Next, review access and governance.

Access and governance are connected because they determine who can use each ChatGPT surface, which roles and groups can use Apps, plugins, or Workspace Agents, what information and actions are allowed, how outputs should be reviewed, and which evidence or issues need escalation before activation begins.

Confirm: product-surface, identity, SSO or SCIM, provisioning, role, group, and RBAC decisions; App, plugin, Workspace Agent, connection, action, approval, publishing, sharing, and human-review requirements; adoption analytics, Task Insights, output-quality review, Compliance API or logging, auditability, and issue-escalation expectations; retention, deletion, data residency, inference residency, regional, usage, and spend-control requirements where relevant; the owner and decision rule for pausing, narrowing, disabling, or deferring the workflow if a required control is unresolved; outstanding approvals.

Access and governance items should be evaluated based on the target workflow.

Some requirements may be required before activation. Others may be deferred if they are not needed for the first workflow.

## Slide 40/48 - Review knowledge readiness

Now review knowledge, App, plugin, connection, and Workspace Agent readiness.

This is where the checklist confirms whether ChatGPT will have the right business context to support the first workflow. At this stage of deployment, that context means the approved knowledge, documents, policies, systems, permissions, and workflow guidance ChatGPT may need to support the work.

Confirm: knowledge-source readiness; App, plugin, connection, and Workspace Agent requirements; outstanding dependencies.

A source may be ready if it is available, current, approved, owned, and appropriate for the target workflow.

An App, plugin, connection, or Workspace Agent may still need validation if plan or role availability, authentication, permissions, action boundaries, publishing, logging, data controls, or ownership are not confirmed.

## Slide 41/48 - Identify unresolved setup actions

After reviewing ownership, access, governance, knowledge sources, Apps, plugins, connections, and Workspace Agent dependencies, identify the unresolved setup actions.

An unresolved setup action is any remaining item that must be validated, approved, assigned, corrected, escalated, or intentionally deferred before activation planning continues.

- Open action
- Risk
- Configuration dependency
- Whether the item is required before activation or can be deferred
- Next action
- Owner

A readiness checklist is only useful if it leads to action. Avoid vague entries such as "confirm governance." Instead, write an actionable item: "Legal operations owner and compliance owner to confirm human-review expectations for vendor-contract summaries before activation."

## Slide 42/48 - Assign readiness status

The final stage is to assign a readiness status to each of the checklist areas you've just created.

For each checklist area, mark the status as one of four options: Ready; Needs validation; Blocked; Deferred.

Here's an example of when to use each status:

- **Ready** — Meaning: The item is confirmed enough to support activation. Use when: Owner, requirement, validation, and next step are clear.
- **Needs validation** — Meaning: The item may be usable, but a customer owner must confirm it. Use when: An assumption, approval, source, access path, or policy question remains open.
- **Blocked** — Meaning: Activation cannot proceed until the issue is resolved. Use when: A required owner, access path, approval, source, or dependency is missing.
- **Deferred** — Meaning: The item is not required for the first activation. Use when: The dependency may be valuable later but is outside the first workflow or launch scope.

The status should be based on available evidence, owner assignment, and whether the item must be resolved before activation begins.

## Slide 43/48 - Completed checklist example

With everything combined, you now have a checklist that shows whether the workspace is ready to support the first activation.

A readiness checklist should not just list setup tasks. It should show what is ready, what needs validation or resolution, who owns each action, and what happens next.

Here is a sample readiness section for a fictional customer:

- **Workspace administrator named** — Status: Ready. Before activation?: Yes. Owner: Workspace administrator. Next action: Coordinate setup and track open dependencies.
- **Access and setup escalation** — Status: Needs validation. Before activation?: Yes. Owner: Workspace admin or IT owner. Next action: Name the owner for access and setup blockers.
- **Legal operations cohort, product-surface, and role/group access** — Status: Needs validation. Before activation?: Yes. Owner: Workspace administrator, identity owner, and access-control owner. Next action: Confirm that the selected ChatGPT surface is enabled for the target role; confirm SSO or SCIM provisioning, group membership, RBAC, user eligibility, and deprovisioning.
- **Human-review expectation** — Status: Needs validation. Before activation?: Yes. Owner: Legal operations and compliance owners. Next action: Confirm the review owner, process, and user guidance.
- **Sensitive-data boundary** — Status: Needs validation. Before activation?: Yes. Owner: Legal, security, or compliance owner. Next action: Confirm permitted inputs, connections, sharing, and use.
- **Contract-intake templates** — Status: Needs validation. Before activation?: Yes. Owner: Legal operations source owner. Next action: Confirm currency, approval, access, and workflow fit.
- **Company Knowledge or synced App context** — Status: Needs validation. Before activation?: Yes, if required for the first workflow. Owner: Source owner, app owner, and workspace administrator. Next action: Confirm source approval and currency, sync or connection ownership, role access, domain restrictions, data boundaries, and whether read-only access is sufficient.
- **Policy guidance** — Status: Blocked. Before activation?: Yes. Owner: Source owner not confirmed. Next action: Name the owner and validate currency and approval. Pause or re-scope if unresolved.
- **Later Workspace Agent or App write-action workflow** — Status: Deferred. Before activation?: No. Owner: App or agent owner. Next action: Before later use, define builder, editor, publisher, runner, and group access; connection ownership; allowed write actions; approvals; constraints; logging; and escalation.
- **Analytics, compliance, retention, residency, and usage controls** — Status: Needs validation. Before activation?: Depends on customer requirements. Owner: Deployment owner, workspace administrator, and security or compliance owner. Next action: Distinguish adoption analytics from Compliance API or action logs; confirm access and review cadence; validate retention, deletion, residency, regional, usage, and spend-control requirements.
- **Feedback and issue route** — Status: Needs validation. Before activation?: Yes. Owner: Partner deployment lead and workflow owner. Next action: Define where users report access, source, review, and output issues.

This example makes the setup state visible. The team can see what is ready, what needs validation, what is blocked, what can be deferred, and who owns the next action.

Notice that Blocked does not mean the item can never be resolved. It means activation should not proceed until the required owner, approval, access path, source, or dependency is resolved. Notice also that Deferred does not mean the item is unimportant. It means the dependency may matter later, but it is not required for the first activation.

This keeps the checklist practical. It helps the team decide what must happen now, what can wait, and what needs a clear owner before users begin working with ChatGPT on the target workflow.

## Slide 44/48 - Recommended exercise: Run a plan-aware admin readiness review

This is an optional practice activity to reinforce what you just learned.

**Purpose:** This activity helps you apply current workspace controls to an approved workflow and decide what is ready, what needs validation, what is blocked, and what should be deferred — without turning the review into a click-by-click console walkthrough.

**Task:** Review this customer context — the customer is preparing for its first ChatGPT activation. The target workflow is human-reviewed vendor-contract intake summaries for a small legal operations cohort.

The team has gathered these readiness notes: the workspace administrator has been named, but the access-control owner and app or agent owner have not; ChatGPT Work is the proposed surface for the legal operations cohort, but access for the target role is not confirmed — SSO exists, while SCIM group provisioning, RBAC, user eligibility, and deprovisioning still need validation; contract intake templates are available, but a source owner has not confirmed whether they are current and approved, and the customer is also considering Company Knowledge or a synced App, whose role access, sync ownership, and data boundary are not confirmed; policy guidance may be required, but ownership and currency are unclear, and if the source is required for responsible summary drafting, the item may become blocked; human review is expected before summaries are used, but the review owner and user guidance are not yet confirmed; sensitive-data boundaries need legal or compliance validation; a later Workspace Agent may update the contract system, but it is not required for the first activation, and builder and publisher access, group sharing, shared-connection ownership, write-action approvals, constraints, logging, and escalation are unresolved; Workspace Analytics will support adoption review, but the customer has not named who can access it or how it will be combined with output review, and any Compliance API or action-log review owner is also unresolved; retention, deletion, data residency, inference residency, regional, usage, and spend-control requirements still need customer-specific validation; the feedback and issue route for early users is not yet named.

Create a final readiness review in your notes. Use one row for each readiness note.

Use these headings: readiness item; status: Ready, Needs validation, Blocked, or Deferred; required before activation?; owner or validation owner; next action; rationale.

As you complete the review, consider: Which items are ready enough to support activation? Which items need validation before activation? Which items would block activation if unresolved? Which items can be deferred because they are not required for the first workflow? Who should own the next action for each unresolved item? Which vague notes should be rewritten as clear setup actions?

Estimated time: 8-10 minutes.

Suggested output and reflection: after completing your response, download the Recommended Exercise Reflection Guide for this activity ("DC3-6.7 OpenAI Partner University _ Set Up Your Workspace Course _ Reflection Guide 5.pdf", 923.9 KB). Use it to compare your response with a strong example and reflect on whether your answer is specific, grounded in the customer or workflow context, and clear about the reasoning behind your decisions.

## Slide 45/48 - Knowledge check

**Question:** A required source is approved and current, but the access path for the first user cohort has not been confirmed. What is the best readiness decision?

- Deferred, because access always comes after activation.
- Blocked permanently, because access cannot be resolved.
- **Needs validation, because user access must be confirmed before activation.** ✓ Correct
- Ready, because the source itself is approved.

The source may be ready, but the workspace is not fully ready for activation until the first user cohort's access path is confirmed or assigned a clear next action.

## Slide 46/48 - Summary

In this module, you completed the Workspace Configuration Readiness Checklist. You learned to: review ownership, access, governance, and knowledge readiness; identify unresolved setup actions; assign readiness status: ready, needs validation, blocked, or deferred; clarify who owns the next action before activation begins.

You now have the key components of a Workspace Configuration Readiness Checklist that can support workspace readiness before activation begins.

## Slide 47/48 - Recap

In this course, you practiced translating a Deployment Success Plan into workspace readiness requirements.

You mapped deployment requirements to workspace implications; clarified ownership, identity, provisioning, roles, and groups; reviewed Apps, plugins, Company Knowledge, ChatGPT Work, and Workspace Agents; validated action, analytics, compliance, retention, residency, and usage controls; and assigned readiness status across setup dependencies.

You can now build the key components of a Workspace Configuration Readiness Checklist.

Use your checklist to align with the customer on what is ready, what needs validation, what is blocked, what can be deferred, and who owns the next action before activation begins.

## Slide 48/48 - Congratulations

Congratulations, you've completed this course!

You now have a practical way to translate a deployment success plan into workspace setup requirements.

A strong Workspace Configuration Readiness Checklist keeps setup connected to the customer's approved workflow, target users, governance expectations, knowledge dependencies, access needs, and launch goals.

Use your checklist notes as a working reference for workspace readiness, administrative ownership, identity and access, source, App, plugin, and Workspace Agent validation, action and governance controls, evidence review, unresolved setup actions, and activation readiness.

Course completed.
