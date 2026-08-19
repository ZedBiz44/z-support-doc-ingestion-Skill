# 2026-08-19 VPS2, Rocky, And Ruby Install

Date: 2026-08-19
Agent: Cody
Status: Completed

## Summary

Installed the current `z-support-doc-ingestion` deployable package on the requested live agents after refreshing the repository to commit `dbe673c`.

## Installed Targets

- VPS2 Frank: `/root/.openclaw-frank/workspace/skills/z-support-doc-ingestion`
- VPS2 Harry: `/root/.openclaw-harry/workspace/skills/z-support-doc-ingestion`
- VPS2 Suzy: `/root/.openclaw-suzy/workspace/skills/z-support-doc-ingestion`
- VPS4 Rocky: `/home/openclaw/.openclaw/workspace/skills/z-support-doc-ingestion`
- VPS3 Ruby: `/opt/hermes-ruby/skills/z-support-doc-ingestion`

## Verification

- Package `SKILL.md` SHA-256: `51dddad962216a569edf88943b3486e03ea6b17cdff80531726637bb3754e8f5`.
- Frank, Harry, and Suzy each reported `eligible: true`, `modelVisible: true`, `userInvocable: true`, and `commandVisible: true` through their local OpenClaw runtime.
- Rocky reported `eligible: true`, `modelVisible: true`, `userInvocable: true`, and `commandVisible: true` through the native OpenClaw runtime.
- Ruby showed `z-support-doc-ingestion` as a local enabled skill through the Hermes skill list, and the installed files were visible inside the running `hermes-ruby` container as user/group `hermes:hermes`.

## Notes

- VPS2 initially did not discover the package from `/root/.openclaw-<agent>/.openclaw/skills`; the runtime discovery proof came from `/root/.openclaw-<agent>/workspace/skills`.
- Temporary SSH key files, local package tarball, and remote `/tmp` package tarballs were removed after verification.
