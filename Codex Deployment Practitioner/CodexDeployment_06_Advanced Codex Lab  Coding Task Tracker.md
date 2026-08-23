# Advanced Codex Lab - Coding Task Tracker

*OpenAI PartnerU — Full course transcript*

## Advanced Codex Lab: Task Tracker Coding Task

Created March 2026

---

## Introduction

This lab is a practical coding exercise for the Advanced Codex course.

You will use Codex to inspect an unfamiliar repository, diagnose issues, implement a feature, and prepare reviewable Git changes. The focus is not manual coding speed. The focus is directing Codex effectively, reviewing diffs, and validating outcomes.

**Canonical repository:** https://github.com/pavlinhristov/CodexLab

**Estimated time:** 30 to 45 minutes.

## Overview

**Use Codex for all steps:**
- Ask Codex to inspect before changing code.
- Ask Codex to run setup and verification commands.
- Ask Codex to explain findings before patching.
- Review Codex diffs before accepting changes.
- Ask Codex to rerun verification after each change.

Do not treat this as a manual coding exercise. Treat Codex as your implementation teammate and keep yourself in the reviewer role.

**Prerequisites:**
- Git
- Codex app or Codex cloud access
- Python 3.9 or newer

## Repository Setup

Start from the canonical lab repository:

```bash
git clone https://github.com/pavlinhristov/CodexLab.git
cd CodexLab
```

Create and activate a virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the app:

```
uvicorn app.main:app --reload
```

Expected local endpoints:
- http://127.0.0.1:8000
- http://127.0.0.1:8000/docs

**Suggested setup prompt:** "Set up this repository for development. Create a virtual environment, install dependencies, start the FastAPI app, and tell me exactly what you ran."

## Task 1 - Understand the Codebase

Before making changes, ask Codex to explain the repository and trace the GET /tasks flow.

**Suggested prompts:**
- "Explain what this repository does and map the key files."
- "Trace GET /tasks from route to storage and identify where filtering logic lives."
- "Summarize this codebase for an engineer joining the team today."

You should leave this task with a clear mental model:
- `app/main.py` defines routes
- `app/schemas.py` defines request/response models
- `app/service.py` holds business logic
- `app/store.py` handles JSON persistence
- `data/tasks.json` contains sample data

## Task 2 - Fix the Two Bugs

This repo includes two intentional bugs. For each bug, ask Codex to run the full loop: reproduce, diagnose, patch, show diff, verify.

### Bug A: Status filtering is broken

Reproduce:

```bash
curl http://127.0.0.1:8000/tasks
curl "http://127.0.0.1:8000/tasks?status=open"
```

Expected after fix: `status=open` returns only open tasks.

**Suggested prompt:** "Reproduce the GET /tasks status filter bug, explain the root cause, implement the smallest clean fix, and verify the result."

### Bug B: Completion does not persist

Reproduce:

```bash
curl -X POST http://127.0.0.1:8000/tasks/1/complete
curl http://127.0.0.1:8000/tasks/1
```

Expected after fix: the task remains done when fetched again; `completed_at` is non-null.

**Suggested prompt:** "Reproduce the complete-task persistence issue, fix it at the storage/business-logic boundary, and rerun the API calls to prove persistence."

## Task 3 - Add Search Support

Implement an optional `q` query parameter on GET /tasks.

**Requirements:**
- Case-insensitive matching.
- Match against both title and description.
- Works together with status filter.
- Existing behavior is unchanged when `q` is omitted.

Verification examples:

```bash
curl "http://127.0.0.1:8000/tasks?q=launch"
curl "http://127.0.0.1:8000/tasks?q=report"
curl "http://127.0.0.1:8000/tasks?status=open&q=plan"
```

**Suggested prompt:** "Implement a q filter for GET /tasks with case-insensitive matching across title and description, preserve existing behavior when q is missing, and verify with curl."

## Task 4 - Prepare a Clean Commit

Have Codex prepare a branch and commit after you approve the final diff.

Before commit, check whether `data/tasks.json` changed only due to runtime testing. If yes, revert it so the commit contains intentional code changes only.

Suggested commands:

```bash
git checkout -b codex/lab-fixes
git status
git add .
git commit -m "Fix task bugs and add search filter"
git push origin codex/lab-fixes
```

**Suggested prompt:** "Prepare this repo for PR review: verify whether data/tasks.json should be restored, summarize code changes, then create a clean commit after my approval."

## Final Verification Checklist

Run or ask Codex to run:

```bash
curl "http://127.0.0.1:8000/tasks?status=open"
curl "http://127.0.0.1:8000/tasks?status=done"
curl -X POST http://127.0.0.1:8000/tasks/3/complete
curl http://127.0.0.1:8000/tasks/3
curl "http://127.0.0.1:8000/tasks?q=launch"
curl "http://127.0.0.1:8000/tasks?status=open&q=plan"
```

**Suggested verification prompt:** "Run the verification steps for this lab and tell me whether the repository now behaves correctly."

**Acceptance checks:**
- Status filtering is correct.
- Completion persists and sets `completed_at`.
- Search is case-insensitive.
- Search and status filters compose correctly.
- Final diff is reviewable and scoped.

## Submit

**Instruction:** Use the following prompt to prepare your submission:

> "Export all messages in this context window as a single block I can copy/paste. Redact personally identifiable user information such as home directory name."

Paste the output into the text box and then submit.

This is the final page of the lab. Submission requires the output of an actual hands-on Codex session (cloning the repo, fixing the bugs, adding search support, and preparing a clean commit) pasted into the text box for review.

---

*End of course transcript: Advanced Codex Lab - Coding Task Tracker*

