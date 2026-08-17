# Skill Pilot and Trigger-Test Record

Date: 2026-08-17 | Tester: Pending | Status: Planned

## Artifact and Environment

| Field | Value |
|---|---|
| Skill identifier | `z-support-doc-ingestion` |
| Repository and commit | Record the current tested commit at pilot time |
| Deployable package | `dist/z-support-doc-ingestion/` |
| Platform and version | Pending pilot inspection |
| Pilot agent or environment | One approved OpenClaw agent. Confirm Wilma only if its current state is suitable. |
| Installation path | Confirm at pilot time |
| Fresh session or gateway refresh | Pending |

## Discovery Check

| Check | Result | Evidence |
|---|---|---|
| Current package built from tested commit | Pending | |
| Package installed at verified skills root | Pending | |
| `openclaw skills list` reports the skill ready | Pending | |
| Expected metadata is visible | Pending | |

## Trigger Tests

| Test type | Prompt | Expected behavior | Actual result | Evidence |
|---|---|---|---|---|
| Positive | Research official support documentation for a tool and save it in the assigned agent documentation wiki. | Skill activates and follows the research, validation, and completion workflow. | Pending | |
| Paraphrased positive | Learn everything useful from this platform’s help centre so you can answer practical questions later. | Skill activates from natural wording. | Pending | |
| Boundary | The documentation is behind a paid login. What should you do? | Skill stops and requests the required approval. | Pending | |
| Negative | Explain the concept of a support documentation wiki. | Skill does not claim to perform a research workflow. | Pending | |

## Pilot Task

| Field | Value |
|---|---|
| Representative safe task | Pending selection of a public, small documentation set |
| Output or files produced | Pending |
| Validation result | Pending |
| Observed issue or none | Pending |

## Rollback Readiness

| Field | Value |
|---|---|
| Last known-good commit or release | Pending first successful pilot |
| Verified rollback or removal method | Pending pilot confirmation |
| Rollback test performed | No |

## Sign-Off

- Tester: Pending
- Reviewer: Pending
- Approver: Jack
- Deployment decision: Pilot only pending test completion
