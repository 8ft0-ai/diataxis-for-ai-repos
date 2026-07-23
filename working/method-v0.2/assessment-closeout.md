# Assessment and close-out record

Use this record after the experiment plan has received the required human approval under the [working method v0.2](README.md).

This document combines task-path evidence, findings, bounded remediation, separate review and the final recommendation. Keep the record compact, but preserve enough evidence for another reviewer to reconstruct the result.

## 1. Experiment summary

- **Experiment name:**
- **Target repository:**
- **Pinned target commit:**
- **Method version or commit:**
- **Approved plan:**
- **Execution contract:**
- **Assessment date:**
- **Assessor:**
- **Adoption level:** Level 1 / Level 2 / Level 3

### Question under test

State the decision question this assessment is intended to answer.

### Environment and execution boundary

- **Operating system or container:**
- **Language and tool versions:**
- **Dependency installation:**
- **Network access used:**
- **Disposable fixture and output locations:**
- **Credentials or secrets used:** none / describe explicit authority
- **Prohibited operations confirmed:**

### Target state and local side-effect evidence

Record remote state, canonical source and disposable local effects separately. Do not collapse them into one clean or dirty result.

- **Starting commit check:**
- **Remote target unchanged:** yes / no / not verified — evidence
- **Canonical tracked source unchanged:** yes / no / not verified — evidence
- **Generated local artefacts observed:** none / list paths and cause
- **Disposable workspace restored:** yes / no / not required — evidence
- **Final working-tree or source-state check:**
- **Target GitHub objects changed:** none / describe Class A incident and remediation
- **Mutation or side-effect classification:** none / Class A / Class B / Class C
- **Incident or deviation record:**

A workspace may become temporarily dirty while approved commands run. Record expected Class C artefacts and recoverable Class B deviations accurately. A clean final state may still be required by the approved plan.

## 2. Evidence register

Record material repository and execution evidence. Use stable paths, commit links, command names and concise result references.

| ID | Evidence | Claim role | State or limitation |
| --- | --- | --- | --- |
| E1 |  |  |  |

### Claim-state rules

- **Observation:** directly visible in repository evidence or an executed result.
- **Authority:** established by a canonical interface, explicit decision, policy or designated source.
- **Inference:** a reasoned conclusion not directly established.
- **Uncertainty:** a question the available evidence cannot resolve.

Do not present inferred intent, priority, policy or rationale as authority.

## 3. Approved readers and tasks

- **Approved reader groups:**
- **Approved task set:**
- **Approval decision:**
- **Material deviations:** none / record the discovery and authority

If an approved task was changed, stopped or replaced, cite the decision that authorised it. Do not normalise an unapproved deviation after the fact.

## 4. Compact task records

Copy this section once for each approved task.

### T1 — <task>

- **Reader group:**
- **Starting context:**
- **Completion condition:**
- **Expected documentation entry point:**
- **Actual path followed:**
- **Commands or interactions:**
- **Local side effects and recovery:** none / Class B / Class C — evidence
- **Execution-evidence states:**
  - [ ] Source inspected
  - [ ] Command executed
  - [ ] Behaviour observed
  - [ ] Clean-context completed
  - [ ] Separately reviewed
  - [ ] Human validated
  - [ ] Not tested
- **Primary result:** Complete / Partial / Blocked / Not tested
- **Observable friction:**
- **Supporting evidence:**
- **Protected decisions and uncertainty:**
- **Smallest sufficient response:** Retain / No change / Correction / Navigation / Tutorial / How-to / Reference / Explanation / Human authority required
- **Finding ID:** none / F1
- **Limitations:**

Evidence states are non-exclusive. Select only states supported by what was actually performed.

A successful command is not automatically clean-context completion. Source inspection is not runtime observation. A fresh agent review is not human validation. Expected or recovered local effects do not by themselves mean the remote target or canonical source changed.

## 5. Findings

Describe observable task failures, correctness problems, authority gaps or maintenance risks. Do not write that documentation is merely “poor”, “incomplete” or “confusing”.

### F1 — <finding>

- **Affected task:**
- **Observed condition:**
- **Completion gap or risk:**
- **Evidence:**
- **Claim state:** Observation / Authority / Inference / Uncertainty
- **Why documentation action may be justified:**

Add findings only when the task evidence supports them.

## 6. Bounded remediation backlog

Each item must trace to a finding, correctness problem, authority gap or maintenance risk.

### R1 — <bounded item>

- **Reader and task:**
- **Finding:**
- **Evidence:**
- **Smallest sufficient response:**
- **Proposed scope:**
- **Deliberate exclusions:**
- **Permitted claims:**
- **Human-authority needs:**
- **Validation:**
- **Stopping conditions:**

Do not draft the proposed documentation as part of an assessment-only experiment unless the execution contract explicitly authorises drafting.

## 7. Retain, no-change and authority-required decisions

### Retain

Record useful existing paths that should remain substantially as they are.

#### K1 — <retained path>

- **Task evidence:**
- **Reason to retain:**
- **Validation or limitation:**

### No change

Record candidate work that the evidence does not justify.

#### N1 — <no-change decision>

- **Candidate change considered:**
- **Reason not justified:**
- **Evidence or proportionality boundary:**

### Human authority required

Record work that cannot proceed safely without intent, policy, priority, ownership or rationale from an authorised human source.

#### A1 — <authority gap>

- **Question requiring authority:**
- **Why repository evidence is insufficient:**
- **Permitted next action:**
- **Forbidden inference:**

## 8. Separate evidence review

### Review identity and boundary

- **Reviewer:**
- **Reviewer type:** different human / different agent session / same account fresh pass / other
- **Independence limitations:**
- **Evidence supplied:**
- **Tasks repeated:**

### Review judgements

#### Reader groups

- **Judgement:** Accept / Revise / Reject
- **Reason:**

#### Representative tasks

- **Judgement:** Accept / Revise / Reject
- **Reason:**

#### Evidence states and task results

- **Judgement:** Accept / Revise / Reject
- **Reason:**

#### Findings and classifications

- **Judgement:** Accept / Revise / Reject
- **Reason:**

#### Usefulness and proportionality

- **Judgement:** Accept / Revise / Reject
- **Reason:**

#### Close-out recommendation

- **Judgement:** Accept / Revise / Reject
- **Reason:**

### Review findings requiring action

- **Required fixes:**
- **Optional improvements:**
- **Clarifications needed:**
- **Out-of-scope observations:**

A same-account or same-agent review must not be described as independent human validation.

## 9. Usefulness and proportionality

Assess the method, not only the target documentation.

- Did task evidence improve the documentation decision?
- Did the process distinguish observable failure from general criticism?
- Did the evidence gate prevent unsupported drafting?
- Did the method retain useful material and permit no-change outcomes?
- Which fields were essential to the decision?
- Which fields duplicated evidence or created unnecessary burden?
- Was the selected adoption level proportionate?
- Would a real maintainer reasonably use this process for a repository of this size and risk?

## 10. Limitations

Record limitations such as:

- repository type and scale;
- untested environments or interfaces;
- source-only claims;
- missing clean-context evidence;
- external dependencies or network variability;
- reviewer independence;
- unvalidated reader priority;
- evidence outside the repository;
- unresolved intent or policy.

Do not hide limitations inside a confidence score.

## 11. Comparative observations

Where the experiment belongs to a series, record evidence that will support later comparison.

- **What was materially different from the earlier experiment:**
- **What method components survived unchanged:**
- **What method components required adaptation:**
- **Did execution change a source-inspection conclusion:**
- **Did human task approval change the task set or priority:**
- **Did separate review change a finding or classification:**
- **Which adoption-level boundary was supported or challenged:**

Do not make the final cross-experiment decision here unless the governing stage authorises it.

## 12. Groundedness review

### Did we do what was needed?

Compare the completed work with the approved task set, execution boundary, acceptance criteria and required review.

- **Assessment:**
- **Evidence:**
- **Unmet items:**

### Did we only do what was asked?

Check changed files, commands, target mutations, speculative work, automation and authority boundaries.

- **Assessment:**
- **Evidence:**
- **Out-of-scope work:**

## 13. Recommendation

Choose exactly one:

- **Adopt** — retain the tested method substantially as used.
- **Adapt** — retain the useful method but change named parts before further adoption.
- **Reject** — the method did not produce sufficient decision value or cannot be made proportionate without fundamental change.

### Decision

**Adopt / Adapt / Reject**

### Rationale

State what the evidence supports, what remains unproven and why the selected decision is stronger than the alternatives.

### Method components to retain

- 

### Method components to adapt or reject

- 

### Next decision question

> 

### Human acceptance

- **Accepted / revised / rejected by:**
- **Decision record:**
- **Date:**

The assessment recommendation is evidence for a decision. It does not replace human acceptance.
