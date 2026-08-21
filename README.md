# Trailpost

**Working description:** Evidence-led Diátaxis workflows for AI-assisted repository documentation.

This repository develops a model-agnostic method for improving documentation decisions in existing software repositories. The method begins with repository evidence and representative reader tasks. It does not ask an AI agent to generate documentation merely because a page or directory appears to be missing.

> Do not ask AI to document the repository. Ask it to identify where readers fail, classify the documentation need, and draft only what the evidence supports.

## Current status

The repository now contains a **minimal assessment-only V1 toolkit** under [`toolkit/`](toolkit/README.md).

The toolkit helps a maintainer or repository-aware agent produce, without changing the target repository:

- a documentation and authority baseline;
- evidence-supported reader groups;
- a human-approved representative task set;
- task-path evaluations with accurate evidence states;
- retained, no-change, correction, navigation and authority-required outcomes where supported;
- an evidence-backed remediation backlog;
- a close-out that records limitations and next decisions.

It stops before documentation drafting. It does not provide a CLI, hosted service, autonomous agent framework, automatic repository scanning or stable drafting contracts for all four Diátaxis forms.

The package is based on two accepted small-repository experiments. It does not establish cross-agent, cross-practitioner, large-repository or broad repository generality.

## Project direction

See the [project roadmap](docs/roadmap.md) for the current release boundary, the next evidence-gathering milestone, conditional drafting work and possible later tooling.

The roadmap records direction. It does not authorise implementation; roadmap items still require the repository's normal GitHub planning, execution and human-approval process.

## Use the toolkit

Start with the [assessment-only V1 overview](toolkit/README.md).

Recommended path:

1. [inspect the repository without mutation](toolkit/repository-assessment.md);
2. [select and approve representative reader tasks](toolkit/reader-task-discovery.md);
3. [walk or execute the approved tasks](toolkit/task-path-walkthrough.md);
4. [classify the smallest sufficient response](toolkit/classification-and-remediation.md);
5. [apply the evidence and validation rules](toolkit/evidence-and-validation.md);
6. [record the assessment close-out](toolkit/assessment-closeout.md);
7. [review the files-to-prompt worked example](toolkit/worked-example.md).

Use the lightest adoption level that can support the decision. Level 3 governance is not required for routine small documentation maintenance.

## Research and provenance

The adopter-facing toolkit consolidates accepted rules. The working records and experiments remain the canonical research evidence behind it.

### Working method

- [working method and evidence rules](working/method-v0.2/README.md);
- [experiment plan record](working/method-v0.2/experiment-plan.md);
- [assessment and close-out record](working/method-v0.2/assessment-closeout.md).

### Experiments

- [RaceIQ assessment experiment](experiments/raceiq/README.md) — the first source-inspection proof using the earlier seven-record shape;
- [RaceIQ close-out](experiments/raceiq/closeout.md) — accepted **Adapt** result and identified method limitations;
- [files-to-prompt method record](experiments/files-to-prompt/method.md);
- [files-to-prompt experiment plan](experiments/files-to-prompt/experiment-plan.md);
- [files-to-prompt assessment and close-out](experiments/files-to-prompt/assessment-closeout.md) — executable second experiment and accepted **Adapt** result.

The experiments support a narrow assessment toolkit. They do not prove independent human agreement, broad portability or documentation-drafting quality.

## Working principles

- Repository evidence is not complete truth.
- Code can establish behaviour, but rarely proves intent.
- Agents must distinguish observation, authority, inference and uncertainty.
- Documentation changes should respond to an observed reader need, correctness problem, authority gap or maintenance risk.
- Diátaxis should classify the reader need, not force a four-folder structure.
- Retaining useful documentation or creating nothing new may be the correct outcome.
- Validation must match the proposed response or document type.
- Humans remain responsible for intent, policy, priority, rationale, acceptance and merge.

## Contributing

Before starting work, read:

- [`AGENTS.md`](AGENTS.md) for repository-aware agent instructions;
- [`CONTRIBUTING.md`](CONTRIBUTING.md) for the contribution path;
- [`docs/issueops.md`](docs/issueops.md) for the repository's IssueOps operating model.

Use a planning issue when a decision still needs to be shaped. Use an execution-contract issue only when the outcome, scope, validation and authority are sufficiently bounded to implement.

## Licence

This repository is available under the [MIT Licence](LICENSE).