# Assessment-only V1 toolkit

> **Project:** **Trailpost**.

This toolkit helps maintainers decide what repository documentation work is justified before asking an AI coding agent to draft or change anything.

Its central proposition is:

> Do not ask AI to document the repository. Ask it to identify where readers fail, classify the documentation need, and draft only what the evidence supports.

The outcome is an evidence-backed documentation decision: a baseline, approved reader tasks, task-path results, bounded remediation and explicit retain, no-change or human-authority decisions. The toolkit may conclude that no new document should be created.

## Who this is for

Use the toolkit when an open-source maintainer, software team or technical writer wants a repository-aware agent to assess existing documentation without treating plausible prose as proof.

The user does not need:

- a CLI or hosted service;
- a prescribed documentation directory structure;
- a particular model or coding agent;
- all four Diátaxis forms;
- permission to modify the target repository during assessment.

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
→ review the evidence
→ close out with limitations and next decisions
```

The gate between task proposal and task execution is mandatory. An agent may propose reader groups and tasks, but a maintainer must approve or revise the readers, tasks, starting contexts, completion conditions, priorities and execution boundary before walkthroughs begin.

Before approval, check the task pack as a whole. Record task ordering and execution-context identity, preflight executable prerequisites, protect blinded fixtures with an immutable evidence allowlist, and set a proportionate evidence budget. Once the required initial record is complete, stop discovery and perform the bounded publication step; publication failure is a blocker, not permission to resume open-ended inspection.

Use `Complete`, `Partial`, `Blocked` and `Not tested` as the primary task results. Keep source inspection, command execution, observed behaviour, clean-context completion, separate review and human validation as distinct evidence states.

## What the toolkit produces

A proportionate assessment can produce:

- a repository identity and pinned evidence state;
- a documentation and authority inventory;
- contradictions, stale claims and unresolved uncertainty;
- evidence-supported reader groups;
- a human-approved set of representative tasks;
- task-path records with accurate execution-evidence states;
- observable findings rather than general documentation criticism;
- the smallest sufficient response for each finding;
- a bounded remediation backlog;
- retain, no-change and human-authority outcomes;
- a close-out that states limitations and the next decision.

The toolkit stops before documentation drafting unless a later execution contract explicitly authorises it.

## Adoption levels

Choose the lightest level that can support the decision.

### Level 1 — Classification

Use Level 1 for a narrow question where the relevant evidence is already available, such as classifying one stale claim or deciding whether an existing page should be retained.

Minimum record:

- affected reader or reader need;
- observed problem and evidence;
- authority and uncertainty boundary;
- smallest sufficient response;
- validation for that response.

Stop at Level 1 when the classification is clear and no real task walkthrough is needed.

### Level 2 — Task evidence

Use Level 2 when the decision depends on whether readers can complete representative tasks.

Minimum record:

- evidence inventory and authority map;
- approved reader groups and tasks;
- starting contexts and completion conditions;
- task-path walkthroughs;
- observable findings;
- bounded remediation, retain and no-change decisions;
- validation appropriate to each response.

Stop at Level 2 when the evidence supports a proportionate backlog and no additional governance or method evaluation is required.

### Level 3 — Governed workflow

Use Level 3 for method evaluation, higher-risk execution, explicit delivery contracts or comparative experiments.

Additional evidence:

- planning decision or execution contract;
- readiness, dependencies and safe starting state;
- full provenance and mutation boundaries;
- separate evidence review;
- comparative close-out where applicable;
- explicit human acceptance and merge authority.

Level 3 is deliberately heavier. Do not impose it on routine documentation maintenance.

## Human decisions and agent boundaries

An agent may:

- inspect and cite repository evidence;
- distinguish observation, authority, inference and uncertainty;
- propose reader groups and tasks;
- execute approved tasks inside the approved boundary;
- classify observed failures;
- recommend bounded remediation, retention or no change;
- prepare an evidence pack for review.

Humans retain responsibility for:

- task approval and priority;
- intent, policy, ownership and architectural rationale;
- disputed authority;
- target-repository mutation;
- acceptance of findings and remediation;
- project naming;
- publication, deployment and merge.

## Package map and reading order

1. [`bootstrap-existing-repository.md`](bootstrap-existing-repository.md) — start an assessment in another repository that already contains documentation, using a pinned toolkit commit and a copy-ready issue template.
2. [`repository-assessment.md`](repository-assessment.md) — inspect a repository without mutation and propose the evidence-backed task set.
3. [`reader-task-discovery.md`](reader-task-discovery.md) — decide which readers and tasks are representative enough to test.
4. [`task-path-walkthrough.md`](task-path-walkthrough.md) — execute approved walkthroughs and record what actually happened.
5. [`classification-and-remediation.md`](classification-and-remediation.md) — choose the smallest sufficient response and write bounded remediation items.
6. [`evidence-and-validation.md`](evidence-and-validation.md) — apply claim states, provenance rules, retrieval labels, mutation boundaries and response-specific validation.
7. [`assessment-closeout.md`](assessment-closeout.md) — record results, retained paths, limitations and next decisions.
8. [`worked-example.md`](worked-example.md) — follow the files-to-prompt experiment as the primary worked example.

The [working method v0.2](../working/method-v0.2/README.md) and the [RaceIQ](../experiments/raceiq/README.md) and [files-to-prompt](../experiments/files-to-prompt/method.md) experiments remain the provenance and research record behind this package.

## Evidence base and current limitations

The assessment method was developed through two small-repository experiments:

- RaceIQ, a static dashboard assessed primarily through source inspection;
- files-to-prompt, a Python CLI assessed through source inspection, executable tasks and a separate same-account review, with disclosed retrieval limitations.

The `v0.1.1` clarifications additionally draw on two fresh-context adoption pilots:

- gitstate-lab, where the method produced a useful assessment but one executable task stopped at preflight;
- arxiv-quant-radar, where the evidence gate worked but task-pack consistency, prerequisite availability, blinded isolation and publication proportionality required adaptation.

These pilots were run by repository-aware agents with maintainer-operated approval gates. They do not establish independent maintainer usability.

Across both experiments, the method produced corrections, navigation, retention, no-change and human-authority outcomes without requiring a complete documentation rewrite.

The evidence does **not** establish:

- agreement between independent maintainers or different agents;
- proportionality in large repositories or monorepos;
- broad generality across services, SDKs, private repositories or organisation-scale documentation estates;
- the quality of AI-drafted documentation changes;
- stable drafting contracts for tutorial, how-to, reference or explanation;
- model-to-model portability.

These are release limitations, not facts to infer away.

## Stop rather than speculate

Stop the assessment when:

- the proposed reader or task is not supported by repository evidence;
- the task set lacks human approval;
- the next claim requires undocumented intent, policy, priority or rationale;
- authoritative evidence is unavailable;
- execution would exceed the approved boundary;
- the proposed response is larger than the observed failure;
- existing documentation already supports the task;
- the maintenance burden would exceed the reader value;
- required validation cannot establish correctness.

Stopping, retaining useful material and creating nothing new are valid outcomes.
