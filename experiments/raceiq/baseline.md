# RaceIQ documentation and evidence baseline

## Assessment snapshot

- Repository: [`8ft0-ai/RaceIQ`](https://github.com/8ft0-ai/RaceIQ)
- Commit: [`7addbd39774f2ab5a59be7bd42c9e6d9cdcf65ab`](https://github.com/8ft0-ai/RaceIQ/tree/7addbd39774f2ab5a59be7bd42c9e6d9cdcf65ab)
- Default branch at assessment: `main`
- Repository type: public static dashboard
- Assessment mode: source and documentation inspection; no target mutation

## Evidence register

| ID | Source | Claim role |
| --- | --- | --- |
| E1 | [`README.md`](https://github.com/8ft0-ai/RaceIQ/blob/7addbd39774f2ab5a59be7bd42c9e6d9cdcf65ab/README.md) | Primary repository entry point and local-run guidance. |
| E2 | [`index.html`](https://github.com/8ft0-ai/RaceIQ/blob/7addbd39774f2ab5a59be7bd42c9e6d9cdcf65ab/index.html) | Visible application shell, tab names and directly loaded scripts. |
| E3 | [`app.js`](https://github.com/8ft0-ai/RaceIQ/blob/7addbd39774f2ab5a59be7bd42c9e6d9cdcf65ab/app.js) | Core runtime data dependencies, rendered feature behaviour and interpretation wording. |
| E4 | [`dashboard-enhancements.js`](https://github.com/8ft0-ai/RaceIQ/blob/7addbd39774f2ab5a59be7bd42c9e6d9cdcf65ab/dashboard-enhancements.js) | Dynamically loaded enhancement scripts and feature grouping. |
| E5 | [`report-cards.js`](https://github.com/8ft0-ai/RaceIQ/blob/7addbd39774f2ab5a59be7bd42c9e6d9cdcf65ab/report-cards.js) | Report Cards capability and its additional data dependencies. |
| E6 | [`data/app_manifest.json`](https://github.com/8ft0-ai/RaceIQ/blob/7addbd39774f2ab5a59be7bd42c9e6d9cdcf65ab/data/app_manifest.json) | App name, version, core data-file list, command, URL, source label and coverage note. |
| E7 | [`data/race_overview.json`](https://github.com/8ft0-ai/RaceIQ/blob/7addbd39774f2ab5a59be7bd42c9e6d9cdcf65ab/data/race_overview.json) | Coverage, summary counts, generated timestamp, known incident and interpretation notes. |
| E8 | [`7addbd39774f2ab5a59be7bd42c9e6d9cdcf65ab`](https://github.com/8ft0-ai/RaceIQ/commit/7addbd39774f2ab5a59be7bd42c9e6d9cdcf65ab) | Pinned repository state used for the experiment. |

## Documentation map

### Root entry point

**Observation:** E1 provides:

- a one-command local serving path;
- the expected local URL;
- a warning about `file://` fetch restrictions;
- a short contents list;
- a current-scope feature list;
- interpretation notes;
- generic static-hosting options.

### In-application guidance

**Observation:** E2 exposes tabs for Overview, Race replay, Team profiles, Report cards, Pit / delay map, Head-to-head, Anomalies and Method.

**Observation:** E3 renders task-specific explanations, including:

- the unobserved opening segment;
- replay confidence;
- probabilistic delay classification;
- anomaly review boundaries;
- Method-tab interpretation guidance;
- the distinction between official results and inferred analytics.

**Observation:** E5 adds Report Cards guidance, confidence reasons and interpretation caveats.

### Machine-readable reference

**Observation:** E6 records the recommended command, local URL, source label, coverage note and fourteen core data files.

**Observation:** E5 loads three additional Report Cards data files that are not listed in E6:

- `data/grid_to_finish.json`;
- `data/grid_to_finish_validation.json`;
- `data/team_report_cards.json`.

## Reader groups

### G1 — Dashboard viewer

**Evidence:** E1 describes a static race dashboard and E2 exposes viewer-facing tabs.

Likely tasks include opening the dashboard, finding a race story, comparing teams and understanding visible caveats.

### G2 — Analytical reviewer

**Evidence:** E3 and E5 repeatedly distinguish official results from inferred delay, battle, score, anomaly and confidence signals.

Likely tasks include deciding whether a claim is official, inferred, coverage-limited or unresolved.

### G3 — Repository maintainer or host

**Evidence:** E1 provides local and hosting instructions; E2–E5 show a multi-file static application with runtime data dependencies.

Likely tasks include serving the complete application, understanding its file dependencies and determining how generated data should be refreshed.

These groups are role descriptions inferred from observable interfaces. They do not assert RaceIQ's organisational structure.

## Authority map

| Question | Strongest available source | Status |
| --- | --- | --- |
| How is the app served locally? | E1 and E6 | Consistent and sufficiently explicit. |
| Which tabs are visible? | E2 | Canonical behaviour evidence for the application shell. |
| Which scripts are loaded? | E2 and E4 | Canonical behaviour evidence at the pinned commit. |
| Which data files are fetched? | E3 and E5 | Canonical behaviour evidence at the pinned commit. |
| Which results are official versus inferred? | E3, E5 and E7 | Explicit interpretation boundary, though split across in-app surfaces. |
| How were the analytics marts generated? | E6 source label only | Unresolved; no generation workflow or canonical external source is identified. |
| What exact formula produced RaceIQ scores? | E5 renders precomputed values; E3 gives a qualitative description | Unresolved; no formula or weighting authority is established. |
| Which file should be treated as the complete manifest? | E6 conflicts with runtime dependencies in E5 | Unresolved scope or correctness defect. |

## Observed contradictions and drift

### B1 — README feature scope omits a current tab

**Observation:** E1's current-scope list does not mention Report Cards or Grid-to-Finish movement.

**Observation:** E2 exposes a Report cards tab and its hero copy mentions grid-to-finish movement. E5 implements the feature.

**Finding:** The root feature summary is stale or incomplete.

### B2 — README contents list is narrower than the runtime application

**Observation:** E1 lists only `index.html`, `app.js`, `styles.css` and `data/*.json`.

**Observation:** E2 directly loads `dashboard-enhancements.js`; E4 dynamically loads multiple additional scripts.

**Finding:** A maintainer cannot treat the README contents block as a complete dependency inventory.

### B3 — App manifest omits Report Cards data dependencies

**Observation:** E6 lists fourteen data files.

**Observation:** E5 fetches three additional Report Cards data files that are absent from E6.

**Finding:** Either the manifest is incomplete or its intended scope is not documented.

## Useful material to retain

- E1's local serving command and `file://` warning are direct and consistent with E6 and the error path in E2.
- E1's opening-capture caveat is consistent with E3 and E7.
- E3 and E5 provide strong in-context interpretation boundaries close to the inferred metrics they qualify.
- The Method tab is a useful existing explanation surface; the evidence does not justify replacing it with a new standalone concepts page.

## Unresolved uncertainty

- Whether the README contents block was intended to be exhaustive.
- Whether E6 is intended as a complete runtime manifest or only a core-data manifest.
- The authoritative generation and refresh process for the data pack.
- The exact scoring formula and ownership of its rationale.
- Whether external contributors are an intended reader group.

These questions require maintainer or source authority. They are not completed with inferred history.
