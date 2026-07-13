# RaceIQ assessment experiment

This directory records the first assessment-only experiment for the method proposed in [issue #1](https://github.com/8ft0-ai/diataxis-for-ai-repos/issues/1) and delivered through [issue #4](https://github.com/8ft0-ai/diataxis-for-ai-repos/issues/4).

## Target

- Repository: [`8ft0-ai/RaceIQ`](https://github.com/8ft0-ai/RaceIQ)
- Evidence snapshot: [`7addbd39774f2ab5a59be7bd42c9e6d9cdcf65ab`](https://github.com/8ft0-ai/RaceIQ/tree/7addbd39774f2ab5a59be7bd42c9e6d9cdcf65ab)
- Assessment mode: non-mutating source and documentation inspection
- Target changes: none

RaceIQ was selected because it is public, small enough to inspect end to end, and exposes observable reader tasks across a static dashboard, interpretation guidance and repository maintenance. It has distinct viewer, analyst and maintainer needs without requiring access to private organisational context.

This is one worked experiment, not proof that the method generalises to every repository.

## Experiment boundary

The experiment tests:

```text
inspect evidence
→ identify reader groups
→ select representative tasks
→ walk existing documentation paths
→ classify observed failures
→ propose bounded remediation
→ assess the method
```

It stops before drafting or applying any RaceIQ documentation change.

The assessment uses repository source as evidence of observable behaviour. Source code is not treated as proof of intent, policy, generation history or architectural rationale. Browser execution was not performed in this run; the walkthroughs label that limitation explicitly.

## Artefacts

- [`assessment-instruction.md`](assessment-instruction.md) — exact non-mutating instruction used
- [`method.md`](method.md) — task discovery, walkthrough, classification and remediation method
- [`baseline.md`](baseline.md) — evidence inventory, reader groups, authority map and uncertainties
- [`walkthroughs.md`](walkthroughs.md) — six representative task-path evaluations
- [`remediation-backlog.md`](remediation-backlog.md) — evidence-backed changes, retained content and no-change decisions
- [`closeout.md`](closeout.md) — findings, limitations and recommendation

## Evidence notation

The assessment uses four claim states:

- **Observation** — directly visible in repository evidence.
- **Authority** — established by a canonical interface, explicit maintainer decision or other designated source.
- **Inference** — a reasoned conclusion not directly established.
- **Uncertainty** — a question the available evidence cannot resolve.

Evidence identifiers are defined in [`baseline.md`](baseline.md#evidence-register).
