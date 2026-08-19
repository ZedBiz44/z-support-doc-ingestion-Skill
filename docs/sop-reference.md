# Support Doc Ingestion SOP Reference

Date: 2026-08-17 | Agent: Manus | Status: Shared-Vault Reference

> **Authority split:** The Notion [Support-Doc-Ingestion-SOP](https://app.notion.com/p/389a3e33d58180ea8188d1030c070075) is the operational source for assignment, approval, ownership, and completion. This repository is the technical source for skill instructions, metadata, generated package, and validation evidence. This file is a concise operational reference.

## Purpose

Make one chosen agent the reliable in-house expert for a tool, platform, plugin, API, or program without splitting its live retrieval from shared ZedBiz knowledge. Reusable public vendor documentation belongs in the active shared wiki under the research agent’s supported namespace, not in GitHub or a second unsearchable vault.

## Roles

| Role | Responsibility |
|---|---|
| Jack or task owner | Gives a plain-English research instruction to the agent who should become the expert. |
| Research agent | Researches, saves source-backed knowledge in its shared-vault namespace, validates live retrieval, and returns a concise completion summary. It does not use GitHub. |
| Coordinator, automation, or administrator | Maintains optional tracking and handles approved cross-VPS or restricted-store transfers. |

## Simple Assignment

> Go through the official support documentation for [tool] and become our in-house expert. Save the useful knowledge in the shared knowledge wiki under your agent namespace and let me know when the saved documentation is findable and usable.

Jack does not need to provide a wiki path, skill command, GitHub task, test question, or transfer method.

## Research Agent Workflow

- Check Context7 when useful, then use official documentation as the authority.
- Discover the official documentation structure and cover meaningful product sections.
- Save public reusable knowledge under the runtime-configured active shared vault reported by `openclaw wiki status`.
- Valid active shared vaults may differ by host; Rocky/VPS4 uses `/home/openclaw/.openclaw/workspace/shared-memory-wiki`.
- Use only supported paths: `sources/<agent>/`, `entities/<agent>/`, `concepts/<agent>/`, `syntheses/<agent>/`, and `reports/<agent>/`.
- Add `primaryAgent`, `owner`, and `scope: specialist-support-docs` to every support-documentation page.
- Use the standard content-type folders instead of root-level agent folders such as `wiki/<agent>/`, which sit outside the Memory Wiki compiler's scanned structure.
- Run compile, lint, and a practical `openclaw wiki search` from the assigned agent’s live runtime. The result must return a page in that agent’s namespace.
- Return what was learned, the namespace used, proof paths, validation result, and meaningful gaps.

## Documentation Reuse

Public vendor documentation in the shared active vault is already searchable by authorized agents. Reuse it through live search instead of copying files between agents on the same VPS.

Use approved transfer only for another VPS or a restricted private store. Exclude `.openclaw-wiki/cache/` and validate the destination’s active runtime.

## Skill Governance and Deployment

The ZedBiz-owned identifier is `z-support-doc-ingestion`. Build `dist/z-support-doc-ingestion/` from the repository source and install only that generated package on a pilot agent. Maintain `docs/implementation-profile.md`, `docs/security-rollback.md`, and `docs/pilot-test-record.md` before wider rollout.

## Back-Office Tracking

The permanent optional tracking repository is [`ZedBiz44/z-support-doc-ingestion-Skill`](https://github.com/ZedBiz44/z-support-doc-ingestion-Skill). It records assignment, completed-research, agent-wiki-index, transfer, refresh, and open-question information after research is reported. It is not a research-agent responsibility.
