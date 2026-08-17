# Support Doc Ingestion Skill

Date: 2026-08-17 | Agent: Cody | Status: Initial repo setup

This repo is the version-controlled home for the `support-doc-ingestion` skill.

The skill helps ZedBiz/OpenClaw agents research tool and program documentation, prove coverage, store the finished documentation in the right individual agent wiki, and log the work so other agents can find or request it later.

## Source Of Truth

The canonical operating SOP is the Notion [Support-Doc-Ingestion-SOP](https://app.notion.com/p/389a3e33d58180ea8188d1030c070075). The repository file `docs/sop-reference.md` is a concise implementation reference only. If the two differ, the Notion SOP controls. Update the reference copy after an approved canonical SOP change.

## Repo Role

- This repo stores the actual skill package, usage notes, templates, setup records, and the live documentation-research tracking records.
- This repo is not the warehouse for every scraped documentation page.
- Finished documentation belongs in the researching agent’s individual wiki, following `/opt/openclaw/shared/knowledge/<agent-name>/wiki`.
- Back-office tracking records in this repository tell coordinators who researched what, where it lives, what was transferred, and when it needs review. Research agents do not need GitHub access.
- Before a workflow becomes a real skill, related Agent Knowledge and ZedBiz Biz Brain planning belongs in `ZedBiz44/ZedBiz-Biz-Brain-System`.
- Once a workflow becomes this skill, this repo becomes the skill source of truth.

## Install Target

OpenClaw skills are discovered from configured skill roots when a `SKILL.md` file is present. The skill command name comes from the YAML frontmatter `name` field.

Typical install layout:

```plain text
<workspace>/skills/support-doc-ingestion/SKILL.md
```

This repo keeps the installable skill at:

```plain text
SKILL.md
```

## Main Files

- `SKILL.md`: installable skill instructions.
- `agents/openai.yaml`: Codex/OpenAI interface metadata.
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
