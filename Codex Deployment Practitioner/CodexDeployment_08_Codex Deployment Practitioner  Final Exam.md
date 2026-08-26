# Codex Deployment Practitioner - Final Exam

## Slide 1/2 - Title

Codex Deployment Practitioner - Final Exam

## Slide 2/2 - Assessment (20 questions, 16 correct required to pass)

**Q1.** A customer wants to introduce Codex across engineering immediately. What is the strongest first deployment recommendation?

- Begin with the team that writes the most code, regardless of workflow readiness
- Enable every team and compare usage after one quarter
- Choose the Codex surface first and design the workflow around it
- **Start with one recurring workflow, define safeguards and review ownership, then expand based on evidence** ✓ Correct

*Explanation: Module 1(Codex Deployment Operating Model)의 Golden Principle — "Start narrow. Prove the safeguards worked. Expand only on evidence." 및 Module 5의 강한 추천 예시("Choose one workflow... Define... governance assumptions... before expanding")와 일치. (Source: Codex Deployment Operating Model)*

**Q2.** Which customer factor should most directly shape the first Codex pilot boundary?

- **The workflow's repeated friction, team maturity, risk profile, and available review process** ✓ Correct
- The customer's preferred demo format
- The popularity of AI tools among individual developers
- The number of programming languages used across the company

*Explanation: Module 2(Codex Deployment Operating Model)의 7가지 operating-model inputs(엔지니어링 목표, SDLC friction, team maturity, risk profile, surfaces, governance needs, rollout expectations) 및 "Assess maturity and risk before choosing the pilot" 섹션과 일치. (Source: Codex Deployment Operating Model)*

**Q3.** A workflow has unclear repository ownership and inconsistent review habits. What is the best readiness judgment?

- Ignore the gaps because Codex can create its own review process
- **Treat the gaps as deployment conditions to resolve before higher-impact delegation** ✓ Correct
- Expand the pilot so more teams can supply feedback
- Move directly to production and monitor for issues

*Explanation: Module 2 "Assess maturity and risk before choosing the pilot" — 불분명한 저장소 소유권/일관되지 않은 리뷰 습관은 risk-profile signal에 해당하며, "A production-adjacent workflow with unclear ownership and elevated permissions should be paused or escalated for later technical validation" 원칙과 일치. (Source: Codex Deployment Operating Model)*

**Q4.** When should a deployment team involve a technical or security specialist?

- Whenever the customer asks a general question about developer productivity
- Only after the pilot has reached production
- Before any workflow discovery begins
- **When decisions require detailed validation of permissions, configuration, security controls, or production-impacting actions** ✓ Correct

*Explanation: Module 3(Codex Deployment Operating Model) "When to involve a technical or security SME" — 새 저장소/워크스페이스 접근, 클라우드 실행, 민감 파일/시스템, 명령 실행, production-impacting steps, 감사/컴플라이언스, 고급 통합 패턴, 불명확한 승인 경계, 상승된 권한 등이 있을 때 SME를 참여시켜야 한다는 내용과 일치. (Source: Codex Deployment Operating Model)*

**Q5.** Which statement best distinguishes agentic delegation from basic autocomplete?

- Autocomplete is always safer than any delegated task
- Agentic delegation removes the need for engineer review
- **Agentic delegation gives Codex a bounded goal, relevant context, and validation expectations for multi-step work** ✓ Correct
- Autocomplete can operate across any long-running workflow without context

*Explanation: "Codex in Developer Workflows" 과정의 "Visual: From Autocomplete to Agentic Delegation" 및 비교 표 — Agentic delegation은 "Works toward a bounded goal and returns outputs for review", "the human defines the task, reviews the output, and remains accountable"이며, 리뷰의 필요성을 없애지 않는다는 내용과 일치. (Source: Codex in Developer Workflows)*

**Q6.** A team asks Codex to "fix the service." What is the best way to improve the task?

- Remove constraints so the agent can explore freely
- **Define the goal, scope, relevant context, validation checks, and stop conditions** ✓ Correct
- Ask Codex to decide what success should mean
- Add a longer description of Codex features

*Explanation: "Codex in Developer Workflows" 과정의 "The Five Elements of a Stronger Delegated Task"(Clear objective, Bounded scope, Expected output, Validation expectation, Dependency awareness)와 "Delegation Brief"(Goal, Context, Scope, Validation, Stop conditions) 프레임워크와 일치. "Fix the service"처럼 모호한 요청은 목표·범위·컨텍스트·검증·중단 조건을 명확히 해야 한다는 원칙. (Source: Codex in Developer Workflows)*

**Q7.** Where should a team look first when deciding how Codex could improve a developer workflow?

- **The point where the workflow loses time, context, or review continuity** ✓ Correct
- The newest Codex feature
- The number of repositories in the organization
- The team's preferred editor theme

*Explanation: "Codex in Developer Workflows" 과정의 "Start with Workflow Continuity" 섹션 — "A weak starting question is: Where can AI generate code? A stronger starting question is: Where do developers repeatedly lose time, continuity, or operational context?"와 일치. (Source: Codex in Developer Workflows)*

**Q8.** Which responsibility should remain with engineers in a Codex-assisted workflow?

- Avoiding all use of automation
- Generating every first draft manually
- **Defining quality expectations and accepting or rejecting production-impacting changes** ✓ Correct
- Letting Codex approve its own work

*Explanation: "Codex in Developer Workflows" 과정의 "Human Judgment Remains Essential" — "Humans remain accountable for decisions that affect architecture, prioritization, production approval, risk, quality, and final acceptance"와 일치. (Source: Codex in Developer Workflows)*

**Q9.** Which workflow generally requires the strongest governance controls?

- Summarizing a test failure for a developer
- Drafting internal documentation for engineer review
- Explaining an approved code snippet in a read-only setting
- **Changing production infrastructure with broad permissions and no approval gate** ✓ Correct

*Explanation: "Codex Security, Governance and Controls" 과정의 Risk Ladder — "High-risk engineering action"(production-impacting changes, infrastructure modification, elevated permissions)은 human-led workflow 또는 explicit approval path, 강한 escalation/auditability가 필요하다는 내용과 일치. (Source: Codex Security, Governance and Controls)*

**Q10.** What should a governance checkpoint map make explicit?

- Only the model selected for the workflow
- **Approval, review, validation, and escalation points and who owns them** ✓ Correct
- A guarantee that no error can occur
- Every possible future use case

*Explanation: "Codex Security, Governance and Controls" 과정의 "Checkpoint Map: Approval, Review, Validation, and Escalation" — 4가지 체크포인트 유형을 구분하고 각각의 소유자·트리거를 명확히 해야 한다는 내용과 일치. (Source: Codex Security, Governance and Controls)*

**Q11.** Why is auditability important in a Codex-assisted engineering workflow?

- It guarantees that generated code is correct
- It replaces the need for human review
- **It helps teams understand what happened, what evidence was produced, and who made key decisions** ✓ Correct
- It allows all developers to use unrestricted permissions

*Explanation: "Codex Security, Governance and Controls" 과정의 "Operational Trust Through Reviewability and Transparency" — Task/Context/Evidence/Decision visibility를 통해 워크플로우를 신뢰하고 거버넌스할 수 있어야 한다는 내용과 일치. (Source: Codex Security, Governance and Controls)*

**Q12.** A workflow can read approved files but should not modify them. Which safeguard best fits?

- Remove logging to protect privacy
- Let the agent choose its own permissions
- Grant broad write access and rely on user judgment
- **Use a read-only boundary and require explicit approval before any action-taking expansion** ✓ Correct

*Explanation: "Codex Security, Governance and Controls" 과정의 "Approval policy" / "Sandbox mode" 개념 — 읽기 전용 경계를 두고 더 넓은 작업(쓰기·확장)으로 넘어가기 전에는 명시적 승인이 필요하다는 원칙과 일치. (Source: Codex Security, Governance and Controls)*

**Q13.** When is an advanced Codex integration most justified?

- **When a repeatable workflow needs consistent context, orchestration, governance, observability, or scale** ✓ Correct
- Before the workflow has an owner or success criteria
- Whenever the customer wants the most sophisticated architecture
- When a one-time task can be completed with a simple prompt

*Explanation: "Advanced Codex Workflow Integration" 과정의 Golden Principle — "Use the minimum useful integration pattern"과 "Define Advanced Workflow Integration"(Repeatable/Governed/Observable/Scalable 네 가지 개선 기준)과 일치. (Source: Advanced Codex Workflow Integration)*

**Q14.** A simple reviewed Codex workflow already meets the customer's need. What should the team do?

- Add orchestration and asynchronous components to prepare for any future possibility
- Expand permissions before collecting evidence
- Replace the workflow with a fully autonomous agent
- **Keep the simpler pattern and add complexity only when evidence shows it is needed** ✓ Correct

*Explanation: "Advanced Codex Workflow Integration" 과정의 Golden Principle — "Use the minimum useful integration pattern, and make ownership, controls, and evidence explicit" 및 "If a mechanism does not improve one of these areas, it may be unnecessary for the current workflow" / "If the rationale is weak, recommend the simpler pattern first"와 일치. (Source: Advanced Codex Workflow Integration)*

**Q15.** What belongs in a governance-aware integration recommendation?

- A feature list without owners or validation
- A promise that the integration will never fail
- Only a diagram of the technical components
- **The workflow need, context and action boundaries, validation evidence, approval and review points, ownership, and an escalation or rollback path** ✓ Correct

*Explanation: "Advanced Codex Workflow Integration" 과정의 "Structure the Recommendation" 섹션 — 워크플로우 필요, 실행 위치/제한, 신뢰·리뷰(검증 증거, 오너, 리뷰어, 승인 지점), 대기해야 할 요소·롤백/에스컬레이션 경로를 모두 포함해야 한다는 내용과 일치. (Source: Advanced Codex Workflow Integration)*

**Q16.** A team wants to schedule a recurring Codex workflow after a successful one-off run. What must be confirmed before recommending automation?

- Confirm every repeat uses the same prompt, repository, branch, output format, and runtime surface
- Confirm the workflow can run without checkpoints, human review, activity visibility, or a named escalation owner
- Confirm the schedule, preferred model, maximum run duration, notification channel, and automatic retry limit
- **Confirm the trigger, approved context, action boundary, validation evidence, review and monitoring owners, and rollback or disable path** ✓ Correct

*Explanation: "Advanced Codex Workflow Integration" 과정의 "Automation Readiness Checklist" — Purpose/pattern, Runtime/boundaries, Evidence/review, Ownership/scale 항목과 "Do not recommend automation simply because a workflow repeats. Recommend automation only when the trigger, boundary, validation, review, monitoring, and rollback path are clear"와 일치. (Source: Advanced Codex Workflow Integration)*

**Q17.** What does deployment depth describe?

- The length of the implementation plan
- The size of the customer's codebase
- The number of developers using Codex
- **How deeply Codex is integrated into a workflow and the corresponding readiness and safeguard requirements** ✓ Correct

*Explanation: "Codex Use Cases: Deployment Depth" 과정의 "Deployment-Depth Ladder"(Level 1~4)와 "Match Depth to Readiness" — 배포 깊이는 워크플로우의 운영 성숙도·리스크·거버넌스 요구 수준과 연결된다는 내용과 일치. (Source: Codex Use Cases: Deployment Depth)*

**Q18.** Which use case is the strongest candidate for a lightweight first Codex deployment?

- A production-wide change with unclear ownership
- A workflow selected only because it uses a popular language
- An open-ended task with no validation method
- **A bounded, recurring task with clear inputs, testable outputs, and an identified reviewer** ✓ Correct

*Explanation: "Codex Use Cases: Deployment Depth" 과정의 "Use-Case Value Screen"(반복성, 리뷰 가능성, 명확한 오너십)과 "Level 1: Lightweight workflow augmentation" — "Codex supports a workflow that is easy to bound and easy to review"와 일치. (Source: Codex Use Cases: Deployment Depth)*

**Q19.** A mature team has strong tests and review, but the proposed workflow can change production systems. How should deployment depth be chosen?

- Choose based only on expected time savings
- **Consider both team readiness and workflow impact, then add safeguards appropriate to the higher risk** ✓ Correct
- Ignore production impact because tests exist
- Use the deepest option immediately because the team is mature

*Explanation: "Codex Use Cases: Deployment Depth" 과정의 "Customer-Context Fit Check"(team maturity, risk profile 등)와 "Match Depth to Readiness" — 팀 성숙도가 높아도 production 영향이 있는 워크플로우는 더 높은 리스크에 맞는 안전장치가 필요하다는 원칙(risk profile이 배포 깊이를 좌우)과 일치. (Source: Codex Use Cases: Deployment Depth)*

**Q20.** What evidence should support expansion beyond the first Codex deployment?

- **Verified workflow value, effective safeguards, reliable review, and readiness for the next level of complexity** ✓ Correct
- A single successful demo
- A request from one developer to automate more tasks
- High interest in additional features

*Explanation: 여러 과정에서 반복되는 Golden Principle과 일치 — "Codex Deployment Operating Model"의 "Scaling is evidence-based"(workflow evidence, safeguard evidence, adoption evidence), "Codex Use Cases: Deployment Depth"의 "What Evidence Supports Expansion?"(workflow value, reviewability, operational readiness, governance fit, adoption discipline) — 확장은 열의가 아니라 검증된 증거에 기반해야 한다는 원칙. (Source: Codex Deployment Operating Model, Codex Use Cases: Deployment Depth)*

**Final result: You passed the assessment!** You completed the assessment with 20 of 20 questions answered correctly.

**Course completed**
