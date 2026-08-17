# Repository Operating Instructions

Date: 2026-08-17 | Agent: Cody | Status: Active

## Purpose

This repo is the technical source for the `support-doc-ingestion` skill package.

## Rules

- Keep the installable skill in root `SKILL.md`.
- Keep interface metadata in `agents/`.
- Keep operator instructions and reference material in `docs/`.
- Keep reusable GitHub tracking templates in `templates/`.
- Keep activity notes in `activity-logs/`.
- Do not store scraped vendor documentation, private client documentation, secrets, tokens, environment files, or full wiki exports in this repo.
- Store finished support documentation inside the correct individual OpenClaw agent wiki.
- Use GitHub tracking records to point to wiki paths, coverage evidence, transfer history, and refresh rules.
- For pre-skill Agent Knowledge or ZedBiz Biz Brain planning, use `ZedBiz44/ZedBiz-Biz-Brain-System` instead of this repo.
- Verify OpenClaw command syntax against the active host before running bulk wiki ingest, compile, lint, or transfer operations.

## Completion Standard

A repo update is complete when `SKILL.md` remains valid, referenced files exist, no secrets are committed, and the change has a short activity record when operationally meaningful.
