# Experiment plan — files-to-prompt

## 1. Experiment identity

- **Experiment name:** Second clean-context documentation assessment
- **Parent stage:** [#7 — Validate the adapted assessment method on a second repository](https://github.com/8ft0-ai/diataxis-for-ai-repos/issues/7)
- **Planning decision:** [#8 — Approve method v0.2 and the second assessment experiment](https://github.com/8ft0-ai/diataxis-for-ai-repos/issues/8)
- **Execution contract:** [#10 — Run and review the second clean-context assessment](https://github.com/8ft0-ai/diataxis-for-ai-repos/issues/10)
- **Method:** [Working method v0.2](../../working/method-v0.2/README.md) at repository commit `69649025f0a5c777d7075f1f152c39895252fd35`
- **Prepared by:** repository-aware AI agent under maintainer-approved issues
- **Assessment date:** 2026-07-23
- **Adoption level:** Level 3

## 2. Target repository

- **Repository:** [`simonw/files-to-prompt`](https://github.com/simonw/files-to-prompt)
- **Pinned commit:** [`1b234ff6dccb2ca3e56b5c256696558fb85306dc`](https://github.com/simonw/files-to-prompt/commit/1b234ff6dccb2ca3e56b5c256696558fb85306dc)
- **Version represented:** `0.6`
- **Repository type:** Small Python command-line tool
- **Public or private:** Public
- **Assessment modes:** source inspection, command execution, behaviour observation and separate review

### Selection rationale

The target differs materially from the first RaceIQ experiment. It is a distributable CLI with executable options, package metadata, contributor instructions and tests. It can therefore test clean-context user tasks, reference accuracy and contributor-path maintenance risk.

### Representativeness limitations

The target does not represent a large monorepo, service deployment, private dependency environment, graphical application, multi-team documentation estate or architecture-rationale corpus.

## 3. Evidence inventory and authority map

| ID | Source | Claim role | Authority or limitation |
| --- | --- | --- | --- |
| E1 | Pinned `README.md`, blob `06e1dad0…` | Installation, option and contributor documentation | Authoritative for documented reader paths, not intended future behaviour |
| E2 | Pinned `pyproject.toml`, blob `9cf07cb2…` | Version, runtime dependency and test extra | Authoritative package metadata; dependency `click` is unbounded |
| E3 | Pinned `files_to_prompt/cli.py`, blob `7eee04f5…` | Current option definitions and output behaviour | Authoritative executable source at the pinned commit |
| E4 | Pinned `tests/test_files_to_prompt.py`, blob `52689959…` | Expected tested behaviour | Authoritative test source at the pinned commit |
| E5 | Issue #10 execution incident and evidence comments | First-pass commands, source hash checks, pytest result and restoration | Durable experiment evidence; the original local transcript is no longer available |
| E6 | Fresh controlled fixture outputs under `/tmp/issue-10-files-to-prompt/outputs/` | Corroborating T1–T5 behaviour and repeated review | Behavioural fallback, not a byte-identical checkout or installed package |
| E7 | Targeted binary-warning test under Click 8.1.8 | Compatibility comparison | One targeted test only; not the full target suite |

### Direct contradictions or stale claims

1. The README and CLI help describe `--ignore-gitignore` as including “all files”, but hidden files remain excluded unless `--include-hidden` is also used.
2. The README says the Markdown language tag is guessed from the filename and shows `markdown` for a `.md` file. The pinned `EXT_TO_LANG` mapping has no `md` entry, and observed `.md` output uses an unlabelled fence.
3. The contributor path installs unconstrained `click`. A first-pass environment resolving Click 8.4.2 produced one failing test, while the targeted test passes under Click 8.1.8.

These observations do not establish which code or documentation behaviour the maintainer prefers.

## 4. Approved reader groups

### G1 — First-time CLI user

- **Evidence basis:** installation and basic usage in E1; console entry point in E2.
- **Reader need:** install the tool, provide files or a directory, and recognise the output.
- **Limitation:** package-index and network availability vary by environment.

### G2 — Advanced CLI user or workflow integrator

- **Evidence basis:** filtering, ignore, structured-output and stdin options in E1 and E3.
- **Reader need:** predict filtering and output behaviour reliably in scripts.
- **Limitation:** some option interactions and output constraints are not fully explicit in prose.

### G3 — Contributor or maintainer

- **Evidence basis:** development instructions in E1, package metadata in E2 and tests in E4.
- **Reader need:** create a development environment and obtain a meaningful test result.
- **Limitation:** the repository does not state a supported Click version range or compatibility policy.

## 5. Approved representative tasks

### T1 — Install and produce a first prompt

- **Reader group:** G1
- **Starting context:** unfamiliar reader with Python and a disposable two-file fixture
- **Completion condition:** installed 0.6 package processes the fixture and the reader recognises path/content separators
- **Entry point:** README installation and usage
- **Expected evidence states:** source inspected, command executed, behaviour observed, clean-context completed

### T2 — Select file types while respecting hidden and ignored files

- **Reader group:** G2
- **Completion condition:** use documented flags to select text files and explain hidden-file and `.gitignore` interaction
- **Entry point:** README options

### T3 — Distinguish ignore-option behaviour

- **Reader group:** G2
- **Completion condition:** predict and verify `--ignore`, `--ignore-files-only` and `--ignore-gitignore`
- **Entry point:** README options and CLI source

### T4 — Generate Markdown and Claude XML output

- **Reader group:** G2
- **Completion condition:** produce both formats from two files, including Markdown containing triple backticks, and identify structural guarantees and limitations
- **Entry point:** README output sections and CLI source

### T5 — Use NUL-separated stdin for filenames containing spaces

- **Reader group:** G2
- **Completion condition:** process both spaced filenames without whitespace splitting
- **Entry point:** README stdin section

### T6 — Establish the contributor test path and reconcile options

- **Reader group:** G3
- **Completion condition:** run the documented contributor installation and pytest path, then compare README options with the Click command definition
- **Entry point:** README development section, `pyproject.toml`, CLI decorators and tests

## 6. Execution and safety boundary

### Permitted operations

- public clone attempt;
- public package retrieval for version 0.6;
- pinned source inspection through the connected GitHub source;
- disposable Python environments, fixtures and outputs;
- `files-to-prompt`, Python, pip, pytest and read-only Git commands;
- synthetic local baselines used only to detect disposable-copy changes.

### Network boundary

- public GitHub target and declared Python dependencies only;
- no credentials, secrets or private source.

### Prohibited operations

- target source edits, commits, pushes or forks;
- target issues, discussions or pull requests;
- target settings, workflows, releases, deployments or publication;
- use of real private files as fixtures;
- inferred target intent or compatibility policy.

### Planned local effects

| ID | Related task | Effect boundary | Authority | Expected class and effects | Permitted paths | Recovery |
| --- | --- | --- | --- | --- | --- | --- |
| P1 | T1–T5 | generated local | #8 and #10 | Class C: environment, fixtures and outputs | `/tmp/issue-10-files-to-prompt/` | clean or discard at close-out |
| P2 | T6 | generated local | #8 and #10 | Class C: editable-install metadata, caches and test output | separate disposable contributor copy and environment | preserve evidence, reset/clean or recreate |

Escalation to Class A is required for a remote or protected mutation, canonical source change outside contract, escaped effect, missing authority, private-data exposure or an effect that cannot be bounded or restored.

## 7. Target-state evidence plan

- Record the pinned target commit through the connected GitHub source.
- Record canonical blob SHAs for material files.
- Keep fixtures and generated outputs in disposable paths.
- Record remote target, canonical source, generated artefacts and restoration separately.
- Do not claim that a source distribution or behavioural transcription is a clone.

## 8. Separate review boundary

- **Reviewer type:** same connected account, fresh pass
- **Tasks repeated:** T1, T3 and T5
- **Additional check:** targeted T6 binary-warning compatibility check
- **Independence limitation:** not independent human validation; fallback execution used a behavioural transcription

## 9. Human task-approval decision

The reader groups, task set, starting contexts, completion conditions, execution boundary and review boundary were approved in issue #8. No task was materially redefined.

## 10. Readiness

- Dependencies satisfied: yes
- Method present on `main`: yes
- Target commit verified through GitHub: yes
- Task approval complete: yes
- Execution boundary recorded: yes
- Review boundary recorded: yes
- Decision: **Ready and executed with recorded retrieval limitations**
