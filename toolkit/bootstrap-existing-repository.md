# Bootstrap a repository that already has documentation

Use this guide when the target repository already contains README files, guides, reference material, contributor instructions or other documentation.

The assessment-only V1 is ready to support this bootstrap. It is not an installer, documentation generator or autonomous remediation system. The initial outcome is evidence and a bounded backlog, not documentation changes.

> **Project-name status:** **TaskFirstDocs** remains a provisional name. This guide does not approve or adopt it.

## What bootstrap means here

Bootstrap means establishing a durable, non-mutating assessment record in the target repository so a maintainer and repository-aware agent can decide what documentation work is justified.

It does not mean:

- copying this whole toolkit into the target repository;
- reorganising existing documentation into four Diátaxis folders;
- generating missing pages from the directory tree;
- authorising an agent to edit documentation immediately;
- assuming that existing material is wrong or incomplete;
- treating code as complete authority for intent, policy or rationale.

Existing documentation is evidence. It may be correct and worth retaining. It may need a local correction or clearer navigation. It may expose an authority gap that only a maintainer can resolve. The assessment should preserve all of those possible outcomes.

## Recommended operating model

Create one assessment issue in the target repository and reference this toolkit at a pinned commit.

Use the target issue as the durable record for:

- repository identity and evidence state;
- documentation and authority inventory;
- proposed reader groups and tasks;
- the maintainer's task-approval decision;
- execution boundaries and limitations;
- links to later walkthrough and close-out evidence.

Do not initially copy the toolkit files into the target repository. Referencing a pinned commit keeps the method stable for the assessment while avoiding a maintenance burden in the target.

Record both:

- the toolkit repository: `8ft0-ai/diataxis-for-ai-repos`;
- the exact toolkit commit selected for the assessment.

Use a released or reviewed commit where possible. Do not rely on a moving branch when reproducibility matters.

## Choose the lightest adoption level

### Start at Level 1 when the question is narrow

Use Level 1 when the repository already exposes the necessary evidence and the decision concerns one bounded item, such as:

- whether a documented command is stale;
- whether an existing page should be retained;
- whether a local correction is sufficient;
- whether a README needs one navigation link;
- whether a proposed new page is unsupported.

A Level 1 bootstrap may need only a small issue record. It does not require a full task set or executable walkthrough when those would not improve the decision.

### Start at Level 2 when reader completion must be tested

Use Level 2 when the decision depends on whether representative readers can complete real tasks using the existing documentation.

Typical reasons include:

- the repository has substantial documentation but readers still cannot find the right path;
- several authority surfaces disagree;
- installation, configuration, contribution or operational instructions need execution evidence;
- the maintainer wants an evidence-backed remediation backlog rather than general criticism;
- a proposed new document would create a material maintenance commitment.

Level 2 is the normal starting point for a first repository-wide assessment.

### Use Level 3 only when governance or method evaluation requires it

Level 3 adds execution contracts, safe starting states, full mutation records, separate review and comparative close-out. Use it for higher-risk execution, method experiments or changes to stable governance.

Do not impose Level 3 on routine documentation maintenance merely because it is more complete.

## Bootstrap sequence

### 1. Pin the target and toolkit evidence

Record:

- target repository identity;
- target default branch;
- target commit or equivalent immutable evidence state;
- toolkit repository and pinned toolkit commit;
- retrieval mode;
- assessment date;
- public or private status;
- material access limitations.

A connector inspection, package reconstruction and pinned clone are not equivalent. Label the retrieval mode accurately.

### 2. Create a non-mutating assessment issue

Use the template later in this guide.

The issue should authorise inspection and task proposal only. It should not authorise:

- target file edits;
- branches or pull requests;
- dependency installation or command execution before approval;
- documentation drafting;
- publication or deployment;
- changes to workflows, settings or permissions.

### 3. Inspect existing documentation as evidence

Begin with surfaces relevant to plausible reader outcomes, such as:

- the root README;
- nested README files;
- documentation directories;
- contribution and development guidance;
- command help and executable interfaces;
- API definitions, schemas and configuration;
- examples and tests;
- architecture and decision records;
- release, deployment and operational instructions;
- relevant issues and pull requests.

Do not inventory every Markdown file merely because it exists. Include material that helps establish reader paths, current behaviour, authority, contradictions or maintenance risk.

For each material surface, ask:

- Which reader need does it serve?
- What claim does it make?
- Is it authoritative for that claim?
- What can it not establish?
- Does another source contradict it?
- Is the current route discoverable from the expected entry point?

### 4. Propose evidence-supported readers

Describe functional reader groups supported by observable repository interfaces.

Examples include:

- first-time CLI user;
- API integrator;
- contributor running tests;
- operator changing configuration;
- maintainer preparing a release;
- analyst interpreting repository-produced output.

Do not invent organisational personas or reader demand from file names alone.

### 5. Propose representative reader tasks

Tasks describe outcomes, not document categories.

Prefer tasks such as:

- install the package and produce a first result;
- configure a documented deployment mode;
- select the correct command option for a real workflow;
- locate the canonical API or schema definition;
- run the contributor test path from a clean environment;
- diagnose a documented failure;
- identify which configuration source is authoritative.

Every task must include:

- reader group;
- evidence basis;
- materiality;
- starting context;
- recognisable completion condition;
- expected documentation entry point;
- proposed retrieval and execution mode;
- execution boundary;
- protected decisions and uncertainty.

Do not select tasks merely to manufacture tutorial, how-to, reference and explanation outcomes.

### 6. Stop for human task approval

The first assessment pass ends here.

A maintainer must approve or revise:

- reader groups;
- task set and priority;
- starting contexts;
- completion conditions;
- permitted commands and network access;
- disposable write locations;
- credential boundary;
- review boundary;
- protected decisions.

Do not execute tasks while this decision is absent, rejected or materially inconsistent with the proposal.

### 7. Execute only the approved walkthroughs

After approval, use [`task-path-walkthrough.md`](task-path-walkthrough.md).

Begin at the entry point a real reader would receive. Record the actual path without silently using knowledge discovered during source inspection.

Where commands are approved, retain durable summaries before disposable environments are removed. Record runtime and resolved dependency versions when they affect the result.

Separate:

- remote target state;
- canonical tracked source state;
- generated local artefacts;
- restoration evidence.

### 8. Choose the smallest sufficient response

Use [`classification-and-remediation.md`](classification-and-remediation.md).

Consider responses in this order:

1. retain;
2. no change;
3. correction;
4. navigation;
5. tutorial;
6. how-to guide;
7. reference;
8. explanation;
9. human authority required.

A repository with extensive documentation may need only a correction, a clearer route to existing guidance or an explicit authority decision.

Do not reorganise the documentation tree for Diátaxis symmetry. Diátaxis classifies an observed reader need; it does not require four folders or four new documents.

### 9. Close with evidence and a bounded backlog

Use [`assessment-closeout.md`](assessment-closeout.md).

The close-out should record:

- task results;
- findings and traceability;
- retained paths;
- no-change decisions;
- authority-required decisions;
- bounded remediation items;
- validation requirements;
- limitations;
- the next decision.

The assessment may correctly conclude that no documentation change is justified.

### 10. Authorise remediation separately

Do not draft or apply documentation changes under the assessment issue unless it explicitly authorises that work.

After the maintainer accepts the backlog, create separate bounded execution contracts for the selected remediation items. Each contract should define:

- affected reader and task;
- observed finding or authority gap;
- exact scope and deliberate exclusions;
- permitted claims;
- human-authority decisions;
- response-specific validation;
- merge authority.

This preserves the evidence gate between testing and drafting.

## Reusable target-repository assessment issue

Copy the template below into the repository being assessed. Replace all angle-bracket placeholders before use.

```md
# Assess the existing repository documentation

## Issue type

Assessment planning and execution boundary.

This issue authorises a non-mutating documentation assessment. It does not authorise documentation changes, implementation branches, pull requests, publication or repository configuration changes.

## Toolkit

Use the assessment-only toolkit from:

`https://github.com/8ft0-ai/diataxis-for-ai-repos`

Pinned toolkit commit:

`<PINNED_TOOLKIT_COMMIT>`

Read, in order:

1. `toolkit/bootstrap-existing-repository.md`
2. `toolkit/repository-assessment.md`
3. `toolkit/reader-task-discovery.md`
4. `toolkit/evidence-and-validation.md`

Do not rely on private conversation history or assumptions about why the target repository was designed.

## Target repository

- **Repository:** `<OWNER/REPOSITORY>`
- **Default branch:** `<DEFAULT_BRANCH>`
- **Pinned target commit or evidence state:** `<PINNED_TARGET_COMMIT>`
- **Assessment level:** Level 1 / Level 2

## Objective

Assess whether the repository's existing documentation supports representative reader tasks.

Produce:

- a repository identity and pinned evidence state;
- an inventory of existing documentation and authority surfaces;
- contradictions, stale claims and unresolved uncertainty;
- evidence-supported reader groups;
- a small proposed set of representative reader tasks;
- a starting context and recognisable completion condition for every task;
- a proposed execution and safety boundary;
- representativeness limitations;
- a human task-approval request.

Stop before executing the proposed tasks.

## Existing documentation

Treat all existing documentation as evidence to inspect and potentially retain.

Do not assume that:

- existing documentation must be rewritten;
- an empty documentation category requires a new page;
- all four Diátaxis forms are needed;
- the directory structure reveals reader need;
- code establishes intent, policy or rationale;
- more documentation is necessarily better.

## Evidence rules

Distinguish:

- **Observation** — directly visible repository or execution evidence.
- **Authority** — a canonical interface, policy, decision record or explicit maintainer statement.
- **Inference** — a reasoned conclusion not directly established.
- **Uncertainty** — a question the available evidence cannot resolve.

Preserve contradictions and uncertainty. Do not complete missing rationale with plausible prose.

## Initial scope

Inspect relevant existing surfaces, including where present:

- root and nested README files;
- documentation directories;
- contribution and development instructions;
- command help, APIs, schemas and configuration;
- examples and tests;
- architecture and decision records;
- release, deployment and operational guidance;
- relevant issues and pull requests.

Do not inventory files that have no material relationship to a plausible reader task.

## Mutation boundary

Do not:

- edit target files;
- create a branch or pull request;
- commit or push;
- create additional target issues unless separately authorised;
- change workflows, settings, permissions or branch protection;
- publish or deploy;
- use credentials, secrets, private user files or production data;
- install dependencies or execute commands before the task set and execution boundary are approved;
- draft proposed documentation changes.

## Required first output

Post the following to this issue:

1. repository identity and pinned commit;
2. documentation and authority inventory;
3. contradictions and stale claims;
4. protected decisions and unresolved uncertainty;
5. proposed reader groups with evidence basis;
6. proposed representative tasks;
7. starting context and completion condition for each task;
8. proposed execution boundary;
9. representativeness and proportionality limitations;
10. explicit human task-approval request.

Stop after posting that proposal.

## Human approval gate

Do not execute walkthroughs until a maintainer records:

- approved reader groups;
- approved tasks and priority;
- approved starting contexts;
- approved completion conditions;
- approved execution boundary;
- approved review boundary;
- protected decisions;
- required changes.

## Expected later close-out

After task approval and execution, use:

- `toolkit/task-path-walkthrough.md`;
- `toolkit/classification-and-remediation.md`;
- `toolkit/assessment-closeout.md`.

The close-out should produce bounded remediation, retained paths, no-change decisions and human-authority questions. It must not draft or apply remediation unless a separate execution contract authorises that work.
```

## Before starting the first external bootstrap

Use a fresh agent context where practical. Supply the target repository, the assessment issue and the pinned toolkit commit, but not the private history of how this toolkit was developed.

The first output should stop at the human task-approval gate. That provides direct evidence of whether the toolkit is understandable and usable without issue archaeology from this repository.

## Current evidence limits

This guide packages an operating path supported by two small-repository experiments. It does not establish:

- broad repository generality;
- independent maintainer or agent agreement;
- large-repository proportionality;
- documentation-drafting quality;
- model-to-model portability.

Record new bootstrap evidence honestly. Do not infer these limits away.