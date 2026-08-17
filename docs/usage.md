# Support Doc Ingestion Usage

Date: 2026-08-17 | Agent: Manus | Status: Simplified

## What You Do

Tell the agent who should become the expert:

> Go through the official support documentation for **[tool]** and become our in-house expert. Save the useful knowledge in your own wiki and let me know when you can answer practical questions about it.

That is all.

You do not need to use a special skill command, a slash command, a wiki path, a GitHub record, a special test question, or a transfer command. You also do not need to name Amanda, Wilma, Marsha, or any other example agent. Send the same sentence directly to whichever agent should own the expertise.

## What the Research Agent Does

The agent finds the official documentation, checks Context7 when useful, organizes useful knowledge in its own wiki, validates that the knowledge is searchable, and tests itself with a practical question. It then sends you a short summary of what it learned, where it saved it, and any meaningful gaps.

The research agent does not use GitHub for this workflow.

## When Another Agent Needs Existing Knowledge

Tell a coordinator, manager agent, or administrator:

> Check whether any agent already has useful documentation for **[tool]**. If so, give **[target agent]** access to it instead of having them research it again.

The coordinator checks the tracking index when available and arranges the transfer. The research agent does not need to know GitHub, source paths, `cp`, or `rsync` commands.

## What the Back Office Tracks

[`ZedBiz44/z-support-doc-ingestion-Skill`](https://github.com/ZedBiz44/z-support-doc-ingestion-Skill) is the optional back-office tracking repository. A coordinator, automation, or administrator may use it to record what was researched, who owns it, where it lives, transfers, refresh dates, and open questions.

It does not hold scraped documentation and it is not work that a research agent must perform.

## What a Good Completion Looks Like

A useful completion message is short:

> I researched **[tool]**, saved the useful documentation in my wiki, and verified that I can find and use it. I can now help with **[key capabilities]**. Known gaps: **[gaps or none]**.
