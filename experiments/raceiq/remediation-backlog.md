# Evidence-backed remediation backlog

This backlog stops before drafting. It records bounded work candidates for RaceIQ and explicit decisions not to create broader documentation.

Evidence identifiers are defined in [`baseline.md`](baseline.md#evidence-register). Task findings are in [`walkthroughs.md`](walkthroughs.md).

## R1 — Make the README feature summary current

- **Reader task:** T2 — understand current capabilities before running.
- **Observed failure:** F1 — the README current-scope list omits the Report cards capability implemented and exposed at the pinned commit.
- **Evidence:** E1, E2, E5.
- **Classification:** Correction.
- **Proposed scope:** Update the existing README feature list so it matches the visible application sections. Clarify that the list describes current user-facing capabilities rather than a roadmap.
- **Deliberate exclusions:** No new overview page; no feature marketing; no inferred future scope.
- **Permitted claims:** Current tab names and source-verified capabilities.
- **Human-authority needs:** Product naming only if maintainers prefer terminology different from the UI.
- **Validation:** Compare the revised list with E2 and repeat T2 from the repository landing page.
- **Stopping conditions:** Stop if the UI is being changed concurrently or if the README is not intended to describe current scope.

## R2 — Route analytical readers to the existing Method guidance

- **Reader task:** T3 — decide whether delay values are official records.
- **Observed failure:** F2 — the repository entry point does not clearly route readers to the stronger in-application interpretation boundary.
- **Evidence:** E1 and E3.
- **Classification:** Navigation plus small correction.
- **Proposed scope:** Add a concise README route explaining that official final results remain separate from inferred analytics and direct readers to the Method tab for confidence and interpretation boundaries.
- **Deliberate exclusions:** Do not copy the full Method content into the README. Do not create a separate concepts page.
- **Permitted claims:** Wording already established in E3 and E7.
- **Human-authority needs:** None for reproducing existing explicit boundaries; maintainer review remains required.
- **Validation:** Repeat T3 from the README and confirm the reader reaches the Method guidance without source inspection.
- **Stopping conditions:** Stop if the Method tab is removed or its wording changes materially.

## R3 — Clarify the deployable asset boundary

- **Reader task:** T5 — identify the complete file and data set required to host the dashboard.
- **Observed failure:** F3 — the README contents block appears narrower than the runtime application.
- **Evidence:** E1, E2, E4, E5.
- **Classification:** Reference correction.
- **Proposed scope:** Replace the apparent exhaustive list with an explicitly illustrative structure, or state that the entire repository folder must be deployed together. Name the enhancement loader and additional script/data dependencies only if maintainers intend the README to be a full inventory.
- **Deliberate exclusions:** No bundler, packaging design or deployment automation.
- **Permitted claims:** Current runtime dependencies at the pinned commit.
- **Human-authority needs:** Whether the preferred contract is “deploy the whole folder” or “maintain an exhaustive manifest”.
- **Validation:** Use the revised guidance to assemble a clean static deployment and load every tab.
- **Stopping conditions:** Stop if a generated release artefact or packaging process becomes the canonical deployment unit.

## R4 — Resolve the app manifest's intended scope

- **Reader task:** T5 — identify deployment dependencies.
- **Observed failure:** F4 — E6 omits the three Report Cards data files fetched by E5.
- **Evidence:** E5 and E6.
- **Classification:** Reference correctness defect or scope clarification.
- **Proposed scope:** Decide whether `data/app_manifest.json` is authoritative for all runtime data files. If yes, include the missing files and validate it mechanically. If no, rename or document its narrower scope.
- **Deliberate exclusions:** Do not infer the manifest contract or alter generation tooling without authority.
- **Permitted claims:** The observable mismatch at the pinned commit.
- **Human-authority needs:** Canonical manifest purpose and ownership.
- **Validation:** Compare the manifest with every runtime `fetch()` dependency and load all tabs from a clean deployment.
- **Stopping conditions:** Stop until the manifest's intended contract is confirmed.

## R5 — Establish refresh provenance before writing maintainer instructions

- **Reader task:** T6 — refresh or regenerate dashboard data.
- **Observed failure:** F5 — the repository does not establish the authoritative input, generation procedure, validation or ownership needed for a safe refresh.
- **Evidence:** E1 and E6.
- **Classification:** Human authority required; potential how-to, reference and explanation work after evidence is supplied.
- **Proposed scope:** First obtain or designate the canonical generation source, inputs, commands, validation artefacts and publication boundary. Only then create a bounded maintainer procedure.
- **Deliberate exclusions:** No reconstructed pipeline from output files; no inferred scoring formula; no plausible project history.
- **Permitted claims:** The current source label, timestamp and output behaviour only.
- **Human-authority needs:** All generation intent, tooling authority, score ownership and release policy.
- **Validation:** Run the authorised refresh in a clean context and compare generated dependencies and interpretation boundaries.
- **Stopping conditions:** Do not draft the guide until authoritative source material exists.

## Retain decisions

### K1 — Retain the local-run instructions

T1 found the README command, URL and `file://` warning clear and consistent with E2 and E6. No tutorial rewrite is justified.

### K2 — Retain in-context interpretation guidance

T4 found the Method and Report Cards explanations close to the metrics they qualify. Improve routing rather than replacing this content.

## No-change decisions

### N1 — Do not create a four-folder Diátaxis structure

The observed failures concern corrections, navigation, reference scope and missing authority. They do not justify creating all four document types.

### N2 — Do not create a new RaceIQ concepts page

The existing Method tab already owns the main interpretation explanation. T3 requires a route to that content, not a duplicate page.

### N3 — Do not create a separate deployment guide yet

A corrected “deploy the complete folder” contract may satisfy T5. A new how-to is only justified if real deployment choices and failure modes exceed the README correction.

### N4 — Do not document the score formula from inference

The assessed repository renders precomputed scores and qualitative inputs but does not establish the exact formula or rationale. That uncertainty must remain visible.
