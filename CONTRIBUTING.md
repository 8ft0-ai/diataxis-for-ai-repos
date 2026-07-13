# Contributing

Thank you for helping develop an evidence-led approach to repository documentation.

The project is at an early stage. Contributions should test or improve the operating method without assuming that the full proposed toolkit, repository structure or provisional name has been approved.

## Start with the right issue

Use a **planning issue** when the repository still needs to decide whether work should proceed, compare approaches, establish boundaries or approve a direction.

Use an **execution-contract issue** when the work is sufficiently bounded to implement without inventing material intent. An executable issue should define:

- the problem and observable outcome;
- permitted scope and explicit non-goals;
- acceptance criteria;
- expected validation evidence;
- change risk;
- dependencies;
- agent instructions;
- authority and post-merge boundaries.

Implementation should normally begin from an approved execution contract. A planning issue does not authorise a branch or pull request unless a recorded decision explicitly converts or decomposes it into executable work.

Templates are available when opening a new issue.

## Before implementation

Read:

- [`AGENTS.md`](AGENTS.md);
- [`docs/issueops.md`](docs/issueops.md);
- the complete issue and its comments;
- the current files affected by the proposed work.

Record readiness, dependency status and the safe starting commit on the issue. Then post the implementation plan before creating the issue branch.

Use one branch per execution contract:

```text
agent/<issue-number>-short-description
```

Do not commit directly to `main`.

## Scope and evidence

Make the smallest coherent change required by the issue.

Do not add adjacent cleanup, automation, schemas, scripts, documentation categories or future-stage work without an explicit contract. A tidier directory structure is not, by itself, evidence of a better reader outcome.

For material findings and claims, distinguish observation, authoritative evidence, inference and unresolved uncertainty. Code can prove behaviour in some contexts, but should not be used to invent policy, intent or historical rationale.

Useful existing documentation should be retained. The correct outcome may be a correction, a navigation change or no new document.

## Validation

Validation must match the changed artefact and the issue risk.

For documentation changes, consider:

- internal links and repository paths;
- commands, examples and named interfaces;
- consistency with canonical evidence;
- rendering and navigation;
- the relevant Diátaxis validation contract, when one exists;
- whether evidence represents the final branch or pull-request head.

If a repository-native check does not exist, describe the manual procedure and its limitations. Do not add tooling merely to make a low-risk contribution appear more automated.

## Pull requests

Open a draft pull request while implementation or required evidence is incomplete.

The pull request should:

- close or link the execution-contract issue;
- identify any parent initiative;
- describe what changed and what was deliberately excluded;
- map each acceptance criterion to evidence;
- state the exact final head and validation status;
- disclose assumptions, uncertainty and residual risk;
- include a groundedness review;
- state whether merge authority has been granted.

A pull request is an evidence pack. It is not approval.

Human review and merge authorisation remain required unless a specific bounded delegation has been recorded.

## Review and remediation

Classify review feedback before editing:

- **Required fix:** necessary for correctness, evidence or contract fulfilment.
- **Optional improvement:** useful, small and inside scope, but not required.
- **Clarification needed:** ambiguous or potentially scope-changing.
- **Out of scope:** should be deferred to another issue.

After a material fix, reread the changed files, inspect the final diff, rerun affected checks and update the evidence pack.

For the complete lifecycle, see [`docs/issueops.md`](docs/issueops.md).
