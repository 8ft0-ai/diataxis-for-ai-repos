# Assessment close-out template

Use this record to close a repository documentation assessment after the approved evidence work is complete.

The record should be proportionate to the adoption level. Do not fill unused Level 3 fields with invented content.

## How to use the template by level

### Level 1

Complete only:

- assessment identity;
- narrow reader need;
- evidence and claim states;
- classification decision;
- validation;
- limitations and next action.

Mark task-walkthrough, mutation-event and comparative sections as **Not applicable — Level 1** when they are not needed.

### Level 2

Complete:

- assessment identity and environment;
- approved readers and tasks;
- compact task results;
- findings and bounded remediation;
- retain, no-change and authority-required decisions;
- validation, review boundary and limitations;
- next decision.

A separate review is useful but is not mandatory unless the approved plan requires it.

### Level 3

Complete the full record, including:

- execution contract and safe starting state;
- mutation and recovery events;
- separate evidence review;
- usefulness and proportionality;
- comparative observations where applicable;
- Adopt, Adapt or Reject when evaluating the method;
- human acceptance record.

## 1. Assessment identity

- **Assessment name:**
- **Target repository:**
- **Pinned commit or evidence state:**
- **Assessment date:**
- **Assessor:**
- **Adoption level:** Level 1 / Level 2 / Level 3
- **Method or toolkit version:**
- **Approved plan or decision:**
- **Execution contract:** Not applicable / reference

### Decision question

> What documentation decision is this assessment intended to support?

### Scope and non-goals

- **Included:**
- **Excluded:**
- **Target mutation permitted:** no / exact authority
- **Documentation drafting permitted:** no / exact authority

## 2. Evidence and environment summary

- **Retrieval modes used:**
- **Operating system, container or sandbox:**
- **Language, runtime and tool versions:**
- **Declared dependency versions:**
- **Resolved dependency versions:**
- **Network access used:**
- **Credentials or secrets used:** none / authority
- **Disposable fixture and output locations:**
- **Durable command/result record:**
- **Material limitations:**

### Evidence register

| ID | Evidence | Retrieval or execution mode | Claim role | Limitation |
| --- | --- | --- | --- | --- |
| E1 |  |  | Observation / Authority / Inference / Uncertainty |  |

## 3. Target state and local effects

For Level 1 source-only work, write **Not applicable — no executable walkthrough** where appropriate.

- **Remote target unchanged:** yes / no / not verified — evidence
- **Canonical tracked source unchanged:** yes / no / not verified — evidence
- **Generated local artefacts:** none / list
- **Disposable workspace restored:** yes / no / not required — evidence
- **Target GitHub objects changed:** none / incident reference

### Event register

| ID | Operation or task | Event class | Effect boundary | Observed effect | Evidence | Recovery or escalation | Final state |
| --- | --- | --- | --- | --- | --- | --- | --- |
| M1 |  | A / B / C | remote or protected / canonical tracked source / generated local |  |  |  |  |

Use **Not applicable — no material local or remote effect** when the assessment involved only read-only evidence inspection.

## 4. Approved readers and tasks

- **Approved reader groups:**
- **Approved task set:**
- **Approval record:**
- **Material deviations:** none / discovery and authority

For Level 1, state the affected reader need instead of inventing a task set.

## 5. Compact task results

Copy for each approved task. Omit this section for a narrow Level 1 classification.

```md
### T1 — <task>

- Reader group:
- Starting context:
- Completion condition:
- Expected entry point:
- Actual path:
- Durable commands or interactions:
- Retrieval mode:
- Runtime and dependency versions:
- Execution-evidence states:
- Primary result: Complete / Partial / Blocked / Not tested
- Observable friction:
- Supporting evidence:
- Protected decisions and uncertainty:
- Smallest sufficient response:
- Finding ID: none / F1
- Limitations:
```

## 6. Findings

Record only observable task failures, correctness problems, authority gaps or maintenance risks.

```md
### F1 — <finding>

- Affected reader and task:
- Expected path or claim:
- Observed condition:
- Completion gap or risk:
- Evidence:
- Claim state:
- Why action may be justified:
- Protected decisions:
```

If no material finding exists, write **No finding — retain or no-change evidence recorded below**.

## 7. Bounded remediation backlog

```md
### R1 — <bounded item>

- Reader and task:
- Finding or authority gap:
- Evidence:
- Smallest sufficient response:
- Proposed scope:
- Deliberate exclusions:
- Permitted claims:
- Human-authority needs:
- Validation:
- Stopping conditions:
```

Do not draft the proposed change unless a separate execution contract authorises drafting.

If no work is justified, write **No remediation item — evidence supports retention or no change**.

## 8. Retain, no-change and authority-required decisions

### Retain

```md
#### K1 — <retained path>

- Reader task or need:
- Evidence:
- Reason to retain:
- Limitation:
```

### No change

```md
#### N1 — <candidate not pursued>

- Candidate change:
- Evidence considered:
- Reason not justified:
- Proportionality or authority boundary:
```

### Human authority required

```md
#### A1 — <authority gap>

- Decision required:
- Why repository evidence is insufficient:
- Permitted next action:
- Forbidden inference:
- Decision owner:
```

Use only the outcomes supported by the assessment. Do not manufacture one of each.

## 9. Validation

For each proposed response, record the matching validation.

| Item | Response type | Validation performed | Result | Limitation |
| --- | --- | --- | --- | --- |
| R1 / K1 / N1 |  |  | Pass / Fail / Not performed |  |

Examples:

- correction checked against the canonical interface;
- navigation repeated from the original entry point;
- tutorial repeated from an unfamiliar starting context;
- how-to executed in the intended environment;
- retain supported by task completion;
- no change supported by evidence or proportionality.

## 10. Evidence review

- **Reviewer:**
- **Reviewer type:** independent human / different agent or session / same account fresh pass / not performed
- **Independence limitation:**
- **Evidence supplied:**
- **Tasks repeated:**

### Judgements

- **Reader groups:** Accept / Revise / Reject / Not reviewed
- **Tasks:** Accept / Revise / Reject / Not reviewed
- **Evidence states:** Accept / Revise / Reject / Not reviewed
- **Findings and classifications:** Accept / Revise / Reject / Not reviewed
- **Usefulness and proportionality:** Accept / Revise / Reject / Not reviewed

Do not label a same-agent review as human validation.

## 11. Usefulness and proportionality

For Level 2 and Level 3, answer:

- Did task evidence improve the documentation decision?
- Did the evidence gate prevent unsupported drafting?
- Did the assessment retain useful material and permit no change?
- Was the chosen adoption level proportionate?
- Which fields materially supported the decision?
- Which fields could be omitted next time?

For Level 1, a one-paragraph proportionality note is sufficient.

## 12. What was proven and remains unproven

### Supported by this assessment

- 

### Not established

- 

Do not generalise from one repository or one agent beyond the evidence.

## 13. Comparative observations

Use only for a series or method evaluation. Otherwise write **Not applicable**.

- **Difference from earlier assessments:**
- **Method components retained:**
- **Method components adapted:**
- **Did execution change a source-inspection conclusion:**
- **Did review change a finding or classification:**
- **Adoption-level boundary supported or challenged:**

## 14. Groundedness review

### Did we do what was needed?

- **Assessment:**
- **Evidence:**
- **Unmet items:**

### Did we only do what was asked?

- **Assessment:**
- **Evidence:**
- **Out-of-scope work:**

## 15. Recommendation and next decision

For routine assessments, state the recommended documentation action and next decision.

For method evaluation, choose exactly one:

- **Adopt** — retain the method substantially as tested.
- **Adapt** — retain the useful method but change named parts.
- **Reject** — the method did not produce sufficient decision value or cannot be made proportionate without fundamental change.

- **Decision or recommendation:**
- **Rationale:**
- **Limitations:**
- **Next decision question:**
- **Human acceptance:** pending / record
- **Decision URL or repository record:**
- **Date:**

The assessment recommendation is evidence for a decision. It does not replace human acceptance.