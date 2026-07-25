# Method record — files-to-prompt experiment

## Governing method

This experiment uses the working method v0.2 from:

- repository: `8ft0-ai/diataxis-for-ai-repos`;
- path: [`working/method-v0.2/`](../../working/method-v0.2/);
- governing repository commit: `69649025f0a5c777d7075f1f152c39895252fd35`;
- planning decision: [issue #8](https://github.com/8ft0-ai/diataxis-for-ai-repos/issues/8);
- execution contract: [issue #10](https://github.com/8ft0-ai/diataxis-for-ai-repos/issues/10).

The method is applied at **Level 3 — Governed workflow** because this is a comparative method experiment with executable reader tasks, an external target, explicit mutation boundaries and a separate evidence review.

## Experiment-specific interpretation

The approved workflow remains unchanged:

```text
Inspect repository evidence
→ use the human-approved reader groups and tasks
→ execute or inspect each task within the approved boundary
→ classify observable failures and retained paths
→ select the smallest sufficient response
→ record provenance, local effects and uncertainty
→ perform a separate evidence review
→ close out with Adopt, Adapt or Reject
```

No documentation is proposed because a Diátaxis category or directory is empty. A response is justified only by an observed task failure, incorrect claim, authority gap or maintenance risk.

## Evidence and authority rules

Material statements use the method's four claim states:

- **Observation** — directly visible in repository evidence or an executed result.
- **Authority** — established by the pinned source, executable interface, approved issue or maintainer decision.
- **Inference** — a reasoned conclusion not directly established.
- **Uncertainty** — a question the available evidence cannot resolve.

The target source can establish current behaviour. It does not establish maintainer intent, desired compatibility policy, reader priority or historical rationale.

## Retrieval and execution provenance

The approved direct GitHub clone was attempted but failed because the execution runtime could not resolve `github.com`.

The first execution pass, recorded durably on issue #10, obtained `files-to-prompt==0.6` from the available package source and verified that these source-distribution files had the same Git blob hashes as the pinned target commit:

| File | Git blob SHA |
| --- | --- |
| `README.md` | `06e1dad0d96ccdf6232899d7da8b20f2c2d4722e` |
| `pyproject.toml` | `9cf07cb2951d96507c23387629c49cc8caf4cff9` |
| `files_to_prompt/cli.py` | `7eee04f5794198a822a3f812c065f1441b7ef207` |
| `tests/test_files_to_prompt.py` | `52689959119bb338e5da735c014c8872fcfaf00b` |

That pass supplies the installed-package and full pytest evidence.

When the experiment resumed, the local transcript had expired, GitHub DNS still failed and the package mirror no longer exposed version 0.6. The fresh review therefore used:

- direct inspection of the same pinned GitHub blobs through the connected GitHub source;
- a local behavioural transcription of the pinned CLI for controlled fixture checks;
- system Python 3.11, Click 8.1.8 and pytest 9.0.2;
- a targeted reproduction of the pinned binary-warning test logic.

The behavioural transcription was not byte-identical to the authoritative blob. Its results are corroborating review evidence only. It is not described as a clone, installed package, pinned checkout or clean-context completion.

## Mutation and recovery interpretation

The merged Class A/B/C rules apply.

- Expected virtual environments, caches, `__pycache__`, `.pytest_cache` and packaging metadata are **Class C** when they stay in approved disposable paths.
- During the first T6 pass, expected packaging artefacts appeared in an unplanned location inside the disposable source reconstruction. This is recorded separately as a bounded **Class B** placement deviation.
- The disposable workspace was restored and verified.
- No remote target or target GitHub object was changed.

## Review boundary

The separate review was a fresh pass by the same connected account. It repeated T1, T3 and T5 with new fixtures and performed a targeted compatibility check for the T6 failure. It is labelled **separately reviewed**, not independent human validation.

## Material method deviations

No reader group, task, completion condition or protected decision was changed.

The retrieval route differed from the preferred clone path because the runtime could not resolve GitHub. This is recorded as an execution limitation rather than silently treated as equivalent evidence.
