# Live Tracking Repository and Canonical SOP Decision

Date: 2026-08-17 | Agent: Manus | Status: Complete

## Decision

`ZedBiz44/z-support-doc-ingestion-Skill` is the permanent live tracking repository for support-documentation research. It stores assignment, completed-research, agent-wiki-index, transfer, refresh, and open-question records.

The Notion [Support-Doc-Ingestion-SOP](https://app.notion.com/p/389a3e33d58180ea8188d1030c070075) is the canonical operating procedure. `docs/sop-reference.md` is a concise implementation reference only. If the two differ, the Notion SOP controls.

## Changes

- Added the six live tracking folders with usage guidance.
- Added an agent wiki index template.
- Updated the installable skill, repository instructions, README, operator usage guide, SOP reference, and validation record to reflect the decisions.
- Restricted `activity-logs/` to repository-maintenance history, not research-task tracking.

## Outstanding Verification

The skill still requires installation and `openclaw skills list` verification on one pilot OpenClaw agent before broader deployment.
