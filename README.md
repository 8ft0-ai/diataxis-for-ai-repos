# diataxis-for-ai-repos

**Provisional project name:** TaskFirstDocs  
**Working description:** Evidence-led Diátaxis workflows for AI-assisted repository documentation.

This repository is exploring a model-agnostic method for improving documentation in existing software repositories. The method begins with repository evidence and representative reader tasks. It does not ask an AI agent to generate documentation merely because a page or directory appears to be missing.

> Do not ask AI to document the repository. Ask it to identify where readers fail, classify the documentation need, and draft only what the evidence supports.

## Current status

The toolkit has not yet been implemented. The repository is in an initial evidence-gathering stage.

The first proposed experiment is tracked in [issue #1](https://github.com/8ft0-ai/diataxis-for-ai-repos/issues/1). It is intended to test whether a repository-aware agent can produce a documentation baseline, task-path evaluations and an evidence-backed remediation backlog without changing the target repository.

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
