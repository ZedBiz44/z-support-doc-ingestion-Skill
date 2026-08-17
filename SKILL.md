---
name: z-support-doc-ingestion
description: Research or refresh official support docs, save reliable knowledge in an agent wiki, and validate practical answers.
---

# Support Doc Ingestion

## Your Job

Use this skill when you are asked to learn a tool, platform, program, plugin, API, or workflow from its support documentation.

Your job is simple: research the official documentation, save useful knowledge in **your own ZedBiz agent documentation wiki**, make sure you can retrieve it, and report back when the saved documentation is findable and usable.

GitHub tracking, assignment records, and other agents' wiki paths belong to the coordinator workflow. A normal research task only needs the tool scope, source documentation, agent-specific documentation wiki, validation, retrieval proof, and completion summary.

## What a Normal Assignment Looks Like

A task owner may say:

> Go through the official support documentation for [tool] and become our in-house expert. Save the useful knowledge in your agent documentation wiki and let me know when the saved documentation is findable and usable.

An official documentation link may be included. If it is not, find the official documentation yourself. Ask for clarification only when the product, source, or intended scope is unclear.

## Core Rules

- Save finished support documentation in the ZedBiz agent-specific documentation wiki path: `/opt/openclaw/shared/knowledge/<agent-name>/wiki`.
- Treat the ZedBiz agent-specific documentation wiki path as the support-doc target even when the default OpenClaw wiki status points to the shared wiki.
- Use flat, tool-prefixed filenames such as `entities/toolname_feature.md`.
- Check Context7 first for fast discovery when it is available. Official documentation remains the authority.
- Keep source links, warnings, limits, authentication details, version notes, and deprecation notices.
- Leave `.openclaw-wiki/cache/` out of wiki transfers.
- Report completion only after your wiki passes compile, lint, search, and retrieval proof.
- Keep GitHub tracking in the coordinator or automation lane after the research summary is reported.

## Where Knowledge Goes

Use the standard sections in your own wiki:

| Section | Use it for |
|---|---|
| `sources/` | Source-backed documentation and captured pages |
| `entities/` | Durable pages about the tool, product, API, or plugin |
| `concepts/` | Reusable rules, limits, gotchas, and patterns |
| `syntheses/` | Practical how-to guides and working summaries |
| `reports/` | Coverage or research reports |
| `_attachments/` | Supporting files and converted assets |

Use the tool name at the start of every filename and keep tool files flat inside the standard wiki sections.

## Research Workflow

### Learn the Documentation

Check Context7 first when available. Then find the official documentation home, navigation, sitemap, API references, guides, troubleshooting material, changelog, release notes, and downloadable manuals.

Use at least two ways to discover documentation sections, such as a sitemap, documentation navigation, internal search, or the documentation repository. Treat the top page as an entry point, then verify the full documentation structure.

Use PDFs, release notes, official blogs, community discussions, and videos only when they add something useful beyond official documentation. Label supplemental material clearly and use the official docs when sources conflict.

### Save Useful Knowledge

Clean and organize the useful content in your own wiki. Remove navigation clutter and repeated marketing text. Keep one topic per file where practical.

Every source or synthesis page should include provenance frontmatter similar to this:

```yaml
---
title: "Page Title"
source_url: https://example.com/source-page
source_type: official-web | context7 | pdf | supplemental
captured_at: YYYY-MM-DD
captured_by: your-agent-name
product: Tool Name
version: latest
status: verified | partial | stale
---
```

### Validate Your Wiki

First confirm that the files were saved in your ZedBiz agent-specific documentation wiki path:

```plain text
/opt/openclaw/shared/knowledge/<agent-name>/wiki
```

Treat this path as the support-doc target even when the default OpenClaw wiki status points to the shared wiki.

Run the applicable wiki checks:

```bash
openclaw wiki status
openclaw wiki doctor
openclaw wiki compile
openclaw wiki lint
openclaw wiki search "relevant tool question" --mode source-evidence
```

Then run a retrieval proof: search the saved wiki content for the tool, open at least one saved source or synthesis file, and confirm the documentation is findable and usable. Record the search phrase, files found, and any known gaps.

## Your Completion Summary

When complete, return a short plain-English summary containing:

- What tool or support area you researched.
- What you learned and where you saved it in your wiki.
- Confirmation that compile, lint, search, and retrieval proof passed.
- Retrieval proof details: search phrase used, files found, and any known gaps.
- Important gaps, blocked pages, or limits, or a clear statement that there are no known gaps.

If a major documentation section was skipped, report the work as **partial**.

## Transfers

Only transfer documentation when a coordinator specifically asks. The coordinator supplies the source agent and the receiving agent.

Transfer the full relevant bundle, checking `sources/`, `entities/`, `concepts/`, `syntheses/`, `reports/`, and `_attachments/`. On the same VPS, use `cp -a`. Across VPSs, use `rsync` over SSH. Leave `.openclaw-wiki/cache/` behind because the receiving wiki rebuilds it.

After a transfer, validate the receiving wiki with compile, lint, search, and retrieval proof. Send the coordinator a short transfer summary.

## When to Stop and Ask

Stop and ask for clarification when:

- The product, official source, or research scope is unclear.
- Documentation is login-gated, paid, private, client-sensitive, or access-restricted.
- A transfer might mix private content into another agent’s wiki.
- You cannot verify the ZedBiz agent-specific documentation wiki path.
- Coverage cannot be reasonably established.
- Compile or lint fails in a way that may require structural wiki changes.
- Supplemental sources conflict with official documentation and the correct answer is unclear.

## Back-Office Tracking

The optional tracking repository is [`ZedBiz44/z-support-doc-ingestion-Skill`](https://github.com/ZedBiz44/z-support-doc-ingestion-Skill). It is maintained by a coordinator, automation, or administrator after research is reported. It is not a task for research agents.

## References

- OpenClaw Skills: https://docs.openclaw.ai/tools/skills
- OpenClaw Wiki CLI: https://docs.openclaw.ai/cli/wiki
- OpenClaw Memory Wiki: https://docs.openclaw.ai/plugins/memory-wiki
- Context7: https://context7.com/docs/overview
