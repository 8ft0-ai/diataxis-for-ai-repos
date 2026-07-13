# Experiment close-out

## Recommendation

**Adapt**

The assessment-to-remediation workflow produced useful, bounded findings and resisted generating a full documentation set. It should continue into V1 only after the method is tightened around task selection, execution evidence and human review.

This is an agent recommendation. Maintainer acceptance remains pending through review of issue #4 and its pull request.

## What the experiment demonstrated

### Observable failure can be separated from general criticism

The walkthroughs did not conclude that RaceIQ documentation was broadly “poor”. They identified specific failures:

- the root feature summary omits a current capability;
- the README does not route analytical readers to stronger interpretation guidance;
- the apparent asset inventory is incomplete;
- the app manifest and runtime dependencies have incompatible scopes;
- the refresh workflow cannot be documented safely from available authority.

### Reader tasks can drive selective outcomes

Six tasks produced mixed results:

- two existing paths should be retained;
- two require small corrections or navigation;
- one exposes a reference-scope decision;
- one is blocked by missing authority.

The method did not require a tutorial, a new explanation page or all four Diátaxis forms.

### Authority and uncertainty can remain separate

Source established observable runtime dependencies and explicit interpretation language. It did not establish generation intent, manifest ownership, score formula or publication policy. Those questions remain unresolved rather than being completed with plausible prose.

### The backlog can favour smaller changes

The highest-confidence work is correction and navigation inside existing surfaces. The only possible larger maintainer guide is deliberately blocked until authoritative source material exists.

## Questions from issue #1

1. **Can the agent distinguish observable reader failure from general criticism?**  
   Yes in this experiment. Findings name a task, expected path, observed path and completion gap.

2. **Can it select representative tasks without inventing hypothetical demand?**  
   Partly. Viewer, analytical reviewer and maintainer tasks are supported by observable interfaces, but their priority has not been independently validated by users.

3. **Can it identify appropriate authority rather than treating code as complete truth?**  
   Yes. Source was used for behaviour and dependency evidence; intent and provenance remained protected.

4. **Can it separate observation, authority, inference and uncertainty?**  
   Yes, although the distinction adds recording overhead and needs a concise reusable format.

5. **Can it classify responses without requiring all four Diátaxis forms?**  
   Yes. The recommended responses are retain, no change, correction, navigation, reference clarification and human authority.

6. **Does every remediation item trace to an observed failure, correctness problem, authority gap or maintenance risk?**  
   Yes. R1–R5 cite T2, T3, T5 or T6 and named evidence.

7. **Does the backlog support smaller corrections and no-change outcomes?**  
   Yes. R1–R4 are bounded corrections or decisions; K1–K2 retain useful material; N1–N4 reject unnecessary expansion.

8. **Is the process understandable and proportionate?**  
   Mostly for a small repository, but the evidence register and walkthrough detail are heavier than a routine README correction. A lighter adoption level is needed.

9. **Which parts are too vague, heavy or agent-dependent?**  
   Task prioritisation, the boundary between navigation and explanation, and confidence scoring remain judgement-heavy. Source-only walkthroughs are also weaker than clean-context execution.

## Evidence required by the planning issue

- Target selection rationale: [`README.md`](README.md)
- Exact assessment instruction: [`assessment-instruction.md`](assessment-instruction.md)
- Working method: [`method.md`](method.md)
- Evidence inventory and documentation map: [`baseline.md`](baseline.md)
- Reader groups and task rationales: [`baseline.md`](baseline.md#reader-groups)
- Completed walkthroughs: [`walkthroughs.md`](walkthroughs.md)
- Classification and remediation traceability: [`remediation-backlog.md`](remediation-backlog.md)
- Claim-state and uncertainty handling: [`baseline.md`](baseline.md#authority-map)
- Retained and rejected work: [`remediation-backlog.md`](remediation-backlog.md#retain-decisions)
- Final recommendation: this file

## Proportionality review

The experiment is proportionate as a one-off method proof because it tests the central evidence gate before building tooling.

It would be disproportionate to require the full seven-artefact pack for every small repository change. A future V1 should support:

- a compact Level 1 classification path;
- a lighter Level 2 task-evidence worksheet;
- the full evidence pack only for Level 3 governed work or method evaluation.

## Effort and friction

Approximate agent effort was concentrated in:

- identifying and pinning authoritative repository evidence;
- reconciling README, application shell, dynamic script loading and data manifests;
- selecting tasks that did not predetermine the documentation form;
- recording uncertainty without turning it into a speculative backlog;
- maintaining traceability across walkthroughs and remediation items.

The greatest friction was not writing. It was deciding what the repository could actually prove.

## Limitations

- The target is a small static dashboard and does not represent a compiled library, service, monorepo or organisation-scale documentation system.
- Browser execution and clean-context user observation were not performed in this run.
- Reader groups and task priority have not been independently validated.
- The drafting agent also performed the assessment; this is not independent evaluation.
- Repository evidence may omit external generation or operating material.
- The method has been tested with one agent and one target only.

## What should enter V1

Retain as working candidates:

- the evidence-state distinction;
- the reader-task selection criteria;
- the walkthrough result record;
- the smallest-sufficient-response rubric;
- the bounded remediation-item fields;
- the explicit retain and no-change outcomes.

Adapt before treating them as stable contracts:

- reduce duplication between the baseline and walkthrough records;
- add an execution-evidence field that separates source inspection, command execution and clean-context testing;
- add a human task-approval checkpoint;
- define a compact path for small repositories;
- avoid numeric confidence scoring unless it proves useful.

## Next decision question

> Can a second maintainer use a lighter version of this method on a different repository, execute the selected tasks in a clean context, and produce materially similar classifications without relying on the first agent's judgement?

Do not add a CLI or automation before that question is tested.
