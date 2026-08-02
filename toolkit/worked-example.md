# Worked example — files-to-prompt

The primary worked example for this toolkit is the accepted assessment of [`simonw/files-to-prompt`](https://github.com/simonw/files-to-prompt) at pinned commit `1b234ff6dccb2ca3e56b5c256696558fb85306dc`.

This page explains how the toolkit decisions appeared in practice. It does not replace the canonical experiment records:

- [`method.md`](../experiments/files-to-prompt/method.md) — governing method, evidence rules, provenance and review boundary;
- [`experiment-plan.md`](../experiments/files-to-prompt/experiment-plan.md) — approved readers, tasks, execution boundary and human task decision;
- [`assessment-closeout.md`](../experiments/files-to-prompt/assessment-closeout.md) — task evidence, findings, bounded remediation, review and limitations.

Read those files for exact commands, evidence identifiers and the full record.

## Why this is the primary adopter example

files-to-prompt is a small distributable Python CLI. It offered materially different evidence from the earlier RaceIQ static-dashboard experiment:

- installation and command execution were relevant to real reader outcomes;
- command options and output formats provided canonical interfaces;
- contributor dependencies and tests exposed a maintenance path;
- clean-context completion could be assessed for several tasks;
- the lighter three-record method could be used end to end.

The experiment remained small enough to understand without private organisational context.

It is not proof that the method generalises to large repositories, services, private codebases or different agents.

## 1. Evidence-supported readers

The planning record proposed and obtained human approval for three functional reader groups:

- **G1 — First-time CLI user**
- **G2 — Advanced CLI user or workflow integrator**
- **G3 — Contributor or maintainer**

These groups were supported by observable repository interfaces: installation and basic usage, advanced command options and formats, and the documented development and test path.

The assessment did not infer organisational structure, reader demand or task priority from source code alone.

## 2. Approved representative tasks

Six tasks were approved before execution:

1. install the package and produce a first prompt;
2. select file types while respecting hidden and ignored files;
3. distinguish the three ignore controls;
4. generate Markdown and Claude XML output;
5. use NUL-separated standard input for filenames containing spaces;
6. establish the contributor test path and reconcile documented options.

Each task had:

- an evidence-supported reader;
- a defined starting context;
- a recognisable completion condition;
- an expected documentation entry point;
- required evidence states;
- a bounded execution environment.

The tasks described reader outcomes. They were not selected to create one tutorial, one how-to, one reference and one explanation.

## 3. Evidence and execution

The first execution pass used `files-to-prompt==0.6` from a source distribution. Four material files were verified against the Git blob hashes at the pinned repository commit. That pass supplied the installed-package and full-test evidence.

When the assessment resumed:

- the runtime still could not resolve `github.com` for a direct clone;
- the package mirror no longer exposed version 0.6 or the required dependency path;
- pinned repository blobs remained available through the connected GitHub source;
- a non-byte-identical behavioural transcription was used only for controlled corroborating checks;
- a targeted compatibility check was run under the available Click version.

The close-out did not treat these routes as equivalent.

This limitation directly informed the V1 rules:

- label retrieval modes explicitly;
- preserve durable command/result summaries before local evidence expires;
- record runtime and dependency versions;
- do not describe a package reconstruction, connector inspection or behavioural fallback as a pinned clone.

## 4. Task outcomes

The tasks produced different decision types.

### Retain

The evidence supported retaining:

- the basic installation and first-use path;
- the distinct ignore controls;
- the NUL-separated standard-input guidance;
- the dynamic outer-fence behaviour for content containing triple backticks.

A complete task did not trigger a rewrite merely because the method was assessing documentation.

### Correction

Two observable documentation problems justified bounded corrections.

#### `--ignore-gitignore` wording

The documentation wording implied that the option included all files. Observed behaviour showed that it disabled `.gitignore` filtering but did not include hidden files without `--include-hidden`.

The smallest sufficient response was a correction to the option description, not a redesign of ignore behaviour or a new guide.

#### Markdown language tag

The README example showed a `markdown` language tag for `.md` input. The pinned implementation lacked an `md` mapping, and observed output used an unlabelled fence.

The assessment could establish the mismatch. It could not decide whether the code should add a mapping or the documentation should describe current behaviour.

### No change

The evidence did not justify:

- a new first-use tutorial;
- a four-folder Diátaxis reorganisation;
- a standalone explanation page for Claude XML output.

These no-change outcomes were part of the result, not omissions from it.

### Human authority required

The contributor task exposed a version-sensitive test result:

- the first full run produced 19 passing tests and one failure under Click 8.4.2;
- the targeted failing test passed under Click 8.1.8;
- repository metadata did not state an intended supported Click range.

The evidence showed a compatibility boundary. It did not establish the maintainer’s desired policy or the correct fix.

The bounded result was to request a maintainer decision before prescribing a dependency constraint or test rewrite.

## 5. Bounded remediation

The close-out produced three bounded items:

1. clarify the interaction between `--ignore-gitignore` and hidden files;
2. reconcile the Markdown language-tag example with the current mapping and output;
3. decide and enforce the intended Click compatibility policy.

Each item named:

- the reader and task;
- the observed finding;
- exact evidence;
- the smallest sufficient response;
- scope and deliberate exclusions;
- permitted claims;
- human-authority needs;
- task-specific validation.

The experiment stopped before drafting or applying changes to the target repository.

The recommendations have not been presented as accepted by the files-to-prompt maintainer.

## 6. Separate evidence review

A fresh pass by the same connected account repeated T1, T3 and T5 and performed a targeted compatibility comparison for T6.

The review accepted the reader groups, representative tasks, findings and classifications with explicit provenance limitations.

It was labelled **separately reviewed**, not independently human validated.

## 7. Mutation and recovery evidence

The target repository and its canonical source remained unchanged.

The contributor task produced:

- expected local packaging metadata and caches, recorded as Class C;
- a bounded placement deviation inside a disposable reconstruction, recorded separately as Class B.

The workspace was restored and verified. The event model prevented expected local artefacts from being misclassified as a protected remote mutation.

## 8. What the example demonstrates

The example supports these narrow conclusions:

- approved reader tasks can expose specific documentation and authority problems;
- executable evidence can change or strengthen source-inspection conclusions;
- complete tasks can justify retention;
- observed mismatches can justify small corrections;
- some questions should stop at human authority;
- a three-record Level 3 assessment can remain reconstructable;
- provenance and environment details materially affect the strength of claims.

It does not establish:

- independent practitioner agreement;
- broad repository or model portability;
- large-repository proportionality;
- the quality of drafted remediation;
- target-maintainer acceptance of the proposed backlog.

## 9. Supporting earlier evidence — RaceIQ

The earlier [RaceIQ experiment](../experiments/raceiq/README.md) remains supporting evidence.

RaceIQ demonstrated that a source-inspection assessment could:

- distinguish observable failure from general criticism;
- preserve uncertainty and missing authority;
- recommend correction and navigation rather than a documentation set;
- retain useful material and record no-change decisions.

Its [close-out](../experiments/raceiq/closeout.md) also showed why the original seven-file evidence pack was too heavy and why clean-context execution, human task approval and lighter adoption levels were needed.

RaceIQ is not the primary adopter example because it did not execute reader tasks in a clean runtime context and used the earlier, heavier record shape.

## 10. Follow the example without copying its conclusions

When using this toolkit on another repository:

- reuse the method and record shapes;
- select readers and tasks from that repository’s evidence;
- define a new execution boundary;
- record actual retrieval and dependency conditions;
- permit different outcomes, including no finding or no change;
- do not assume that files-to-prompt’s task set or remediation applies elsewhere.

The worked example demonstrates the operating method. It is not a benchmark answer key.