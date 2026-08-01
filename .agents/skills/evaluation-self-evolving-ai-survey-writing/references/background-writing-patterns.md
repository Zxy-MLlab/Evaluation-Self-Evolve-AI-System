# Background Writing Patterns for Technical Surveys

## Contents

1. Purpose of a Survey Background
2. Lessons from Published Surveys
3. The FRAME Framework
4. Recommended Architecture for This Survey
5. Paragraph-Level Writing Pattern
6. Boundary with Other Sections
7. Common Failure Modes
8. FRAME Quality Gate

## Purpose of a Survey Background

Use this reference to draft or revise the conceptual Background of the
**Evaluation in Self-Evolving AI Systems** survey. The Background is a
**concept-to-taxonomy bridge**. It fixes the meanings, boundaries, entities, and
relations that the later literature synthesis assumes.

It should let a reader answer five questions before reaching Part I:

1. What observable process counts as self-evolution?
2. How does it relate to neighboring forms of adaptation or optimization?
3. What is the minimal lifecycle and unit of longitudinal analysis?
4. What constitutes an evaluation system, beyond a score or judge?
5. How are Control, Proof, and Meta-Evaluation distinguished without reviewing
   their full literatures prematurely?

The Background does **not** report databases, search strings, screening counts,
reviewer agreement, or literature-coding procedures. Those belong in a separate
Review Methodology section.

## Lessons from Published Surveys

The following formally published surveys illustrate transferable structural
moves. Learn from their logic; do not imitate their wording.

| Survey | Transferable move |
|---|---|
| [Neural Architecture Search: A Survey](https://jmlr.org/papers/volume20/18-598/18-598.pdf), JMLR 2019 | Defines three interacting primitives---search space, search strategy, and performance estimation---and uses the same causal skeleton to organize the article. A useful Background introduces only the machinery the taxonomy later needs. |
| [A Continual Learning Survey: Defying Forgetting in Classification Tasks](https://doi.org/10.1109/TPAMI.2021.3057446), IEEE TPAMI 2022 | Defines the phenomenon through a sequential setting and explicitly distinguishes the chosen setting from nearby alternatives. Scope follows from operational conditions rather than a list of labels. |
| [Automatically Correcting Large Language Models](https://aclanthology.org/2024.tacl-1.27/), TACL 2024 | Formalizes the language model, critic, refiner, feedback, and their interfaces before classifying methods. Actors and relations make the subsequent axes intelligible. |
| [A Survey on Evaluation of Large Language Models](https://doi.org/10.1145/3641289), ACM TIST 2024 | Establishes the minimum evaluation concepts needed for its what/where/how organization. It also shows why generic model history should be kept subordinate to the survey's analytical lens. |
| [A Survey on Large Language Model Based Autonomous Agents](https://doi.org/10.1007/s11704-024-40231-1), Frontiers of Computer Science 2024 | Introduces a unified system-level construction framework before surveying applications and evaluation. The evaluated unit can be an interacting system rather than an isolated model output. |

Across these examples, strong Background sections repeatedly do four things:

- define the focal phenomenon with observable conditions;
- distinguish it from nearby paradigms by relations, not synonyms;
- formalize a small set of actors, states, and interfaces;
- make later taxonomy dimensions feel derived rather than arbitrary.

They do not repeat the Introduction's motivation, preview every result, or mix
conceptual definitions with the review search protocol.

## The FRAME Framework

### F --- Fix the focal phenomenon

Define self-evolution as a process, not as an aspiration to improve. A system
normally qualifies when all four conditions hold:

1. **Repeated opportunity:** it encounters more than one opportunity to update
   across interactions, tasks, deployments, or generations.
2. **Evidence-informed change:** experience or evaluation evidence affects
   whether, where, or how a change is proposed, selected, admitted, or retained.
3. **Persistent state change:** at least one reusable functional component changes
   beyond the current output.
4. **Downstream consequence:** the retained change can affect later behavior or
   later update decisions.

State explicitly that self-evolution describes the update process. It does not by
itself imply improvement, generalization, safety, or cumulative progress. Those
are empirical claims requiring evaluation evidence.

Avoid defining the field only by examples such as parameters, prompts, memory,
tools, or workflows. Examples illustrate the persistent-state criterion; they do
not replace it.

### R --- Relate neighboring paradigms

Use neighboring fields to sharpen the focal boundary. State the relation that
matters, not a generic history.

| Paradigm | Conceptual relation to self-evolution |
|---|---|
| Inference-time self-refinement | Revises a current output. It becomes self-evolution only when the correction or derived knowledge is retained in reusable system state. |
| Continual or lifelong learning | Studies retained learning from sequential experience, often at the parameter or representation level. It is a major lineage but does not cover every system-level evolution object. |
| Online adaptation and concept drift | Emphasize non-stationarity, monitoring, and timely adaptation. They overlap when detected change leads to persistent system updates. |
| AutoML and neural architecture search | Automate candidate generation, performance estimation, and selection. They share an evaluation-controlled search loop, even when the process is not autonomous after deployment. |
| Neuroevolution and open-ended learning | Evolve populations, archives, environments, or objectives over generations. They contribute fitness, novelty, lineage, and challenge-generation concepts. |
| Adaptive agents and robotics | Couple models, memory, tools, policies, and environments. They motivate system- and trajectory-level evaluation rather than output-only scoring. |
| Evaluator co-evolution | Treats metrics, rubrics, judges, tests, or protocols as versioned evolution objects and raises the additional problem of evaluator governance. |

Do not turn these relations into database eligibility rules in Background. The
conceptual relation belongs here; corpus inclusion and exclusion belong in Review
Methodology.

### A --- Abstract the evolving system and lifecycle

Introduce the smallest formal model that later sections will reuse. Represent a
system snapshot as

\[
S_t=(\theta_t,p_t,m_t,\mathcal{T}_t,w_t,d_t,e_t),
\]

where the terms may denote model parameters, prompts, memory, tools or skills,
workflow, retained data, and evaluation artifacts. The tuple is illustrative,
not a requirement that every system contain every component.

A compact update lifecycle is

\[
(S_t,x_t)\rightarrow \tau_t
\xrightarrow{\mathcal{E}_t} z_t
\rightarrow \{\Delta_t^{(k)}\}_{k=1}^{K}
\xrightarrow{g_t} S_{t+1},
\]

where \(x_t\) is a task or environment condition, \(\tau_t\) an execution trace,
\(z_t\) evaluation evidence, \(\Delta_t^{(k)}\) candidate updates, and \(g_t\) a
decision rule. The lifecycle should expose relations among execution, evidence,
candidate change, and state transition; it should not prescribe one algorithm.

Define two longitudinal units:

- **System snapshot:** the versioned functional state used at a given point.
- **Evolution trajectory:** the sequence of snapshots together with proposed,
  accepted, rejected, quarantined, or rolled-back updates; evaluation evidence;
  evaluator versions; resource use; and relevant environment history.

These definitions prevent a before/after score from being mistaken for the whole
evolution process.

### M --- Model the evaluation system

Define evaluation as a governed system rather than a single metric or model:

\[
\mathcal{E}_t=
(\mathcal{C}_t,\mathcal{O}_t,\mathcal{D}_t,\mathcal{J}_t,
\mathcal{P}_t,\mathcal{A}_t,\mathcal{G}_t),
\]

where:

- \(\mathcal{C}_t\): criteria, objectives, rubrics, constraints, and thresholds;
- \(\mathcal{O}_t\): objects directly observed or judged;
- \(\mathcal{D}_t\): evidence sources, tasks, environments, traces, and anchors;
- \(\mathcal{J}_t\): evaluator mechanisms such as tests, humans, models, or formal tools;
- \(\mathcal{P}_t\): execution, sampling, repetition, and aggregation protocol;
- \(\mathcal{A}_t\): access, disclosure, and isolation policy;
- \(\mathcal{G}_t\): decision rule mapping evidence to action or a scientific claim.

Keep four distinctions explicit:

1. **Evaluation object vs. evolution object:** what is judged need not be what is
   modified.
2. **Evidence source vs. evaluator:** an environment may produce observations
   that a verifier interprets.
3. **Signal vs. decision:** a score or critique has no state-transition authority
   until a rule uses it.
4. **Evaluator vs. evaluation system:** a judge is one component inside a broader
   protocol with criteria, data access, aggregation, and governance.

Define only terms that recur in the taxonomy, comparison tables, or later
argument. Every formal symbol should earn repeated use.

### E --- Establish role semantics and evidence independence

Introduce the three functional roles in one compact passage:

- **Control Evaluation** supplies evidence that guides search, feedback,
  candidate selection, admission, or rollback.
- **Proof Evaluation** supplies sufficiently independent evidence for comparing
  snapshots or trajectories and supporting a stated claim of progress.
- **Meta-Evaluation** assesses and governs the validity, calibration, robustness,
  coverage, drift, versioning, or promotion of evaluation systems.

These are roles, not technology classes. Assign a role using four properties:

1. **Access:** what the evolving system can inspect or query;
2. **Timing:** when and how often evidence is exposed;
3. **Use:** whether evidence guides generation, ranking, admission, or only an
   external comparison;
4. **Authority:** which state transition or scientific claim it can authorize.

Treat evidence independence as relational and graded. A nominally held-out test
becomes part of Control Evaluation when repeatedly queried to choose updates.
Conversely, the same testing method can support Proof only when its data,
protocol, evaluator, and logs are sufficiently insulated from the optimization
loop.

End at the semantic distinction. Part I owns the detailed functions, literature
taxonomy, and Control--Proof--Meta synthesis. Background should prepare that
analysis, not perform it twice.

## Recommended Architecture for This Survey

Use five subsections when venue space permits:

1. **Self-Evolving AI Systems** --- operational definition and the difference
   between change and improvement.
2. **Related Paradigms and Conceptual Boundaries** --- relation to refinement,
   continual learning, online adaptation, automated search, evolution, and
   adaptive agents.
3. **System States and Evolution Trajectories** --- snapshots, candidate updates,
   admitted transitions, and longitudinal unit of analysis.
4. **Evaluation Systems and Conceptual Primitives** --- evaluation objects,
   evolution objects, evidence, evaluators, signals, protocols, and decisions.
5. **Functional Roles and Evidence Independence** --- compact role semantics and
   the access/timing/use/authority test.

If space is tight, merge Sections 2 and 3. Do not merge Background with Review
Methodology merely to reduce the number of top-level sections.

## Paragraph-Level Writing Pattern

For most Background paragraphs, use this sequence:

1. **Definition or distinction:** state the concept in the first sentence.
2. **Relation:** explain how it connects to the evolving-system lifecycle.
3. **Consequence:** state what the distinction enables later in the survey.
4. **Evidence:** cite representative literature where the claim is field-derived.

Prefer one discriminative example over a catalogue. Prefer a compact equation or
figure when it removes ambiguity among three or more entities.

## Boundary with Other Sections

| Material | Proper location |
|---|---|
| Why the field transition matters; missing survey perspective; RQs; contributions | Introduction |
| Definitions, conceptual boundaries, lifecycle, entities, and role semantics | Background |
| Databases, dates, queries, eligibility, screening, coding, and synthesis procedure | Review Methodology |
| Detailed Control, Proof, and Meta functions and supporting studies | Part I: Functions |
| What is assessed and at what granularity | Part II: Objects |
| Tests, rewards, judges, formal tools, and hybrid implementations | Part III: Methods |

## Common Failure Modes

- **Second Introduction:** repeating motivation, novelty, research questions, and
  contributions.
- **Methodology leakage:** reporting search, screening, and coding inside a
  conceptual section.
- **Generic history:** narrating AI development without sharpening a later
  distinction.
- **Definition by examples:** listing components without necessary conditions.
- **Neighbor collapse:** treating self-refinement, continual learning, AutoML,
  and self-evolution as synonyms.
- **Static abstraction:** defining a system but omitting versioned snapshots and
  the transition relation.
- **Evaluator reduction:** equating evaluation with one metric, reward model, or
  LLM judge.
- **Ontology without relations:** defining objects and signals without showing
  how evidence affects decisions.
- **Technology-role confusion:** assuming a test is inherently Proof or a reward
  model inherently Control.
- **Taxonomy duplication:** reviewing the full Control--Proof--Meta literature
  before Part I.
- **Notation without reuse:** introducing symbols that disappear after one
  paragraph.

## FRAME Quality Gate

Before accepting a Background draft, verify:

1. Self-evolution is defined by observable conditions.
2. The text states that evolution is a process, not proof of improvement.
3. Output-only refinement is distinguished from persistent state change.
4. Every neighboring paradigm has a clear conceptual relation.
5. A system snapshot and an evolution trajectory are both defined.
6. The lifecycle connects execution, evidence, candidate change, and transition.
7. Evaluation is modeled as a system rather than a solitary score or judge.
8. Evaluation object and evolution object are distinct.
9. Evidence source, evaluator, signal, protocol, and decision are related.
10. Control, Proof, and Meta are assigned by access, timing, use, and authority.
11. Evidence independence is treated as graded and relational.
12. The section prepares Part I without duplicating its literature synthesis.
13. The section does not repeat the Introduction's contributions or roadmap.
14. The section contains no search, screening, or coding claims.
15. Every definition and symbol is reused later or removed.
