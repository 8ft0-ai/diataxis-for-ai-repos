# Classification and bounded remediation

Classify the reader need only after the approved task has been walked or the relevant evidence has been inspected.

Diátaxis helps choose the form of a justified response. It is not a four-folder completion checklist.

## 1. Apply the evidence gate

A documentation response requires at least one observed basis:

- a reader task did not reach its completion condition;
- an existing claim conflicts with authoritative behaviour or an interface;
- the reader cannot locate useful existing material;
- an authority gap prevents safe action;
- the current documentation creates a material maintenance risk.

Do not create work because:

- a page or directory is missing;
- one of the four Diátaxis categories is empty;
- a generated structure would look more complete;
- plausible prose can be inferred from code;
- another repository has a document this repository lacks.

## 2. Choose the smallest sufficient response

Consider responses in this order. Stop at the first response that resolves the observed need without exceeding the evidence.

### 1. Retain

Use when the existing path is useful, sufficiently correct and supports the task.

Record the evidence and any limitation. Do not rewrite useful material for stylistic symmetry.

### 2. No change

Use when the evidence does not justify a documentation change.

Examples:

- the task completed through the existing path;
- a proposed audience or task is unsupported;
- the maintenance burden would exceed likely reader value;
- the question belongs to policy or product intent rather than documentation.

### 3. Correction

Use for a stale, incorrect, contradictory or misleading claim in an existing surface.

Prefer correction over a new page when the failure is local.

### 4. Navigation

Use when useful material exists but the reader cannot find or recognise the correct path.

The response may be a link, routing paragraph, index entry or clearer entry-point label.

### 5. Tutorial

Use only when an unfamiliar reader needs a guided sequence from a defined starting point to a recognisable learning outcome.

A tutorial is not simply a long installation guide. It prioritises learning through a controlled path.

### 6. How-to guide

Use when a competent reader needs to complete a real task, including prerequisites, choices and likely failure modes.

A how-to guide is task-oriented, not a general tour of the system.

### 7. Reference

Use for exact commands, options, schemas, APIs, configuration fields or other canonical contracts.

Reference claims require authoritative interfaces and should be mechanically checked where practical.

### 8. Explanation

Use when readers need concepts, context, trade-offs or rationale and authoritative source material exists.

Do not invent architectural history or motivation from implementation details.

### 9. Human authority required

Use when the next step depends on intent, policy, priority, ownership, support commitments or rationale that the repository cannot establish.

Stop. Record the exact decision needed and the inference that must not be made.

## 3. Diátaxis classification rubric

The four forms are distinguished by reader need and validation, not directory location.

| Form | Reader need | Evidence required | Typical failure | Validation |
| --- | --- | --- | --- | --- |
| Tutorial | Learn by completing a guided sequence | Evidence that an unfamiliar reader needs a defined learning path | Hidden context, missing sequence or no recognisable outcome | Repeat from the defined starting point and reach the stated outcome |
| How-to | Complete a real task | An approved task with prerequisites, choices and failure modes | Procedure incomplete, unsafe or not executable | Perform the real task in the intended environment |
| Reference | Look up exact facts or interfaces | Canonical commands, schemas, APIs, configuration or executable contracts | Claim stale, incomplete or inconsistent with authority | Check each material claim against the canonical interface |
| Explanation | Understand concepts or rationale | Decision records, issues, source material or authorised human knowledge | Context absent or concepts disconnected | Check rationale against authoritative sources; preserve uncertainty |

A task may justify a correction or navigation response rather than one of these four forms.

## 4. Record the finding precisely

A finding describes an observable condition, not a general judgement.

```md
### F1 — <finding title>

- Affected reader and task:
- Starting context:
- Expected path or claim:
- Observed path or behaviour:
- Completion gap or maintenance risk:
- Supporting evidence:
- Claim state: Observation / Authority / Inference / Uncertainty
- Why action may be justified:
- Protected decisions:
```

Do not write “documentation is incomplete” without naming the task, missing evidence and completion effect.

## 5. Create a bounded remediation item

Every remediation item must trace to a finding, correctness problem, authority gap or maintenance risk.

```md
### R1 — <bounded remediation title>

- Reader and approved task:
- Finding or authority gap:
- Exact evidence:
- Smallest sufficient response:
- Proposed scope:
- Deliberate exclusions:
- Permitted claims:
- Claims or decisions requiring human authority:
- Validation:
- Stopping conditions:
- Priority decision: human-controlled / already authorised
```

The assessment should describe the change boundary, not draft the final documentation unless a later issue explicitly authorises drafting.

## 6. Bound permitted claims

For each item, separate what can be said from what remains protected.

### Permitted claims

May be based on:

- observed current behaviour;
- canonical command or interface definitions;
- declared configuration or schema;
- explicit maintainer decisions;
- reproducible task evidence.

### Protected claims

Require human authority when they concern:

- intended behaviour rather than observed behaviour;
- support or compatibility policy;
- ownership and priority;
- architectural rationale;
- historical motivation;
- publication or operating policy;
- whether code or documentation should change.

Code can show that two surfaces disagree. It does not decide which surface expresses intent.

## 7. State deliberate exclusions

Bounded work should say what it will not do.

Examples:

- correct one option description without redesigning option semantics;
- add a route to existing guidance without reorganising the documentation tree;
- record an authority decision without inventing the decision;
- update one interface reference without creating a general tutorial;
- preserve an existing working path without rewriting it.

Deliberate exclusions prevent a local finding from becoming a speculative documentation programme.

## 8. Match validation to the response

- **Correction:** repeat the affected lookup or task and confirm the revised claim matches authority.
- **Navigation:** begin at the original entry point and confirm the reader reaches the useful existing material.
- **Tutorial:** start as the defined unfamiliar reader and reach the recognisable outcome without hidden context.
- **How-to:** complete the real task with prerequisites, choices and failure modes represented.
- **Reference:** compare material claims with canonical interfaces, schemas or commands.
- **Explanation:** compare concepts and rationale with decision records or authorised knowledge.
- **Retain:** record why the existing path completed the task and what limitation remains.
- **No change:** record why the evidence or proportionality test does not justify work.
- **Human authority required:** verify that the decision request names the missing authority and forbids unsupported inference.

The drafting agent’s own reread is not independent validation.

## 9. Stop conditions

Stop or classify as no change when:

- no evidence-supported reader need exists;
- the task completed and no correctness or maintenance risk remains;
- the proposed response exceeds the observed failure;
- the next claim requires undocumented intent;
- required authority or validation is unavailable;
- the task is too low-value for the maintenance burden;
- safe execution would exceed the approved boundary;
- a new page would duplicate useful existing material.

Stopping is not a failed assessment. It is evidence that the gate worked.

## 10. Review the backlog as a whole

Before close-out, check:

- Does every item trace to a named reader task or material correctness risk?
- Is the response the smallest sufficient one?
- Are retain and no-change outcomes represented where supported?
- Are protected decisions explicit?
- Are document types selected by reader need rather than symmetry?
- Are scope, exclusions and validation clear enough for a later execution contract?
- Could any item be removed without leaving an observed failure unresolved?

A shorter, better-grounded backlog is preferable to a complete-looking one.