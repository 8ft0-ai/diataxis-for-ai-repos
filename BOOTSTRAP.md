# Bootstrap another repository

Use this prompt to start an evidence-led documentation assessment in an existing software repository.

Copy the prompt into a repository-aware agent session and replace the target-repository placeholders before use.

---

You are bootstrapping an evidence-led documentation assessment for an existing software repository.

## Target repository

Repository:

`<OWNER/REPOSITORY>`

Repository URL:

`https://github.com/<OWNER/REPOSITORY>`

Use the repository's current default branch unless I provide a different target.

## Assessment toolkit

Use the assessment-only toolkit from:

`https://github.com/8ft0-ai/diataxis-for-ai-repos`

Pinned toolkit commit:

`7dfd922cd51a3aa7306ec3a60b438cf00480b28b`

Treat that pinned toolkit state as the methodology authority for this assessment.

Read the following toolkit files before substantive assessment work:

1. `toolkit/bootstrap-existing-repository.md`
2. `toolkit/repository-assessment.md`
3. `toolkit/reader-task-discovery.md`
4. `toolkit/evidence-and-validation.md`

Do not rely on previous conversation history, account memory or assumptions about why this repository was designed.

## Objective

Determine whether the repository's existing documentation supports the real tasks its readers need to perform.

Do not begin by looking for missing Markdown files.

Do not assume that every repository needs tutorials, how-to guides, reference and explanation.

Instead:

1. inspect repository evidence;
2. identify evidence-supported reader groups;
3. propose representative reader tasks;
4. identify the documentation paths those readers would reasonably encounter;
5. identify observable problems, contradictions, authority gaps and uncertainty;
6. propose a small task set for validation;
7. stop for human approval before executing those task walkthroughs.

The first outcome is an evidence-backed assessment plan, not documentation changes.

## Adoption level

Use **Level 2 — Task evidence** unless the repository clearly presents only one narrow documentation question that can be resolved proportionately at Level 1.

Do not escalate to Level 3 governance unless there is a concrete reason such as higher-risk execution, method evaluation, stronger provenance requirements or an explicit delivery contract.

## Evidence principles

Treat the repository as evidence, not complete truth.

Distinguish:

- **Observation** — directly visible repository or execution evidence.
- **Authority** — a source that is canonical for the claim being made.
- **Inference** — a reasoned conclusion not directly established by the evidence.
- **Uncertainty** — something the available evidence cannot resolve.

Code may establish behaviour but does not normally establish intent, policy, priority or architectural rationale.

Do not invent missing rationale.

Do not treat plausible prose as established fact.

Existing documentation may be correct and should be retained when it already supports the reader task.

## Initial inspection

Inspect only material that helps establish reader paths, behaviour, authority, contradictions or maintenance risk.

Relevant surfaces may include:

- root and nested README files;
- documentation directories;
- contributor and development instructions;
- installation and configuration guidance;
- command help and executable interfaces;
- APIs and schemas;
- examples and tests;
- architecture or decision records;
- release, deployment and operational guidance;
- relevant issues or pull requests where they are necessary to establish authority or rationale.

Do not inventory every documentation file merely because it exists.

## Reader discovery

Identify functional reader groups supported by repository evidence.

Examples may include:

- first-time user;
- API integrator;
- contributor;
- operator;
- maintainer;
- analyst interpreting repository output.

Do not invent personas from the directory structure.

For every proposed reader group, state the evidence that supports its relevance.

## Representative tasks

Propose a small set of representative tasks.

Prefer approximately **3–5 tasks** unless the repository is unusually small or the evidence clearly justifies a different number.

Tasks must describe reader outcomes rather than documentation categories.

Examples:

- install the package and produce a first result;
- configure a supported mode;
- find the authoritative API or schema definition;
- run the contributor test path;
- understand how to perform a documented operational task;
- determine which configuration source is authoritative.

For each task record:

- reader;
- evidence basis;
- why the task matters;
- expected starting context;
- expected documentation entry point;
- recognisable completion condition;
- whether source inspection is sufficient or execution would materially improve the evidence;
- relevant authority sources;
- uncertainty or protected human decisions;
- any execution, network, credential or freshness constraints.

Completion conditions must be **answer-neutral**. They should describe what successful completion looks like without revealing the target-specific answer the reader is expected to discover.

## Mutation boundary

This bootstrap assessment is read-only.

Do not:

- edit repository files;
- create implementation branches;
- commit or push;
- open remediation pull requests;
- draft new documentation;
- reorganise documentation;
- create documents merely because a Diátaxis category is absent;
- install dependencies or run commands unless later explicitly approved;
- change workflows, settings, permissions, releases or deployment state.

If you need a durable GitHub record for the assessment, first propose the exact bounded write and obtain authority if it has not already been granted.

## Smallest sufficient response

When identifying possible findings, do not jump directly to new documentation.

Consider responses in this order:

1. retain existing material;
2. no change;
3. correct an inaccurate statement;
4. improve navigation or routing;
5. tutorial;
6. how-to guide;
7. reference;
8. explanation;
9. human authority required.

A missing document is not evidence of a reader need.

A clean documentation structure is not evidence that readers can complete their tasks.

## Required first output

Produce a concise assessment baseline containing:

### Repository identity

- repository;
- default branch;
- pinned target commit or evidence state;
- retrieval mode and material access limitations;
- toolkit commit.

### Documentation and authority map

Identify the material documentation and authority surfaces relevant to plausible reader tasks.

### Observed problems

Record:

- contradictions;
- stale or questionable claims;
- navigation problems;
- authority gaps;
- unresolved uncertainty.

Do not convert inference into fact.

### Proposed readers

List evidence-supported reader groups and the repository evidence supporting each one.

### Proposed representative tasks

For each task include:

- reader;
- task;
- evidence basis;
- starting context;
- expected entry point;
- observable completion condition;
- proposed evidence or execution mode;
- authority sources;
- relevant limitations and uncertainty.

### Proportionality check

Explain:

- what you deliberately did not inspect;
- why the proposed task set is sufficient for this first assessment;
- whether any task or process appears unnecessarily heavy.

### Human approval request

End by asking the maintainer to:

- approve, reject or modify the proposed reader groups;
- approve, reject or modify the tasks and their priority;
- approve starting contexts and completion conditions;
- approve any task that requires command execution, network access, credentials or a fresh context;
- identify protected decisions or areas where repository evidence is not authoritative.

## Mandatory stopping condition

**Stop after producing the proposed reader and task assessment.**

Do not execute the task walkthroughs yet.

Do not draft documentation.

Do not create remediation work.

The next phase begins only after the maintainer approves or revises the proposed task set.

A valid outcome of the later assessment may be that existing documentation should be retained and nothing new should be created.
