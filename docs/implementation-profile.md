# Skill Implementation Profile

Date: 2026-08-17 | Prepared by: Manus | Status: Pilot Pending

## Identity and Ownership

| Decision | Value |
|---|---|
| Skill display name | Z Support Doc Ingestion |
| Canonical skill identifier | `z-support-doc-ingestion` |
| Owner and publisher | ZedBiz |
| Repository | `ZedBiz44/z-support-doc-ingestion-Skill` |
| Authoritative branch | `main` |
| License or attribution decision | ZedBiz-authored internal skill. Vendor documentation remains with its original sources and attribution. |
| Naming exception | None. The deployable package directory must be `z-support-doc-ingestion`. |

## Purpose and Scope

| Decision | Value |
|---|---|
| Primary job | Research official support documentation, save source-backed knowledge in the active shared wiki under an agent-owned namespace, and prove live retrieval. |
| Active wiki vault | Runtime-configured shared wiki vault reported by `openclaw wiki status`; common examples are `/opt/openclaw/shared/knowledge/wiki` and Rocky/VPS4's `/home/openclaw/.openclaw/workspace/shared-memory-wiki`. |
| Agent-owned namespace | `sources/<agent>/`, `entities/<agent>/`, `concepts/<agent>/`, `syntheses/<agent>/`, `reports/<agent>/`, and `_attachments/<agent>/` when needed. |
| Ownership metadata | `primaryAgent`, `owner`, and `scope: specialist-support-docs` on every support-documentation page. |
| Intended users | ZedBiz OpenClaw agents performing assigned support-documentation research. |
| Positive triggers | Learn, research, refresh, verify, or reuse support documentation for a tool, platform, plugin, API, or workflow. |
| Non-triggers | One-off operational work, a request to use a tool without researching it, unrelated document editing, or private-content ingestion without approval. |
| Included actions | Public documentation research, wiki entry creation, live retrieval proof, and coordinator-approved cross-VPS or restricted-store transfer. |
| Excluded actions | Login-gated or private content without approval, credentials, client-sensitive materials, plugin/service development, and production system changes. |

## Platforms and Packaging

| Decision | Value |
|---|---|
| Supported platforms | OpenClaw pilot. OpenAI/Codex interface metadata is included for compatible discovery. |
| Authoring source | Repository root `SKILL.md` and `agents/openai.yaml`. |
| Deployable package | `dist/z-support-doc-ingestion/`, built from the current source commit. |
| Required adapters | OpenClaw skill discovery and `agents/openai.yaml`. |
| Target installation | Confirm exact agent skills root during pilot. Do not install the authoring repository root. |
| Validators | `z-ai-skill-developer/scripts/validate_skill.py`, relevant platform checks, fresh-session discovery, and pilot trigger tests. |

## Controls and Approval

| Decision | Value |
|---|---|
| Default operating mode | Follow the assigned task mode. Diagnose Mode requires confirmation before changes. |
| Human approver | Jack |
| Pilot environment | One approved OpenClaw agent, initially Wilma only if the target state is confirmed current. |
| Wider rollout | Only after the current commit passes discovery, trigger, pilot, and rollback checks and Jack approves expansion. |
| Stop and escalation | Stop for unresolved source scope, access, private content, active-vault mismatch, structural wiki failure, or source conflict. |
| Retry limit | Three failed validation or repair attempts unless Jack sets a lower limit. |

## Security and Rollback

| Decision | Value |
|---|---|
| Security review | `docs/security-rollback.md` |
| Approved data and sources | Public official documentation, Context7, approved supplemental public sources, and approved local wiki content. |
| Execution boundary | The active shared wiki’s supported agent namespaces and coordinator-supplied cross-VPS or restricted-store transfer targets. |
| Last known-good commit | To be established by the first successful fresh pilot of the `z-support-doc-ingestion` package. |
| Rollback owner | Jack or designated technical administrator. |
| Rollback procedure | Remove or replace only the pilot package at its verified skills-root location, refresh the agent’s skill list or session, and preserve the authoring repository and evidence. Wiki migrations retain a verified backup until live retrieval succeeds. |

## Completion Evidence

| Evidence | Required record |
|---|---|
| Structural validation | `docs/validation-record.md` |
| Platform discovery and trigger testing | `docs/pilot-test-record.md` |
| Pilot result | `docs/pilot-test-record.md` |
| Security and rollback approval | `docs/security-rollback.md` |
| Source commit | Git commit and release record, if created |
| Operational summary | Notion Support-Doc-Ingestion-SOP and daily Technical Journal |
| Approval | Jack’s recorded pilot or rollout decision |
