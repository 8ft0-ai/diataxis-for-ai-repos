# Working method v0.2

This directory contains the provisional assessment method approved in [issue #8](https://github.com/8ft0-ai/diataxis-for-ai-repos/issues/8) for the second repository experiment under [stage #7](https://github.com/8ft0-ai/diataxis-for-ai-repos/issues/7).

It is a working experiment artefact. It is not a stable V1 contract, a required repository structure or proof that the method generalises across repository types, maintainers or agents.

## Purpose

The method helps a maintainer decide what documentation work is justified before asking an agent to draft anything.

Its central proposition remains:

> Do not ask AI to document the repository. Ask it to identify where readers fail, classify the documentation need, and draft only what the evidence supports.

The value is better documentation decisions, not a larger documentation set.

## Evidence-gated workflow

```text
Inspect repository evidence
→ identify evidence-supported reader groups
→ propose representative reader tasks
→ obtain human approval of the task set
→ walk or execute the approved tasks
→ classify observable failures and retained paths
→ select the smallest sufficient response
→ record bounded remediation and protected decisions
→ conduct a separate evidence review
→ close out with Adopt, Adapt or Reject
```

The human task-approval checkpoint is a hard gate. An agent may propose reader groups and tasks, but it must not execute the walkthroughs until a maintainer accepts or revises:

- the reader groups;
- the tasks and their priority;
- each starting context and completion condition;
- the execution and safety boundary;
- material protected decisions.

If execution later shows that an approved task is invalid, unsafe or unsupported, stop and record the discovery. Do not silently substitute a more convenient task.

## Two kinds of evidence label

Claim states and execution-evidence states answer different questions. Do not collapse them into one confidence score.

### Claim states

Use these labels for material statements:

| State | Meaning |
| --- | --- |
| **Observation** | Directly visible in repository evidence or an executed result. |
| **Authority** | Established by a canonical interface, explicit maintainer decision, policy, executable contract or other designated source. |
| **Inference** | A reasoned conclusion not directly established by authority. |
| **Uncertainty** | A question the available evidence cannot resolve. |

The repository is evidence, not complete truth. Code can establish behaviour in a particular context, but rarely proves intent, priority, policy, architectural rationale or historical motivation.

### Execution-evidence states

Use any states that apply. They are non-exclusive and describe what was actually done:

| State | Meaning |
| --- | --- |
| **Source inspected** | Repository source, configuration, documentation or other checked-in evidence was examined. |
| **Command executed** | A named command was run in the recorded environment. |
| **Behaviour observed** | Runtime output or behaviour was directly observed. |
| **Clean-context completed** | The reader task reached its completion condition from the approved unfamiliar starting context. |
| **Separately reviewed** | Another review pass checked the evidence or repeated part of the task. |
| **Human validated** | A human independently accepted or reproduced the relevant result. |
| **Not tested** | The relevant execution or behaviour was not tested. |

`Separately reviewed` is not the same as `human validated`. A fresh pass by the same agent, account or model may be useful, but it must be described accurately.

Do not write `command executed` when only source was inspected. Do not write `clean-context completed` merely because a command succeeded outside the approved starting context.

## Adoption levels

The method is proportionate only when the record burden matches the decision risk.

### Level 1 — Classification

Use Level 1 when the question is narrow and the evidence is already available, such as classifying an existing page or a proposed small correction.

Minimum evidence:

- the affected reader or reader need;
- the current evidence or observed problem;
- the proposed classification;
- authority and uncertainty boundaries;
- the smallest sufficient response.

Stop at Level 1 when the classification is clear, the change is bounded and no real task walkthrough is needed to determine correctness.

Escalate when reader impact is disputed, the expected path is unclear, a task must be executed, or the proposed work could create a new document or material maintenance burden.

### Level 2 — Task evidence

Use Level 2 when a maintainer needs evidence that readers can or cannot complete representative tasks.

Minimum evidence:

- an evidence inventory and authority map;
- approved reader groups and tasks;
- defined starting contexts and completion conditions;
- task-path records with evidence states;
- observable findings;
- bounded remediation, retain and no-change decisions;
- validation appropriate to the proposed response.

Stop at Level 2 when the evidence supports a proportionate backlog and no additional governance or comparative method evaluation is required.

Escalate when the assessment itself is experimental, commands or external environments carry material risk, independent review is required, or the result will change project governance or stable contracts.

### Level 3 — Governed workflow

Use Level 3 for method evaluation, higher-risk work or changes requiring explicit execution contracts and review boundaries.

Required evidence:

- an approved planning decision or execution contract;
- readiness, dependencies and safe starting state;
- the approved experiment or delivery plan;
- full provenance and execution-evidence states;
- target or repository mutation boundaries;
- a separate evidence review;
- a comparative or stage close-out where applicable;
- explicit human acceptance and merge authority.

Level 3 is not automatically better. It is deliberately heavier and should not be imposed on routine small documentation maintenance.

## Representative task selection

A representative task must describe a reader outcome, not a documentation category.

Each task needs:

- an evidence-supported reader group;
- a defined starting context;
- a recognisable completion condition;
- an expected documentation entry point;
- a reason it is material enough to test;
- an execution boundary where commands or runtime behaviour are involved.

Prefer a small set that exercises distinct reader needs. Do not select tasks merely to manufacture tutorial, how-to, reference and explanation outcomes.

A repository may justify fewer tasks, fewer reader groups or no new documentation.

## Task result states

Use one primary result:

| Result | Meaning |
| --- | --- |
| **Complete** | The approved completion condition was reached through the existing path. |
| **Partial** | The path provides material help but does not reach the completion condition. |
| **Blocked** | The task cannot safely proceed because evidence, authority, prerequisites or access are missing. |
| **Not tested** | The task or required behaviour was not executed or observed. |

A result does not determine the documentation response by itself. A blocked task may require human authority rather than a new guide. A complete task may justify retention and no change.

## Smallest sufficient response

Consider responses in this order:

1. **Retain** — the existing path is useful and sufficiently correct.
2. **No change** — no documentation change is justified by the evidence.
3. **Correction** — fix a stale, incorrect or misleading claim in an existing surface.
4. **Navigation** — route the reader to useful material that already exists.
5. **Tutorial** — provide a guided learning experience only when an unfamiliar reader needs a sequenced path to a recognisable outcome.
6. **How-to** — provide a task-focused procedure only when a competent reader needs to complete a real operation, including prerequisites and failure modes.
7. **Reference** — document exact interfaces, commands, options, schemas or other canonical contracts.
8. **Explanation** — explain concepts or rationale only when authoritative source material exists.
9. **Human authority required** — stop when intent, policy, priority, ownership or rationale cannot be established.

Do not create all four Diátaxis forms for symmetry. A correction, navigation change, retained path or explicit no-change decision may be the strongest outcome.

## Bounded remediation

Every remediation item must identify:

- the affected reader and approved task;
- the observable failure, correctness problem, authority gap or maintenance risk;
- exact supporting evidence;
- the smallest sufficient response;
- permitted claims;
- claims or decisions requiring human authority;
- scope and deliberate exclusions;
- validation appropriate to the response;
- stopping conditions.

Do not reconstruct undocumented intent from outputs or code. Do not enlarge a change beyond the observed failure.

## Validation by response type

- **Tutorial:** verify that an unfamiliar reader can start from the defined context and reach the stated outcome without hidden knowledge.
- **How-to:** verify that a competent reader can complete the real task, including prerequisites, choices and likely failure modes.
- **Reference:** check claims against canonical commands, interfaces, schemas or executable contracts. Prefer mechanical checks where practical.
- **Explanation:** check rationale against decisions, issues, source material or human knowledge. Never present inferred intent as established history.
- **Correction or navigation:** repeat the affected reader task and confirm that the revised path resolves the observed failure without unnecessary expansion.
- **Retain or no change:** record why the current path or absence of change is supported by the task evidence.

The agent that drafts a change should not be treated as independent validation of its own work.

## Local execution effects and target state

Executable walkthroughs should distinguish four separate observations:

- whether the remote target changed;
- whether canonical tracked source changed;
- which generated local artefacts were observed;
- whether the disposable workspace was restored when required.

Use the mutation and recovery classes defined in [`docs/issueops.md`](../../docs/issueops.md):

- **Class A — Protected or unbounded mutation:** stop normal work and require maintainer direction after minimum safe remediation and an incident record.
- **Class B — Recoverable local execution deviation:** pause the affected operation, bound and record the effect, restore or recreate the disposable workspace, verify the restored state and continue only within the original authority boundary.
- **Class C — Expected local side effect:** permit expected caches, package metadata, virtual environments and generated output inside approved disposable paths; record where material and clean or recreate before final verification when required.

A clean final state may be required evidence. The workspace does not need to remain continuously clean while explicitly approved commands run inside the disposable boundary.

Escalate a Class B or C effect to Class A when it escapes the approved environment, changes remote or protected state, cannot be confidently bounded, or cannot be safely restored. Do not use local recoverability to excuse unauthorised source changes.

## Stopping conditions

Stop and record the blocker when:

- the proposed reader or task is not supported by repository evidence;
- the task set has not received the required human approval;
- the next claim requires undocumented intent, policy, priority or rationale;
- authoritative source material is unavailable;
- the proposed response exceeds the observed failure;
- existing documentation already supports the task;
- the task is too low-value to justify the maintenance burden;
- safe execution would mutate a protected target or exceed the approved environment boundary;
- credentials, private data or publication would be required without explicit authority;
- the approved task becomes invalid or must be materially redefined;
- required validation cannot establish correctness;
- a Class A protected or unbounded mutation occurs;
- a Class B effect cannot be bounded, restored or verified within the original authority boundary.

Class B and Class C effects do not require a full stop when their approved recovery conditions are satisfied. Record them accurately in the plan and close-out where they are material.

Stopping is a valid outcome. It preserves the evidence gate.

## The three working records

The method v0.2 experiment shape contains three records:

1. [`README.md`](README.md) — the reusable method and evidence rules.
2. [`experiment-plan.md`](experiment-plan.md) — target evidence, proposed readers and tasks, execution boundary and the human approval decision.
3. [`assessment-closeout.md`](assessment-closeout.md) — compact task records, findings, bounded remediation, separate review and final recommendation.

Experiment-specific copies may reference the governing method rather than duplicate it in full. Material deviations must be recorded; they must not be silently absorbed into an experiment report.

## Separate evidence review

A separate review should receive the final task records and cited evidence. It should assess:

- whether reader groups are supported;
- whether tasks are representative and materially distinct;
- whether execution-evidence states are accurate;
- whether findings follow from evidence;
- whether protected decisions and uncertainty were preserved;
- whether the response is the smallest sufficient one;
- whether the process was useful and proportionate;
- whether the close-out recommendation is justified.

Where practical, the reviewer should repeat at least one material task. The record must state whether the review was performed by a different human, a different agent session, or the same connected account.

## Current limitations

The method has been exercised once against a small static dashboard using source inspection. It has not yet demonstrated:

- repeatability across materially different repository types;
- clean-context execution;
- agreement between independent humans or different agents;
- proportionate use in larger repositories;
- stable document-type contracts;
- cross-agent portability.

The second experiment is intended to test some of these limits. It must not be treated as proof of the remaining ones.
