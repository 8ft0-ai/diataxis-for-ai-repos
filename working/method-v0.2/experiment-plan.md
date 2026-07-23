# Experiment plan record

Use this record to prepare a Level 2 or Level 3 repository documentation assessment under the [working method v0.2](README.md).

The plan is not authority to execute tasks until the human task-approval decision is recorded as approved. Keep material decisions in the repository or issue system so another reviewer can reconstruct the experiment without private chat history.

## 1. Experiment identity

- **Experiment name:**
- **Parent stage or planning issue:**
- **Execution contract:**
- **Method version or commit:**
- **Prepared by:**
- **Preparation date:**
- **Adoption level:** Level 1 / Level 2 / Level 3

## 2. Target repository

- **Repository:**
- **Pinned commit:**
- **Default branch at assessment:**
- **Repository type:**
- **Public or private:**
- **Assessment mode:** source inspection / command execution / runtime observation / other

### Selection rationale

Explain why this target is suitable for the question being tested. Include the observable characteristics that support selection.

Do not select a target merely because it appears likely to produce every Diátaxis form or a large remediation backlog.

### Representativeness limitations

Record which repository types, users, environments or operating conditions this target does not represent.

## 3. Evidence inventory and authority map

Record only evidence material to the proposed reader tasks.

| ID | Source | Claim role | Authority or limitation |
| --- | --- | --- | --- |
| E1 |  |  |  |

Use claim states consistently:

- **Observation** — directly visible in repository evidence or an executed result.
- **Authority** — established by a canonical interface, decision, policy or designated source.
- **Inference** — a reasoned conclusion not directly established.
- **Uncertainty** — a question the available evidence cannot resolve.

### Contradictions or stale claims

Record direct conflicts between documentation, executable interfaces, configuration, schemas, tests or other authority surfaces.

Do not convert disagreement into inferred intent.

### Protected decisions and unresolved authority

List intent, policy, priority, rationale, ownership or historical questions that the repository cannot establish.

## 4. Proposed reader groups

Include only functional groups supported by observable repository interfaces and documentation paths. Do not invent organisational personas.

### G1 — <reader group>

- **Evidence basis:**
- **Reader need:**
- **Known limitations:**

### G2 — <reader group>

- **Evidence basis:**
- **Reader need:**
- **Known limitations:**

Add further groups only where the evidence justifies them.

## 5. Proposed representative tasks

Each task must describe a reader outcome rather than a documentation category.

### T1 — <task>

- **Reader group:**
- **Why this task is material:**
- **Starting context:**
- **Completion condition:**
- **Expected documentation entry point:**
- **Expected execution-evidence states:**
- **Protected decisions:**

### T2 — <task>

- **Reader group:**
- **Why this task is material:**
- **Starting context:**
- **Completion condition:**
- **Expected documentation entry point:**
- **Expected execution-evidence states:**
- **Protected decisions:**

Add tasks only when they exercise a distinct, evidence-supported reader need. A smaller set is acceptable.

## 6. Execution and safety boundary

### Permitted operations

List the exact read, clone, install, build, test, runtime or fixture operations allowed.

- 

### Permitted network access

- **Allowed endpoints or purposes:**
- **Dependency sources:**
- **Credentials permitted:** none unless explicitly authorised

### Permitted local writes

List disposable environments, fixtures, caches or generated outputs that may be created and where they will live.

### Local side-effect plan

Classify the effect and recovery boundary before running commands that may create local files.

- **Side-effect class:** protected / tracked source / generated local
- **Expected local side effects:**
- **Permitted generated paths:**
- **Tracked files that must remain unchanged:**
- **Recovery if observed:** stop and escalate / restore and continue / clean at close-out
- **Conditions requiring escalation:**

Use the [working method mutation classes](README.md#local-execution-effects-and-target-state). An expected Class C artefact becomes Class B when it appears outside the planned path but remains bounded and recoverable. Escalate to Class A when the effect escapes the disposable boundary, changes remote or protected state, cannot be confidently bounded, or cannot be safely restored.

### Prohibited operations

State protected side effects explicitly, including as applicable:

- editing tracked target files;
- committing, pushing, forking or publishing;
- creating target issues, discussions or pull requests;
- changing repository settings, workflows, permissions or branch protection;
- using credentials, secrets, private files or production data;
- deployment, release or publication;
- inferring undocumented intent from code or outputs.

### Immutability and safe-operation evidence

Record the protected target, canonical source and disposable generated-output boundaries separately.

- **Remote target starting-state check:**
- **Canonical tracked-source starting-state check:**
- **Expected generated-output boundary:**
- **Workspace restoration method:**
- **Final remote target check:**
- **Final canonical tracked-source check:**
- **Final disposable workspace check:**

A clean final workspace may be required by the contract. It does not need to remain continuously clean while explicitly approved commands execute inside the disposable boundary.

## 7. Review boundary

- **Reviewer type:** different human / different agent session / same account fresh pass / other
- **Independence limitations:**
- **Tasks to repeat:**
- **Evidence supplied to reviewer:**
- **Review questions:**
  - Are the reader groups evidence-supported?
  - Are the tasks representative and materially distinct?
  - Are execution-evidence states accurate?
  - Do findings follow from evidence?
  - Is the classification the smallest sufficient response?
  - Was unsupported intent preserved as uncertainty?
  - Was the process useful and proportionate?
  - Is the close-out recommendation justified?

A separate review is not human validation unless a human actually performs it.

## 8. Human task-approval decision

This is the gate between planning and execution.

### Decision

- [ ] Approved
- [ ] Approved with changes
- [ ] Rejected

### Approved reader groups

- 

### Approved tasks and priority

- 

### Approved starting contexts and completion conditions

- 

### Approved execution boundary

- 

### Approved review boundary

- 

### Required changes from the proposal

- 

### Decision authority and record

- **Approved by:**
- **Decision URL or reference:**
- **Decision date:**

Do not execute walkthroughs while this decision is incomplete, rejected or materially inconsistent with the proposed tasks.

## 9. Stopping conditions for this experiment

In addition to the method-level stopping conditions, stop when:

- the pinned commit cannot be obtained or verified;
- an approved task would require a prohibited operation;
- credentials, private data, publication or deployment become necessary without authority;
- the actual target interface materially differs from the approved evidence basis;
- a task must be silently redefined to make it executable;
- required validation cannot distinguish success from failure;
- a Class A protected or unbounded mutation occurs;
- a Class B effect cannot be confidently bounded, restored or verified inside the original authority boundary.

Expected Class C artefacts and recoverable Class B deviations do not require full maintainer reauthorisation when the approved recovery conditions are satisfied. Record them accurately and preserve the evidence already produced.

Record the blocker and request the exact decision needed when escalation is required. Do not substitute a different task or broaden the experiment without approval.

## 10. Readiness for execution

- **Dependencies satisfied:** yes / no
- **Method version available:** yes / no
- **Target commit verified:** yes / no
- **Task approval complete:** yes / no
- **Execution boundary complete:** yes / no
- **Local side-effect plan complete:** yes / no
- **Review boundary complete:** yes / no
- **Safe starting state recorded:** yes / no
- **Decision:** Ready to execute / clarification required / blocked

Execution begins only after the governing execution contract also records readiness and an implementation or execution plan.
