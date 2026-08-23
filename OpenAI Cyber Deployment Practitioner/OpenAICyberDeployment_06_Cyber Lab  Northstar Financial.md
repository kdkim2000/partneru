# Cyber Lab - Northstar Financial

## Slide 1/3 - Title

Cyber Lab - Northstar Financial

## Slide 2/3 - Northstar Financial Security Lab Instructions

In this lab, you will review a fictional customer security situation and prepare a concise recommendation. Your goal is to turn a broad request into a bounded, evidence-led next step that the customer can safely review and act on.

Everything you need is included below. You do not need product access, a repository, downloadable materials, or external research.

Estimated time: 20 minutes

**Customer situation**

Northstar Financial is a fictional regional financial services company preparing an update to its digital customer portal.

The engineering team plans to release a pull request in three days. The change affects account-update authorization logic in the customer-owned `customer-account-service`.

The AppSec team already has 62 open findings, many of which are low confidence. The AppSec lead has capacity to review one focused security output this week. The engineering director needs a clear release decision and wants any concern returned to developers with useful evidence.

The customer asks:

> Can we use Codex Security across all of our repositories to clear the backlog, automatically fix any critical issues, and make sure this release is safe?

Northstar has authorized a read-only review of the authorization-related pull request, the directly related authorization files, and the directly related tests.

Northstar has NOT authorized review of other repositories, production testing, exploit reproduction, third-party system review, automatic remediation, automatic merge, or an automated release decision.

**Evidence**

A bounded review of the authorized pull request produces this training note:

> The pull request changes one account-update path. In the changed path, the role-checking helper that appeared in the previous version is no longer called. Existing tests confirm that an authenticated user can update an account, but the supplied materials do not include a test showing whether one user can update another customer's account. No runtime validation or exploit reproduction has been performed.

**Your task**

Prepare a Customer Security Recommendation for Northstar Financial. Your recommendation should help the customer decide what to do before the planned release while preserving the approved scope, human review, and evidence boundaries.

Your recommendation must address:

1. Customer situation: What immediate decision must Northstar make, who needs to make it, and where is the workflow currently stuck?
2. Recommended first step: What bounded defensive review should Northstar perform first, and why is it more appropriate than reviewing every repository?
3. Scope and reviewers: What is in scope, what is out of scope, and which customer reviewers must remain accountable
4. Evidence position: What is directly supported by the materials, what is a reasonable inference, how should the concern be classified, and what remains unproven?
5. Success measures and guardrails: What would make the review useful, and which boundaries must remain in place
6. Next action and owner: What should happen next, who owns it, and what decision will it enable?

Do not promise broad product access, production testing, automatic remediation, automatic merge, guaranteed vulnerability discovery, or a guaranteed security outcome.

**Submission requirements**

- Length: 250-400 words, one page
- Format: PDF preferred; DOCX accepted

Upload the completed file in the next section titled Northstar Financial Lab Submission module for review.

## Slide 3/3 - Northstar Financial Lab Submission

**Exercise Instruction**

Your task

Prepare a Customer Security Recommendation for Northstar Financial. Your recommendation should help the customer decide what to do before the planned release while preserving the approved scope, human review, and evidence boundaries.

Your recommendation must address:

1. Customer situation: What immediate decision must Northstar make, who needs to make it, and where is the workflow currently stuck?
2. Recommended first step: What bounded defensive review should Northstar perform first, and why is it more appropriate than reviewing every repository?
3. Scope and reviewers: What is in scope, what is out of scope, and which customer reviewers must remain accountable
4. Evidence position: What is directly supported by the materials, what is a reasonable inference, how should the concern be classified, and what remains unproven?
5. Success measures and guardrails: What would make the review useful, and which boundaries must remain in place
6. Next action and owner: What should happen next, who owns it, and what decision will it enable?

Do not promise broad product access, production testing, automatic remediation, automatic merge, guaranteed vulnerability discovery, or a guaranteed security outcome.

**Submission requirements**

- Length: 250-400 words, one page
- Format: PDF preferred; DOCX accepted

*(This slide requires uploading a completed file for review — a file-upload submission, not a text-based knowledge check. No answer key or automatic grading is presented in-page.)*
