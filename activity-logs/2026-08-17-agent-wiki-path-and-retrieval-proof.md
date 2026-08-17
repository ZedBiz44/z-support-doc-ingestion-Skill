Date: 2026-08-17 | Agent: Cody | Status: Complete

# Agent Wiki Path And Retrieval Proof Cleanup

Updated the support-doc-ingestion workflow to match the ZedBiz OpenClaw wiki setup and reduce redundant validation language.

## Changes

- Replaced vague "discover your own wiki" wording with the ZedBiz agent-specific documentation wiki convention: `/opt/openclaw/shared/knowledge/<agent-name>/wiki`.
- Clarified that the agent-specific documentation wiki path remains the support-doc target even when the default OpenClaw wiki status points to the shared wiki.
- Replaced agent-created practical questions with retrieval proof: search saved content, open at least one saved source or synthesis file, and report the search phrase, files found, and gaps.
- Removed research-agent GitHub responsibility from active workflow language.
- Updated the Notion SOP and Skill pages to remove the GitHub test-result contradiction and make back-office tracking records required only when tracking is being used.

## Reason

The live Wilma check showed `openclaw wiki status` points to `/opt/openclaw/shared/knowledge/wiki`, the shared wiki. Support documentation ingestion needs the agent-specific documentation wiki path instead.
