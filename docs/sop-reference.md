# Support Doc Ingestion SOP Reference

Date: 2026-08-17 | Agent: Cody | Status: Repo Reference Copy

## Purpose

This SOP explains how ZedBiz agents research tool documentation, prove source coverage, store finished documentation in the correct agent wiki, and log the work so other agents can find or request it later.

Notion is not part of the documentation ingestion system. GitHub is the tracking log and lookup index, not the documentation warehouse.

## Business Rule

The goal is to make the right agent capable of using the right tool with fewer mistakes, fewer hallucinated steps, and less human babysitting. If an agent already documented a tool, others should not redo the work. GitHub tracks where documentation lives so it can be transferred when needed. An assignment is not complete until coverage is proven, GitHub is updated, and a real task-style test passes.

## Quick Reference

- Confirm the assignment and create the GitHub assignment record.
- Check Context7 for discovery, then build the official docs source inventory.
- Capture or scrape docs into clean Markdown, using manual curation as fallback.
- Build wiki entries in the correct individual agent wiki.
- Verify wiki context, then compile, lint, search, and run a real task-style test.
- Update the GitHub completed research record.
- Transfer documentation on request only after checking GitHub, then compile/lint/search/test in the receiving wiki.

## Core Architecture

Finished documentation lives in individual agent wiki areas, not the shared main wiki.

```plain text
/opt/openclaw/shared/knowledge/wilma/wiki
/opt/openclaw/shared/knowledge/amanda/wiki
/opt/openclaw/shared/knowledge/inga/wiki
```

Use the standard OpenClaw `memory-wiki` folder layout inside each agent wiki.

```plain text
<agent-wiki>/
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

Use a flat file naming convention with the exact tool name prefix:

```plain text
{folder}/{toolname}_{topic}.md
```

Examples:

- `entities/asana_goals.md`
- `sources/asana_official_api.md`
- `concepts/asana_workflow_rules.md`
- `syntheses/asana_practical_guide.md`

## Source Mix And Priority

Check sources in this order:

- Context7 first for speed and discovery.
- Official website docs second and always as the authority.
- PDFs and direct files third.
- Supplemental sources fourth when needed.

The expected mix is roughly 70% website documentation, 20% Context7, and 10% PDFs or other files. Treat this as a planning target, not a rigid rule.

## GitHub Tracking Model

GitHub answers questions like:

- Did anyone document this tool?
- Which agent did the research?
- Which wiki path contains the documentation?
- Which agents have received a copy?
- When was it last refreshed?

Recommended tracking structure:

```plain text
assignments/
completed-research/
agent-wiki-index/
transfer-log/
refresh-needed/
open-questions/
```

### Required Assignment File

Create one assignment file before research begins.

```plain text
assignments/YYYY-MM-DD-tool-name-agent-name.md
```

Must include tool name, version if relevant, assigned agent, target wiki path, likely future agent users, primary source URLs, Context7 library ID if available, expected source mix, completion criteria, and coverage checklist.

### Required Completed Research Record

Create one record per completed batch.

```plain text
completed-research/tool-name/YYYY-MM-DD-agent-name.md
```

Must include documentation title, researching agent, agent wiki path, memory-wiki sections used, source coverage summary, Context7 status, PDF/supplemental status, compile/lint/search results, real task test result, transfer history, and refresh due date.

Refresh rule: flag documentation older than 6 months for review. Any major tool version release triggers an immediate re-research assignment.

### Required Transfer Record

Create one transfer record whenever documentation is copied or synced from one agent wiki to another.

```plain text
transfer-log/YYYY-MM-DD-tool-name-source-agent-to-target-agent.md
```

Must include tool set transferred, source and target agent paths, exact files or file patterns copied, whether all six bundle locations were checked, transfer method, receiving wiki compile/lint/search results, receiving-agent task-style test, and open gaps or `none`.

## Ordered SOP

### Confirm The Assignment

- Identify the tool, researching agent, and target wiki path.
- Identify which other agents may need the documentation later.
- Create the GitHub assignment file before research begins.

### Build The Source Inventory

- Check Context7 first and record the library ID and coverage quality.
- Find the official documentation home page, sitemap, navigation tree, API reference, changelog, release notes, docs repo, and `llms.txt` when available.
- Build a complete source inventory before reading deeply.
- Log every major section, API reference, guide, troubleshooting page, and blocked section.

### Prove Website Documentation Coverage

Use at least two discovery methods, such as sitemap, docs sidebar, internal search, GitHub docs repo tree, `llms.txt`, or changelog links.

Record page counts by section, captured pages, and excluded pages with reasons. Do not mark website research complete until coverage proof is recorded in GitHub.

### Use Context7 As A Source Lane

- Record the exact Context7 library ID used.
- Pull version-specific docs and examples where available.
- Compare Context7 findings against official website docs.
- Flag mismatches, outdated examples, or version differences.
- Treat Context7 as fast discovery, not final authority.

### Process PDFs And Other Files

- Convert PDFs to clean Markdown where possible.
- Preserve title, author, source URL, publish date, version, and capture date.
- Mark extracted content lower-confidence if the PDF is old or version-unclear.

### Add Supplemental Research When Needed

Use YouTube, blogs, GitHub issues, Stack Overflow, forums, or release announcements only after official docs and Context7 have been checked. Label each supplemental source clearly. If supplemental content conflicts with official docs, official docs win unless there is strong evidence they are outdated.

### Build The Agent Wiki Entries

- Add cleaned documentation into the correct individual agent wiki path.
- Put source-backed pages in `sources/`, durable tool pages in `entities/`, reusable patterns in `concepts/`, practical operator guides in `syntheses/`, and reports in `reports/`.
- Keep filenames flat and prefixed with the exact tool name.
- Do not invent random top-level folders inside the agent wiki.

### Normalize Content

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

### Confirm Wiki Context Before Commands

Before running `openclaw wiki` commands, confirm the shell or service context points to the target agent wiki.

Record:

- Target agent name
- Target wiki path
- Working directory used for the command
- Relevant runtime variables when applicable: `HOME`, `OPENCLAW_CONFIG_PATH`, `OPENCLAW_STATE_DIR`
- `openclaw wiki status` output summary showing the expected wiki/vault context

Do not treat `compile` or `lint` as valid if the command ran against the wrong agent wiki.

### Compile And Test The Agent Wiki

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

Ask the target agent a real task-style question using only its wiki. Confirm the answer cites or names a source file, does not invent unsupported steps, and flags gaps or uncertainty. Record the test result in GitHub.

### Transfer Documentation To Another Agent

Check GitHub first to confirm the documentation already exists and locate the source wiki path.

Transfer the full linked bundle for the tool, not just one folder. Check all relevant locations:

- `sources/{toolname}_*`
- `entities/{toolname}_*`
- `concepts/{toolname}_*`
- `syntheses/{toolname}_*`
- `reports/{toolname}_*`
- `_attachments/{toolname}_*`

Do not transfer `.openclaw-wiki/cache/`; the receiving wiki rebuilds that during compile.

Same VPS transfer uses `cp -a`. Cross-VPS transfer uses `rsync -av --progress`.

After any transfer, run compile and lint in the receiving agent's verified context, then run a search test and a real task-style question. Record the transfer in GitHub.

## Completion Gate

Mark an assignment complete only when GitHub records:

- [ ] Assignment file created before research began
- [ ] Context7 checked and coverage noted
- [ ] Website documentation coverage proof with page inventory logged
- [ ] Agent wiki path where documentation lives
- [ ] Wiki command context verified before compile/lint
- [ ] Compile/lint result
- [ ] Real task-style test passed
- [ ] Transfer history or explicit `none`
- [ ] Receiving agent search/test passed after any transfer
- [ ] Refresh rule or review date

If any major documentation section was skipped, mark the assignment `partial`, not complete.

## When To Stop And Ask

Stop and ask for confirmation when:

- The task is in Diagnose Mode and action has not been approved.
- Source documentation is login-gated, paid, private, or client-sensitive.
- Transfer would mix private client docs into another agent wiki.
- The target wiki context cannot be verified.
- Coverage cannot be proven after reasonable source discovery.
- Compile or lint fails in a way that may require structural wiki changes.
- Supplemental sources conflict with official docs and the right answer is unclear.

## References

- OpenClaw Memory Wiki: https://docs.openclaw.ai/plugins/memory-wiki
- OpenClaw Wiki CLI: https://docs.openclaw.ai/cli/wiki
- OpenClaw Memory Overview: https://docs.openclaw.ai/concepts/memory
- Context7 Overview: https://context7.com/docs/overview
- Context7 API Guide: https://context7.com/docs/api-guide
