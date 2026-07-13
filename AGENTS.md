# Agent instructions

These instructions apply to repository-aware AI agents working in this repository.

## Project state

`diataxis-for-ai-repos` is developing an evidence-led method for AI-assisted repository documentation. **TaskFirstDocs** is a provisional name.

The toolkit itself has not yet been implemented. Do not infer a complete product, architecture or roadmap from proposed files or issue discussions.

The stable branch is `main`.

## Authority order

Use this order when instructions or evidence appear to conflict:

1. the approved issue contract and its later recorded decisions;
2. this file and other current repository instructions;
3. the implementation plan recorded on the issue;
4. current repository evidence;
5. contributor or agent assumptions.

Private chat history is not authoritative. Record material decisions in GitHub.

Source code may establish behaviour. It does not, by itself, establish project intent, policy, priority or architectural rationale.

## Classify the issue before acting

A **planning issue** shapes a decision. It does not authorise implementation unless an approved decision explicitly says so.

An **execution-contract issue** authorises only the bounded work described by its outcome, scope, non-goals, acceptance criteria, validation expectations and authority boundary.

Use stage-level planning only for several dependent issues, cross-cutting governance or autonomy changes, or an end-to-end proof that cannot be reviewed in one pull request.

## Required delivery flow

Before changing repository content:

1. Read the issue and relevant comments.
2. Inspect current repository instructions and affected files.
3. Confirm the issue is executable.
4. Check scope, non-goals, acceptance criteria, validation, risk and dependencies.
5. Record readiness and the safe starting commit.
6. Post an implementation plan.
7. Create one issue-scoped branch from the recorded starting point.

Preferred branch format:

```text
agent/<issue-number>-short-description
```

For each repository mutation, confirm the phase, exact target, intended side effect and forbidden side effects. Use a fuller check for pull requests, merges, workflows, settings, releases or any ambiguous operation.

Implement the smallest coherent change that satisfies the issue. Do not combine unrelated cleanup, future-stage work or structural reorganisation.

## Evidence and documentation rules

For material claims, distinguish:

- **Observation:** directly found in repository evidence.
- **Authority:** supported by a canonical interface, policy, decision record or maintainer statement.
- **Inference:** a reasoned conclusion not directly established.
- **Uncertainty:** information the available evidence cannot resolve.

Preserve uncertainty. Never present inferred intent as established history.

Do not create documentation because a Diátaxis category, page or directory is empty. Retain useful existing material. Prefer correction or navigation changes when they solve the observed reader problem.

Validation must match the document type and the changed claim. See [`docs/issueops.md`](docs/issueops.md).

## Pull requests and review

Open a draft pull request as the evidence pack. It must link the execution contract, describe deliberate exclusions, map acceptance criteria to current evidence, state exact validation status, and disclose assumptions and caveats.

Review asks two separate questions:

1. Did we do what was needed?
2. Did we only do what was asked?

Use exactly one recommendation:

- `Approve`
- `Approve after minor fixes`
- `Do not approve yet`

Evidence is not approval. Human approval and merge authority remain required unless the repository owner records a specific bounded delegation.

## Stop conditions

Stop and record the blocker when:

- the issue is planning-only or materially unclear;
- a dependency or safe starting point cannot be established;
- implementation requires new product intent, policy, architecture or authority;
- satisfying the request would violate a non-goal;
- required validation is failing or cannot determine correctness;
- a tool targets the wrong repository object;
- an unintended mutation occurs;
- workflows, permissions, settings, publication or deployment would change without explicit authority.

After an unintended mutation, perform only the minimum safe remediation, record the event, and await maintainer direction before resuming normal writes.

## Protected decisions

Agents may inspect, classify, compare, implement approved bounded changes and prepare evidence.

Humans retain responsibility for:

- project intent and naming;
- policy, priority and architectural rationale;
- disputed authority;
- approval of reader groups and representative tasks;
- acceptance of remediation work;
- repository settings and permissions;
- publication, deployment and merge.
