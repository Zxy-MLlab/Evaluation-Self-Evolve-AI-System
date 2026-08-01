# Introduction Writing Patterns for Technical Surveys

## Purpose

Use this reference to draft or revise the Introduction of the **Evaluation in Self-Evolving AI Systems** survey. It distills recurring moves from representative, formally published surveys and adapts them to this project's evaluation-centric position.

The aim is not to imitate phrasing. It is to reproduce the underlying argumentative work: make the topic necessary, locate an exact gap among adjacent reviews, justify the organizing lens, and state what the survey produces beyond a bibliography.

## Evidence Base

The following surveys provide complementary examples of strong Introduction design:

| Survey | Useful structural move |
|---|---|
| [Neural Architecture Search: A Survey](https://jmlr.org/papers/volume20/18-598/18-598.pdf), JMLR 2019 | Opens with a concrete automation bottleneck, positions adjacent AutoML areas, introduces three causal dimensions, and makes the roadmap follow them. |
| [A Survey on Evaluation of Large Language Models](https://doi.org/10.1145/3641289), ACM TIST 2024 | Organizes a broad field through reader-facing questions about what, where, and how to evaluate; aligns contributions with the article structure. |
| [Automatically Correcting Large Language Models](https://aclanthology.org/2024.tacl-1.27.pdf), TACL 2024 | Moves from model failures to feedback as the operative mechanism, narrows from human to automated feedback, defines a conceptual pipeline, and states explicit inclusion criteria. |
| [Evaluating Step-by-step Reasoning Traces: A Survey](https://aclanthology.org/2025.findings-emnlp.94.pdf), Findings of EMNLP 2025 | Shows that a dominant endpoint metric is insufficient, connects evaluation to optimization, identifies disagreement about the evaluation object, and derives a criterion-and-evaluator taxonomy. |
| [From Automation to Autonomy: A Survey on LLMs in Scientific Discovery](https://aclanthology.org/2025.emnlp-main.895.pdf), EMNLP 2025 | Compares adjacent surveys by their organizing lens, identifies the missing dynamic perspective, anchors a taxonomy in an external process, defines scope boundaries, and derives an autonomy trend. |
| [Locate, Steer, and Improve](https://aclanthology.org/2026.findings-acl.502.pdf), Findings of ACL 2026 | Contrasts observational reviews with an actionable need, names two precise limitations, and responds with a memorable pipeline whose contributions describe reader utility. |

These examples vary in topic, age, and venue. Their shared lesson is more reliable than any single template: a survey Introduction is a **gap-to-lens argument**, not a condensed table of contents.

## The BRIDGE Argument

### B — Begin with the field transition

Start from a change that alters the research problem. Avoid opening with a generic claim that AI is rapidly developing.

For this survey, the relevant transition is:

`fixed system evaluated after training → system repeatedly evaluated and persistently modified`

Establish only the minimum background needed to make that transition intelligible. Define self-evolution by persistent state change across updates, not by ordinary variation in outputs or a single inference-time refinement.

The opening paragraph should answer:

- What was the conventional arrangement?
- What changed technically or operationally?
- Why does that change make the old view of evaluation incomplete?

### R — Reveal the conceptual consequence

Move immediately from the transition to its consequence. In a self-evolving system, evaluation is not only a terminal measurement; it can define objectives, detect gaps, diagnose failures, produce feedback, allocate search, select candidates, govern state transitions, and later assess whether the trajectory constitutes progress.

Then state the tension that makes a new survey lens necessary:

`evaluation drives updates ↔ optimization erodes evidential independence`

Add the second-order problem:

`the system evolves ↔ the evaluator can become stale, drift, or be exploited`

This is the conceptual hinge of the Introduction. It must appear before naming Control, Proof, and Meta-Evaluation; otherwise the framework looks arbitrary.

### I — Inspect adjacent reviews

Position the survey against **families of reviews**, not a list of individual papers. A useful comparison for this project is:

| Review family | Typical organizing question | What it contributes | What remains outside its main lens |
|---|---|---|---|
| Self-evolving model and agent surveys | What, when, where, or which component evolves? | Update mechanisms, components, and application settings | Evaluation authorities and evidence independence across the full trajectory |
| LLM and agent evaluation surveys | What capability, benchmark, metric, or judge is used? | Evaluation objects, methods, protocols, and evaluator reliability | Persistent system updates and the causal role of evaluation in selecting them |
| Continual-learning and concept-drift reviews | Does performance persist under sequential change? | Retention, forgetting, transfer, drift, and longitudinal metrics | Agentic component changes, evaluator co-evolution, and promotion authority |
| AutoML, neuroevolution, and open-ended evolution reviews | How are candidates searched and selected? | Fitness, performance estimation, archives, novelty, and selection pressure | Independent proof that repeated selection yields robust deployed progress |
| Verification, safety, and meta-evaluation reviews | Are outputs, systems, or evaluators valid and trustworthy? | Assurance, calibration, robustness, formal and human evidence | Integration with the full self-evolution lifecycle |

Use a fair pattern:

1. Say what each family successfully organizes.
2. Identify the relation or dimension that falls between those families.
3. Explain why that missing relation matters for self-evolving systems.

Avoid straw-man claims such as “existing surveys do not consider evaluation.” Prefer: “these perspectives provide necessary pieces but do not yet organize them around evaluation's changing authority over an evolution trajectory.”

### D — Define the exact gap and scope

State the gap as a missing **conceptual relation**, not merely a missing document:

> The literature does not yet provide a unified account of what evaluation does, what it observes, how it is implemented, when its evidence remains independent, and how evaluators themselves are audited and updated as system versions accumulate.

Then delimit the review. The default scope includes AI systems that:

- undergo repeated updates rather than a single static training run;
- retain a changed system state across interactions, tasks, generations, or deployments;
- may evolve parameters, prompts, memory, data, tools, skills, workflows, architectures, policies, or evaluation components;
- use evaluation before, during, or after updates.

The survey is not a catalogue of every self-improvement algorithm, every static LLM benchmark, or every one-shot self-correction method. Include adjacent work when it contributes a transferable evaluation function, object, method, failure mode, or governance principle.

Place detailed search strings, screening counts, and eligibility procedures in the review-methodology section. The Introduction needs only enough scope to make the claims interpretable.

### G — Ground the organizing lens and research questions

Present the paper's five-part architecture as the answer to the gap:

1. **Functions:** what evaluation does in the evolution lifecycle.
2. **Objects:** what is directly assessed and what is ultimately changed.
3. **Methods:** which signals, evaluators, protocols, and infrastructures implement evaluation.
4. **Limitations:** where those arrangements fail or cease to support trustworthy long-term evolution.
5. **Future directions:** which research requirements follow from the documented limitations.

Introduce Control, Proof, and Meta-Evaluation only as the high-level synthesis of the **Functions** dimension:

- **Control Evaluation** guides search and governs updates.
- **Proof Evaluation** supplies operationally independent evidence about improvement across system snapshots.
- **Meta-Evaluation** audits and governs evaluators and their promotion.

Do not present these roles as three mandatory models or an established community taxonomy. They are the survey's synthesis of fragmented functions and authorities.

Research questions should be consequences of the gap and should map one-to-one onto major sections. Test every question:

- Is it answerable by the reviewed corpus?
- Does the body contain an explicit synthesis that answers it?
- Does at least one stated contribution explain what the survey delivers for it?
- Is it distinct from the other questions?

### E — Enumerate deliverables and end with the roadmap

Contributions should name outputs a reader can inspect or use. Strong contribution verbs include:

- define, distinguish, synthesize, organize, map, compare, expose, derive, and specify.

Weak contribution language merely says the paper “reviews,” “discusses,” or “provides a comprehensive overview.” Avoid unsupported priority claims such as “the first” and promotional adjectives such as “unprecedented.”

For this survey, useful deliverables are:

1. a functional taxonomy and authority model centered on Control, Proof, and Meta-Evaluation;
2. an object taxonomy that separates the object observed from the component evolved;
3. a method taxonomy plus the coding frame `Function × Object × Method × Evidence Independence × Temporal Scale`;
4. a cross-literature synthesis exposing the imbalance between abundant control signals, limited independent longitudinal proof, and immature evaluator governance;
5. a limitation-to-requirement research agenda and reporting guidance.

The roadmap should be short and should mirror the research questions. If the roadmap needs a different ordering from the RQs, the architecture is probably not yet coherent.

## Recommended Paragraph Architecture for This Survey

Whether or not subsection headings are used, the Introduction should perform these paragraph-level jobs in order:

1. **Transition:** fixed post-training evaluation gives way to persistent system adaptation.
2. **Consequence and tension:** evaluation becomes causal infrastructure, while optimized evidence loses independence and evaluators can themselves fail.
3. **Adjacent-review positioning:** existing survey families cover complementary pieces but use different units, timescales, and evidential assumptions.
4. **Exact gap and scope:** state the missing evaluation-centric account and define what this review includes.
5. **Research questions:** ask Functions, Objects, Methods, Limitations, and Future Directions.
6. **Contributions and synthesis:** state concrete outputs and the main structural finding.
7. **Roadmap:** map sections to the questions in one compact paragraph.

If headings are retained, replace administrative labels such as “Motivation” with argumentative labels:

- From Adaptation to Self-Evolution
- Evaluation as the Infrastructure of Evolution
- The Missing Evaluation-Centric Perspective
- Scope and Research Questions
- Contributions and Organization

## Evidence and Claim Discipline

Separate three levels of claim:

1. **Documented literature claim:** a cited work explicitly reports or argues it. Use verbs such as “shows,” “finds,” or “defines” only after checking the source.
2. **Cross-paper synthesis:** the review team infers a pattern from multiple studies. Signal it with “our synthesis indicates,” “across these streams,” or “the literature map reveals.”
3. **Proposed framework:** this survey introduces terminology or governance principles. Use “we distinguish,” “we propose,” or “we organize,” and do not attribute community consensus.

Use citations as evidence at the point of the claim. Avoid citation piles after broad sentences whose individual sources support different propositions. Prefer representative sources for the opening and reserve exhaustive coverage for the body.

## Common Failure Modes

- **Inventory opening:** beginning with a long list of parameters, prompts, memories, tools, workflows, data, and policies before establishing the transition.
- **Generic importance:** relying on “rapid progress,” “increasing attention,” or application hype without explaining why evaluation changes conceptually.
- **Missing survey comparison:** introducing the new taxonomy without showing how it differs from adjacent organizing lenses.
- **Straw-man gap:** saying prior work ignores evaluation when several evaluation surveys plainly exist.
- **Premature framework:** naming Control, Proof, and Meta-Evaluation before deriving the authority conflict that motivates them.
- **Scope drift:** turning the Introduction into a general history of self-evolving AI or a miniature related-work section.
- **Question discontinuity:** listing RQs that the preceding gap did not motivate or that later sections do not answer.
- **TOC contributions:** restating section titles as contributions without identifying a taxonomy, distinction, finding, map, checklist, or agenda.
- **Unsupported novelty:** using “first” or “comprehensive” without a reproducible comparison.
- **Empty ending:** closing with “we hope to inspire” instead of a concrete roadmap or field-level takeaway.

## Introduction Quality Gate

Before accepting a draft, verify:

1. The first paragraph names a real field transition and its consequence for evaluation.
2. The core optimization–evidence tension appears before the proposed taxonomy.
3. Adjacent surveys are grouped fairly by lens, with both coverage and residual gap stated.
4. The gap is a missing relation or capability, not merely “no survey exists.”
5. Self-evolution and the review boundary are explicit.
6. Control, Proof, and Meta-Evaluation are presented as a functional synthesis, not three fixed models or established consensus.
7. Every RQ follows from the gap and maps to a body section.
8. Every contribution names a concrete deliverable or synthesis finding.
9. The main literature asymmetry is clearly marked as this survey's synthesis.
10. The roadmap mirrors the research questions and contains no new concepts.
11. Claims, citations, and verbs are calibrated to the available evidence.
12. Evaluation remains the grammatical and conceptual subject throughout.
