# Support Doc Ingestion Usage

Date: 2026-08-17 | Agent: Cody | Status: Active

## What This Skill Does

Use this when you want an agent to make tool documentation usable inside an OpenClaw agent wiki.

Plain-English version: it makes sure the agent checks the whole documentation set, stores the finished notes in the right agent wiki, proves the docs are searchable, and logs enough in GitHub so nobody repeats the same work later.

## Live Tracking Repository

Use [`ZedBiz44/z-support-doc-ingestion-Skill`](https://github.com/ZedBiz44/z-support-doc-ingestion-Skill) as the permanent live tracking repository. Create assignments, completed-research records, agent-wiki index records, transfer records, refresh records, and open questions in its top-level tracking folders. Do not use `activity-logs/` for research-task tracking.

## Quick TLDR

- Pick the tool or program.
- Pick the researching agent.
- Pick the target agent wiki.
- Tell the agent to use `$support-doc-ingestion`.
- Require coverage proof before calling it done.
- Require a real task-style test before calling it usable.
- Check GitHub first before asking another agent to redo the same documentation.

## Prompt To Research New Documentation

```plain text
Use $support-doc-ingestion.

Research [tool/program/plugin name] documentation for [agent name].
Target wiki path: /opt/openclaw/shared/knowledge/[agent]/wiki
Primary official docs: [URL]
Check Context7 first if available.
Use official docs as authority.
Include PDFs or supplemental sources only if useful.
Create the GitHub assignment record first.
Do not mark complete until coverage is proven, wiki compile/lint/search passes, and the agent answers a real task-style question using its wiki.
```

## Prompt To Transfer Existing Documentation

```plain text
Use $support-doc-ingestion.

Check GitHub to see whether [source agent] already documented [tool/program/plugin name].
If yes, transfer the full documentation bundle from:
/opt/openclaw/shared/knowledge/[source-agent]/wiki

to:
/opt/openclaw/shared/knowledge/[target-agent]/wiki

Copy all relevant sources, entities, concepts, syntheses, reports, and attachments.
Do not copy .openclaw-wiki/cache/.
After transfer, verify target wiki context, compile, lint, search, and run one real task-style test from the target agent.
Record the transfer in GitHub.
```

## Prompt To Refresh Stale Documentation

```plain text
Use $support-doc-ingestion.

Refresh [tool/program/plugin name] documentation for [agent name].
Check the existing GitHub completed research record first.
Re-check Context7, official docs, changelog, release notes, PDFs, and important supplemental sources.
Update the individual agent wiki only after verifying what changed.
Record the refresh result and new review date in GitHub.
```

## What GitHub Should Track

GitHub should track:

- Tool researched
- Assigned agent
- Target wiki path
- Source inventory and coverage proof
- Context7 status
- Compile/lint/search/test results
- Transfer history
- Refresh due date
- Open questions or blocked sections

GitHub should not track:

- Full scraped documentation sites
- Private client docs
- Secrets or credentials
- Generated `.openclaw-wiki/cache/` files
- Whole agent wiki exports unless explicitly approved for backup work

## Example

If Wilma already documented the Meow Plugins and Inga needs the Meow SEO Engine docs, do not ask Inga to research from scratch.

Have Inga or Cody check GitHub, find Wilma's completed research record, transfer the matching `meow_*` files into Inga's wiki, then compile/lint/search/test in Inga's wiki context.

That is the main business win: fewer duplicated hours, fewer blind agents, and less Jack-as-human-router work.
