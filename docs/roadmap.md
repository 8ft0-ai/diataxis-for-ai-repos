# Project roadmap

This roadmap records the direction of `diataxis-for-ai-repos` after the assessment-only `v0.1.0` release.

It is not an implementation plan and does not authorise repository changes. A roadmap entry becomes executable work only through the repository's normal GitHub planning and execution process.

**Project-name status:** **TaskFirstDocs** remains a provisional name. This roadmap does not approve or adopt it.

## Purpose and authority

The roadmap exists to make three things visible:

1. what the project currently provides;
2. what evidence should be gathered next;
3. which later capabilities may be considered if that evidence supports them.

It should prevent two opposite failures:

- treating the current assessment-only toolkit as a complete documentation system;
- treating every possible future capability as an approved commitment.

Authority remains with approved GitHub decisions and execution contracts. When this file conflicts with a later approved issue or maintainer decision, the later recorded authority governs and the roadmap should be updated.

## Roadmap states

Every future item should use one of these states.

### Committed

The work has an approved GitHub decision or execution contract that defines its outcome, scope, non-goals, validation and authority boundary.

A roadmap label alone cannot make work committed. The entry should link to the governing issue.

### Candidate

The direction appears useful, but more evidence or a human decision is required before implementation. Candidate work may be explored through a planning issue or bounded experiment.

### Possible later direction

The idea may become relevant after earlier evidence gates are satisfied. It is not planned work, should not be estimated, and must not be implemented merely because it appears here.

## Current release — assessment-only `v0.1.0`

**State: Current capability**

The [`v0.1.0` release](https://github.com/8ft0-ai/diataxis-for-ai-repos/releases/tag/v0.1.0) provides a minimal assessment-only toolkit. It helps a maintainer or repository-aware agent:

- inspect repository evidence without changing the target repository;
- identify evidence-supported reader groups;
- propose representative tasks and stop for human approval;
- walk or execute approved task paths;
- distinguish observation, authority, inference and uncertainty;
- classify observable failures and retained paths;
- select the smallest sufficient response;
- produce bounded remediation, retain, no-change and authority-required outcomes;
- close the assessment with limitations and next decisions;
- bootstrap an assessment in a repository that already contains documentation.

The release stops before documentation drafting. It does not provide a CLI, installer, hosted service, autonomous agent framework, automatic repository scanning or a complete drafting system.

Its evidence base is narrow: two small-repository experiments. It does not establish independent agreement, large-repository proportionality, broad repository generality, drafting quality or model-to-model portability.

## Horizon 1 — validate adoption of the released assessment workflow

**State: Completed evidence gathering; adaptation committed in [#29](https://github.com/8ft0-ai/diataxis-for-ai-repos/issues/29)**

### Proposed milestone

> An unfamiliar maintainer or repository-aware agent can use the released `v0.1.0` toolkit against another repository, stop at the human task-approval gate, complete approved task walkthroughs and produce a useful, proportionate remediation backlog without relying on this project's development history.

### Why this comes next

The project has shown that the method can be developed and applied by participants familiar with its evolution. It has not yet shown that the released package is sufficiently clear for a fresh-context adopter.

The next risk is therefore adoption and proportionality, not missing automation.

### Evidence to gather

A Horizon 1 pilot should include:

- the exact pinned `v0.1.0` toolkit identity;
- a fresh agent or maintainer context that does not rely on private project history;
- a target repository materially different from RaceIQ and files-to-prompt;
- an initial non-mutating repository assessment;
- proposed readers and tasks followed by an explicit human approval gate;
- approved task-path walkthroughs with durable evidence;
- observable usability and proportionality findings;
- retain, no-change and authority-required outcomes where justified;
- identification of unnecessary process, ambiguous instructions and missing guidance;
- a comparative close-out that separates method findings from target-repository findings.

### Exit conditions

Horizon 1 is complete when the project has enough evidence to decide whether to:

- retain the released assessment workflow substantially as written;
- simplify or clarify the toolkit before expanding it;
- run another materially different assessment pilot;
- begin a bounded drafting-contract experiment;
- stop or defer expansion because the assessment method is not yet proportionate.

A successful pilot does not require documentation changes. A useful assessment that retains existing documentation or creates no remediation work is valid evidence.

### Recorded outcome

Two fresh-context adoption pilots were completed:

- [#27](https://github.com/8ft0-ai/diataxis-for-ai-repos/issues/27) assessed gitstate-lab and accepted `v0.1.0` substantially as tested, while authorising a materially different second pilot;
- [#28](https://github.com/8ft0-ai/diataxis-for-ai-repos/issues/28) assessed arxiv-quant-radar and accepted an **Adapt** disposition.

The second pilot showed that the evidence and stopping disciplines remained useful, but task-pack consistency, executable-prerequisite preflight, blinded evidence isolation, initial evidence budgeting, publication stopping and claim-state attribution required clarification. [Issue #29](https://github.com/8ft0-ai/diataxis-for-ai-repos/issues/29) authorises that clarification-only maintenance release.

Horizon 1 does not establish independent maintainer usability, broad portability or the target behaviours that remained blocked or not tested. A bounded rerun of the affected controls remains required before drafting-contract work begins.

## Horizon 2 — bounded drafting and document-type validation

**State: Candidate, gated by Horizon 1**

The original project direction includes drafting contracts for tutorial, how-to, reference and explanation. These should not be added as a four-document generation matrix.

A drafting contract should be introduced only when accepted assessment evidence produces a real remediation item that requires that document form.

### Candidate capability

A bounded drafting workflow may:

1. take one accepted remediation item;
2. identify the authoritative evidence and protected uncertainties;
3. define permitted claims, scope and forbidden inferences;
4. draft the smallest coherent change;
5. validate it according to its Diátaxis form;
6. repeat the relevant reader-task walkthrough;
7. record the before-and-after result;
8. stop for human acceptance and merge.

### Document-type validation boundary

- **Tutorial:** an unfamiliar reader can start from a defined state and reach a recognisable outcome without hidden context.
- **How-to guide:** a competent reader can complete the real task, including prerequisites, choices and relevant failure modes.
- **Reference:** claims agree with authoritative interfaces, schemas, commands or executable contracts; mechanical checks are preferred where practical.
- **Explanation:** rationale is supported by decision records, issues, pull requests, source material or human authority; inferred intent is not presented as established history.

### Evidence required before implementation

Before creating drafting contracts, the project should have:

- an accepted assessment finding that cannot be solved by retention, correction or navigation alone;
- a human-approved remediation scope;
- authoritative evidence sufficient for the intended claims;
- an explicit validation procedure for the selected document type;
- a clear before-and-after task or claim comparison;
- a stopping condition for unresolved intent, policy or rationale.

The correct next step may be one drafting contract, not all four.

## Horizon 3 — test portability, proportionality and independent review

**State: Possible later direction**

After the assessment workflow and at least one bounded drafting workflow are credible, the project may test whether the method remains useful across different contexts.

Potential evidence questions include:

- Can different agents apply the same contracts without materially different authority or scope errors?
- Can independent maintainers agree on reader tasks, findings and remediation classifications?
- What is the lightest useful form for a small repository?
- How should the method change for monorepos, SDKs, services, private repositories or organisation-scale documentation estates?
- Which evidence records are essential, and which are process overhead?
- Can drafting and validation be reviewed independently from the drafting agent?

These questions should be tested through bounded pilots rather than answered through broader claims in the toolkit.

## Possible supporting tooling

**State: Possible later direction**

Supporting mechanisms may be considered only after repeated manual use reveals stable, burdensome steps.

Possible examples include:

- reusable GitHub issue templates;
- agent-specific adapters or repository-local skills that preserve the model-agnostic contracts;
- lightweight schemas for task, finding and close-out records;
- mechanical checks for reference claims and internal links;
- a small helper for evidence inventory or report assembly;
- comparative evaluation fixtures;
- release or packaging automation.

Tooling should support the method rather than become the product proposition. It must not:

- infer reader needs from directory shape alone;
- bypass human task approval;
- convert uncertain intent into documentation claims;
- generate all four Diátaxis forms for completeness;
- make target-repository changes without a separate execution contract;
- treat successful execution as independent validation.

A CLI, hosted product or autonomous agent framework is not planned merely because it is technically possible.

## Evidence required to advance

A horizon should advance only when the preceding work produces evidence that changes a real project decision.

At minimum, an advancement decision should record:

- the user and reader problem being addressed;
- the evidence collected so far;
- what failed or remained costly in the current method;
- why a new capability is preferable to simplifying existing guidance;
- the smallest experiment that could test the proposed change;
- human decisions and protected authority boundaries;
- success, failure and stopping conditions;
- what the evidence still will not prove.

Process activity is not advancement. More prompts, templates, schemas or Markdown do not demonstrate better documentation outcomes.

## How roadmap items become authorised work

The roadmap records direction. GitHub records authority.

The normal path is:

1. open a planning issue when the problem, evidence or alternatives still need to be shaped;
2. record the relevant evidence and decision;
3. retain, reject, defer or convert the candidate into one or more bounded execution-contract issues;
4. define outcome, scope, non-goals, acceptance criteria, validation, dependencies and authority;
5. implement on an issue-scoped branch;
6. review the pull request as an evidence pack;
7. require explicit human acceptance and merge authority;
8. update this roadmap when the state or evidence boundary materially changes.

No agent should create a branch or implementation merely because an item is marked Candidate or Possible later direction.

## Explicitly not planned yet

The project does not currently commit to:

- a complete documentation drafting system;
- automatic documentation generation or remediation;
- a CLI, installer or package manager distribution;
- a hosted service or autonomous agent platform;
- automatic repository scanning or issue creation;
- a required four-folder Diátaxis structure;
- all four drafting contracts in one release;
- broad repository, practitioner, organisation or model generality;
- recovery of undocumented intent or architectural rationale;
- replacement of human review, policy decisions or merge authority;
- approval of the provisional name **TaskFirstDocs**.

These are boundaries against premature commitment, not permanent prohibitions. Moving one into Candidate or Committed requires evidence and a recorded decision.

## Completed milestones

- Defined the evidence-led central workflow and authority boundaries.
- Ran the RaceIQ assessment experiment and accepted an **Adapt** result.
- Ran the executable files-to-prompt experiment and accepted an **Adapt** result.
- Consolidated the accepted assessment method into the minimal toolkit.
- Added a bootstrap guide for repositories with existing documentation.
- Published the assessment-only [`v0.1.0` release](https://github.com/8ft0-ai/diataxis-for-ai-repos/releases/tag/v0.1.0).

## Current commitments

The only committed work is [#29](https://github.com/8ft0-ai/diataxis-for-ai-repos/issues/29): a clarification-only `v0.1.1` candidate covering the six findings accepted from the second adoption pilot.

This commitment does not authorise drafting contracts, automation, target-repository remediation, merge, release publication or the post-clarification rerun.

## Open decisions

- Does the bounded post-clarification rerun confirm task-pack consistency, prerequisite preflight, blinded isolation and publication stopping?
- What level of independent maintainer involvement is needed before claiming external usability?
- Should the first drafting experiment follow a successful bounded rerun, or be deferred until more assessment evidence exists?
- Which document type should receive the first drafting contract if evidence justifies one?
- What form of independent review is proportionate?
- When, if ever, does repeated manual work justify supporting tooling?
- Should **TaskFirstDocs** be approved, changed or retired as the project name?
