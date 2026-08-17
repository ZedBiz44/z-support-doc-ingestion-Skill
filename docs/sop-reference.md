# Support Doc Ingestion SOP Reference

Date: 2026-08-17 | Agent: Manus | Status: Simplified Reference

> **Canonical source:** The Notion [Support-Doc-Ingestion-SOP](https://app.notion.com/p/389a3e33d58180ea8188d1030c070075) is the authoritative operating procedure. This file is a concise implementation reference. If the two differ, the Notion SOP controls.

## Purpose

The goal is to make one chosen agent the reliable in-house expert for a tool, platform, plugin, API, or program. Useful documentation is saved in that agent’s own wiki, not in the shared main wiki or GitHub.

## Roles

| Role | Responsibility |
|---|---|
| Jack or task owner | Gives a plain-English instruction directly to the agent who should become the expert. |
| Research agent | Researches, saves useful knowledge in its ZedBiz agent-specific documentation wiki, validates it, and returns a concise completion summary. It does not use GitHub. |
| Coordinator, automation, or administrator | Optional back-office role that maintains the tracking index and coordinates reuse or transfers. |

## Simple Assignment

> Go through the official support documentation for [tool] and become our in-house expert. Save the useful knowledge in your agent documentation wiki and let me know when the saved documentation is findable and usable.

Jack does not need to provide a wiki path, skill command, GitHub task, test question, or transfer method.

## Research Agent Workflow

- Check Context7 when useful, then use official documentation as the authority.
- Discover the official documentation structure and cover meaningful product sections.
- Save useful, source-backed knowledge in the agent-specific documentation wiki path: `/opt/openclaw/shared/knowledge/<agent-name>/wiki`.
- Treat the agent-specific documentation wiki path as the support-doc target even when the default OpenClaw wiki status points to the shared wiki.
- Run compile, lint, a relevant search, and retrieval proof against the saved support documentation.
- Return what was learned, where it was saved, validation result, and any meaningful gaps.

## Documentation Reuse

When another agent needs an existing tool’s knowledge, Jack asks a coordinator whether anyone already knows it. The coordinator checks the tracking index if available and arranges a transfer rather than duplicate research.

Same-VPS transfers use `cp -a`; cross-VPS transfers use `rsync` over SSH. The transfer excludes `.openclaw-wiki/cache/` and is validated in the receiving wiki.

## Back-Office Tracking

The permanent optional tracking repository is [`ZedBiz44/z-support-doc-ingestion-Skill`](https://github.com/ZedBiz44/z-support-doc-ingestion-Skill). It records assignment, completed-research, agent-wiki-index, transfer, refresh, and open-question information after research is reported. It is not a research-agent responsibility.
