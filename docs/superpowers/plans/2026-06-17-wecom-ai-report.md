# WeCom AI Report Automation Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Set up a daily Codex automation that generates and pushes a local Markdown report about WeCom AI / Agent developments.

**Architecture:** The repository stores generated reports and project notes. A Codex cron automation performs daily research, writes `reports/YYYY-MM-DD.md`, commits the result, and pushes it to `origin/main`.

**Tech Stack:** Markdown, Git, Codex cron automation, web research.

---

### Task 1: Add Repository Structure

**Files:**
- Create: `/Users/wangchongshan/workplace/report/wecom/reports/.gitkeep`
- Create: `/Users/wangchongshan/workplace/report/wecom/docs/superpowers/specs/2026-06-17-wecom-ai-report-design.md`
- Create: `/Users/wangchongshan/workplace/report/wecom/docs/superpowers/plans/2026-06-17-wecom-ai-report.md`

- [ ] **Step 1: Create the report directory placeholder**

Create `reports/.gitkeep` so Git keeps the report directory before the first generated report.

- [ ] **Step 2: Save the design document**

Save the daily report requirements, source strategy, report format, automation behavior, risks, and success criteria in `docs/superpowers/specs/2026-06-17-wecom-ai-report-design.md`.

- [ ] **Step 3: Save this implementation plan**

Save this plan in `docs/superpowers/plans/2026-06-17-wecom-ai-report.md`.

- [ ] **Step 4: Verify repository status**

Run:

```bash
git -C /Users/wangchongshan/workplace/report/wecom status --short
```

Expected: only the new `reports/` and `docs/` files appear as untracked or staged changes.

- [ ] **Step 5: Commit and push the structure**

Run:

```bash
git -C /Users/wangchongshan/workplace/report/wecom add reports/.gitkeep docs/superpowers/specs/2026-06-17-wecom-ai-report-design.md docs/superpowers/plans/2026-06-17-wecom-ai-report.md
git -C /Users/wangchongshan/workplace/report/wecom commit -m "Add WeCom AI report automation docs"
git -C /Users/wangchongshan/workplace/report/wecom push origin main
```

Expected: commit succeeds and pushes to `origin/main`.

### Task 2: Create the Daily Automation

**Automation:**
- Name: `WeCom AI Agent Daily Report`
- Workspace: `/Users/wangchongshan/workplace/report/wecom`
- Schedule: daily at 07:00 Asia/Shanghai

- [ ] **Step 1: Create the cron automation**

Create a Codex cron automation that researches current WeCom AI / Agent / MCP / intelligent bot / message API updates, writes `reports/YYYY-MM-DD.md`, commits the report, and pushes to `origin/main`.

- [ ] **Step 2: Verify the automation exists**

View the created automation and confirm it is active, points at `/Users/wangchongshan/workplace/report/wecom`, and contains the daily report prompt.

### Task 3: Manual First Run Check

**Files:**
- Create or update: `/Users/wangchongshan/workplace/report/wecom/reports/YYYY-MM-DD.md`

- [ ] **Step 1: Run the same workflow manually if an immediate report is needed**

Generate today's report using the design document as the format guide, then commit and push it.

- [ ] **Step 2: Verify pushed report**

Run:

```bash
git -C /Users/wangchongshan/workplace/report/wecom status --short --branch
```

Expected: the branch is clean and tracking `origin/main`.

## Self-Review

- The plan covers repository structure, automation creation, and verification.
- There are no placeholder sections.
- The file paths match the approved repository path and report layout.
