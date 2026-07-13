# Assessment instruction used

Use this instruction to reproduce the assessment against the pinned RaceIQ snapshot.

```text
You are assessing the existing documentation of:

Repository: 8ft0-ai/RaceIQ
Commit: 7addbd39774f2ab5a59be7bd42c9e6d9cdcf65ab

This is an assessment-only task.

Do not:
- modify the target repository;
- create a branch, issue or pull request in the target repository;
- draft proposed documentation;
- infer undocumented intent, policy, architecture or history;
- create work because a Diátaxis category, file or directory is absent;
- treat source code as complete truth;
- treat your own evaluation as independent human validation.

Your goal is to determine where representative readers can and cannot complete real tasks using the existing documentation and repository evidence.

Work in this order:

1. Inventory evidence
   - Identify documentation entry points.
   - Identify executable interfaces, data manifests, visible UI structure and other canonical behaviour evidence.
   - Record contradictions, stale claims and uncertainty.
   - Distinguish observation, authority, inference and uncertainty.

2. Identify reader groups
   - Include only groups supported by the repository's observable purpose and interfaces.
   - Do not invent organisational personas.
   - State the evidence supporting each group.

3. Select representative tasks
   - Each task must have a defined starting context and recognisable completion condition.
   - Prefer tasks that exercise meaningful documentation paths, not only repository setup.
   - Keep the set proportionate to the repository.
   - The correct outcome may be fewer tasks if the evidence does not justify more.

4. Walk each task
   Record:
   - reader group;
   - starting knowledge and environment;
   - task and completion condition;
   - expected entry point;
   - actual documentation and evidence path;
   - next permitted action;
   - protected decisions;
   - result: complete, partial, blocked or not tested;
   - observed friction;
   - confidence and limitations.

   Do not report that documentation is simply "poor". Describe the observable failure.

5. Classify observed needs
   Consider, in this order:
   - retain existing content;
   - no documentation change;
   - correction;
   - navigation change;
   - tutorial;
   - how-to guide;
   - reference;
   - explanation;
   - unresolved authority requiring human input.

   Do not require all four Diátaxis forms.

6. Create bounded remediation items
   Each item must include:
   - affected reader and task;
   - observed failure;
   - exact supporting evidence;
   - proposed document form or smaller corrective action;
   - scope and deliberate exclusions;
   - claims that available evidence permits;
   - claims requiring human authority;
   - validation method;
   - stopping conditions.

7. Stop before drafting
   Do not write the proposed RaceIQ documentation changes.
   Do not create target-repository work items.
   Record retained-content, no-change and unresolved-authority outcomes explicitly.

8. Close out
   Evaluate whether the method:
   - distinguished task failure from general criticism;
   - selected credible tasks;
   - used appropriate authority;
   - preserved uncertainty;
   - produced a useful and proportionate backlog.

   Recommend Adopt, Adapt or Reject.
   State limitations and the next decision question.
```

## Reproduction boundary

The instruction depends only on the pinned public repository evidence and the working method in this experiment. It does not depend on private chat history.

A reproduction that executes the dashboard in a browser may strengthen or revise source-verified walkthrough results. It must not silently convert unexecuted behaviour into observed runtime evidence.
