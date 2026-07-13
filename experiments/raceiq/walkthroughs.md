# Representative task-path walkthroughs

All walkthroughs use RaceIQ at [`7addbd39774f2ab5a59be7bd42c9e6d9cdcf65ab`](https://github.com/8ft0-ai/RaceIQ/tree/7addbd39774f2ab5a59be7bd42c9e6d9cdcf65ab). Evidence identifiers refer to [`baseline.md`](baseline.md#evidence-register).

Runtime execution was not performed. Results distinguish source-verified documentation paths from unexecuted browser behaviour.

## T1 — Run the dashboard locally

- **Reader:** G1 dashboard viewer.
- **Starting context:** Repository root, Python available, no RaceIQ-specific knowledge.
- **Completion condition:** The reader knows the command and URL required to serve the app without using `file://`.
- **Expected entry point:** E1 README.
- **Actual path:** E1 `Run locally` → `python -m http.server 8000` → `http://localhost:8000` → `file://` warning.
- **Evidence:** E1; E6 repeats the command and URL; E2's error template repeats the same recovery path.
- **Next permitted action:** Run the command and open the URL.
- **Protected decisions:** Whether Python is the preferred production host; deployment policy.
- **Result:** **Complete for documented guidance; runtime not tested.**
- **Observed friction:** None material in the documented path.
- **Confidence:** High for instruction consistency; no claim that the app was executed.
- **Classification:** Retain.

## T2 — Understand the dashboard's current capabilities before running it

- **Reader:** G1 dashboard viewer.
- **Starting context:** Repository landing page only.
- **Completion condition:** The reader can identify the main dashboard sections currently available.
- **Expected entry point:** E1 current-scope list.
- **Actual path:** E1 lists overview, standings, replay, traces, team pace, delay, battles, anomalies and method. E2 additionally exposes Report cards; E5 implements that capability.
- **Evidence:** E1, E2, E5.
- **Next permitted action:** Inspect application source or run the app to discover the omitted tab.
- **Protected decisions:** Product priority and intended feature naming.
- **Result:** **Partial.**
- **Observed friction:** The root feature summary is stale or incomplete, so a reader cannot obtain the current scope from the expected entry point.
- **Confidence:** High; the omission is directly observable at the pinned commit.
- **Finding:** F1 — root feature-scope correction required.
- **Classification:** Correction, not a new page.

## T3 — Decide whether pit and delay values are official records

- **Reader:** G2 analytical reviewer.
- **Starting context:** README and a visible delay result.
- **Completion condition:** The reader can state whether the value is official, inferred or unresolved.
- **Expected entry point:** E1 interpretation notes or a clear route to methodology.
- **Actual path:** E1 says delay analytics use validated captured-segment data, but does not state that classification is probabilistic or not an official pit record. E3 states both boundaries in the Pit / delay and Method renderers.
- **Evidence:** E1 and E3.
- **Next permitted action:** Open the Method or Pit / delay tab and retain the inference caveat when using a value.
- **Protected decisions:** Whether a particular event is a true pit stop; official race adjudication.
- **Result:** **Partial from the README; complete in source-verified in-application guidance.**
- **Observed friction:** The useful explanation exists, but the expected repository entry point does not route the analytical reader to it.
- **Confidence:** High for source wording; browser discoverability not executed.
- **Finding:** F2 — navigation and concise interpretation-boundary correction.
- **Classification:** Navigation plus small correction; retain the Method explanation.

## T4 — Distinguish true Grid-to-Finish movement from First Observed movement

- **Reader:** G2 analytical reviewer.
- **Starting context:** A Report Card movement value.
- **Completion condition:** The reader can explain which value uses the heat-sheet start and which begins at the first captured snapshot.
- **Expected entry point:** In-context Report Cards or Method guidance.
- **Actual path:** E5 labels both movement measures and presents an interpretation note. E3's Method renderer defines Grid-to-Finish and First Observed movement and states that the first approximately 20 minutes were not captured. E7 records the coverage boundary.
- **Evidence:** E3, E5, E7.
- **Next permitted action:** Use Grid-to-Finish for start-to-result movement and First Observed only for the captured segment.
- **Protected decisions:** Whether either derived movement should influence official rankings.
- **Result:** **Complete in source-verified in-application guidance.**
- **Observed friction:** The explanation is distributed across two tabs, but each relevant surface keeps the caveat close to the metric.
- **Confidence:** High for source coverage; runtime interaction not tested.
- **Classification:** Retain. A separate explanation page is not justified by this task.

## T5 — Identify the complete file and data set required to host the dashboard

- **Reader:** G3 repository maintainer or host.
- **Starting context:** README contents and hosting sections.
- **Completion condition:** The reader can determine which repository assets must be deployed together.
- **Expected entry point:** E1 contents list and hosting section, supported by E6.
- **Actual path:** E1's contents block lists only three named root files plus `data/*.json`. E2 loads `dashboard-enhancements.js`; E4 loads multiple additional scripts; E5 fetches three data files absent from E6.
- **Evidence:** E1, E2, E4, E5, E6.
- **Next permitted action:** Deploy the entire repository folder rather than constructing a package from the documented list.
- **Protected decisions:** Whether the application should later be bundled or generated into a smaller release artefact.
- **Result:** **Partial.**
- **Observed friction:** The apparent inventory is not complete, and the machine-readable manifest does not cover all runtime data dependencies.
- **Confidence:** High for dependency mismatch at the pinned commit.
- **Findings:** F3 — README dependency-scope ambiguity; F4 — app manifest scope or correctness defect.
- **Classification:** Reference correction with a human decision on manifest scope.

## T6 — Determine how to refresh or regenerate the dashboard data

- **Reader:** G3 repository maintainer.
- **Starting context:** A need to update RaceIQ for a new or corrected race pack.
- **Completion condition:** The reader can identify the authoritative input, generation procedure, validation steps and output files.
- **Expected entry point:** E1 or an identified maintainer guide.
- **Actual path:** E1 says the dashboard is generated from an analytics-ready LiveRC race pack. E6 records a source label and generation timestamp. No generation procedure, input location, validation command or ownership record is established by the assessed evidence.
- **Evidence:** E1 and E6; absence of an authoritative procedure remains an assessment observation, not a claim about project intent.
- **Next permitted action:** Request maintainer authority and source material before documenting or running a refresh.
- **Protected decisions:** Canonical input, generation tooling, validation policy, score formula and publication process.
- **Result:** **Blocked.**
- **Observed friction:** The repository exposes generated outputs without enough authority to reconstruct the refresh workflow safely.
- **Confidence:** Medium. The assessed evidence does not establish a procedure, but an external or private source may exist.
- **Finding:** F5 — unresolved maintenance authority gap.
- **Classification:** Human authority required before any how-to, reference or explanation is drafted.

## Walkthrough summary

| Task | Result | Primary response |
| --- | --- | --- |
| T1 Run locally | Complete guidance; runtime not tested | Retain |
| T2 Understand capabilities | Partial | Correction |
| T3 Interpret delay authority | Partial | Navigation + correction |
| T4 Interpret movement measures | Complete source guidance | Retain |
| T5 Identify deployment dependencies | Partial | Reference correction |
| T6 Refresh generated data | Blocked | Human authority required |
