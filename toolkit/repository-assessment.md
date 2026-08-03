# Repository assessment instruction

Use this instruction to inspect an existing repository and prepare a proposed documentation assessment without changing the target repository or drafting documentation.

The instruction ends at a human approval gate. Do not execute reader tasks until that gate is satisfied.

## Reusable instruction

```text
You are assessing the documentation of an existing software repository.

Your purpose is not to generate missing documentation. Your purpose is to identify where evidence-supported readers may fail, distinguish what the repository can and cannot establish, and propose a bounded set of representative tasks for human approval.

Authority and evidence

1. Record the repository identity, default branch and pinned commit or equivalent evidence state before analysis.
2. Treat the repository as evidence, not complete truth.
3. Code, tests, schemas and executable interfaces may establish current behaviour. They rarely establish intent, priority, policy, ownership, architectural rationale or historical motivation.
4. Label material claims as Observation, Authority, Inference or Uncertainty.
5. Preserve contradictions and uncertainty. Do not reconcile them with plausible prose.

Mutation boundary

1. Do not edit, commit, push, fork, publish target content, deploy or change settings in the target repository.
2. Do not create target issues, discussions or pull requests.
3. Do not run commands, install dependencies or create local fixtures unless a later approved execution boundary permits them.
4. Do not use credentials, secrets, private user files or production data.
5. Do not draft proposed documentation changes during this assessment phase.
6. The only permitted write is the explicitly authorised, bounded assessment-record comment at the existing durable record. If no such write is authorised, return the prepared record and report the blocker.

Initial controls

1. Before inventory or analysis, set a proportionate evidence budget for required toolkit files, target documentation and authority surfaces, mutable live objects, elapsed time or interactions where useful, and material exclusions.
2. Identify the existing durable record and the bounded assessment-record comment that is authorised there.
3. Stop discovery when the required output is supported; do not consume the remaining budget merely because it is available.

Assessment work

1. Within the initial evidence budget, inventory the documentation entry points and other material authority surfaces.
2. Identify direct contradictions, stale claims and unresolved authority gaps.
3. Propose only reader groups supported by observable interfaces and documentation paths.
4. Propose a small, proportionate set of representative reader tasks.
5. Give every task a starting context, recognisable completion condition, expected documentation entry point, execution-context identity, order dependency, evidence allowlist, forbidden prior exposure, executable-prerequisite preflight disposition and reason it is material.
6. Check the proposed task pack as a whole for context or ordering conflicts, unavailable execution prerequisites and blinded-evidence leakage. Revise, defer or remove invalid tasks before requesting approval.
7. Propose the execution and safety boundary needed to test each task.
8. Identify protected decisions that require human authority.
9. State where fewer tasks, fewer readers or no further assessment may be appropriate.

Do not select tasks merely to manufacture tutorial, how-to, reference and explanation outcomes. Do not create work because a category or directory is empty.

Required output

A. Repository identity and pinned evidence state
B. Documentation and evidence inventory
C. Authority map
D. Contradictions and stale claims
E. Protected decisions and unresolved uncertainty
F. Proposed reader groups with evidence basis
G. Proposed representative tasks with starting contexts, completion conditions, execution-context allocation, ordering, evidence allowlists and prerequisite preflight dispositions
H. Proposed execution boundary and prohibited operations
I. Whole-pack consistency disposition, initial evidence budget, material exclusions, bounded assessment-record publication step, representativeness and evidence limitations
J. Human approval request

Once the required evidence is collected, stop discovery and attempt only the authorised assessment-record comment within its stated bound. If that write fails, preserve or return the prepared record and report a publication blocker. Stop after section J. Do not begin walkthrough execution until a maintainer approves or revises the reader groups, tasks, priorities, starting contexts, completion conditions, task-pack controls, evidence budget, publication stop, execution boundary and review boundary.
```

## Required assessment record

### A. Repository identity

- **Repository:**
- **Default branch:**
- **Pinned commit or evidence state:**
- **Repository type:**
- **Public or private:**
- **Inspection date:**
- **Retrieval mode:** pinned clone / connector inspection / source inspection / exact package reconstruction / other
- **Retrieval limitation:**

Do not describe connector inspection or package reconstruction as a pinned clone.

### B. Documentation and evidence inventory

Record only surfaces relevant to plausible reader outcomes.

| ID | Surface | Reader role | Claim role | Authority or limitation |
| --- | --- | --- | --- | --- |
| E1 |  |  |  |  |

Possible surfaces include:

- root and nested README files;
- contribution and development guidance;
- command help and executable interfaces;
- API signatures, schemas and configuration;
- tests and examples;
- architecture decisions, issues and pull requests;
- generated or packaged artefacts where provenance is clear.

A directory listing alone does not establish a documentation need.

### C. Authority map

For each material question, identify the strongest available authority and what it cannot prove.

| Question | Strongest available source | Established claim | Unresolved authority |
| --- | --- | --- | --- |
|  |  |  |  |

### D. Contradictions and stale claims

Record direct disagreement between documentation and authoritative behaviour or interfaces.

| ID | Documentation claim | Conflicting evidence | Claim state | Reader impact |
| --- | --- | --- | --- | --- |
| C1 |  |  | Observation / Authority / Uncertainty |  |

Do not infer which side reflects maintainer intent.

### E. Protected decisions and uncertainty

List questions the repository cannot safely resolve, including:

- intended compatibility or support policy;
- ownership and publication responsibility;
- architectural rationale;
- task priority or business value;
- historical motivation;
- whether behaviour or documentation should change.

These remain human decisions.

### F. Proposed reader groups

Use functional groups supported by repository evidence. Avoid invented organisational personas.

#### G1 — <reader group>

- **Evidence basis:**
- **Reader need:**
- **Known limitation:**

Propose fewer groups when the repository supports fewer distinct needs.

### G. Proposed representative tasks

Each task must describe an outcome, not a Diátaxis category.

#### T1 — <task>

- **Reader group:**
- **Evidence basis:**
- **Why material:**
- **Starting context:**
- **Completion condition:**
- **Expected documentation entry point:**
- **Execution-context identity:** shared / separate fresh context / named context
- **Order dependency:** none / before or after named task
- **Permitted evidence allowlist:**
- **Forbidden prior exposure:**
- **Expected evidence states:** source inspected / command executed / behaviour observed / clean-context completed / not tested
- **Executable-prerequisite preflight:** pass / fail / not required — evidence
- **Protected decisions:**

Prefer a small set of materially distinct tasks. A task is not representative merely because it is easy to execute.

### H. Proposed execution boundary

Record the operations required to test the proposed tasks.

- **Permitted read operations:**
- **Permitted clone or retrieval operations:**
- **Permitted commands:**
- **Permitted dependencies and network access:**
- **Permitted disposable writes:**
- **Credentials:** none unless explicitly authorised
- **Target state that must remain unchanged:**
- **Restoration or cleanup requirement:**
- **Prohibited operations:**

If no execution is needed, say so rather than inventing a command path.

Before proposing an executable task for approval, verify the exact pinned checkout or immutable source, runtime, dependencies, read-only credential boundary, authorised network path, disposable workspace, permitted side effects and recovery boundary. A failed preflight requires task revision, deferral or an explicit source-inspection-only proposal.

For blinded tasks, define immutable evidence objects and check whether commit titles, timelines, linked issues, broad comment retrieval or the current target state reveal the excluded outcome. If isolation cannot be established, revise the fixture or label the task non-blind before approval.

### I. Limitations and proportionality

State:

- the whole-pack consistency disposition;
- what repository types, readers or environments this assessment does not represent;
- which proposed tasks rely only on source inspection;
- which claims require execution or human knowledge;
- whether Level 1, Level 2 or Level 3 is proportionate;
- whether a smaller assessment or no further work is justified.

Set and report an initial evidence budget covering:

- toolkit files required by the selected path;
- target documentation and authority surfaces;
- mutable live objects;
- elapsed time or interactions where they provide a useful bound;
- material evidence excluded by the budget.

The budget limits exploration, not the claims required for a finding. Once the required assessment record is complete, stop discovery and perform only the authorised bounded assessment-record write. This write records the assessment in the existing durable record; it does not authorise target-content publication or deployment. If the write fails, preserve or return the prepared record and report the blocker rather than continuing to inspect.

### J. Human task-approval gate

Request an explicit decision.

```text
Decision: Approved / Approved with changes / Rejected

Approved reader groups:
Approved tasks and priority:
Approved starting contexts and completion conditions:
Approved task ordering and execution-context allocation:
Approved evidence allowlists and forbidden prior exposure:
Executable-task preflight dispositions:
Approved execution boundary:
Approved evidence budget and publication stop:
Approved review boundary:
Protected decisions:
Required changes:
Decision authority and record:
```

Do not execute walkthroughs while this decision is absent, rejected or materially inconsistent with the proposal.
