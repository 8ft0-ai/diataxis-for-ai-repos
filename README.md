# diataxis-for-ai-repos

**Provisional project name:** TaskFirstDocs  
**Working description:** Evidence-led Diátaxis workflows for AI-assisted repository documentation.

This repository is exploring a model-agnostic method for improving documentation in existing software repositories. The method begins with repository evidence and representative reader tasks. It does not ask an AI agent to generate documentation merely because a page or directory appears to be missing.

> Do not ask AI to document the repository. Ask it to identify where readers fail, classify the documentation need, and draft only what the evidence supports.

## Current status

The project remains in evidence gathering. It is not yet a stable V1 toolkit.

The first assessment-only experiment was completed against [`8ft0-ai/RaceIQ`](experiments/raceiq/README.md). Its close-out recommendation was **Adapt**: retain the evidence-led workflow, but reduce record duplication, distinguish source inspection from execution evidence, add a human task-approval checkpoint and provide lighter adoption paths.

The current stage is tracked in [issue #7](https://github.com/8ft0-ai/diataxis-for-ai-repos/issues/7). It will test the adapted method against a materially different repository using clean-context task execution and a separate evidence review before deciding whether minimal V1 packaging is justified.

The provisional working records for that stage are in [`working/method-v0.2/`](working/method-v0.2/README.md):

- [working method and evidence rules](working/method-v0.2/README.md);
- [experiment plan record](working/method-v0.2/experiment-plan.md);
- [assessment and close-out record](working/method-v0.2/assessment-closeout.md).

These records are experimental. They do not define a required repository structure, approve automation or establish cross-repository generality.

The name **TaskFirstDocs** remains provisional until explicitly approved.

## Working principles

- Repository evidence is not complete truth.
- Code can establish behaviour, but rarely proves intent.
- Agents must distinguish observation, authority, inference and uncertainty.
- Documentation changes should respond to an observed reader need, correctness problem, authority gap or maintenance risk.
- Diátaxis should classify the reader need, not force a four-folder structure.
- Retaining useful documentation or creating nothing new may be the correct outcome.
- Humans remain responsible for intent, policy, priority, rationale, acceptance and merge.

## Contributing

Before starting work, read:

- [`AGENTS.md`](AGENTS.md) for repository-aware agent instructions;
- [`CONTRIBUTING.md`](CONTRIBUTING.md) for the contribution path;
- [`docs/issueops.md`](docs/issueops.md) for the repository's IssueOps operating model.

Use a planning issue when a decision still needs to be shaped. Use an execution-contract issue only when the outcome, scope, validation and authority are sufficiently bounded to implement.

## Licence

This repository is available under the [MIT Licence](LICENSE).