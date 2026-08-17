# Shared-Vault Agent Namespace Correction

Date: 2026-08-17 | Agent: Manus | Status: Implemented and runtime-validated

## Trigger

A read-only audit found that Wilma’s WpSpectra support documents were stored in `/opt/openclaw/shared/knowledge/wilma/wiki`, while Wilma’s active `memory-wiki` vault was `/opt/openclaw/shared/knowledge/wiki`. The personal folder compiled, but a live runtime search returned no WpSpectra results.

## Corrected Model

Reusable public vendor support documentation now belongs in the active shared vault under a supported content-type namespace:

```text
sources/<agent>/
entities/<agent>/
concepts/<agent>/
syntheses/<agent>/
reports/<agent>/
```

Each page requires `primaryAgent`, `owner`, and `scope: specialist-support-docs`. Arbitrary root-level `wiki/<agent>/` folders are prohibited because the compiler only scans the standard content-type groups.

## Wilma WpSpectra Migration

The six WpSpectra knowledge files were copied into `*/wilma/` namespaces in the active vault after a checksummed backup was created. Source files remain preserved in the former folder until the migration record is closed.

## Runtime Evidence

The active-vault compile discovered all six migrated pages with no frontmatter errors. The live Wilma runtime returned the migrated namespace pages for these queries:

- Spectra Legacy migration
- Spectra Blocks Pro matched pair
- Spectra cache regenerate assets
- Spectra display conditions security

The shared `ZedBiz` search continued to return general shared knowledge, confirming no regression.

## Skill and SOP Changes

Updated the installable skill, adapter metadata, implementation profile, security and rollback review, usage guide, SOP reference, validation record, repository instructions, and canonical Notion SOP. The generated `dist/z-support-doc-ingestion/` package passed the structural validator.

## Remaining Verification

Deploy the current generated package to Wilma’s skills root and complete fresh current-commit discovery and trigger tests before wider rollout.
