# Support Doc Ingestion Usage

Date: 2026-08-20 | Agent: Cody | Status: VPS1 Shared-Vault Model

## What You Do

Use this prompt only with a VPS1 shared-wiki OpenClaw agent that has the approved shared wiki active:

> Go through the official support documentation for **[tool]** and become our in-house expert. Save the useful knowledge in the shared knowledge wiki under your agent namespace and let me know when the saved documentation is findable and usable.

That is all.

Use `z-agent-knowledge-mapper` for VPS2 agents, VPS3/Hermes agents, Rocky/VPS4 agents, or any agent-local/custom wiki setup. The skill command, wiki path, GitHub record, test question, transfer command, and named-agent examples are handled by the system or coordinator workflow when needed.

## What the Research Agent Does

The agent finds the official documentation, checks Context7 when useful, saves source-backed knowledge in its supported namespace inside the approved VPS1 active shared wiki, and proves it can retrieve the saved pages through its live runtime. Its pages carry `primaryAgent`, `owner`, and `scope: specialist-support-docs` metadata.

The agent captures reusable building blocks: procedures, prerequisites, permissions, decision points, validation steps, failure conditions, manual fallbacks, UI friction, automation opportunities, and material prompts or configurations. It evaluates both the technical track and the human-operator track, but creates a finished guide or SOP only when that is part of the assignment.

The agent then sends a short summary of what it learned, its namespace, the search phrase and returned files, and meaningful gaps. GitHub tracking sits in the coordinator lane after the research agent reports completion.

## When Another Agent Needs Existing Knowledge

Tell a coordinator, manager agent, or administrator:

> Check whether the shared knowledge wiki already has useful documentation for **[tool]**. If it does, have **[target agent]** use that shared knowledge instead of repeating the research.

For public vendor documentation on the same VPS1 shared-wiki environment, no file transfer is needed. The target agent uses the active shared wiki search. GitHub, cross-VPS transfer, restricted-store transfer, `cp`, and `rsync` remain in the coordinator lane.

## What the Back Office Tracks

[`ZedBiz44/z-support-doc-ingestion-Skill`](https://github.com/ZedBiz44/z-support-doc-ingestion-Skill) is the optional back-office tracking repository. A coordinator, automation, or administrator may use it to record what was researched, ownership metadata, shared-vault namespace, cross-VPS or restricted transfers, refresh dates, and open questions.

It does not hold scraped documentation and it is not work that a research agent must perform.

## What a Good Completion Looks Like

A useful completion message is short:

> I researched **[tool]**, saved the useful documentation in **[section/agent namespace]** of the VPS1 shared knowledge wiki, and verified live retrieval. I searched **[phrase]** and found **[paths]**. Reusable building blocks captured: **[procedures/API/UI/validation/gotchas]**. Known gaps: **[gaps or none]**.
