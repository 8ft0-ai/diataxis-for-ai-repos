# Evidence, provenance and validation

The toolkit depends on accurate distinctions between what was inspected, what was executed, what authority exists and what remains uncertain.

Do not collapse these distinctions into a single confidence score.

## 1. Claim states

Use one of these labels for each material statement.

### Observation

Directly visible in repository evidence or an executed result.

Examples:

- a README contains a named claim;
- a command produced a recorded output;
- a test failed under the recorded dependency version.

### Authority

Established by a canonical interface, policy, decision record, explicit maintainer statement or other designated source.

Examples:

- an approved issue defines the execution boundary;
- an API schema defines a field;
- command help defines the supported option name.

Authority is contextual. A source may be authoritative for current behaviour but not for intent.

### Inference

A reasoned conclusion not directly established by authority.

Use inference sparingly and label it clearly. Do not let inference silently become project history or policy.

### Uncertainty

A question the available evidence cannot resolve.

Examples:

- whether code or documentation should change;
- which dependency range a maintainer intends to support;
- why an architectural decision was made;
- which reader task has priority.

Uncertainty should remain visible until an authorised source resolves it.

### Observation and judgement against authority

Keep the directly visible condition separate from the conclusion drawn against a quality gate, policy or acceptance criterion.

For example:

- **Observation:** 95 of 114 recorded rationales use one of two repeated strings.
- **Authority:** the approved quality gate requires paper-specific rationales.
- **Inference or judgement:** the repeated rationales are not sufficiently paper-specific to satisfy that gate.

Cite the governing authority for the judgement. Do not present the judgement as though it were the observed condition, and do not treat a reviewer decision as historical project intent.

## 2. Primary task results and execution-evidence states

Every approved task has exactly one primary result:

- **Complete** — the approved completion condition was reached;
- **Partial** — the path produced material progress but did not reach the completion condition;
- **Blocked** — the task could not safely begin or continue because a prerequisite, evidence, authority or access boundary was missing;
- **Not tested** — the approved task depended on behaviour that was not executed or observed, so the task completion contract remains untested.

Keep the primary result separate from execution evidence. Record subordinate evidence explicitly as yes/no rather than reusing a primary-result term:

| Evidence state | Meaning |
| --- | --- |
| Source inspected: yes / no | Whether repository source, documentation, configuration or tests were examined. |
| Command executed: yes / no | Whether a named command was run in the recorded environment. |
| Behaviour observed: yes / no | Whether runtime output or behaviour was directly observed. |
| Clean-context completed: yes / no | Whether the approved reader reached the completion condition from the approved unfamiliar or isolated starting context. |
| Separately reviewed: yes / no | Whether another review pass checked evidence or repeated part of the task. |
| Human validated: yes / no | Whether a human independently accepted or reproduced the result. |

A command can execute without completing the reader task. Source inspection does not establish runtime behaviour. A same-agent fresh pass is not human validation. `Not tested` is reserved for the primary task-result vocabulary; do not use it as a subordinate checkbox alongside a different primary result.

## 3. Retrieval and execution modes

Record how authoritative material was obtained and how behaviour was tested.

### Pinned clone

A repository checkout was obtained and verified at the named commit.

Record:

- clone source;
- exact commit;
- verification command or repository evidence;
- final working-tree state.

### Exact package reconstruction

A package, archive or distribution was obtained and material files were verified against authoritative hashes, blobs or the pinned source.

Record:

- package identity and version;
- source or mirror;
- files compared;
- comparison method;
- files or repository context not represented.

Do not call this a clone.

### Connector inspection

Repository content was read through a connected repository service.

Record:

- connector or source;
- repository and ref;
- files or objects inspected;
- limitations on local execution, history or working-tree evidence.

### Source inspection

Checked-in source, configuration, documentation or tests were examined.

This label can accompany a pinned clone, connector inspection or package reconstruction. It does not imply command execution.

### Behavioural fallback

A controlled substitute, transcription, mock or representative environment was used when authoritative execution was unavailable.

Record:

- why the fallback was required;
- which behaviour it can corroborate;
- how it differs from the authoritative source or environment;
- claims it cannot support.

Never describe a non-byte-identical transcription as the pinned implementation.

### Not retrieved

Use when required authoritative material could not be obtained.

State the blocker and the claims that remain unsupported. This is a retrieval observation, not a primary task result.

### Blinded evidence isolation

Before approving a blinded task:

1. define an explicit allowlist of immutable evidence objects;
2. identify outcome evidence that must remain excluded;
3. check commit titles and messages, issue and pull-request timelines, linked objects, broad comment retrieval and the current target state for leakage;
4. use a target state that predates the excluded outcome where the task depends on discovering an earlier defect;
5. allocate a separate fresh execution context when another task would expose excluded evidence.

If excluded outcome evidence is exposed, the blind is invalid. Quarantining the evidence may preserve other claims, but it cannot restore clean-context completion.

### Freshness and zero-history are execution properties

Define a fresh, clean-context or zero-history requirement by the information boundary the task actually needs, not by a named chat mode, browser feature or other UI mechanism.

Before evidence inspection, record:

- the material information available to the execution context before the task invocation;
- the task's forbidden prior exposure;
- the authorised instructions, fixture identities, allowlists or control capsules supplied as part of the invocation;
- whether the current context can credibly satisfy the required boundary.

Authorised task inputs supplied at invocation do not by themselves invalidate freshness unless the task contract says that they disclose excluded evidence. A product feature such as a temporary or isolated chat may help establish the property, but it is not the definition of the property.

If the context already has forbidden prior exposure, or the prior-information boundary cannot be established confidently, stop or reclassify the task before substantive evidence inspection. Later quarantine, omission or an instruction to forget cannot restore a blind or clean-context claim.

### Executable-task preflight

Before approval, verify:

- the exact pinned checkout or immutable source can be acquired;
- required runtimes, tools and dependency resolution are available;
- credentials are read-only and within the authorised boundary;
- the required network path is available;
- the disposable workspace, permitted side effects and recovery action are defined.

A documented command is not an executable fixture. Record preflight as `Pass`, `Fail` or `Not required`. A failed preflight requires revision, deferral or an explicitly approved source-inspection-only task.

### Publication and write-path capability preflight

When a bounded task or session can complete only by publishing or writing a durable record, verify the write path **before substantive evidence collection begins**.

Record:

- the exact destination object;
- the exact authorised write operation;
- the connected tool or capability that will perform it;
- the credential or permission boundary;
- preflight disposition: `Pass`, `Fail` or `Not required`.

This preflight establishes capability only. It does not create authority and must not widen the allowed destination, write type, credentials or mutation scope.

On `Fail`, preserve or return the bounded record that the task is authorised to prepare, report the publication blocker and stop. Do not continue open-ended evidence discovery in the hope that a write path will become available later.

## 4. Retrieval modes are not equivalent

Do not silently substitute one mode for another.

A pinned clone may provide commit, history and working-tree evidence that a package reconstruction does not.

An exact package reconstruction may support installed-package behaviour but omit repository-only files.

Connector inspection may provide authoritative file contents without supporting local command execution.

A behavioural fallback may corroborate one conclusion but cannot establish clean-context completion against the pinned target.

The close-out should say which mode supports each material finding.

## 5. Durable command and result evidence

Before a disposable environment, log or fixture is removed, retain a concise command/result summary in a durable repository record or linked issue.

For each material command, record:

- purpose;
- exact command or interaction;
- working directory or fixture identity;
- operating system, container or sandbox;
- language, runtime and tool versions;
- declared and resolved dependency versions;
- network access used;
- exit status;
- material output, warning or failure summary;
- artefacts created;
- cleanup or restoration result;
- evidence retained;
- limitations.

A path to an ephemeral local transcript is not sufficient durable evidence.

Do not copy secrets, tokens, private files or unnecessary full logs into the record.

## 6. Dependency and runtime versions

Record versions when they can affect the result, including:

- language runtime;
- package manager;
- framework or command library;
- test runner;
- build tool;
- operating system or container image;
- relevant external service or API version.

Distinguish:

- versions declared by repository metadata;
- versions actually resolved and executed;
- versions used only in a fallback or comparison.

Do not infer a supported compatibility policy from one successful or failing version.

## 7. Target state and local effects

Executable assessments should record four separate questions:

1. Did the remote target change?
2. Did canonical tracked source change?
3. Which generated local artefacts appeared?
4. Was the disposable workspace restored when required?

A clean final workspace can be required evidence. Continuous cleanliness is not required while approved commands run inside an approved disposable boundary.

### Effect boundaries

- **Remote or protected** — repository objects, settings, workflows, publication, deployment or external protected state.
- **Canonical tracked source** — checked-in target or assessment source whose content must remain unchanged.
- **Generated local** — disposable fixtures, environments, caches, packaging metadata and outputs.

### Event classes

Use the complete repository definitions in [`docs/issueops.md`](../docs/issueops.md#mutation-and-recovery-classes).

- **Class A — Protected or unbounded mutation:** stop normal work, perform minimum safe remediation, record the event and require maintainer direction.
- **Class B — Recoverable local execution deviation:** pause the affected operation, bound and record the local effect, restore or recreate the disposable workspace, verify the result and continue only inside the original authority.
- **Class C — Expected local side effect:** allow expected generated artefacts inside approved disposable paths; record and clean where required.

One task may produce several events. Record expected Class C caches separately from a Class B placement deviation.

Escalate when an effect reaches protected state, changes canonical source outside authority, escapes the disposable boundary, requires new intent or authority, cannot be bounded or cannot be restored.

## 8. Validate by response type

Validation follows the documentation response, not a generic proofreading checklist.

### Tutorial

Validate that an unfamiliar reader can begin from the defined starting context, follow the sequence and reach a recognisable outcome without hidden knowledge.

### How-to guide

Validate that a competent reader can complete the real task, including prerequisites, choices and likely failure modes.

### Reference

Validate material claims against canonical commands, APIs, schemas, configuration or executable contracts. Prefer mechanical comparison where practical.

### Explanation

Validate concepts and rationale against decision records, issues, pull requests, source material or authorised human knowledge. Never present inferred intent as established history.

### Correction

Repeat the affected lookup or task and confirm the revised claim matches the strongest available authority.

### Navigation

Begin at the original entry point and confirm that the revised route takes the reader to the useful existing material.

### Retain

Record the task evidence showing that the existing path is useful and sufficiently correct. State any limitation that remains.

### No change

Record why the evidence, reader value or proportionality test does not justify work.

### Human authority required

Check that the record names the exact decision needed, identifies why repository evidence is insufficient and states the inference that must not be made.

## 9. Separate review, terminality and human validation

A separate evidence review should assess:

- reader-group credibility;
- task representativeness;
- evidence-state accuracy;
- finding-to-evidence traceability;
- smallest-sufficient classification;
- preserved uncertainty;
- usefulness and proportionality;
- close-out conclusions.

Where practical, repeat at least one material task.

State whether the reviewer is:

- an independent human;
- a different agent or session;
- the same account performing a fresh pass;
- another disclosed relationship.

Only actual independent human acceptance or reproduction should be labelled **Human validated**.

When the approved workflow requires a separate review, define the durable record that closes the review gate. Before starting another review, check whether a qualifying terminal review already exists. Check again before publication when mutable review state could have changed during the session.

If the gate is already terminal, stop without publishing another substantively duplicate review. Historical duplicate reviews remain orchestration evidence; repetition does not add independent validation weight merely by count.

A re-review is allowed when the governing contract requires it after material evidence changes, remediation or another explicit trigger. Record that trigger rather than treating a terminal review gate as permanently immutable.

## 10. Evidence register

Use a compact register for material sources.

| ID | Evidence | Retrieval or execution mode | Claim role | Limitation |
| --- | --- | --- | --- | --- |
| E1 |  |  | Observation / Authority / Inference / Uncertainty |  |

Do not force every minor statement into the register. Include the evidence needed to support findings, protected decisions, remediation and validation.

## 11. Final evidence checks

Before close-out or review, ask:

- Does every material claim have an accurate claim state?
- Are direct observations separated from judgements or inferences against a named authority?
- Is there exactly one primary task result from `Complete`, `Partial`, `Blocked` or `Not tested`?
- Do subordinate execution-evidence states use explicit yes/no wording rather than reusing a primary task result?
- Did every executable task have a recorded preflight disposition?
- Did every task/session that requires durable publication have a publication/write-path capability preflight before substantive evidence collection?
- Did every blinded task preserve its evidence allowlist and leakage boundary?
- Was any freshness or zero-history claim defined by the actual prior-information boundary rather than a particular UI mechanism?
- Are retrieval modes explicit and non-equivalent?
- Are resolved dependency and runtime versions recorded?
- Are material command results durable?
- Are remote, canonical-source and generated-local effects separated?
- Are fallback claims limited to what the fallback can support?
- Is uncertainty preserved where authority is absent?
- Does validation match the selected response?
- Is review independence described honestly?
- If a review gate is already terminal, did later review attempts stop without duplicate publication unless a re-review trigger exists?

Evidence quality is part of the documentation decision. It is not administrative decoration.