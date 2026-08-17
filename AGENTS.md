# Repository Operating Instructions

Date: 2026-08-17 | Agent: Cody | Status: Active

## Purpose

This repo is the technical source for the `z-support-doc-ingestion` skill package and the permanent back-office tracking repository for support-documentation research.

The Notion [Support-Doc-Ingestion-SOP](https://app.notion.com/p/389a3e33d58180ea8188d1030c070075) is the operational source for assignment, approval, ownership, and completion. This repository is the technical source for the skill, metadata, generated package, and validation evidence. `docs/sop-reference.md` is a concise operational reference only.

## Rules

- Keep authoritative shared instructions in root `SKILL.md`.
- Keep authoritative interface metadata in `agents/`.
- Build `dist/z-support-doc-ingestion/` with `scripts/build_package.sh`; install only that generated package, not the repository root.
- Keep operator instructions, implementation profile, security/rollback review, pilot-test record, and reference material in `docs/`.
- Keep reusable GitHub tracking templates in `templates/`.
- Keep activity notes in `activity-logs/`; use it only for repository maintenance history.
- Coordinators, automations, or administrators store live research-task records in `assignments/`, `completed-research/`, `agent-wiki-index/`, `transfer-log/`, `refresh-needed/`, and `open-questions/`.
- Research agents do not need GitHub access; they return concise completion or transfer summaries to the coordinator.
- Do not store scraped vendor documentation, private client documentation, secrets, tokens, environment files, or full wiki exports in this repo.
- Store finished support documentation inside the correct individual OpenClaw agent wiki.
- Use GitHub tracking records to point to wiki paths, coverage evidence, transfer history, and refresh rules.
- For pre-skill Agent Knowledge or ZedBiz Biz Brain planning, use `ZedBiz44/ZedBiz-Biz-Brain-System` instead of this repo.
- Verify OpenClaw command syntax against the active host before running bulk wiki ingest, compile, lint, or transfer operations.

## Completion Standard

A repo update is complete when the generated `dist/z-support-doc-ingestion/` package validates, referenced runtime files exist, no secrets are committed, required security and implementation records are current, and the change has a short activity record when operationally meaningful.
