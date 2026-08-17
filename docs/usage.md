# Support Doc Ingestion Usage

Date: 2026-08-17 | Agent: Manus | Status: Simplified

## What You Do

Tell the agent who should become the expert:

> Go through the official support documentation for **[tool]** and become our in-house expert. Save the useful knowledge in your agent documentation wiki and let me know when the saved documentation is findable and usable.

That is all.

Use the same plain-English sentence directly with whichever agent should own the expertise. The skill command, wiki path, GitHub record, test question, transfer command, and named-agent examples are handled by the system or coordinator workflow when needed.

## What the Research Agent Does

The agent finds the official documentation, checks Context7 when useful, organizes useful knowledge in its ZedBiz agent-specific documentation wiki, validates that the knowledge is searchable, and proves it can retrieve the saved files. It then sends you a short summary of what it learned, where it saved it, the search phrase/files used for retrieval proof, and any meaningful gaps.

GitHub tracking sits in the coordinator lane, after the research agent reports completion.

## When Another Agent Needs Existing Knowledge

Tell a coordinator, manager agent, or administrator:

> Check whether any agent already has useful documentation for **[tool]**. If so, give **[target agent]** access to it instead of having them research it again.

The coordinator checks the tracking index when available and arranges the transfer. GitHub, source paths, `cp`, and `rsync` stay in the coordinator lane.

## What the Back Office Tracks

[`ZedBiz44/z-support-doc-ingestion-Skill`](https://github.com/ZedBiz44/z-support-doc-ingestion-Skill) is the optional back-office tracking repository. A coordinator, automation, or administrator may use it to record what was researched, who owns it, where it lives, transfers, refresh dates, and open questions.

It does not hold scraped documentation and it is not work that a research agent must perform.

## What a Good Completion Looks Like

A useful completion message is short:

> I researched **[tool]**, saved the useful documentation in my agent documentation wiki, and verified that I can find it again. Retrieval proof: searched **[phrase]** and found **[files]**. Known gaps: **[gaps or none]**.
