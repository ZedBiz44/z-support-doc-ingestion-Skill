---
name: support-doc-ingestion
description: Research tool documentation, prove coverage, store results in the correct OpenClaw agent wiki, transfer docs between agent wikis when requested, and log the work in GitHub.
---

# Support Doc Ingestion

Use this skill when assigned a documentation research, ingestion, refresh, transfer, or verification task for any tool, platform, program, plugin, API, or workflow.

This skill is for ZedBiz documentation research and OpenClaw `memory-wiki` ingestion. It keeps finished documentation in individual agent wiki areas and uses GitHub only as the tracking and lookup layer.

## Core Rules

- Notion is not part of the documentation ingestion system.
- GitHub is the tracking log and lookup index, not the documentation warehouse.
- Finished documentation lives in the individual agent wiki area, not the shared main wiki.
- Use the OpenClaw `memory-wiki` folder layout inside each agent wiki.
- Use flat filenames with the exact tool name as the prefix.
- Do not mark work complete without coverage proof, GitHub tracking, compile/lint, search, and a real task-style test.
- Context7 is checked first for discovery speed; official docs remain the authority for final decisions.
- Do not transfer `.openclaw-wiki/cache/`; rebuild generated cache files in the receiving wiki.
- Pre-skill Agent Knowledge or ZedBiz Biz Brain planning belongs in `ZedBiz44/ZedBiz-Biz-Brain-System`; this repo is for the actual support-doc-ingestion skill package and tracking templates.

## Quick Reference

- Confirm the assignment and create the GitHub assignment record.
- Check Context7 for discovery, then build the official docs source inventory.
- Capture or scrape docs into clean Markdown, using manual curation as fallback.
- Build wiki entries in the correct individual agent wiki.
- Verify wiki context, then compile, lint, search, and run a real task-style test.
- Update the GitHub completed research record.
- Transfer documentation on request only after checking GitHub, then compile/lint/search/test in the receiving wiki.

## Agent Wiki Locations

Finished documentation should live in an individual agent wiki path such as:

```plain text
/opt/openclaw/shared/knowledge/wilma/wiki
/opt/openclaw/shared/knowledge/amanda/wiki
/opt/openclaw/shared/knowledge/inga/wiki
```

Each agent wiki should use this layout:

```plain text
agent-wiki-root/
  AGENTS.md
  WIKI.md
  index.md
  inbox.md
  sources/
  entities/
  concepts/
  syntheses/
  reports/
  _attachments/
  _views/
  .openclaw-wiki/
```

## File Naming Rule

Use a flat structure. Do not create nested tool folders inside the wiki sections.

Format:

```plain text
folder/toolname_topic.md
```

Examples:

- `entities/asana_goals.md`
- `entities/asana_tasks.md`
- `sources/asana_official_api.md`
- `concepts/asana_workflow_rules.md`
- `syntheses/asana_practical_guide.md`

## Source Priority

Use this priority order:

- Context7 first for discovery speed and developer/API examples.
- Official website docs for authority. Official docs are always required.
- PDFs and direct files for manuals, changelogs, release notes, and downloadable guides.
- Supplemental sources only when needed, such as YouTube, blogs, forums, GitHub issues, Stack Overflow, or release announcements.

The expected mix is roughly 70% website documentation, 20% Context7, and 10% PDFs or other files. Treat this as a planning target, not a rigid rule.

## GitHub Tracking

**Permanent live tracking repository:** [`ZedBiz44/z-support-doc-ingestion-Skill`](https://github.com/ZedBiz44/z-support-doc-ingestion-Skill).

Use this repository for the skill package and for all live assignment, completed-research, agent-wiki-index, transfer, refresh, and open-question records. Use `activity-logs/` only for maintenance history of this repository, not as a fallback for research-task tracking.

Required tracking structure:

```plain text
assignments/
completed-research/
agent-wiki-index/
transfer-log/
refresh-needed/
open-questions/
```

The assignment record must include:

- Tool name
- Version or product edition, when relevant
- Assigned research agent
- Target wiki path
- Other agents likely to need access later
- Primary source URLs
- Context7 library ID, if available
- Expected source mix
- Completion criteria
- Coverage checklist

When research is complete, create a completed research record with:

- Documentation title
- Researching agent
- Agent wiki path where the documentation lives
- Memory-wiki sections used
- Source coverage summary
- Context7 status
- PDF and supplemental source status
- Compile/lint/search results
- Real task-style test result
- Transfer history or `none`
- Refresh due date or review rule

Flag documentation older than 6 months for review. Any major tool version release triggers an immediate re-research assignment.

## Workflow

### Confirm The Assignment

- Identify the tool or program being researched.
- Identify the researching agent.
- Identify the target agent wiki path.
- Identify which other agents may need the documentation later.
- Create the GitHub assignment file before research begins.

### Build The Source Inventory

- Check Context7 first for discovery.
- Record the Context7 library ID and coverage quality.
- Find the official documentation home page.
- Check for sitemap, navigation tree, `llms.txt`, API reference, docs repo, changelog, and release notes.
- Build a complete source inventory before reading deeply.
- Record inaccessible, login-gated, paid, blocked, or unavailable sections.

### Prove Website Coverage

Use at least two discovery methods:

- Sitemap or `sitemap.xml`
- Docs sidebar or navigation tree
- Internal search
- GitHub docs repository tree
- `llms.txt`, when available
- Changelog and release note links

Record page counts by section, captured pages, excluded pages, and reasons for exclusion. Do not mark website research complete until coverage proof is recorded in GitHub.

### Use Context7

- Record the exact Context7 library ID used.
- Pull version-specific docs and code examples where available.
- Compare Context7 against the official docs.
- Flag mismatches, outdated examples, missing features, or version differences.
- Treat Context7 as a fast source lane, not the final authority.

### Process PDFs And Other Files

- Convert PDFs to clean Markdown where possible.
- Preserve title, author, source URL, publish date, version, and capture date.
- Mark extracted content lower-confidence if the PDF is old or version-unclear.

### Add Supplemental Research

Use supplemental sources only after official docs and Context7 have been checked.

Good supplemental sources include:

- YouTube walkthroughs
- Official blog posts
- GitHub issues and discussions
- Stack Overflow threads
- Release announcements
- Real-world implementation blogs

Label each supplemental source as `supplemental`. If supplemental content conflicts with official docs, official docs win unless there is strong evidence they are outdated.

## Build Wiki Entries

Add cleaned documentation into the correct individual agent wiki path.

Use wiki sections this way:

- `sources/`: source-backed pages and captured documentation
- `entities/`: durable tool, product, API, plugin, account, or platform pages
- `concepts/`: reusable ideas, rules, gotchas, and implementation patterns
- `syntheses/`: practical operator guides and summaries
- `reports/`: generated coverage, audit, or research reports
- `_attachments/`: supporting files or converted assets

Do not invent random top-level folders inside the agent wiki.

## Frontmatter

Every source or synthesis page should include frontmatter.

```yaml
---
title: "Page Title"
source_url: https://example.com/source-page
source_type: official-web | context7 | pdf | supplemental
source_priority: primary | secondary | supplemental
captured_at: 2026-08-17
captured_by: Wilma
product: Tool Name
version: latest
status: draft | review | verified | partial | stale | deprecated
agent_wiki: /opt/openclaw/shared/knowledge/wilma/wiki
target_agents:
  - wilma
  - inga
tags:
  - documentation
  - tool-research
---
```

Remove navigation clutter, duplicate footer text, cookie banners, ads, and unrelated marketing copy. Preserve source links, warnings, limits, authentication details, version notes, and deprecation notices.

## Ingestion Options

Default path:

- Use Firecrawl, Apify, Jina Reader, or another approved scraper to pull full documentation sites into clean Markdown.
- Save files with provenance frontmatter.
- Run `openclaw wiki ingest <file-or-supported-path> --json`.
- If directory or glob ingestion is not verified on the target host, ingest one file at a time.
- Verify exact ingest syntax with `openclaw wiki --help` or current OpenClaw docs before bulk jobs.
- Run `openclaw wiki compile`.
- Verify with `openclaw wiki search "query" --mode source-evidence`.

Fallback path:

- Manually export or copy content into clean Markdown.
- Add frontmatter.
- Place files in the appropriate wiki section.
- Compile, lint, search, and test in the receiving agent wiki.

## Verify Wiki Context

Before running `openclaw wiki` commands, confirm the active shell or service context points to the target agent wiki.

Record in GitHub:

- Target agent name
- Target wiki path
- Working directory used for the command
- Relevant runtime variables when applicable: `HOME`, `OPENCLAW_CONFIG_PATH`, `OPENCLAW_STATE_DIR`
- `openclaw wiki status` output summary showing the expected wiki or vault context

Do not treat `compile` or `lint` as valid if the command ran against the wrong agent wiki.

Passing check example:

```plain text
Target agent: Wilma
Expected wiki: /opt/openclaw/shared/knowledge/wilma/wiki
Working directory: /opt/openclaw/shared/knowledge/wilma/wiki
HOME: /root/.openclaw-wilma
OPENCLAW_CONFIG_PATH: /opt/openclaw-wilma/openclaw.json
OPENCLAW_STATE_DIR: /root/.openclaw-wilma
openclaw wiki status: vault=/opt/openclaw/shared/knowledge/wilma/wiki, status=ok
Decision: PASS - safe to compile/lint Wilma's wiki.
```

Failing check example:

```plain text
Target agent: Inga
Expected wiki: /opt/openclaw/shared/knowledge/inga/wiki
Working directory: /opt/openclaw/shared/knowledge/wilma/wiki
HOME: /root/.openclaw-wilma
OPENCLAW_CONFIG_PATH: /opt/openclaw-wilma/openclaw.json
openclaw wiki status: vault=/opt/openclaw/shared/knowledge/wilma/wiki, status=ok
Decision: FAIL - this would compile Wilma's wiki, not Inga's. Stop and fix context before continuing.
```

## Compile And Test

Run wiki commands in the verified target agent wiki context.

```bash
openclaw wiki status
openclaw wiki doctor
openclaw wiki compile
openclaw wiki lint
```

Search for the ingested documentation.

```bash
openclaw wiki search "example tool authentication" --mode source-evidence
```

Ask the target agent a real task-style question:

```plain text
Using only your wiki, answer: [specific operational question about the tool].
```

The answer must cite or name a source file, avoid unsupported steps, and flag gaps or uncertainty. Record the test result in GitHub.

## Transfer Documentation To Another Agent

Before transfer, check GitHub to confirm the documentation already exists and locate the source wiki path.

Transfer the full linked bundle for the tool, not just one folder. Check all relevant locations:

- `sources/toolname_*`
- `entities/toolname_*`
- `concepts/toolname_*`
- `syntheses/toolname_*`
- `reports/toolname_*`
- `_attachments/toolname_*`

Do not transfer `.openclaw-wiki/cache/`; the receiving wiki rebuilds that during compile.

Same VPS transfer uses `cp -a`. Cross-VPS transfer uses `rsync -av --progress`.

After transfer:

- Compile the receiving agent wiki.
- Run lint in the receiving agent wiki.
- Run a search test in the receiving agent wiki.
- Ask the receiving agent a real task-style question.
- Record the transfer in GitHub.

Create a GitHub transfer record:

```plain text
transfer-log/YYYY-MM-DD-tool-name-source-agent-to-target-agent.md
```

The transfer record must include exact files or file patterns copied, source path, target path, method used, compile/lint/search results, receiving-agent task test, and open gaps or `none`.

## Completion Gate

Mark an assignment complete only when GitHub records:

- Assignment file created before research began
- Context7 checked and coverage noted
- Website documentation coverage proof with page inventory
- Agent wiki path where documentation lives
- Wiki command context verified before compile/lint
- Compile/lint result
- Real task-style test passed
- Transfer history or explicit `none`
- Receiving-agent search/test passed after any transfer
- Refresh rule or review date

If any major documentation section was skipped, mark the assignment `partial`, not complete.

## When To Stop And Ask

Stop and ask for confirmation when:

- The task is in Diagnose Mode and action has not been approved.
- Source documentation is login-gated, paid, private, or client-sensitive.
- Transfer would mix private client docs into another agent wiki.
- You cannot verify the target wiki context.
- You cannot prove coverage after reasonable source discovery.
- Compile or lint fails in a way that may require structural wiki changes.
- Supplemental sources conflict with official docs and the right answer is unclear.

## Deployment Notes

- Create a folder named `support-doc-ingestion` under the target workspace `skills/` directory.
- Save this file as `SKILL.md` in that folder.
- Run `openclaw skills list` to confirm the skill is visible.
- If it does not appear, restart the session or gateway so OpenClaw refreshes the available skill list.

## Usage Notes

- Invoke directly with `$support-doc-ingestion` when skill references are available.
- Natural-language triggers include documentation ingestion, tool documentation research, docs refresh, wiki transfer, and support documentation verification.
- In Diagnose Mode, use the skill to inspect and propose; wait for confirmation before changing files or transferring wiki entries.
- In Get-er-Done Mode, use the skill to execute, verify, and log the completed work.

## References

- OpenClaw Skills: https://docs.openclaw.ai/tools/skills
- OpenClaw Creating Skills: https://docs.openclaw.ai/tools/creating-skills
- OpenClaw Wiki CLI: https://docs.openclaw.ai/cli/wiki
- OpenClaw Memory Wiki: https://docs.openclaw.ai/plugins/memory-wiki
- OpenClaw Memory Overview: https://docs.openclaw.ai/concepts/memory
- Context7 Overview: https://context7.com/docs/overview
- Context7 API Guide: https://context7.com/docs/api-guide
