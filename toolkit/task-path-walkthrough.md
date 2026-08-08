# Task-path walkthrough protocol

Use this protocol only after the representative readers, tasks, starting contexts, completion conditions and execution boundary have received human approval.

A walkthrough records the path a reader actually follows. It does not grade documentation in the abstract.

## 1. Reconfirm the approved task

Before starting each task, copy the approved fields without silently changing them:

- reader group;
- task statement;
- starting context;
- completion condition;
- expected documentation entry point;
- execution-context identity and required order;
- permitted evidence allowlist and forbidden prior exposure;
- executable-prerequisite preflight disposition;
- publication/write-path capability preflight disposition when durable publication is part of completion;
- permitted operations;
- prohibited operations;
- review boundary;
- protected decisions.

If the task must be materially redefined, stop and request approval.

Do not begin an executable task whose approved preflight is missing or failed. Do not begin a blinded or clean-context task if the current context already has forbidden prior exposure. Stop and record the invalid condition; changing order or pretending to forget requires new authority.

Freshness is an execution property defined by the information available before task invocation and the task's forbidden prior exposure. Authorised instructions, fixture identities, allowlists or control capsules supplied at invocation do not themselves invalidate freshness unless they disclose evidence the task contract excludes. A particular chat or UI mode may help establish isolation, but it is not the definition of isolation.

If the prior-information boundary cannot be established confidently, stop or reclassify the task before substantive evidence inspection. Later quarantine cannot restore a blind or clean-context claim.

## 2. Record the evidence environment and required capabilities

Before substantive evidence collection or execution, record:

- target repository and pinned commit or evidence state;
- retrieval mode;
- operating system, container or sandbox;
- language, runtime and tool versions;
- declared and resolved dependency versions;
- network access used;
- credentials or secrets used;
- fixture, cache and output locations;
- target-state and restoration checks;
- publication/write destination and operation when the task must publish a durable record;
- publication/write-path capability preflight: `Pass` / `Fail` / `Not required`.

Dependency and runtime versions are first-class evidence when the task depends on installation, build, tests or runtime behaviour.

When publication is required for completion, verify before substantive evidence collection that the connected capability can perform the exact authorised write to the exact destination using only the approved credential/permission boundary. Capability preflight does not create authority or widen the allowed write.

If publication capability preflight is `Fail`, preserve or return the bounded record the task is authorised to prepare, report the publication blocker and stop. Do not continue inspecting evidence in the hope that a write path will become available later.

## 3. Use explicit retrieval and execution modes

Choose the labels that describe what actually happened. Do not treat them as equivalent.

### Retrieval modes

- **Pinned clone** — a repository checkout was obtained and verified at the named commit.
- **Exact package reconstruction** — a package or archive was obtained and material files were verified against authoritative hashes or blobs.
- **Connector inspection** — repository content was read through a connected repository interface without a local checkout.
- **Source inspection** — checked-in source or documentation was examined, regardless of retrieval channel.
- **Behavioural fallback** — a controlled substitute or transcription was used to corroborate behaviour when authoritative execution was unavailable.
- **Not retrieved** — the required authoritative material was not obtained.

A behavioural fallback is not a pinned checkout. Connector inspection is not command execution. An exact package reconstruction is not automatically equivalent to a full repository clone.

### Execution-evidence states

Record subordinate evidence explicitly as yes/no:

- **Source inspected:** yes / no
- **Command executed:** yes / no
- **Behaviour observed:** yes / no
- **Clean-context completed:** yes / no
- **Separately reviewed:** yes / no
- **Human validated:** yes / no

Do not claim clean-context completion merely because a command succeeded in a different environment. Do not claim human validation for a same-agent review.

`Complete`, `Partial`, `Blocked` and `Not tested` are primary task results, not subordinate evidence-state labels. A task whose primary result is `Complete` may still record `command executed: no` and `behaviour observed: no` when source inspection was sufficient for its approved completion condition.

## 4. Follow the existing documentation path

Begin at the approved entry point.

Record in order:

1. documentation or interface consulted;
2. choice made by the reader;
3. command, navigation or lookup performed;
4. result observed;
5. additional evidence required;
6. point where the completion condition was met or failed.

Do not optimise the path using knowledge gained from source inspection unless the reader’s approved starting context includes that knowledge. Record source inspection as evidence, not as an invisible shortcut.

## 5. Preserve a durable command/result summary

Before disposable environments or outputs are removed, record enough evidence for another reviewer to reconstruct the material result.

For each material command, record:

```md
#### Command C1

- Purpose:
- Working directory or fixture:
- Command:
- Runtime and dependency versions:
- Retrieval or execution mode:
- Exit status:
- Material stdout or result summary:
- Material stderr or warning summary:
- Output or artefacts created:
- Evidence retained:
- Limitation:
```

Do not rely only on an ephemeral transcript path. Retain concise results in the repository assessment record or linked issue.

Redact secrets and private data. Prefer synthetic fixtures.

## 6. Record target state and local effects

Separate these observations:

- whether the remote target changed;
- whether canonical tracked source changed;
- which generated local artefacts appeared;
- whether the disposable workspace was restored when required.

Use the repository’s [Class A/B/C mutation and recovery rules](../docs/issueops.md#mutation-and-recovery-classes).

A single task may produce several events. Record expected Class C caches separately from a distinct Class B placement deviation. Stop and require maintainer direction for Class A events.

### Event record

| ID | Operation | Class | Effect boundary | Observed effect | Evidence | Recovery or escalation | Final state |
| --- | --- | --- | --- | --- | --- | --- | --- |
| M1 |  | A / B / C | remote or protected / canonical tracked source / generated local |  |  |  |  |

## 7. Determine the task result

Use exactly one primary result:

- **Complete** — the approved completion condition was reached through the existing path.
- **Partial** — the path provided material help but did not reach the completion condition.
- **Blocked** — the task could not safely proceed because evidence, authority, prerequisites or access were missing.
- **Not tested** — the approved task required behaviour that was not executed or observed, so the task completion contract remains untested.

The result does not predetermine the documentation response. A complete task may justify retention. A blocked task may require human authority rather than a guide. Use primary `Not tested` only when the required task behaviour was not executed or observed; otherwise describe non-executed subordinate evidence with explicit fields such as `command executed: no` or `behaviour observed: no`.

## 8. Describe observable friction

Record what happened without broad quality labels.

Prefer:

- “The README says the option includes all files, but hidden files remained excluded without a second flag.”
- “The contribution command installed successfully, but the full suite failed under the resolved dependency version.”
- “The expected entry point linked to the correct reference, and the completion condition was reached.”

Avoid:

- “The docs are poor.”
- “This is confusing.”
- “The repository needs more explanation.”

Name the reader, expected path, actual path, completion gap and evidence.

## 9. Compact task record

Copy this record for each approved task.

```md
### T1 — <task>

- Reader group:
- Starting context:
- Freshness / forbidden-prior-exposure check: pass / fail / not required — evidence
- Completion condition:
- Expected documentation entry point:
- Actual path followed:
- Commands or interactions:
- Durable command/result evidence:
- Retrieval mode:
- Runtime and dependency versions:
- Publication/write-path capability preflight: Pass / Fail / Not required — evidence
- Mutation or local-effect events: none / M1, M2
- Execution-evidence states:
  - Source inspected: yes / no
  - Command executed: yes / no
  - Behaviour observed: yes / no
  - Clean-context completed: yes / no
  - Separately reviewed: yes / no
  - Human validated: yes / no
- Primary result: Complete / Partial / Blocked / Not tested
- Observable friction:
- Supporting evidence:
- Protected decisions and uncertainty:
- Smallest sufficient response:
- Finding ID: none / F1
- Limitations:
```

## 10. Finish and publish the task record

Publication capability must already have been preflighted under section 2 when publication is part of the approved completion condition.

Once the approved task evidence and required limitations are recorded:

1. stop discovery and additional repository inspection;
2. assemble the compact task record;
3. attempt only the authorised durable publication within the approved interaction or time bound;
4. stop after successful publication.

If an already-passed write path becomes unavailable at publication time, preserve or return the prepared record and report a publication blocker. Do not resume evidence collection merely because publication is stalled.

## 11. Separate evidence review and terminality

A separate review should receive the final task records and cited evidence.

It should check:

- whether the reader groups are supported;
- whether the tasks are representative and materially distinct;
- whether evidence-state claims are accurate;
- whether findings follow from evidence;
- whether protected decisions remain uncertain;
- whether the selected response is the smallest sufficient one;
- whether the process was useful and proportionate.

Where practical, repeat at least one material task.

Label the reviewer accurately:

- independent human;
- different agent or session;
- same account fresh pass;
- other disclosed relationship.

A separate pass by the drafting or assessing agent is useful evidence, but it is not independent human validation.

If the approved workflow requires a separate review, define which durable qualifying review closes that gate. Before beginning another review, inspect the current durable record for an already-terminal qualifying review. Check again immediately before publication when the review state could have changed while the session was running.

If the review gate is already terminal, stop without publishing another substantively duplicate review. Duplicate historical review comments remain orchestration evidence, not extra validation merely by repetition.

A re-review may proceed only when the governing contract requires it after material evidence changes, remediation or another explicit trigger. Record that trigger.