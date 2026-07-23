# IssueOps operating model

This repository uses IssueOps to make AI-assisted delivery reconstructable, bounded and human-controlled.

The issue records durable intent. The implementation plan exposes the proposed path. The branch contains one contract. The pull request carries current evidence. Human review determines whether the residual risk is acceptable.

```text
Issue = execution contract
Readiness = contract and dependency gate
Implementation plan = proposed execution path
Safe-operation check = mutation gate
Feature branch = bounded implementation
Validation = current evidence
Pull request = evidence pack
Review = contract verification
Merge = authorised human acceptance
Post-merge verification = evidence unavailable earlier
```

Repository records are authoritative. Work must not depend on private chat history or unstated memory.

## Work types

### Planning issue

Use a planning issue when the repository must first decide:

- whether work should proceed;
- what outcome matters;
- which approach or trade-off is acceptable;
- where authority and non-goals sit;
- whether delivery should be decomposed.

A planning issue shapes a decision. It does not authorise implementation unless its body or a later approved decision explicitly grants that authority.

Do not create a branch for planning-only work.

### Execution contract

Use an execution-contract issue when an agent or contributor can implement the work without inventing material intent.

The issue should define:

- problem;
- expected observable outcome;
- scope;
- non-goals;
- acceptance criteria;
- validation evidence expected;
- change risk;
- agent instructions;
- dependencies;
- relationship to a parent or roadmap;
- authority boundary;
- post-merge verification.

### Stage-level planning

Use a stage pack proportionately, only when work spans several dependent contracts, changes governance or autonomy boundaries, or needs an end-to-end proof that cannot be demonstrated in one pull request.

Ordinary maintenance and bounded documentation work should use normal execution contracts.

## Readiness before branching

Refresh repository state before declaring an issue ready:

- read the current issue and comments;
- inspect relevant files and repository instructions;
- check linked issues and pull requests;
- verify dependencies;
- identify the current `main` head;
- check for existing branches or pull requests;
- confirm the work is not completed or superseded.

Record:

```md
## Planning readiness

- Expected outcome:
- Scope boundaries:
- Acceptance criteria:
- Validation expectations:
- Change risk:
- Decision: Ready to implement / clarification required.

## Dependency check

- Required prior work:
- Required state:
- Current state:
- Safe starting commit:
- Decision:
```

Only a ready decision permits implementation planning. If correctness depends on unresolved product intent, policy, architecture or authority, stop and request the exact decision.

## Implementation plan

Post the plan before creating a branch.

The plan should state:

- proposed branch;
- safe starting commit on `main`;
- files or areas expected to change;
- intended behaviour or content change;
- implementation sequence;
- validation commands and inspections;
- assumptions and caveats;
- post-merge verification;
- explicit exclusions.

The plan does not expand issue authority. Record material deviations as discoveries; do not rewrite the original plan to make history appear linear.

## Branch and scope rules

Use one issue-scoped branch:

```text
agent/<issue-number>-short-description
```

Do not commit directly to `main`.

Refresh the starting point after a prerequisite merges. Do not combine multiple contracts, unrelated cleanup, speculative automation or future-stage work in one branch.

Implement the smallest coherent change that satisfies the acceptance criteria.

## Safe operations

Before a mutation, verify:

```text
Phase: <current lifecycle phase>
Operation: <exact action>
Target: <exact repository object>
Expected side effect: <one intended mutation>
Forbidden side effects: <what must not change>
```

When an authorised operation may create local files or alter a disposable workspace, also record:

```text
Effect boundary: remote or protected / canonical tracked source / generated local
Existing authority: <issue, decision or contract that permits the operation>
Expected event class: none / Class C / other
Expected local side effects: <caches, metadata, build or test output>
Permitted generated paths: <approved disposable locations>
Recovery if observed: stop and escalate / restore and continue / clean at close-out
```

The effect boundary describes where a change occurs. The event class describes the required response. One operation may produce several effects with different event classes; record each material event separately rather than collapsing them into one classification.

Classification depends on the observed effect, existing authority and recovery boundary, not merely the command name. A normally expected artefact becomes more serious when it escapes the approved path, changes protected state, requires new intent or authority, or cannot be bounded.

A compact check is sufficient for routine, unambiguous file updates. Use the full check for:

- pull-request creation and merge;
- workflows;
- labels or lifecycle automation;
- repository settings, permissions or branch protection;
- releases, publication or deployment;
- ambiguous targets;
- operations after unexpected tool behaviour.

### Mutation and recovery classes

#### Class A — Protected or unbounded mutation

Use Class A when a remote or protected object changes without authority, tracked source changes outside the contract, secrets or private data are exposed, the effect requires new intent or authority, or the impact cannot be confidently bounded or safely restored.

Examples include:

- targeting the wrong repository, issue, pull request, review or branch;
- unauthorised push, merge, release, publication or deployment;
- changes to workflows, settings, permissions or branch protection without authority;
- tracked source changes outside the approved scope;
- effects that escape the approved disposable boundary;
- bounded local effects caused by an operation that lacked existing authority;
- effects that require new product intent, policy, architecture or authority;
- effects whose impact is unclear or cannot be safely restored.

Response:

1. stop normal write operations;
2. perform only the minimum remediation required for safety;
3. record the action, impact and remediation;
4. require maintainer direction before resuming normal writes.

#### Class B — Recoverable local execution deviation

Use Class B when an authorised operation creates an unexpected but bounded effect inside an approved disposable environment.

Examples include:

- an installation command dirtying a disposable source snapshot unexpectedly;
- build or test output appearing outside the preferred generated-output path but remaining inside the approved workspace;
- a command failing after partial local setup;
- local packaging metadata or caches appearing in an unplanned location without changing canonical source.

Response:

1. pause the affected operation;
2. inspect and bound the effect;
3. record the deviation and any evidence already produced;
4. restore or recreate the disposable workspace;
5. verify the restored state;
6. continue without further maintainer approval only when the original authority boundary remains intact.

Escalate to Class A when the effect escapes the disposable boundary, changes remote or protected state, requires new intent or authority, cannot be confidently bounded, or cannot be safely restored.

#### Class C — Expected local side effect

Use Class C for expected generated artefacts from an authorised operation inside approved disposable paths, including:

- virtual environments;
- dependency caches;
- `__pycache__`;
- `.pytest_cache`;
- `*.egg-info` or equivalent packaging metadata;
- build, test or generated output.

Record Class C artefacts when they are material to the reader task or close-out. Clean or recreate the workspace before final verification when the contract requires a clean final state. Continuous cleanliness is not required while explicitly approved commands run inside the disposable boundary.

One task or command may produce both expected Class C artefacts and a separate Class B deviation. Record these as separate events with their own effect boundary, evidence, recovery and final state.

Do not hide an incident, silently normalise it after the fact or use local recoverability to excuse an unauthorised source or remote mutation.

## Evidence and provenance

Agents must distinguish four claim states:

| State | Meaning |
| --- | --- |
| Observation | Directly visible in repository evidence or an executed result. |
| Authority | Established by a canonical interface, policy, decision record or maintainer statement. |
| Inference | A reasoned conclusion not directly established by authority. |
| Uncertainty | A question the available evidence cannot resolve. |

The repository is evidence, not complete truth. Code may establish behaviour, but rarely proves intent.

For documentation work:

- cite or identify material evidence;
- preserve uncertainty;
- distinguish current from intended behaviour;
- retain useful existing material;
- do not reorganise for Diátaxis symmetry;
- do not create a document merely because a category or directory is empty.

## Validation

Validation must match the change, risk and document type.

### Tutorial

Validate that an unfamiliar reader can start from the defined context, follow the sequence and reach the stated outcome without hidden knowledge.

### How-to guide

Validate that a competent reader can complete the real task, including prerequisites, choices and likely failure modes.

### Reference

Validate claims against canonical commands, schemas, interfaces or executable contracts. Prefer mechanical checks where practical.

### Explanation

Validate rationale against decisions, issues, pull requests, source material or human knowledge. Never present inferred intent as established history.

### Repository-operating documents

For files such as `AGENTS.md`, contribution guidance and templates, validate:

- internal links and repository paths;
- consistency of terminology and authority boundaries;
- presence of required fields;
- a dry-run of the intended workflow;
- absence of unintended automation or settings changes.

Use the strongest available evidence:

1. repository-native validation against the final branch or pull-request head;
2. equivalent controlled validation;
3. a representative fallback for a low-risk change;
4. an explicit pending or not-performed status.

Do not describe weaker evidence as equivalent to stronger evidence. After a material change, rerun affected validation against the final head.

## Pull request as evidence pack

Open the pull request as a draft while implementation, validation or evidence is incomplete.

The pull request should include:

- linked execution contract;
- parent or roadmap relationship;
- what changed;
- deliberate exclusions;
- acceptance-criteria evidence;
- exact final head;
- repository-native validation;
- representative fallback, if any;
- validation not performed or pending;
- post-merge verification;
- risks, assumptions and caveats;
- groundedness review;
- final recommendation;
- merge-authority status.

A reviewer should be able to reconstruct the work without private conversation history.

## Groundedness review

Review the contract, not only the diff.

### Did we do what was needed?

Check the expected outcome, acceptance criteria, required behaviour, compatibility and validation.

### Did we only do what was asked?

Check changed files, non-goals, unrelated refactoring, speculative additions and authority changes.

Use exactly one recommendation:

- **Approve**
- **Approve after minor fixes**
- **Do not approve yet**

Evidence can support a recommendation. It does not replace human acceptance.

## Approval and merge

Do not recommend approval when:

- implementation is incomplete;
- an acceptance criterion is unmet;
- out-of-scope work is unexplained;
- required validation is failing or stale;
- evidence does not represent the final head;
- material review findings remain;
- an authority boundary is weakened;
- merge authority is absent.

Before merge, confirm the correct repository, pull request, final head, recommendation, checks, merge method and authority. Human approval is the default.

A repository owner may record a bounded delegation for specified low-risk work. Such delegation does not permit skipped review, widened scope or automatic merge.

## Post-merge verification

Use post-merge verification only for evidence that genuinely cannot exist earlier, such as template discovery on GitHub, a merge-triggered publication or production-only behaviour.

After merge:

- confirm the expected commit is on `main`;
- confirm issue-closing behaviour;
- inspect named post-merge checks;
- record success or failure;
- create a bounded corrective issue if required.

Do not defer tests or inspections that could have run before merge.

## Stop conditions

Stop before implementation when:

- the issue is planning-only;
- outcome, scope or acceptance criteria are unclear;
- dependencies or the safe starting point are unresolved;
- material intent or authority is missing;
- a non-goal would be violated.

Stop during implementation when:

- scope becomes materially broader;
- the contract becomes contradictory;
- safe validation is impossible and correctness depends on it;
- a tool targets the wrong object;
- a Class A protected or unbounded mutation occurs;
- a Class B effect cannot be confidently bounded, restored or verified within the original authority boundary;
- continuing would require new intent or authority;
- a protected repository or publication operation is required.

Class B and Class C effects do not require a full stop when the approved recovery conditions are satisfied. They must still be recorded accurately where material.

Stop before merge when:

- the recommendation is not `Approve`;
- validation is failing, stale or materially incomplete;
- review findings remain;
- implementation is incomplete;
- merge authority is absent.
