# Project retrospective — `8ft0-ai/diataxis-for-ai-repos`

## Evidence boundary

This retrospective reconstructs the project from the repository and its durable GitHub record. I used the attached retrospective brief only to establish the questions to answer, not as evidence of what happened. I have likewise not used the separately supplied IssueOps guide, early concept text or vision text to establish project history; where the same ideas appear below, the evidence comes from the current repository, issues, experiment records, releases and reviews.

I use **Observation** for something directly recorded in repository evidence, **Authority** for an explicit project or maintainer decision, **Inference** for my interpretation of that evidence, and **Uncertainty** where the record cannot establish a stronger conclusion.

## Overall finding

The answer to the central question is **both, but increasingly in different parts of the project**.

The project has genuinely become better at helping an agent and maintainer make evidence-led documentation decisions. The strongest parts of the original proposition survived repeated testing: start with reader tasks rather than missing pages; distinguish repository behaviour from intent; retain useful material; allow no-change outcomes; stop when authority or execution evidence is unavailable; and choose the smallest response that resolves an observed problem.

At the same time, a substantial share of later project effort has gone into governing the conditions under which AI agents evaluate that method: safe starting commits, mutation classes, fresh contexts, blinded evidence allowlists, publication preflights, review terminality, evidence budgets, exact result-state vocabulary and durable orchestration records. Some of those controls arose from real failures and improved experimental correctness. But they are much more strongly evidenced as **controls for running rigorous AI-assisted experiments** than as things an ordinary maintainer needs in order to decide whether a README should be corrected. The current toolkit says Level 3 should not be imposed on routine work, but parts of this experimental control surface have nevertheless reached the Level 2 assessment templates.

My overall judgement is therefore not that the project has lost its way. The core method has held up reasonably well. The risk is that further internal development now has a higher probability of making the methodology better at evaluating itself than making it materially easier for another maintainer to make a documentation decision.

That is a good reason to pause.

# The original problem

The earliest planning record framed the problem unusually well. Repository-aware agents can generate plausible prose quickly, but plausible prose does not establish either that a reader problem exists or that the prose is correct. The first experiment was explicitly intended to prove decision quality rather than output volume: identify representative tasks, observe failures, preserve uncertainty, produce bounded remediation, and permit retained-content and no-change outcomes. It stopped before drafting.

That is important because it means the project's fundamental problem was never “repositories need more documentation”. It was closer to:

> How can a maintainer use a repository-aware agent to decide what documentation work, if any, is justified without letting the agent turn plausibility into authority?

**Observation:** the current README still expresses essentially that proposition. It remains an assessment-first, model-agnostic toolkit, explicitly does not provide automatic repository scanning, autonomous remediation, a CLI or stable drafting contracts, and states that its evidence base is narrow.

**Inference:** the intellectual core has therefore remained surprisingly stable. The project has changed its operating machinery much more than it has changed its theory of documentation.

There was, however, an early fork in emphasis. Five minutes after the initial planning issue was created on 13 July, issue #2 established a fairly substantial repository-specific IssueOps control surface: execution contracts, readiness, implementation plans, safe-operation checks, evidence-pack pull requests and human merge authority. This preceded any evidence from the documentation method itself. The issue explicitly called that setup a prerequisite for safe future delivery, while also warning against excessive ceremony.

That was not necessarily a mistake. Later wrong-object GitHub operations demonstrated that agent mutation risk was real. But it means part of the project's procedural complexity was **foundational governance chosen before the documentation hypothesis was tested**, rather than complexity discovered through documentation adoption.

That distinction matters throughout the retrospective.

# The journey

## Phase 1 — prove that task evidence changes the documentation decision

The first meaningful question was whether the proposed assessment method could distinguish an actual reader failure from a general critique of the documentation.

RaceIQ provided a useful first answer. Six tasks did not produce six documentation requests. Two existing paths were retained; two warranted local correction or navigation; one exposed a reference-scope decision; and one stopped because authoritative intent was missing. The experiment explicitly rejected the need for a tutorial, a new explanation page or all four Diátaxis forms.

The same experiment also exposed the first proportionality problem. Its seven-artefact evidence pack was judged useful for a method proof but disproportionate for routine documentation work. Task prioritisation remained partly agent-dependent, source-only walkthroughs were weaker than execution, and Observation/Authority/Inference/Uncertainty added useful discipline at a recording cost. The proposed response was not more tooling. It was a lighter Level 1 and Level 2 path, with the full evidence pack reserved for governed Level 3 work.

**What survived:** task-first assessment, the evidence gate, protected human authority, retain/no-change outcomes and bounded remediation.

**What changed:** record structure needed to become lighter, task approval needed an explicit human checkpoint, and execution evidence needed to be represented separately from source inspection.

**Proportionality:** good. This was exactly the kind of adaptation the evidence justified.

## Phase 2 — make the method executable, then discover provenance problems

The second experiment against `files-to-prompt` deliberately changed repository shape and introduced real CLI execution. The method was reduced from seven artefacts to three records. This was already a useful sign: the project did not preserve ceremony simply because it had been built once.

The executable tasks revealed things source inspection could not. Documentation for `--ignore-gitignore` overstated its behaviour; the documented Markdown language tag conflicted with observed output; and the contributor test path exposed a Click-version compatibility question that repository evidence could not resolve as policy. The result was two bounded corrections, one human-authority decision and several retained/no-change paths. No target documentation was drafted.

The experiment also produced a more subtle lesson. On resumption, the original package environment could no longer be reproduced cleanly. A source distribution, GitHub connector inspection and behavioural transcription offered different grades of evidence. The project responded by requiring durable command summaries, runtime/dependency versions and explicit retrieval modes rather than pretending those modes were equivalent.

That was a strong adaptation. The evidence problem was concrete and the response was bounded.

The mutation model changed for similarly concrete reasons. A wrong GitHub action had previously created an unintended issue and correctly triggered a full stop. But an approved editable install later created packaging metadata and caches in a disposable workspace, and treating those normal local effects as the same severity made executable walkthroughs unnecessarily fragile. Issue #13 therefore introduced Class A protected/unbounded mutations, Class B recoverable local deviations and Class C expected local side effects.

This is a useful example of complexity that was **earned by evidence**. It also illustrates why it should probably remain Level 3 machinery: it solves agent-execution and repository-operation safety, not documentation classification itself.

## Phase 3 — freeze a deliberately incomplete V1

After the two experiments, the project chose to package an assessment-only V1 rather than finish the broader idea by adding drafting contracts.

That was one of the stronger decisions in the project.

`v0.1.0`, released on 2 August 2026, explicitly said what it did not contain: documentation drafting, automatic remediation, CLI, hosted service, stable drafting contracts, broad portability claims or independent human validation. It described the evidence as two small-repository experiments.

The adopter-facing package retained the principles the experiments had supported: representative tasks, human task approval, evidence states, smallest-sufficient responses, retain/no-change outcomes and response-specific validation. Level 3 was explicitly described as deliberately heavier and not the normal path for routine documentation maintenance.

A practical bootstrap guide was then added because a maintainer needed a concrete way to start the assessment against an existing repository. Later, issue #42 identified an even more basic onboarding problem: a maintainer still had to reconstruct the starting prompt from the toolkit. The response was one root-level `BOOTSTRAP.md`, deliberately without changing the method, adding automation or beginning drafting.

That is a good example of adopter-facing work responding to a real usability seam rather than expanding the conceptual framework.

## Phase 4 — fresh-agent adoption exposed defects in the experiment boundary

The first fresh-context adoption pilot, against `gitstate-lab`, was encouraging but not friction-free. A fresh agent proposed tasks, stopped at the human gate, executed the approved work conservatively and produced one bounded correction/navigation candidate, retained material, no-change outcomes and owner decisions. One executable task stopped rather than substituting missing tools or credentials.

The close-out, however, recorded four additional orchestration interventions: progress/stop-expansion prompting, a second execution session because the first could not resume, another progress prompt and a procedural correction when the assessor requested review before publishing its own result. Level 2 itself was judged proportionate, but the Level 3 evaluation record was time-consuming.

The project correctly did **not** change the released method after every inconvenience. It explicitly judged the observed issues insufficient for a clarification release and asked whether the same problems would recur in a materially different pilot.

The second fresh-context pilot, against `arxiv-quant-radar`, supplied that evidence.

Two initial assessors failed to publish the required first-phase record despite repeated procedural prompting. A third succeeded after a fixed evidence budget and explicit publication instruction.

More importantly, the approved task design itself contained invalid conditions:

- T1 exposed information that a later T2 clean-context task forbade;
- T3's intended blind was contaminated by metadata exposing later remediation clues;
- T4 lacked an exact checkout and executable prerequisites;
- T2 was therefore correctly blocked rather than pretending context could be reset.

The method's stopping behaviour worked. The experiment design did not.

The accepted response was six clarifications: whole-pack consistency, executable prerequisite preflight, blinded evidence isolation, evidence budgeting, publication stopping, and clearer separation between direct observation and judgement against authority. The owner accepted `Adapt` and authorised a small clarification release, while explicitly withholding drafting authority.

Again, that adaptation was evidence-led. But this phase is where the project's centre of gravity began to change. The findings were now primarily about **how to run a controlled AI evaluation**, not about how to identify a reader's documentation problem.

## Phase 5 — controls started generating further controls

`v0.1.1` incorporated the six clarifications but was published with an explicit evidence boundary: the controls had not yet passed the planned rerun and did not establish independent-maintainer usability, broad portability, drafting readiness or model consistency.

The bounded rerun did show real improvement. T2 and T4 were deferred *before* invalid execution because their prerequisites were unavailable. Fresh/blinded contexts were treated as properties that could fail. The independent reviewer found durable evidence for whole-pack preflight, isolation enforcement, evidence budgeting, result-state handling, publication completion and observation-versus-judgement separation.

But the rerun also produced four more method-control adaptations:

1. repeated independent reviews needed terminality/idempotency;
2. “freshness” needed to be defined as an information property rather than a particular UI mechanism;
3. sessions that must publish needed write-path capability preflight before doing substantive research;
4. `Not tested` needed to be reserved for the primary task result rather than reused as an evidence state.

These corrections are individually sensible. Collectively, they are a warning sign.

The project was now spending significant intellectual effort defining how separate agents prove freshness, how review gates terminate, how publication capability is verified and how subordinate execution-state vocabulary is represented. These are legitimate concerns for controlled evaluation. Their direct value to a normal maintainer asking “can a contributor follow our setup guide?” is much less obvious.

The project's self-correction remained strong. Issue #34 attempted to transition into a drafting experiment, but that move was explicitly recognised as an incorrect transition after the accepted `Adapt` result. It was superseded and closed `not_planned`; the narrower method adaptations were completed first.

That was restraint, not failure.

## Phase 6 — test operability without weakening the evidence claim

The project then correctly identified a larger gap: none of the work established that an unfamiliar human maintainer could operate the method.

Issue #37 was designed to test exactly that. It was also stopped before execution because the project is operated by one person and no genuinely independent human maintainer participant was available. The owner explicitly refused to reclassify the same person or substitute a fresh agent for independent-human evidence. The primary result was `Blocked`, and independent-maintainer usability remained untested.

That is one of the strongest pieces of evidence that the project's epistemic discipline is real rather than decorative.

A narrower solo-maintainer/fresh-agent pilot followed. Its first version also failed for a valid reason: answer-bearing completion conditions had been supplied to contexts whose claimed value depended on discovering the answer without prior exposure. The independent review correctly concluded that the `clean-context completed: yes` claims were invalid, and the owner chose `Repeat`.

The corrected repeat used answer-neutral task contracts and separate fresh contexts. One T1 execution context still correctly stopped when it detected prior target exposure; another eligible context completed T1, while T2 completed without intervention. A separate agent concluded that the corrected evidence **supports the bounded claim**. The owner accepted only the narrow conclusion that the workflow was operable in this one solo-maintainer/fresh-agent case, for two source-inspection tasks and with the recorded intervention level. It explicitly did not establish independent-human validation, independent-maintainer usability, broad portability, model portability, runtime correctness, drafting quality or Horizon 2 readiness.

That is careful experimental practice.

It also marks a natural end point for internal testing.

# What the experiments actually established

The experiments become easier to interpret if their questions are separated from their mechanics.

### RaceIQ

The real hypothesis was that task evidence could produce a selective documentation decision rather than a generic critique. It did. The evidence was capable of answering that question at source-inspection level, but not runtime usability or independent-reader validity. The main adaptation — lighter records, explicit task approval and execution-evidence distinctions — was proportionate.

### `files-to-prompt`

The question was whether the lighter method could survive executable tasks on a small CLI. It did, with provenance complications. It genuinely established that execution could materially strengthen or change documentation findings, and that environment/dependency provenance matters. It did not establish target-maintainer acceptance or independent-human repeatability.

### `gitstate-lab` adoption pilot

This asked whether a fresh repository-aware agent could operate the released assessment method without private development history. The narrow answer was yes, but with several orchestration interventions and one blocked executable path. It did not test unfamiliar-human usability.

### `arxiv-quant-radar` adoption pilot

This was capable of exposing more complex task isolation and execution problems, and did. Its most useful finding was not about the target documentation. It was that the method could approve task packs whose execution conditions were mutually incompatible or insufficiently isolated. The conservative stop behaviour was a success; the original task design was not.

### `v0.1.1` control rerun

This tested the fixes rather than target-documentation quality. It established that the new preflight and isolation controls could prevent invalid execution and preserve honest `Not tested` results. That is useful evidence about the control system. It does not increase the evidence for drafting quality or real-user documentation outcomes.

### Independent-maintainer pilot

It never ran. That is the correct interpretation. It established that the current project cannot internally provide the participant needed to test independent-maintainer usability.

### Solo-maintainer/fresh-agent pilot and corrected repeat

The first attempt was contaminated by the task contract itself. The repeat corrected that design and established a bounded operability claim for two source-only tasks. It is meaningful, but narrow.

There is a pattern here. Failed, blocked and contaminated experiments were often among the most informative events in the project because the record did not quietly convert them into successes.

# The operating model

## Did the controls improve correctness?

Yes. There are concrete examples.

The human task gate prevented agents from unilaterally deciding which reader needs mattered. RaceIQ had already shown that task selection remained judgement-heavy, which justified an explicit checkpoint.

Executable preflight prevented missing tooling, credentials and exact checkouts from becoming weak substituted evidence. In the first adoption pilot, T4 stopped rather than installing or improvising missing prerequisites.

Whole-pack consistency and fresh-context controls prevented an impossible same-agent T2 sequence from being treated as valid. The later rerun deferred tasks before execution when their conditions were unsatisfied.

Blinding controls prevented later remediation evidence from masquerading as an independent discovery. The project explicitly rejected “forgetting” or quarantining exposed evidence as a way to restore a blind.

The mutation circuit breaker caught real wrong-object GitHub operations, while the later Class A/B/C distinction avoided treating ordinary local caches as protected-state incidents.

Answer-neutral task contracts corrected a genuine evaluation error in #38 rather than accepting favourable results produced by answer-bearing prompts.

These are not cosmetic controls.

## What did the controls cost?

They cost a lot of orchestration.

The first fresh-context pilot required four extra procedural interventions beyond its planned human gates.

The second required two abandoned assessment attempts, an imposed evidence budget, publication instructions and further progress interventions before reaching a usable close-out. Its final review explicitly said that this amount of coordination prevented an unqualified usability or proportionality claim.

The control rerun itself generated duplicate-review behaviour significant enough to require a formal review-terminal/idempotency rule.

The current evidence guide now covers primary task states, subordinate yes/no evidence states, multiple retrieval modes, blinded evidence isolation, freshness definitions, executable prerequisite preflights, publication/write-path preflights, durable command evidence, version capture, mutation-effect boundaries, Class A/B/C recovery semantics, document-type validation and independent-review terminality. All of these ideas have plausible reasons. Together, they form a substantial operating model.

**Inference:** the project has crossed a line where a maintainer can reasonably wonder whether they are assessing documentation or running an experiment in agent epistemology.

That distinction should now be made sharper rather than adding another control.

# Human involvement

Human involvement falls into two very different categories.

The first is legitimate and essential. A maintainer should decide whether the proposed reader tasks matter, which authority wins when sources conflict, what policy or compatibility promise is intended, whether remediation is worth doing, and whether a change is accepted. The original planning issue assigned exactly these classes of decision to humans, and the current toolkit continues to protect them.

The second category is humans acting as workflow glue.

That includes telling an agent to stop expanding its evidence set, restarting work in another session because the first could not resume, prompting an agent to publish a completed result, constructing or locating a sufficiently fresh execution context, recognising that a supplied prompt has contaminated an evaluation, triggering a separate reviewer, checking whether that reviewer is already terminal, and making repeated procedural dispositions that contain no new documentation judgement.

Those interventions have been useful for method research. They should not be mistaken for enduring product value.

If another competent maintainer used this repository without its author present, I would expect the main questions to arise not around Diátaxis itself but around the operational vocabulary:

- Do I really need a “fresh context” for this ordinary task?
- Must I define a forbidden-prior-exposure set when I am not running a blind experiment?
- Why must I preflight the comment publication mechanism before reading my own repository?
- Is an assessment issue required or just recommended?
- Which of these Level 2 fields can safely be omitted?
- When does a simple command check become a governed executable experiment?
- Is “separate review” expected for normal usage or only Level 3?

The toolkit does answer many of these questions. The problem is that a newcomer first has to understand enough of the operating model to know which answers matter.

# Restraint: what the project correctly did not do

The project deserves explicit credit for several non-actions.

It did not turn Diátaxis into four required folders. The classification rubric starts with retain, no change, correction and navigation before reaching tutorial, how-to, reference or explanation.

It did not treat complete tasks as an excuse to rewrite material. The worked example records retained installation, ignore-control and stdin guidance alongside two local corrections and one human-authority decision. It explicitly rejected a new tutorial, a four-folder reorganisation and an unnecessary standalone explanation page.

It did not invent compatibility policy when two Click versions behaved differently. That was left as a maintainer decision.

It did not build a CLI, hosted service, schema framework or autonomous documentation agent despite repeated opportunities to do so. The current release remains assessment-only.

It did not force the independent-maintainer experiment to complete when no independent human participant existed.

It did not accept contaminated fresh-context evidence merely because the underlying task answers were useful.

It did not use the roadmap as implementation authority. The attempted drafting transition in #34 was explicitly superseded when the prior `Adapt` result still required method work.

These decisions are important because they show that “nothing new” has repeatedly been treated as a legitimate project result.

# The current artefact

The repository discovered today is much better than the experimental history might suggest.

The README is concise. It explains the proposition, identifies the assessment-only boundary, presents the adoption levels and states the narrow evidence base rather than forcing a newcomer through the history of the experiments.

`BOOTSTRAP.md` is a significant improvement. It gives a copy-ready, read-only starting instruction and stops at a human task-approval gate. That solves the concrete problem recorded in issue #42: previously the maintainer had to reconstruct the starting prompt from several toolkit documents.

The classification material is probably the strongest adopter-facing artefact. Its core rule is simple: require an observed basis, then consider retain → no change → correction → navigation before one of the four Diátaxis forms. It is difficult to misunderstand and directly expresses the project's original proposition.

The assessment material is less proportionate. A normal Level 2 task record now contains execution-context identity, ordering, an evidence allowlist, forbidden prior exposure, freshness boundaries, subordinate evidence states and prerequisite preflights. The assessment itself includes evidence budgets and publication capability preflight.

Many of those fields are conditional in spirit. In the template they are visually part of the normal contract.

There is also one minor discoverability seam: `BOOTSTRAP.md` now exists at the root, but the current README still primarily routes users through the toolkit reading sequence rather than explicitly presenting that new root prompt as the first thing to copy. I would not start another internal improvement cycle for this. The first external users can tell you whether it is an actual discovery problem rather than an aesthetic inconsistency.

The worked example remains honest but incomplete relative to the eventual project proposition. It ends with an evidence-backed remediation backlog. It did not apply the proposed documentation changes, repeat the reader tasks afterwards, or demonstrate drafting quality. The file explicitly says so.

That is not a defect in the current assessment-only release. It is an evidence boundary.

# What has actually been proven?

## Supported

There is reasonable repository evidence for the following claims:

- Representative reader tasks can produce more specific documentation decisions than general repository inspection.
- The method can produce retained-content and no-change outcomes rather than automatically generating pages.
- It can distinguish observable behaviour from undocumented intent and preserve authority gaps.
- It can identify small corrections and navigation changes as preferable to new documents.
- Executable tasks can expose documentation and dependency problems that source inspection alone misses.
- Conservative stopping rules can prevent missing prerequisites, contaminated contexts and absent authority from being converted into unsupported conclusions.
- The assessment workflow is operable in at least one bounded solo-maintainer/fresh-agent, source-inspection case after answer-neutral task contracts are used.

## Partially supported

These claims have evidence, but it remains narrow:

- **Repository portability.** The project has exercised a static dashboard, Python CLI, governance/protocol repository, report pipeline and a validation repository. That is more diversity than the initial two fixtures, but the assessments remain tightly controlled and heavily owner-operated.
- **Fresh-agent usability.** Fresh agents have operated the workflow, but some runs needed progress, publication or context-management intervention.
- **Level 2 proportionality.** `gitstate-lab` was judged proportionate at Level 2, while `arxiv-quant-radar` required material coordination and exposed task-design complexity.
- **Independent review.** Different agent contexts have reproduced material findings, but that is explicitly not independent-human validation.
- **The post-`v0.1.1` controls.** They have improved experimental correctness in the fixtures designed to exercise them, but evidence that ordinary adopters need the full set is weak.

## Not yet supported

The repository does not establish:

- independent-maintainer usability;
- independent-human validation;
- large-repository or monorepo proportionality;
- broad repository portability;
- model portability;
- documentation-drafting quality;
- effectiveness of all four drafting contracts;
- a before-and-after improvement in real reader outcomes caused by an applied documentation change;
- target-maintainer acceptance of the worked-example remediation backlog;
- that ordinary Level 2 adopters find the current control surface proportionate;
- that the method improves documentation outcomes over a simpler task-walkthrough approach without the heavier provenance/governance machinery.

The project itself preserves many of these limitations explicitly.

# Where we may have overdone it

The project has not generally over-engineered the **documentation theory**. It may have over-engineered the **experimental operating model**.

### Safe-operation governance

The IssueOps model is useful repository-development governance, and wrong-object GitHub incidents show why protected mutations need care. But readiness evidence, safe starting commits, operation checks, evidence-pack PRs and post-merge verification existed before the first documentation experiment.

**Classification:** genuinely necessary for this repository's own agent-assisted development at Level 3; not demonstrated as necessary for normal documentation assessment.

Moving it out of the mental model of a Level 1/2 adopter would reduce perceived ceremony without sacrificing the evidence gate itself.

### Mutation Classes A/B/C

The classes solved a real problem: a remote wrong-object mutation and local test artefacts should not have the same response.

**Classification:** justified Level 3 complexity. Probably unnecessary for a normal source-only assessment. If executable assessment tooling eventually becomes a product feature, this may matter again.

### Freshness, zero-history and blinded allowlists

These controls prevented real experimental contamination, especially in the arXiv pilot and #38. They are necessary when a task claims to measure an unfamiliar reader or blind reviewer.

**Classification:** genuinely necessary for validity of those experiments; conditional at Level 2; potentially overbearing when represented as routine fields for tasks that make no clean-context claim.

A normal maintainer verifying an API option does not need to prove epistemic isolation from previous conversations.

### Publication/write-path capability preflight

This arose because agents repeatedly completed analysis but failed to publish the durable GitHub record. The control fixes that failure.

**Classification:** justified for autonomous or semi-autonomous Level 3 sessions whose success contract requires a GitHub write. Its value for an ordinary maintainer who can simply copy the returned assessment into an issue is unproven.

This is a good candidate to remain experimental rather than defining normal assessment.

### Independent-review terminality/idempotency

The project acquired this because repeated reviewers could publish duplicate records after the gate had already been satisfied.

**Classification:** necessary for the project's experiment orchestration; very difficult to justify as a normal adopter concern today.

This is perhaps the clearest example of process created to manage process.

### Result and evidence-state precision

Keeping `Complete`, `Partial`, `Blocked` and `Not tested` separate from `command executed: yes/no` is conceptually sound. It prevented genuine ambiguity.

**Classification:** useful complexity, although the full matrix of subordinate states is probably unnecessary for many source-only tasks.

### Evidence budgets

The budget was introduced only after two assessors repeatedly failed to stop and publish. That is strong evidence of a real agent behaviour problem.

**Classification:** useful, but the exact accounting of files/live objects/time should remain proportional. “Stop when you have sufficient evidence” is probably the enduring principle; numerical budgets are an experimental enforcement mechanism.

### Repeated fresh reviews and controlled contexts

These produced useful research evidence. They also consumed a large proportion of the project's later activity.

**Classification:** appropriate when claiming experimental independence. Not user value in itself.

The key simplification is therefore not “delete the evidence rules”. It is to distinguish much more aggressively between:

> **the method a maintainer needs to make a documentation decision**

and

> **the controls this project needed to make defensible claims about whether an AI agent followed that method.**

They are not the same product.

# What went particularly well

The strongest decision was to make **task evidence, rather than document structure, the gate**. That repeatedly prevented speculative page creation.

The second was treating repository evidence as incomplete authority. The `files-to-prompt` Click finding is a clean example: behaviour could be observed, but intended compatibility policy could not be reconstructed from it.

Retain and no-change as first-class outcomes mattered more than they may appear. They prevented Diátaxis from becoming a content-generation matrix and gave the method a way to say that the repository is already good enough for a particular task.

Document-type-specific validation is also conceptually strong. A reference claim should be checked against an interface; a how-to against a real task; explanation against actual rationale evidence. The project has not yet proven drafting, but the validation distinction itself is well founded in the assessment model.

Keeping V1 assessment-only was a good scope decision. It allowed the project to learn that the harder problem was not generating prose but establishing what could safely be said.

The project also became better at admitting experimental invalidity. T2 was blocked rather than context-reset. #37 was stopped instead of faking independent-human evidence. #38 was repeated after the task prompt itself contaminated the result. Those behaviours give more confidence in the surviving conclusions than another successful-looking demo would have done.

Finally, the root bootstrap prompt is an appropriately simple response to a real adoption problem. Not every improvement became another protocol.

# If we started again today

Knowing what the experiments have taught us, I would build a smaller first version than the current repository, while retaining almost all of its intellectual core.

The first version would contain:

1. **One short README** explaining the proposition, limits and three adoption levels.
2. **One copy-ready bootstrap prompt** that performs a read-only assessment and stops for human task approval.
3. **One task-walkthrough protocol** containing reader, task, starting point, completion condition, actual path, evidence, result and friction.
4. **One evidence/classification guide** covering Observation/Authority/Inference/Uncertainty and the response order: retain → no change → correction → navigation → Diátaxis form → human authority.
5. **One compact close-out/remediation template** with traceability and validation.
6. **One worked assessment example** containing retained material, a correction, no change and an authority gap.

That is enough to test the essential proposition.

I would introduce executable prerequisite evidence only when an adopter chooses an executable task. I would introduce fresh-context and blind controls only when the claim actually depends on an unfamiliar or blinded reader. I would introduce publication preflight only if an agent is responsible for durable publication rather than returning a result to a human. I would introduce independent-review terminality only for a governed Level 3 workflow. Mutation recovery classes would remain repository/agent-operation guidance unless normal adopters demonstrated a need for them.

IssueOps itself could remain as this project's development operating model without being part of the method people are evaluating.

A CLI, schemas, autonomous scanning and hosted workflow would still not be present. The experiments have provided no evidence that their absence is blocking the core value.

The largest difference from the current repository would therefore not be missing capability. It would be **where complexity lives**.

The current repository has mostly the right ideas. I would place more of the later controls behind conditional Level 3 boundaries rather than making them visible in the main Level 2 record shape.

# Is this a sensible pause point?

Yes.

The strongest unresolved evidence questions can no longer be answered especially well by the project testing itself.

The repository already knows that its agents can run bounded assessments. It knows that task-first evidence produces useful retain/correction/navigation/authority outcomes. It has tested several repository shapes. It has repeatedly tested freshness, publication and independent-agent review controls. Another internal pilot can always discover another edge condition, but the marginal question is increasingly likely to be “did our experimental control behave correctly?” rather than “did this help a maintainer make a better documentation decision?”

The project explicitly identified independent-maintainer usability as the next important evidence gap. That experiment was blocked because there was no independent human participant. A fresh agent cannot close that gap.

The corrected solo-maintainer pilot is useful precisely because its conclusion was kept narrower. It should not be stretched into a reason to run more internal substitutes for the missing external evidence.

`v0.1.2` has now been published at the accepted assessment-method baseline. The superseded release-preparation issue #44 was closed after #45 completed publication without widening the method, drafting, automation, tooling or Horizon 2 scope. That housekeeping does not materially change the pause decision.

I would therefore treat the project as having reached a **method-learning plateau**.

The next valuable evidence should come from people who did not design the method, applying it to repositories this project did not select.

# What should happen during the pause?

The appropriate operating mode is deliberately quiet.

Accept feedback and real adoption reports. Observe where maintainers actually start, what they omit, which fields they misunderstand, how they choose tasks and whether the task-approval gate feels useful or bureaucratic.

Record genuine method defects when they occur, but do not create a new control merely because a theoretical ambiguity can be constructed.

Wait for a real evidence-backed remediation opportunity that cannot be solved by retain, correction or navigation before testing drafting. That would make Horizon 2 answer a user problem rather than a roadmap slot.

If people repeatedly work around the same manual step, that becomes evidence for tooling. Until then, the absence of a CLI is not a defect.

Development should restart when there is evidence such as:

- an independent maintainer cannot bootstrap the method unaided;
- multiple users encounter the same unnecessary Level 2 ceremony;
- users repeatedly misunderstand authority versus inference;
- a real task assessment produces an accepted remediation that genuinely requires a tutorial, how-to, reference or explanation;
- the method produces a misleading or unsupported recommendation in real use;
- a stable, repeated mechanical burden makes a small tool demonstrably worthwhile;
- materially different repositories expose a portability failure in the core method.

It should **not** restart because six months have passed, because a roadmap has an empty Horizon, because one of the four Diátaxis forms has not been exercised, because another model has become available, because a further control can be imagined, or because the repository could look more complete.

# Suggested feedback taxonomy

A simple issue label or one-line classification is enough:

| Category | Meaning |
|---|---|
| **Onboarding friction** | Could not discover or start the method unaided. |
| **Terminology confusion** | A method term or state was misunderstood. |
| **Disproportionate process** | The evidence burden exceeded the decision value. |
| **Task-selection difficulty** | Could not choose representative, answer-neutral tasks confidently. |
| **Evidence/authority ambiguity** | Could not determine what source could support a claim. |
| **Target-specific problem** | Friction belongs to the target repository rather than the method. |
| **Method defect** | The method permits or encourages a materially wrong decision. |
| **Agent/tool limitation** | A runtime, connector, publication or context limitation prevented execution. |
| **Retain/no-change success** | The method correctly prevented unnecessary documentation work. |
| **Evidence-backed remediation** | A real reader failure justifies bounded documentation change. |
| **Drafting demand** | A remediation genuinely requires one Diátaxis drafting form. |
| **Tooling demand** | Repeated mechanical effort may justify supporting automation. |

No additional workflow is needed to manage this taxonomy until the volume of feedback itself demonstrates that one is necessary.

# If we stopped here for six months

The project would not become valueless or unfinished in any damaging sense.

It would still contain a coherent assessment method, a copy-ready entry point, a good classification rubric, explicit evidence and authority rules, a task-walkthrough model, a worked executable example and unusually candid experiment records. The public artefact would continue to teach the most valuable lesson the project has produced: **documentation work should be justified by a reader need and evidence, not by an AI agent's ability to produce prose.**

1. **What is genuinely useful today?**  
   The assessment-only method: task-first discovery, the evidence gate, Observation/Authority/Inference/Uncertainty, human task approval, smallest-sufficient responses, retain/no-change outcomes, bounded remediation and response-specific validation.

2. **What is still experimental?**  
   Fresh-context methodology, blinded evaluations, publication capability preflights, independent-agent review machinery, the full Level 3 operating model and the extent to which those controls belong in ordinary Level 2 adoption.

3. **What remains unresolved?**  
   Independent-maintainer usability, independent-human validation, large-repository proportionality, broad portability, drafting quality, all-four-form validation, model portability and real before/after reader outcomes.

4. **What should we resist building?**  
   A CLI, autonomous agent framework, hosted service, automatic repository scanner, four-contract drafting suite, elaborate feedback system or further governance merely because those are plausible next layers.

5. **What evidence should we wait for?**  
   Real maintainers attempting to bootstrap the method; real confusion and process burden; real reader-task failures; accepted remediation decisions; and a case where a new document genuinely beats correction, navigation or no change.

6. **What would justify restarting active development?**  
   Repeated external friction that can be traced to the method, or one well-grounded drafting opportunity that tests a capability the current assessment-only toolkit deliberately does not claim.

The project is, at this point, **a useful method surrounded by a research-grade operating system**. The useful method has earned its place: the experiments repeatedly show that task evidence, authority discipline and explicit no-change outcomes improve the quality of documentation decisions. The operating system also earned parts of its complexity by catching real contamination, mutation and execution failures, but its value is much more strongly demonstrated for governing these experiments than for ordinary adopters. The next important test is therefore not whether this repository can devise and survive another internal pilot. It is whether another maintainer, without its author acting as orchestration glue, finds the small core useful enough to keep using. Until that evidence exists, the correct next action is to wait.