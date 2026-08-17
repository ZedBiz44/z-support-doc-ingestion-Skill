---
name: z-support-doc-ingestion
description: Research or refresh official support docs, save reliable knowledge in the active shared wiki, and validate practical answers.
---

# Support Doc Ingestion

## Your Job

Use this skill when you are asked to learn a tool, platform, program, plugin, API, or workflow from its support documentation.

Research the official documentation, save useful knowledge in the **active ZedBiz shared wiki** under your agent-owned namespace, prove the running agent can retrieve it, and return a concise completion summary. GitHub tracking and administrative records belong to a coordinator, automation, or administrator, not the research agent.

## What a Normal Assignment Looks Like

> Go through the official support documentation for [tool] and become our in-house expert. Save the useful knowledge in the shared knowledge wiki under your agent namespace and let me know when the saved documentation is findable and usable.

An official documentation link may be included. Find it when absent. Ask only when the product, source, access, or scope is unclear.

## Core Rules

- Save reusable public vendor documentation in the **active shared wiki vault**: `/opt/openclaw/shared/knowledge/wiki`.
- Keep ownership by using the supported content-type namespace: `sources/<agent>/`, `entities/<agent>/`, `concepts/<agent>/`, `syntheses/<agent>/`, and `reports/<agent>/`.
- Do **not** use an arbitrary root folder such as `wiki/<agent>/`; the compiler does not index it.
- Add `primaryAgent`, `owner`, and `scope: specialist-support-docs` to every support-documentation page.
- Use flat, tool-prefixed filenames inside the agent namespace, such as `entities/wilma/wpspectra_product_and_plugin_family.md`.
- Check Context7 first when available. Official documentation remains authoritative.
- Keep source links, warnings, limits, authentication details, version notes, and deprecation notices.
- Keep public reusable vendor documentation in the shared vault. Keep private client, paid, login-gated, or sensitive material in an approved restricted store.
- Report completion only after active-vault compile, lint, live runtime search, and retrieval proof pass.

## Where Knowledge Goes

| Section | Destination pattern | Use it for |
|---|---|---|
| Sources | `sources/<agent>/` | Source-backed documentation and captured pages |
| Entities | `entities/<agent>/` | Durable pages about a tool, product, API, or plugin |
| Concepts | `concepts/<agent>/` | Reusable rules, limits, gotchas, and patterns |
| Syntheses | `syntheses/<agent>/` | Practical how-to guides and working summaries |
| Reports | `reports/<agent>/` | Coverage and research reports |
| Attachments | `_attachments/<agent>/` when required | Supporting files and converted assets |

The Memory Wiki compiler recursively discovers pages inside these standard sections. Do not invent another top-level content tree.

## Research Workflow

### Learn the Documentation

Check Context7 first when available. Then find the official documentation home, navigation, sitemap, API references, guides, troubleshooting material, changelog, release notes, and downloadable manuals.

Use at least two discovery methods when practical. Use supplementary PDFs, blogs, community discussions, and videos only when they add value. Label supplemental material clearly and prefer official documentation when sources conflict.

### Save Useful Knowledge

Clean and organize useful content. Remove navigation clutter and repeated marketing text. Keep one topic per file when practical.

Every page must include the approved wiki metadata plus provenance appropriate to its type. Include these ownership fields:

```yaml
primaryAgent: your-agent-name
owner: your-agent-name
scope: specialist-support-docs
```

For source-backed pages, also preserve source URL, source type, capture date, capture agent, product, version, and status.

### Validate Through the Live Runtime

First confirm that `openclaw wiki status` reports the active shared vault:

```text
/opt/openclaw/shared/knowledge/wiki
```

Run the applicable checks in the assigned agent’s live runtime:

```bash
openclaw wiki status
openclaw wiki doctor
openclaw wiki compile
openclaw wiki lint
openclaw wiki search "relevant tool question" --mode source-evidence
```

A direct file search, a compile run from a different folder, or a personal folder that is not the active runtime vault is **not** retrieval proof. Search must return a saved page from the agent namespace in the active shared vault. Open at least one returned source or synthesis page and record the search phrase, paths found, and known gaps.

### Return the Completion Summary

Report:

- The tool or support area researched.
- What was learned and the shared-vault namespace used.
- Confirmation that compile, lint, live search, and retrieval proof passed.
- The search phrase, returned paths, and at least one opened saved page.
- Important gaps, blocked pages, or limits, or a clear statement that none are known.
- Whether the result is complete or partial.

If a major documentation section was skipped, report the work as **partial**.

## Reuse and Transfers

Public reusable support documentation in the shared vault is already available to authorized agents. Reuse it through live search; do not copy it between agents on the same VPS.

Use a coordinator-approved transfer only when documentation must move to another VPS or an approved restricted store. Transfer the full related bundle, exclude `.openclaw-wiki/cache/`, and validate the receiving active vault with compile, lint, live search, and retrieval proof.

## When to Stop and Ask

Stop and ask when:

- The product, official source, or research scope is unclear.
- Documentation is login-gated, paid, private, client-sensitive, or access-restricted.
- The content needs a restricted store rather than the shared vault.
- The active vault is not the shared wiki or the agent namespace cannot be confirmed.
- Coverage cannot be reasonably established.
- Compile, lint, or live search fails.
- Supplemental sources conflict with official documentation and the correct answer is unclear.

## Back-Office Tracking

The optional tracking repository is [`ZedBiz44/z-support-doc-ingestion-Skill`](https://github.com/ZedBiz44/z-support-doc-ingestion-Skill). It is maintained after the research summary by a coordinator, automation, or administrator. It is not a research-agent task.

## References

- OpenClaw Skills: https://docs.openclaw.ai/tools/skills
- OpenClaw Wiki CLI: https://docs.openclaw.ai/cli/wiki
- OpenClaw Memory Wiki: https://docs.openclaw.ai/plugins/memory-wiki
- Context7: https://context7.com/docs/overview
