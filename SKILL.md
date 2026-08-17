---
name: z-support-doc-ingestion
description: Research or refresh official support docs, save reliable knowledge in an agent wiki, and validate practical answers.
---

# Support Doc Ingestion

## Your Job

Use this skill when you are asked to learn a tool, platform, program, plugin, API, or workflow from its support documentation.

Your job is simple: research the official documentation, save useful knowledge in **your own wiki**, make sure you can retrieve it, and report back when you can answer practical questions about the tool.

You do **not** need GitHub access. You do not need to create an assignment record. You do not need to know another agent’s wiki path unless a coordinator specifically asks you to transfer documentation.

## What a Normal Assignment Looks Like

A task owner may say:

> Go through the official support documentation for [tool] and become our in-house expert. Save the useful knowledge in your own wiki and let me know when you can answer practical questions about it.

An official documentation link may be included. If it is not, find the official documentation yourself. Ask for clarification only when the product, source, or intended scope is unclear.

## Core Rules

- Save finished documentation in your own agent wiki, not the shared main wiki.
- Discover your configured wiki location from your operating context. Do not ask Jack to provide it.
- Use flat, tool-prefixed filenames such as `entities/toolname_feature.md`.
- Check Context7 first for fast discovery when it is available. Official documentation remains the authority.
- Keep source links, warnings, limits, authentication details, version notes, and deprecation notices.
- Do not copy `.openclaw-wiki/cache/` between wikis.
- Do not claim completion until your wiki passes compile, lint, search, and a practical self-test.
- Do not use GitHub as part of this research task. A coordinator or automation may track the result later.

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

Do not create nested tool folders. Use the tool name at the start of every filename.

## Research Workflow

### Learn the Documentation

Check Context7 first when available. Then find the official documentation home, navigation, sitemap, API references, guides, troubleshooting material, changelog, release notes, and downloadable manuals.

Use at least two ways to discover documentation sections, such as a sitemap, documentation navigation, internal search, or the documentation repository. Do not assume the top page is the full product documentation.

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

First confirm that the current command context points to your own wiki. If it does not, stop and correct the context before continuing.

Run the applicable wiki checks:

```bash
openclaw wiki status
openclaw wiki doctor
openclaw wiki compile
openclaw wiki lint
openclaw wiki search "relevant tool question" --mode source-evidence
```

Then create one practical question a real user would ask about the tool. Answer it using only your wiki. Your answer must identify a source file, avoid invented steps, and state any gaps or uncertainty.

## Your Completion Summary

When complete, return a short plain-English summary containing:

- What tool or support area you researched.
- What you learned and where you saved it in your wiki.
- Confirmation that compile, lint, search, and the practical self-test passed.
- Important gaps, blocked pages, or limits, or a clear statement that there are no known gaps.

If a major documentation section was skipped, report the work as **partial**, not complete.

## Transfers

Only transfer documentation when a coordinator specifically asks. The coordinator supplies the source agent and the receiving agent.

Transfer the full relevant bundle, checking `sources/`, `entities/`, `concepts/`, `syntheses/`, `reports/`, and `_attachments/`. On the same VPS, use `cp -a`. Across VPSs, use `rsync` over SSH. Never copy `.openclaw-wiki/cache/`.

After a transfer, validate the receiving wiki with compile, lint, search, and a practical self-test. Send the coordinator a short transfer summary.

## When to Stop and Ask

Stop and ask for clarification when:

- The product, official source, or research scope is unclear.
- Documentation is login-gated, paid, private, client-sensitive, or access-restricted.
- A transfer might mix private content into another agent’s wiki.
- You cannot verify your own wiki context.
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
