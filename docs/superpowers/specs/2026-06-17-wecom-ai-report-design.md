# WeCom AI / Agent Daily Report Design

## Goal

Create a lightweight daily intelligence workflow that tracks the latest information about Enterprise WeChat / WeCom, especially AI, Agent, MCP, intelligent bot, and message-sending API changes, then archives each daily summary as Markdown in this GitHub-backed repository.

## Scope

The first version uses a Codex cron automation rather than a custom crawler service. Each run researches current public sources, writes one Markdown report under `reports/`, commits the report, and pushes it to `origin/main`.

This version does not send reports to a WeCom bot or require WeCom administrator permissions.

## Repository Layout

- `reports/`: daily generated reports, one file per date.
- `docs/superpowers/specs/`: design notes for this workflow.
- `docs/superpowers/plans/`: implementation and maintenance plans.

## Daily Report Format

Each report is named `reports/YYYY-MM-DD.md` and uses this structure:

```md
# 企业微信 AI / Agent 情报日报 - YYYY-MM-DD

## 今日结论
## 官方与高可信更新
## AI / Agent / MCP / 智能机器人动态
## 消息发送与 API 开放迹象
## 会议/活动雷达
## 值得继续跟进的链接
## 未证实或低可信信号
## 明日关注点
```

Each item should include a source link and a confidence label:

- `官方`: Enterprise WeChat, WeChat, Tencent Cloud, or official GitHub organization.
- `半官方/生态`: Tencent ecosystem partners, official integration docs from reputable vendors, or public platform docs.
- `媒体`: technology media or industry reporting.
- `社区`: GitHub issues, developer posts, forums, or social discussion.

## Source Strategy

The daily task should search and compare sources across:

- Enterprise WeChat developer documentation and public updates.
- Tencent Cloud AI Agent, ADP, LKE, bot, and connector documentation.
- WeChat Open Class and WeChat AI ecosystem announcements.
- GitHub repositories such as `WeComTeam/wecom-cli` and related MCP / Agent tooling.
- Reputable Chinese technology media and developer communities.
- Developer conferences, product launch events, technical salons, hackathons, and official meetup pages that may include WeCom, WeChat, Tencent Cloud, AI Agent, MCP, OpenClaw, or enterprise collaboration topics.

The daily task should not use short-video or broad social feeds as regular sources. Excluded routine sources include Bilibili, YouTube, Jike, Weibo, and X. Only cite them if a later human request explicitly asks for social/video monitoring.

Core keywords:

- `企业微信 AI Agent`
- `企业微信 智能体`
- `企业微信 MCP`
- `企业微信 智能机器人 API`
- `企业微信 主动发送消息 API`
- `企业微信 外部联系人 发送消息`
- `企业微信 客户群 主动消息`
- `WeComTeam wecom-cli`
- `腾讯云 ADP 企业微信`
- `微信 AI 智能体 开发者接入`
- `腾讯云 开发者大会 AI Agent`
- `微信公开课 企业微信 AI 开发者`
- `腾讯云 AI 产业应用大会 ADP`
- `AI Agent 开发者大会 企业微信`
- `OpenClaw 开发者活动 企业微信`

## Judgement Criteria

The report should emphasize whether any signal changes one of these boundaries:

- Message sender: user, application, bot, customer-contact assistant, or Agent.
- Message target: internal user, internal group, customer, customer group, or open chat.
- Send mode: active push, callback response, task creation, member-confirmed group send, or webhook.
- Permission model: new scope, new bot mode, new API mode, or new connector authorization.
- Operational limits: frequency caps, confirmation requirements, audit controls, or availability by edition.
- Event value: whether a conference or salon is relevant enough to attend, based on agenda fit, speaker/source authority, registration status, location, date, and likelihood of WeCom / Tencent Cloud / Agent product announcements.

## Automation Behavior

The automation should run daily, generate the current date's report, then use Git to commit and push. Before writing, it should pull the latest remote state to avoid overwriting user changes. If the report already exists, it may update that file for the same date. It should not rewrite older reports unless explicitly requested.

If no meaningful updates are found, the report should still be created with a clear "暂无重大变化" conclusion and include the exact searches or sources checked.

## Risks

- Some official pages may not expose RSS feeds, so web search results and direct documentation checks are both needed.
- Media reports can repeat old announcements. The report must compare publication dates and event dates.
- API capability language can be ambiguous. The report should distinguish confirmed API behavior from inferred product direction.

## Success Criteria

- A Markdown report appears under `reports/` every day after the automation runs.
- Each report includes source links and confidence labels.
- Reports explicitly track whether WeCom is moving toward AI/Agent-driven message sending or broader conversation-write APIs.
- Generated reports are committed and pushed to `origin/main`.
