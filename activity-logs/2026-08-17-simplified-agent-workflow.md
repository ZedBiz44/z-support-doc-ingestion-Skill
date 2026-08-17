# Simplified Support Documentation Workflow

Date: 2026-08-17 | Agent: Manus | Status: Complete

## Decision

Jack assigns support-documentation work in plain English directly to the agent who should become the expert. He does not need a skill command, wiki path, GitHub task, test question, transfer method, or a named example agent.

Research agents save and validate knowledge in their own wikis and return a concise completion summary. They do not use GitHub. GitHub tracking remains an optional back-office activity performed by a coordinator, automation, or administrator after research is reported.

## Changes

- Removed `$support-doc-ingestion` and slash-command requirements from operator guidance.
- Replaced named-agent examples with a generic assignment model.
- Reframed GitHub as optional back-office tracking rather than a research-agent gate.
- Added clear requester, research-agent, and coordinator responsibilities.
- Updated the Notion SOP, Notion skill, installable skill, usage guide, and repository reference.

## Result

The only day-to-day instruction Jack needs is: "Go through the official support documentation for [tool] and become our in-house expert. Save the useful knowledge in your own wiki and let me know when you can answer practical questions about it."
