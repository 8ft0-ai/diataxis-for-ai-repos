# Assessment and close-out — files-to-prompt

## 1. Experiment summary

- **Experiment:** Second clean-context documentation assessment
- **Target:** [`simonw/files-to-prompt`](https://github.com/simonw/files-to-prompt)
- **Pinned commit:** [`1b234ff6dccb2ca3e56b5c256696558fb85306dc`](https://github.com/simonw/files-to-prompt/commit/1b234ff6dccb2ca3e56b5c256696558fb85306dc)
- **Method:** [Working method v0.2](../../working/method-v0.2/README.md) at `69649025f0a5c777d7075f1f152c39895252fd35`
- **Approved plan:** [issue #8](https://github.com/8ft0-ai/diataxis-for-ai-repos/issues/8)
- **Execution contract:** [issue #10](https://github.com/8ft0-ai/diataxis-for-ai-repos/issues/10)
- **Assessment date:** 2026-07-23
- **Adoption level:** Level 3

### Question under test

Can method v0.2 produce a useful, proportionate and reconstructable documentation decision from executable reader tasks against a small Python CLI, without mutating the target or manufacturing new documentation?

### Environment and provenance

The first pass used an installed `files-to-prompt==0.6` package reconstructed from a source distribution whose four material files matched the pinned GitHub blob hashes. That pass recorded T1–T6 results on issue #10.

On resumption:

- direct GitHub clone failed because `github.com` could not be resolved;
- the package mirror no longer exposed version 0.6 or its dependencies;
- system Python 3.11 provided Click 8.1.8 and pytest 9.0.2;
- fresh fixture checks used direct pinned-source inspection plus a behavioural CLI transcription;
- the fresh pass is corroborating review evidence, not a pinned checkout or installed-package clean-context run.

### Target state and local-effect evidence

- **Remote target unchanged:** yes; no target write operation was performed.
- **Canonical tracked source unchanged:** yes; the target was inspected through the pinned GitHub commit, and the first pass matched the four material source-distribution files to their Git blob SHAs.
- **Generated local artefacts observed:** environments, fixtures, outputs, packaging metadata, `__pycache__` and test caches.
- **Disposable workspace restored:** yes for the first T6 contributor copy; later fallback paths were disposable.
- **Target GitHub objects changed:** none.

### Mutation and local-effect event register

| ID | Task or operation | Event class | Effect boundary | Observed effect | Evidence | Recovery or escalation | Final state |
| --- | --- | --- | --- | --- | --- | --- | --- |
| M1 | T6 editable install and pytest | Class C | generated local | expected packaging metadata and caches | issue #10 execution record | record and clean at close-out | disposable |
| M2 | T6 editable install | Class B | generated local | expected artefacts appeared inside the disposable source reconstruction rather than a preferred generated path | issue #10 incident record | reset and clean the disposable copy; verify status | restored and verified |

## 2. Evidence register

| ID | Evidence | Claim role | State or limitation |
| --- | --- | --- | --- |
| E1 | Pinned README blob `06e1dad0…` | Documented installation, options and development path | Authority for current documentation |
| E2 | Pinned `pyproject.toml` blob `9cf07cb2…` | Version and dependency declarations | Authority; `click` has no version bound |
| E3 | Pinned CLI blob `7eee04f5…` | Current option and output implementation | Authority for behaviour at the pinned commit |
| E4 | Pinned tests blob `52689959…` | Expected tested behaviour | Authority for tests at the pinned commit |
| E5 | Issue #10 first-pass evidence | Installed-package commands, T1–T6 results, Click 8.4.2 pytest result, mutation restoration | Durable observation; original local files expired |
| E6 | Fresh T1–T5 fixture outputs | Behavioural corroboration | Controlled fallback, not clean-context installed-package evidence |
| E7 | Fresh repeated T1, T3 and T5 outputs | Separate review | Same-account review; not human validation |
| E8 | Targeted binary-warning test under Click 8.1.8: `1 passed` | Compatibility comparison | One targeted test, not the full target suite |

## 3. Approved readers and tasks

Approved groups: G1 first-time CLI user; G2 advanced CLI user or workflow integrator; G3 contributor or maintainer.

Approved tasks: T1–T6 from issues #8 and #10. No task was silently replaced.

## 4. Compact task records

### T1 — Install and produce a first prompt

- **Reader group:** G1
- **Actual path:** README installation and basic usage; two-file disposable fixture
- **Commands/interactions:** installed-package first pass; fresh fixture corroboration
- **Mutation events:** Class C disposable environment and output only
- **Evidence states:** source inspected; command executed; behaviour observed; clean-context completed; separately reviewed
- **Primary result:** Complete
- **Observable friction:** current resumption environment could not retrieve the package, but the original approved run completed successfully
- **Smallest sufficient response:** Retain
- **Limitations:** package/network availability is environmental rather than a documentation correctness result

### T2 — Select file types while respecting hidden and ignored files

- **Reader group:** G2
- **Observed behaviour:** `-e txt` selected text files; hidden files were excluded by default; `--include-hidden` included them; `.gitignore` was honoured by default; `--ignore-gitignore` included gitignored visible files but still excluded hidden files
- **Evidence states:** source inspected; command executed; behaviour observed
- **Primary result:** Complete
- **Observable friction:** “include all files” overstates `--ignore-gitignore`; hidden-file filtering remains separate
- **Smallest sufficient response:** Correction
- **Finding:** F1

### T3 — Distinguish ignore-option behaviour

- **Reader group:** G2
- **Observed behaviour:** `--ignore 'data*'` excluded matching files and directories; adding `--ignore-files-only` preserved traversal into the matching directory; `--ignore-gitignore` included a file otherwise excluded by `.gitignore`
- **Evidence states:** source inspected; command executed; behaviour observed; separately reviewed
- **Primary result:** Complete
- **Smallest sufficient response:** Retain
- **Limitations:** fnmatch and `.gitignore` handling are simplified implementations, but the tested task is supported

### T4 — Generate Markdown and Claude XML output

- **Reader group:** G2
- **Observed behaviour:** both output modes completed; content containing triple backticks was wrapped in a four-backtick fence; CXML output used the documented document structure
- **Evidence states:** source inspected; command executed; behaviour observed
- **Primary result:** Complete
- **Observable friction:** `.md` output used an unlabelled fence although the README example shows `markdown`; CXML emits raw content and should be treated as XML-like rather than a general XML escaping guarantee
- **Smallest sufficient response:** Correction
- **Finding:** F2

### T5 — Use NUL-separated stdin for filenames containing spaces

- **Reader group:** G2
- **Observed behaviour:** both filenames containing spaces were processed without splitting
- **Evidence states:** source inspected; command executed; behaviour observed; clean-context completed; separately reviewed
- **Primary result:** Complete
- **Smallest sufficient response:** Retain

### T6 — Establish the contributor test path and reconcile options

- **Reader group:** G3
- **Observed behaviour:** the documented editable installation completed in the first pass; pytest ran 20 tests with 19 passing and one failing under Click 8.4.2; failure occurred at `CliRunner(mix_stderr=False)`; the same targeted test logic passed under Click 8.1.8; README option names matched the Click decorators
- **Mutation events:** M1 and M2
- **Evidence states:** source inspected; command executed; behaviour observed; separately reviewed
- **Primary result:** Partial
- **Observable friction:** the documented contributor path does not identify a supported Click range and can resolve to incompatible test behaviour
- **Smallest sufficient response:** Human authority required
- **Finding:** F3
- **Limitations:** the resumed environment could not rerun the full target suite; comparison uses the durable first-pass result and a fresh targeted test

## 5. Findings

### F1 — `--ignore-gitignore` overstates inclusion behaviour

- **Affected task:** T2
- **Observed condition:** the option disables `.gitignore` filtering but does not include hidden files unless `--include-hidden` is also supplied
- **Evidence:** E1, E3, E5 and E6
- **Claim state:** Observation
- **Why action is justified:** the current “include all files” wording can lead an integrator to predict the wrong file set

### F2 — Markdown language-tag claim conflicts with `.md` behaviour

- **Affected task:** T4
- **Observed condition:** the README example shows a `markdown` fence for `.md`, while the pinned mapping has no `md` key and observed output is unlabelled
- **Evidence:** E1, E3, E5 and E6
- **Claim state:** Observation
- **Why action is justified:** the reference example describes output that the pinned implementation does not produce

### F3 — Contributor test path depends on an unstated Click compatibility decision

- **Affected task:** T6
- **Observed condition:** `click` is unbounded; the full suite produced 19 passed and 1 failed under Click 8.4.2, while the targeted failing test passes under Click 8.1.8
- **Evidence:** E2, E4, E5 and E8
- **Claim state:** Observation for the results; Uncertainty for the intended compatibility policy
- **Why action is justified:** contributors cannot infer which dependency range or test adaptation the maintainer intends

## 6. Bounded remediation backlog

### R1 — Clarify `--ignore-gitignore` interaction

- **Reader and task:** G2, T2
- **Finding:** F1
- **Smallest sufficient response:** Correction / reference clarification
- **Scope:** state that the option ignores `.gitignore` rules; hidden files still require `--include-hidden`; align README and Click help wording
- **Deliberate exclusions:** no redesign of ignore semantics
- **Validation:** repeat T2 combinations and compare documented result sets

### R2 — Reconcile Markdown language-tag documentation

- **Reader and task:** G2, T4
- **Finding:** F2
- **Smallest sufficient response:** Correction
- **Scope:** make the README example and language-tag claim match the authoritative mapping and observed `.md` behaviour
- **Permitted claim:** `.md` currently receives an unlabelled fence at the pinned commit
- **Human-authority boundary:** whether code should add an `md` mapping is a maintainer decision
- **Validation:** repeat T4 with `.md`, `.py` and embedded backticks

### R3 — Decide and enforce contributor Click compatibility

- **Reader and task:** G3, T6
- **Finding:** F3
- **Smallest sufficient response:** Human authority required, followed by a bounded contributor-path correction
- **Decision required:** supported Click versions, dependency constraint or test adaptation
- **Scope after decision:** align package metadata, tests and development instructions with the chosen policy
- **Deliberate exclusions:** do not infer a version bound from only two observed Click versions
- **Validation:** create a fresh environment from declared metadata and run the full suite

## 7. Retain, no-change and authority-required decisions

### Retain

- **K1:** basic installation, usage and default output routing for T1
- **K2:** the three distinct ignore controls for T3
- **K3:** NUL-separated stdin guidance for T5
- **K4:** dynamic outer-fence behaviour for Markdown containing triple backticks

### No change

- **N1:** no new tutorial is justified; the existing first-use path completed
- **N2:** no four-folder Diátaxis reorganisation is justified
- **N3:** no new standalone CXML explanation is justified by the tested task; a concise limitation is sufficient

### Human authority required

- **A1:** choose the intended Click compatibility policy before prescribing a dependency constraint or test rewrite
- **A2:** decide whether `.md` should gain a code mapping or the README should document the current unlabelled output

## 8. Separate evidence review

- **Reviewer type:** same connected account, fresh pass
- **Tasks repeated:** T1, T3 and T5 with independent fixtures
- **Additional check:** exact target binary-warning test logic under Click 8.1.8
- **Independence limitation:** not independent human validation; execution used a behavioural transcription

### Review judgements

- Reader groups: Accept
- Representative tasks: Accept
- Evidence states and task results: Accept with explicit provenance limitations
- Findings and classifications: Accept
- Usefulness and proportionality: Accept with adaptation
- Close-out recommendation: Accept **Adapt**

The fresh pass reproduced the T1, T3 and T5 behavioural conclusions. It also confirmed that the T6 failure is version-sensitive rather than an invariant failure of the test logic.

## 9. Usefulness and proportionality

The method improved the decision by separating three kinds of outcome:

- useful paths to retain;
- two concrete documentation corrections;
- one compatibility decision that documentation cannot safely invent.

The evidence gate prevented a generic rewrite or a new documentation set. The three-record shape was usable, but execution provenance became burdensome when local evidence expired and the runtime could no longer retrieve the target package. Future use should make the durable evidence summary the primary record rather than relying on ephemeral local output paths.

## 10. Limitations

- Direct clone was unavailable because of runtime DNS.
- The resumed package mirror did not expose version 0.6 or Click.
- The first full execution transcript was not retained locally; the GitHub issue record is the durable evidence.
- Fresh fallback execution used a non-byte-identical behavioural transcription.
- The full pytest suite was not rerun on resumption.
- Review was by the same account, not an independent human.
- The experiment covers one small Python CLI and does not prove broader generality.

## 11. Comparative observations

Compared with RaceIQ:

- executable tasks exposed correctness and dependency risks that source-only walkthroughs could not establish;
- the lighter three-record structure remained sufficient;
- explicit task approval, evidence states, retain/no-change outcomes and protected authority continued to add value;
- environment and retrieval provenance required more care;
- the merged mutation-event model prevented expected local artefacts from becoming another false full stop.

## 12. Groundedness review

### Did we do what was needed?

Yes, with disclosed limitations. The approved readers and T1–T6 were assessed, findings trace to evidence, useful paths were retained, a separate review was performed and no target mutation occurred.

### Did we only do what was asked?

Yes. The repository change contains only the three experiment records. No target documentation, code, automation, schema, workflow or external GitHub object is created.

## 13. Recommendation

**Adapt**

### Rationale

The method produced decision value: it distinguished retained paths, precise corrections and a genuine authority boundary. It should not yet be frozen unchanged. Before broader adoption, adapt the method to require a durable execution-evidence summary and explicit retrieval-mode labels such as clone, exact package reconstruction, source inspection and behavioural fallback.

### Components to retain

- evidence gate before drafting;
- human-approved representative tasks;
- claim and execution-evidence states;
- smallest-sufficient-response ordering;
- retain and no-change outcomes;
- mutation event register and separate target-state evidence;
- separate evidence review with honest independence labels.

### Components to adapt

- make durable command/result summaries mandatory before ephemeral environments are discarded;
- record dependency versions as first-class contributor-task evidence;
- distinguish retrieval and execution modes explicitly in every executable assessment;
- avoid treating a source distribution, transcription or connector inspection as equivalent to a pinned clone.

### Next decision question

> Do the RaceIQ and files-to-prompt experiments justify freezing an assessment-only V1, or should one more materially different repository test proportionality before the method becomes a stable contract?

### Human acceptance

Pending maintainer review through the issue #10 pull request.
