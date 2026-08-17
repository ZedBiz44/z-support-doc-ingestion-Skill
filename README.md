# Support Doc Ingestion Skill

Date: 2026-08-17 | Agent: Cody and Manus | Status: Shared-Vault Model

This repo is the version-controlled home for the `z-support-doc-ingestion` skill.

The skill helps ZedBiz/OpenClaw agents research tool and program documentation, prove coverage, save public reusable knowledge in the active shared wiki under an agent-owned namespace, and report completion without requiring research agents to use GitHub.

## Source Of Truth

The Notion [Support-Doc-Ingestion-SOP](https://app.notion.com/p/389a3e33d58180ea8188d1030c070075) is the operational source for assignment, approval, ownership, and completion. This repository is the technical source for `SKILL.md`, adapter metadata, deployable package, and validation evidence. `docs/sop-reference.md` is a concise operational reference.

## Repo Role

- This repo is the authoring and tracking source for the skill, usage notes, templates, setup records, and live documentation-research records.
- The generated deployable package is `dist/z-support-doc-ingestion/`; install that package, not the repository root.
- This repo is not the warehouse for every scraped documentation page.
- Public reusable vendor documentation belongs in the active shared wiki, organized under `sources/<agent>/`, `entities/<agent>/`, `concepts/<agent>/`, `syntheses/<agent>/`, and `reports/<agent>/`.
- Agent ownership is expressed through the supported namespace and page metadata: `primaryAgent`, `owner`, and `scope: specialist-support-docs`.
- Private, client-sensitive, paid, or login-gated material belongs in an approved restricted store, not the shared vault.
- Same-VPS reuse occurs through shared-vault search. Cross-VPS and restricted-store transfers remain a coordinator responsibility.
- Back-office tracking records in this repository tell coordinators who researched what, where it lives, what was transferred, and when it needs review. Research agents do not need GitHub access.
- Before a workflow becomes a real skill, related Agent Knowledge and ZedBiz Biz Brain planning belongs in `ZedBiz44/ZedBiz-Biz-Brain-System`.
- Once a workflow becomes this skill, this repo becomes the skill source of truth.

## Install Target

OpenClaw skills are discovered from configured skill roots when a `SKILL.md` file is present. The skill command name comes from the YAML frontmatter `name` field.

Typical install layout:

```plain text
<workspace>/skills/z-support-doc-ingestion/SKILL.md
```

The authoritative source files remain at the repository root. Build the minimal deployable package before installation:

```bash
scripts/build_package.sh
```

Then install:

```plain text
dist/z-support-doc-ingestion/
```

## Main Files

- `SKILL.md`: authoritative shared skill instructions.
- `agents/openai.yaml`: authoritative Codex/OpenAI interface metadata.
- `scripts/build_package.sh`: generates the minimal `dist/z-support-doc-ingestion/` deployable package.
- `docs/implementation-profile.md`: ownership, active-vault model, platform, approval, and completion-evidence record.
- `docs/security-rollback.md`: source boundaries, shared-vault controls, security review, rollback, and removal record.
- `docs/pilot-test-record.md`: current-artifact discovery, trigger-test, and pilot evidence.
- `docs/usage.md`: plain-English instructions for Jack and the research agent.
- `docs/sop-reference.md`: SOP reference copy aligned with the Notion SOP.
- `templates/assignment-record.md`: GitHub assignment record template.
- `templates/completed-research-record.md`: completed research record template.
- `templates/transfer-record.md`: documentation transfer record template.
- `templates/agent-wiki-index-record.md`: agent wiki ownership and location index template.
- `assignments/`, `completed-research/`, `agent-wiki-index/`, `transfer-log/`, `refresh-needed/`, and `open-questions/`: permanent live documentation-research tracking folders.
- `activity-logs/`: repo setup and change history notes, not research-task tracking.

## References

- OpenClaw Skills: https://docs.openclaw.ai/tools/skills
- OpenClaw Creating Skills: https://docs.openclaw.ai/tools/creating-skills
- OpenClaw Wiki CLI: https://docs.openclaw.ai/cli/wiki
- OpenClaw Memory Wiki: https://docs.openclaw.ai/plugins/memory-wiki
- Context7 Overview: https://context7.com/docs/overview
- Context7 API Guide: https://context7.com/docs/api-guide
