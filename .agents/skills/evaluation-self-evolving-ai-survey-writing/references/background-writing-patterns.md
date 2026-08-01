# Background, Scope, and Review Methodology Patterns for Technical Surveys

## Purpose

Use this reference to draft or revise the Background, Scope, and Review Methodology of the **Evaluation in Self-Evolving AI Systems** survey. It distills recurring moves from well-structured, formally published technical surveys and established review-reporting guidance, then adapts them to this project's evaluation-centric architecture.

The goal is not to imitate wording. It is to reproduce the work a strong background section performs: turn a broad topic into an operationally bounded object of study, define the primitives needed by the taxonomy, and make the literature synthesis auditable.

## What This Section Must Do

The Introduction establishes **why the survey is needed**. The Background and Scope establish **what the survey means and includes**. The Review Methodology establishes **how its literature claims were produced**. Do not merge these jobs into a second motivation section.

A successful section leaves the reader able to answer five questions before encountering the taxonomy:

1. What observable conditions make a system self-evolving rather than merely adaptive at inference time?
2. Which neighboring research traditions are included, and under what relation to the focal topic?
3. What entities and relations constitute an evaluation system?
4. How is an evaluation instance assigned a Control, Proof, or Meta role?
5. How were studies retrieved, selected, coded, and synthesized?

## Evidence Base

The following sources illustrate complementary parts of this design:

| Source | Useful structural move |
|---|---|
| [Neural Architecture Search: A Survey](https://jmlr.org/papers/volume20/18-598/18-598.pdf), JMLR 2019 | Defines three interacting components—search space, search strategy, and performance estimation—and relates them through a feedback loop before reviewing methods. The background supplies the causal skeleton used by the rest of the survey. |
| [A Continual Learning Survey: Defying Forgetting in Classification Tasks](https://arxiv.org/pdf/1909.08383), IEEE TPAMI 2022 | Gives an operational criterion for continual learning, formalizes the sequential setting, distinguishes neighboring paradigms, and states explicit scope limitations. The boundaries are justified rather than listed. |
| [Automatically Correcting Large Language Models](https://aclanthology.org/2024.tacl-1.27.pdf), TACL 2024 | Introduces the model, critic, and refiner as distinct entities; formalizes their relations; then defines classification axes and inclusion criteria. The conceptual framework makes later coding reproducible. |
| [A Survey on Evaluation of Large Language Models](https://doi.org/10.1145/3641289), ACM TIST 2024 | Introduces only the language-model concepts needed to support its what/where/how evaluation organization. It shows the value—and the limit—of concise historical context. |
| [PRISMA 2020 Statement](https://www.bmj.com/content/372/bmj.n71), BMJ 2021 | Specifies the reporting needed to reconstruct eligibility, information sources, selection, data collection, synthesis, and the flow of records. It is reporting guidance, not proof that a review was well conducted. |
| [PRISMA-S](https://link.springer.com/article/10.1186/s13643-020-01542-z), Systematic Reviews 2021 | Requires reproducible search reporting: databases and platforms, all additional sources, full strategies, dates, limits and their justification, deduplication, and records per source. |

These examples differ in subject and review type, but share a durable principle:

> A survey Background is an **operational contract** between the paper's motivating claims, taxonomy, and evidence base.

## The ANCHOR Framework

### A — Anchor the phenomenon in observable criteria

Begin with a definition that can be used to include a study, exclude a study, and identify the unit of analysis. A broad paraphrase such as “a system that improves itself” is not operational.

For this survey, self-evolution should normally require:

1. **Sequential opportunity:** the system can encounter more than one update opportunity across interactions, tasks, deployments, or generations.
2. **Evidence-informed change:** experience or evaluation evidence can affect whether, where, or how a change is proposed, selected, admitted, or retained.
3. **Persistent state change:** at least one reusable functional component changes beyond the current output. Examples include parameters, prompts, memory, tools, skills, workflows, data, architecture, policy, or evaluation artifacts.
4. **Downstream consequence:** the retained change can affect behavior or update decisions at a later time.

Represent the evolving system as a sequence of versioned snapshots:

\[
S_0 \rightarrow S_1 \rightarrow \cdots \rightarrow S_T,
\]

where each \(S_t\) denotes the functional state used after the \(t\)-th admitted update. An **evolution trajectory** includes the snapshots, proposed and rejected updates, evaluation evidence, resource expenditure, and relevant environment history—not merely the initial and final scores.

Use one compact lifecycle if notation helps:

\[
(S_t, x_t) \rightarrow \tau_t \rightarrow z_t
\rightarrow \{\Delta_t^{(k)}\}_{k=1}^{K}
\rightarrow d_t \rightarrow S_{t+1},
\]

where \(x_t\) is a task or environment condition, \(\tau_t\) an observed execution trace, \(z_t\) evaluation evidence, \(\Delta_t^{(k)}\) candidate changes, and \(d_t\) a decision such as continue, revise, commit, reject, quarantine, or roll back. Do not imply that every system implements every stage.

Avoid a long history of AI unless a historical distinction changes the inclusion boundary or later taxonomy.

### N — Name neighboring concepts and define the boundary relation

Adjacent fields should not be treated as interchangeable synonyms. State the relation of each to the review:

| Neighboring paradigm | Relation to self-evolution in this survey |
|---|---|
| Inference-time self-refinement | Excluded as direct self-evolution when it only changes the current output; included when a correction is retained as reusable state or when it supplies a transferable evaluation mechanism. |
| Continual or lifelong learning | Included when sequential experience produces retained model or system change; supplies longitudinal concepts such as retention, forgetting, and transfer. |
| Online adaptation and concept drift | Included when monitoring or evaluation triggers persistent adaptation; supplies sensing, change-detection, and recovery methods. |
| AutoML and neural architecture search | Included as an enabling lineage when performance estimation selects and retains candidates; not assumed to be autonomous post-deployment evolution. |
| Neuroevolution and open-ended learning | Included when fitness, novelty, archives, or environments shape persistent populations or lineages; supplies selection and challenge-generation concepts. |
| Self-adaptive software and adaptive robotics | Included when evaluation or monitoring governs a persistent system transition; supplies runtime assurance and rollback mechanisms. |
| Evaluator co-evolution | Included when metrics, rubrics, judges, tests, or protocols are themselves versioned and governed, even if the policy update is analyzed separately. |

Distinguish two kinds of inclusion:

- **Direct evidence:** the study investigates a system that satisfies the operational self-evolution criteria.
- **Enabling evidence:** the study supplies an evaluation function, object, method, failure mode, or governance principle that transfers to such systems.

This distinction prevents a broad interdisciplinary corpus from being misrepresented as a mature, unified self-evolving-AI literature.

### C — Construct conceptual primitives and their relations

Define an **evaluation system** as more than a score or judging model. A useful representation is:

\[
\mathcal{V}_t=
(\mathcal{C}_t,\mathcal{O}_t,\mathcal{D}_t,\mathcal{J}_t,
\mathcal{P}_t,\mathcal{A}_t,\mathcal{G}_t),
\]

where:

- \(\mathcal{C}_t\): criteria, objectives, rubrics, constraints, and thresholds;
- \(\mathcal{O}_t\): objects directly observed or judged;
- \(\mathcal{D}_t\): evidence sources, datasets, environments, traces, and anchors;
- \(\mathcal{J}_t\): evaluator mechanisms, such as tests, humans, models, or formal tools;
- \(\mathcal{P}_t\): execution and aggregation protocol;
- \(\mathcal{A}_t\): access and disclosure policy;
- \(\mathcal{G}_t\): decision rule mapping evidence to downstream action.

Then distinguish the primitives used throughout the survey:

- **Evaluation object:** what is directly assessed, such as an output, step, trajectory, candidate update, snapshot, evolution run, or evaluator.
- **Evolution object:** what is persistently modified, such as parameters, memory, a tool, workflow, data, architecture, policy, or evaluation protocol.
- **Evidence source:** where observations come from, such as execution, a held-out task, an environment, a human, or a formal specification.
- **Evaluator:** the mechanism that interprets evidence under criteria.
- **Evaluation signal:** the returned representation, such as a score, rank, critique, uncertainty estimate, violation, counterexample, or certificate.
- **Evaluation protocol:** how tasks are sampled, run, repeated, aggregated, and disclosed.
- **Evaluation decision:** an induced action, such as continue, revise, allocate budget, accept, commit, reject, quarantine, or roll back.

Make the relations explicit. The evaluation object need not be the evolution object, the evaluator need not be the evidence source, and an evaluation signal is not itself a state transition until a decision rule gives it authority.

### H — Harmonize functional roles with information and authority

Define Control, Proof, and Meta-Evaluation compactly in Background; defer their full functional taxonomy and literature synthesis to Part I.

- **Control Evaluation** influences search, feedback, selection, admission, or rollback within the evolution process.
- **Proof Evaluation** provides sufficiently independent evidence for comparing snapshots or trajectories and supporting a stated claim of progress.
- **Meta-Evaluation** assesses or governs the validity, calibration, robustness, coverage, drift, versioning, or promotion of evaluation systems.

These are functional roles, not technology classes. The same unit test, human panel, environment, reward model, or LLM judge can play different roles depending on four properties:

1. **Access:** what the evolving system can inspect or query;
2. **Timing:** when and how often the evidence is exposed;
3. **Use:** whether it guides candidate generation, ranking, admission, or only final comparison;
4. **Authority:** which state transition or scientific claim it can authorize.

Evidence independence is therefore relational and graded, not an intrinsic label attached to a dataset. A nominally held-out set becomes part of Control Evaluation if it is queried repeatedly to choose updates. Conversely, a method becomes suitable for Proof only to the extent that its data, protocol, evaluator, and logs remain insulated from the optimization loop.

Do not introduce an infinite hierarchy of meta-evaluators. Evaluator promotion must terminate in evidence outside the candidate evaluator's own control—for example, fixed anchors, executable outcomes, independent humans, formal specifications, or institutionally separated review.

### O — Operationalize the review design and scope

Name the review design before listing databases. For this project, the most defensible default is a **structured scoping survey with evidence mapping**: the literature spans heterogeneous fields, study designs, outcome measures, and terminology, so the objective is to map concepts and relationships rather than aggregate a common effect size.

Do not use “systematic review” as a prestige label. Use it only if the completed workflow supports the claim. A review can use systematic search and reporting practices while being described as a structured or scoping survey.

Specify all scope dimensions:

- time interval and treatment of foundational exceptions;
- language;
- publication types and publication-status verification;
- topical inclusion and exclusion rules;
- relationship to self-evolution: direct or enabling evidence;
- treatment of static evaluation studies;
- treatment of conference papers and preprints;
- unit of analysis when multiple versions of one work exist.

For this fast-moving topic, use explicit evidence layers rather than silently mixing records:

1. **Core archival corpus:** peer-reviewed work used for stable taxonomic and maturity claims.
2. **Enabling corpus:** adjacent literature used to transfer established evaluation concepts and methods.
3. **Frontier corpus:** recent conference papers or preprints used to identify emerging mechanisms, reported separately and never used alone to claim field maturity or consensus.

The repository currently contains a 50-item journal-focused research set and a broader candidate bibliography that includes conference papers and preprints. Treat the 50-item set as a provisional evidence map until the final search is rerun; keep publication status as an explicit coding field.

### R — Record retrieval, selection, coding, and synthesis

A reproducible method reports actions already performed, not instructions for a future author. Record at least:

#### Retrieval

- every database **and platform**;
- all supplementary sources, citation chasing, and manual searches;
- the last search date for each source;
- the full, source-specific search string exactly as run;
- fields, filters, limits, and justification for each limit;
- raw records retrieved per source and export format;
- search peer review or pilot validation, if performed.

#### Selection

- duplicate-removal tool and matching rule;
- title/abstract and full-text screening stages;
- number of reviewers at each stage and whether decisions were independent;
- conflict-resolution procedure;
- exclusion reasons at full text;
- counts at identification, deduplication, screening, eligibility, and inclusion;
- protocol deviations and their dates.

#### Coding

- a versioned codebook with operational definitions;
- pilot coding and resulting revisions;
- whether coding was single or independent multiple coding;
- agreement or adjudication procedure;
- handling of missing, ambiguous, or multiple-valued fields;
- links between each coded claim and its source passage where feasible.

Use the project's primary frame:

`Function × Object × Method × Evidence Independence × Temporal Scale`

Also capture evolution object, domain, benchmark or environment, publication status, resource cost, safety evidence, evaluator version, intermediate snapshots, and evidence layer.

#### Synthesis

Explain what each synthesis operation can support:

- descriptive mapping shows coverage and concentration;
- cross-tabulation reveals combinations that are common or absent;
- qualitative thematic synthesis explains mechanisms and failure modes;
- gap analysis identifies missing evidence, but absence from the corpus is not proof that no work exists;
- publication counts do not establish methodological maturity;
- heterogeneous results should not be pooled as if they measured the same outcome.

Make the audit trail accessible through supplements: complete queries, raw exports when licensing permits, deduplication log, screening table, exclusion reasons, codebook, coded corpus, flow diagram, and version history.

## Recommended Section Architecture

Use seven subsections when venue space allows:

1. **Operational Definition of Self-Evolving AI Systems** — necessary criteria, snapshots, and evolution trajectory.
2. **Conceptual Boundaries and Related Paradigms** — relations to adjacent fields and direct versus enabling evidence.
3. **Evaluation-System Primitives and Lifecycle** — entities, relations, signals, and decisions.
4. **Functional Roles and Evidence Independence** — compact Control–Proof–Meta semantics and role-assignment criteria.
5. **Review Design and Scope** — review type, objectives, evidence layers, and eligibility boundaries.
6. **Search and Study Selection** — information sources, search execution, deduplication, screening, and flow.
7. **Literature Coding and Synthesis** — codebook, reliability, mapping, and gap-analysis logic.

If space requires five subsections, merge Sections 1–2 and Sections 5–6. Do not merge the conceptual definitions with the search protocol; readers should be able to distinguish a theoretical boundary from a database eligibility rule.

## Recommended Argument Flow for This Survey

1. State the operational definition and immediately explain why a versioned trajectory, rather than a single output, is the unit of analysis.
2. Use neighboring paradigms to sharpen the boundary; do not provide a generic history.
3. Define the evaluation-system primitives and show one lifecycle relation.
4. Derive functional roles from how evidence is used and what authority it receives.
5. Explain why the field's fragmentation calls for scoping and evidence mapping.
6. Specify evidence layers and eligibility before reporting the search.
7. Report the search and screening as an auditable sequence.
8. End with the coding frame and explain what the synthesis can—and cannot—conclude.

## Methodological Honesty Rule for the Current Repository

`data/research-report.md` explicitly states that database-level hit counts were not fabricated and that a same-date rerun, exports, deduplication, and a PRISMA-S-compatible flow are still required. Therefore:

- do not convert recommended database queries into past-tense claims that they were run;
- do not present 50 selected papers as the output of a fully reproducible flow until the missing audit artifacts exist;
- do not infer two-reviewer screening, agreement statistics, or quality assessment that was not recorded;
- retain conspicuous, compile-safe placeholders such as `\emph{[LAST SEARCH DATE]}` and `\emph{[N RECORDS]}`;
- separate verified conceptual prose from protocol fields awaiting verification;
- include a short author-facing list of every unresolved placeholder with the draft.

This is stronger scholarship than filling gaps with plausible numbers. A transparent incomplete field can be completed; an invented method cannot be audited.

## Common Failure Modes

- **Second introduction:** repeating importance, motivation, and contributions instead of fixing definitions and boundaries.
- **Generic history:** narrating AI development without using history to establish a distinction needed later.
- **Definition by examples:** listing parameters, prompts, memory, tools, and workflows without necessary inclusion criteria.
- **Neighbor collapse:** treating continual learning, AutoML, self-refinement, and self-evolution as synonyms.
- **Ontology without relations:** defining object, signal, and decision but not showing how evidence receives authority.
- **Technology-role confusion:** assuming tests are Proof or reward models are Control regardless of access and use.
- **Framework duplication:** fully reviewing Control, Proof, and Meta functions in Background and leaving Part I repetitive.
- **Aspirational methodology:** writing “the final manuscript should report” instead of documenting completed actions or marking missing fields.
- **Database-name method:** listing search engines without platforms, exact queries, dates, filters, counts, or deduplication.
- **False PRISMA claim:** treating a flowchart as compliance or methodological quality.
- **Silent corpus mixing:** using journals, conferences, preprints, and adjacent fields without labeling their evidential role.
- **Unreliable coding claim:** reporting dimensions but not the codebook, pilot, reviewer process, or adjudication.
- **Count-as-maturity inference:** interpreting many publications as proof that a method is reliable or established.

## ANCHOR Quality Gate

Before accepting a draft, verify:

1. Self-evolution is defined by observable necessary conditions rather than aspiration or examples.
2. The unit of analysis includes versioned snapshots and an evolution trajectory.
3. Output-only refinement is distinguished from persistent system change.
4. Every neighboring paradigm has an explicit inclusion relation.
5. Direct self-evolution evidence is distinguishable from enabling adjacent evidence.
6. Evaluation system is distinguished from an individual evaluator or metric.
7. Evaluation object and evolution object are separate.
8. Evidence source, evaluator, signal, protocol, access policy, and decision authority are related explicitly.
9. Control, Proof, and Meta are assigned by access, timing, use, and authority.
10. Evidence independence is treated as graded and relational.
11. The review design is named and justified.
12. Time, language, publication, topic, and evidence-layer boundaries are explicit.
13. Databases and platforms, exact searches, dates, filters, and source counts are reported.
14. Deduplication, screening, reviewers, disagreements, exclusions, and flow counts are auditable.
15. Coding has a codebook, pilot or adjudication procedure, and missing-data rule.
16. Synthesis claims do not exceed what descriptive mapping and qualitative comparison can support.
17. Unverified protocol facts remain visible placeholders rather than invented detail.
18. The Background prepares Part I without duplicating its taxonomy.
