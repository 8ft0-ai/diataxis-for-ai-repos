# Reader-task discovery

Representative tasks are the decision unit for this toolkit. They connect repository evidence to observable reader outcomes without assuming that a missing page or empty Diátaxis category requires new documentation.

Use this method after the initial repository assessment and before any walkthrough execution.

## 1. Identify evidence-supported reader groups

A reader group is justified when the repository exposes a distinct interface, entry point or responsibility that a reader must use.

Evidence may include:

- installation and first-use paths;
- commands, APIs or configuration surfaces;
- contribution and test instructions;
- operational procedures;
- architecture or design records;
- generated outputs intended for interpretation;
- maintenance or release interfaces.

Describe functional needs, not invented personas.

Good examples:

- first-time CLI user;
- API integrator;
- contributor running the test suite;
- operator changing a documented configuration;
- analyst interpreting a repository-produced result.

Weak examples:

- “busy developer” without repository evidence;
- organisational roles inferred from file names;
- audiences selected only to fill tutorial, how-to, reference and explanation categories.

### Reader-group record

```md
### G1 — <functional reader group>

- Evidence basis:
- Interface or documentation path used:
- Reader need:
- Known limitation:
- Claims requiring human authority:
```

A repository may support one reader group. Do not add groups for symmetry.

## 2. Propose reader outcomes, not document types

A representative task states what a reader is trying to achieve.

Prefer:

- install the package and produce a recognisable first result;
- find the exact option needed to include hidden files;
- configure the service for a documented deployment mode;
- understand which output field is authoritative;
- run the contributor test path from a clean environment.

Avoid:

- read the tutorial;
- find the how-to guide;
- inspect the reference section;
- create an explanation page.

Diátaxis classification occurs after the task evidence shows what response is needed.

## 3. Apply the task-selection criteria

A task should satisfy all of these criteria unless the maintainer records a justified exception.

### Evidence-supported

The repository exposes an interface, claim, workflow or outcome that makes the task plausible.

### Material

Failure would prevent completion, produce an incorrect result, create a meaningful authority gap or impose a recurring maintenance risk.

### Distinct

The task exercises a reader need not already covered by another task. Several commands that test the same documentation claim may belong in one task.

### Bounded

The starting context, completion condition and execution boundary can be stated clearly.

### Observable

The assessor can distinguish complete, partial, blocked and not-tested outcomes using repository or execution evidence.

### Proportionate

The likely decision value is worth the assessment and future maintenance burden.

## 4. Define the starting context

The starting context describes what the representative reader can reasonably know or access before beginning.

Record:

- prior competence assumed;
- environment and tools already available;
- repository state or release used;
- credentials or access assumed;
- documentation entry point supplied;
- knowledge deliberately not assumed.

Examples:

- “A competent Python user with a clean virtual environment, the repository URL and no prior project knowledge.”
- “A maintainer with the repository checked out at the pinned commit and access only to checked-in contributor guidance.”

Do not silently grant the reader knowledge discovered during the assessment.

## 5. Define a recognisable completion condition

A completion condition must allow another reviewer to determine whether the task succeeded.

Good completion conditions:

- a named command exits successfully and creates the documented output;
- the reader selects the correct flag combination and predicts the resulting file set;
- the contributor installs declared dependencies and the full test suite completes;
- the reader identifies the canonical schema and uses the correct field definition.

Weak completion conditions:

- “understands the project”;
- “documentation is clearer”;
- “has enough information” without an observable outcome.

A task may be blocked because the repository lacks authority. That is a valid result.

## 6. Record the expected entry point

State where the reader is expected to begin:

- root README;
- command help;
- contribution guide;
- API reference;
- architecture index;
- an existing linked document.

The assessment should record the actual path separately. Do not rewrite the expected path after observing the result.

## 7. Choose a proportionate task set

Use the smallest task set that exercises distinct material reader needs.

A useful Level 2 set often contains three to six tasks, but the evidence may justify fewer.

Consider including, where supported:

- an unfamiliar-reader starting task;
- a real usage or operational task;
- an exact interface or reference lookup;
- a failure, compatibility or troubleshooting path;
- a contributor or maintainer task.

Do not include one of each merely to satisfy a matrix.

### Cases where fewer tasks are correct

Use fewer tasks when:

- the repository exposes only one material reader path;
- several candidate tasks rely on the same claim and outcome;
- execution risk exceeds likely documentation value;
- the current question is a narrow Level 1 correction;
- authoritative evidence is unavailable.

### Cases where no further assessment is correct

Stop when:

- existing documentation already supports the material reader need;
- the proposed task is hypothetical and lacks evidence;
- the task depends on undocumented intent or policy;
- no safe completion condition exists;
- the likely response would be disproportionate;
- the task would require prohibited access, mutation or publication.

## 8. Proposed task record

```md
### T1 — <reader outcome>

- Reader group:
- Evidence basis:
- Why this task is material:
- Starting context:
- Completion condition:
- Expected documentation entry point:
- Expected execution-evidence states:
- Required environment or dependencies:
- Proposed retrieval and execution mode:
- Proposed execution boundary:
- Protected decisions and uncertainty:
- Representativeness limitation:
```

## 9. Review the proposed set before approval

Check:

- Does each group have repository evidence?
- Does each task describe a reader outcome?
- Are starting contexts realistic and distinct?
- Are completion conditions observable?
- Are tasks materially different?
- Does the set avoid predetermining a Diátaxis form?
- Could one task or reader be removed without reducing decision value?
- Are unsafe or authority-dependent tasks marked for stopping?
- Is the adoption level proportionate?

## 10. Human task-approval checkpoint

The maintainer must approve or revise the task set before execution.

Record:

```md
## Human task-approval decision

Decision: Approved / Approved with changes / Rejected
Approved reader groups:
Approved tasks and priority:
Approved starting contexts:
Approved completion conditions:
Approved execution boundary:
Approved review boundary:
Protected decisions:
Required changes:
Approved by:
Decision URL or repository record:
Date:
```

Approval is not permission to broaden the tasks later. If execution shows that a task is invalid, unsafe or unsupported, stop and record the discovery. Do not substitute an easier task without new authority.