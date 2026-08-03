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
- permitted operations;
- prohibited operations;
- review boundary;
- protected decisions.

If the task must be materially redefined, stop and request approval.

Do not begin an executable task whose approved preflight is missing or failed. Do not begin a blinded task if the current context has already seen forbidden evidence. Stop and record the invalid condition; changing order or pretending to forget requires new authority.

## 2. Record the evidence environment

Before execution, record:

- target repository and pinned commit or evidence state;
- retrieval mode;
- operating system, container or sandbox;
- language, runtime and tool versions;
- declared and resolved dependency versions;
- network access used;
- credentials or secrets used;
- fixture, cache and output locations;
- target-state and restoration checks.

Dependency and runtime versions are first-class evidence when the task depends on installation, build, tests or runtime behaviour.

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

These states are non-exclusive:

- **Source inspected** — repository source, documentation or configuration was examined.
- **Command executed** — a named command was run in the recorded environment.
- **Behaviour observed** — runtime output or behaviour was directly observed.
- **Clean-context completed** — the approved reader reached the completion condition from the approved unfamiliar starting context.
- **Separately reviewed** — another review pass checked the evidence or repeated part of the task.
- **Human validated** — a human independently accepted or reproduced the result.
- **Not tested** — the relevant execution or behaviour was not tested.

Do not claim clean-context completion merely because a command succeeded in a different environment. Do not claim human validation for a same-agent review.

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

Use one primary result:

- **Complete** — the approved completion condition was reached through the existing path.
- **Partial** — the path provided material help but did not reach the completion condition.
- **Blocked** — the task could not safely proceed because evidence, authority, prerequisites or access were missing.
- **Not tested** — required behaviour was not executed or observed.

The result does not predetermine the documentation response. A complete task may justify retention. A blocked task may require human authority rather than a guide. Use `Not tested` when required behaviour did not run; use `Blocked` when the approved task could not safely begin or continue. Record both only when they describe different aspects, with one primary result.

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
- Completion condition:
- Expected documentation entry point:
- Actual path followed:
- Commands or interactions:
- Durable command/result evidence:
- Retrieval mode:
- Runtime and dependency versions:
- Mutation or local-effect events: none / M1, M2
- Execution-evidence states:
  - [ ] Source inspected
  - [ ] Command executed
  - [ ] Behaviour observed
  - [ ] Clean-context completed
  - [ ] Separately reviewed
  - [ ] Human validated
  - [ ] Not tested
- Primary result: Complete / Partial / Blocked / Not tested
- Observable friction:
- Supporting evidence:
- Protected decisions and uncertainty:
- Smallest sufficient response:
- Finding ID: none / F1
- Limitations:
```

## 10. Finish and publish the task record

Once the approved task evidence and required limitations are recorded:

1. stop discovery and additional repository inspection;
2. assemble the compact task record;
3. attempt the authorised durable publication within the approved interaction or time bound;
4. stop after successful publication.

If publication cannot complete, preserve or return the prepared record and report a publication blocker. Do not resume evidence collection merely because publication is stalled.

## 11. Separate evidence review

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