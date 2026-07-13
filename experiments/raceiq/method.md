# Working assessment method

This is the minimum method used for the RaceIQ experiment. It is a working artefact, not yet a stable V1 contract.

## 1. Select reader groups from observable interfaces

A reader group is justified when the repository exposes a goal, interface or responsibility that the group would plausibly use.

Acceptable evidence includes:

- the repository description or README;
- executable commands;
- visible application navigation;
- data manifests and interpretation boundaries;
- contributor or operating guidance.

Do not infer internal teams, governance roles or business priorities.

## 2. Select representative tasks

A task is included when it:

- represents a plausible reader goal;
- begins from a defined context;
- has a recognisable completion condition;
- exercises an existing documentation path;
- is materially different from the other tasks;
- remains proportionate to the repository.

Tasks are not selected to force predetermined Diátaxis outcomes.

## 3. Walk the task path

Use this record:

```md
## T<n> — <task>

- Reader:
- Starting context:
- Completion condition:
- Expected entry point:
- Actual path:
- Evidence:
- Next permitted action:
- Protected decisions:
- Result: Complete / Partial / Blocked / Not tested
- Observed friction:
- Confidence:
```

### Result meanings

- **Complete** — the existing path provides sufficient guidance or evidence to reach the completion condition.
- **Partial** — the reader can advance but must discover missing context, reconcile contradictory sources or make an unsupported choice.
- **Blocked** — the available evidence cannot support the next material action.
- **Not tested** — the behaviour was not executed and source inspection is insufficient to claim completion.

## 4. Record observable failures

A failure must identify a gap between the reader's task and the available path.

Useful failure forms include:

- an entry point omits or misstates a current capability;
- two repository sources describe incompatible scopes;
- a reader cannot determine which source is authoritative;
- instructions stop before the real completion condition;
- an inference is presented without its interpretation boundary;
- a maintenance task requires intent or provenance not present in the repository.

Avoid broad judgements such as "the docs are incomplete".

## 5. Classify the response

Use the smallest sufficient response.

| Classification | Use when |
| --- | --- |
| Retain | Existing content already supports the task and remains useful. |
| No change | The task is unsupported, disproportionate or not established as a real documentation need. |
| Correction | Existing content contains a stale, misleading or contradictory claim. |
| Navigation | Useful content exists but the reader cannot reliably find it from the expected entry point. |
| Tutorial | An unfamiliar reader needs a guided learning sequence to reach a defined outcome. |
| How-to | A competent reader needs steps to complete a real task, including choices and failure modes. |
| Reference | The need concerns exact interfaces, files, commands, fields or canonical behaviour. |
| Explanation | The reader needs rationale, concepts, trade-offs or interpretation boundaries. |
| Human authority required | The repository cannot establish intent, policy, provenance or a disputed canonical source. |

A missing document type is not evidence that the type is required.

## 6. Create a bounded remediation item

Use this format:

```md
## R<n> — <outcome>

- Reader task:
- Observed failure:
- Evidence:
- Classification:
- Proposed scope:
- Deliberate exclusions:
- Permitted claims:
- Human-authority needs:
- Validation:
- Stopping conditions:
```

Each remediation item must trace to at least one walkthrough finding or explicit correctness or maintenance risk.

## 7. Validate by response type

- **Correction:** compare the final claim with the current authoritative interface or file set.
- **Navigation:** repeat the task from the original entry point.
- **Tutorial:** test from a clean, defined starting context.
- **How-to:** execute the real task, including important failure modes.
- **Reference:** compare every material claim with canonical evidence; prefer mechanical checks.
- **Explanation:** verify rationale against decisions, source material or human knowledge. Preserve uncertainty when authority is absent.
- **Retain/no change:** confirm that no observed task failure requires broader content.

## 8. Stopping conditions

Stop and preserve uncertainty when:

- the next step requires undocumented project intent;
- the canonical source is disputed or unclear;
- a proposed change would exceed the observed failure;
- validation requires target mutation that has not been authorised;
- the evidence supports only a hypothesis;
- the drafting agent would be validating its own unexecuted assumptions.

## Proportionality check

Before recommending work, ask:

1. Does the item solve an observed reader failure?
2. Is a smaller correction or navigation change sufficient?
3. Can useful existing material be retained?
4. Does the repository establish the claims the change would make?
5. Is the maintenance burden justified?
