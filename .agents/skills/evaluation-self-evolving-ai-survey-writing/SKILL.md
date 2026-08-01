---
name: evaluation-self-evolving-ai-survey-writing
description: Draft or revise the Evaluation in Self-Evolving AI Systems survey using the repository's architecture and literature evidence. Use for abstracts, introductions, background and scope, review methodology, related-work synthesis, section outlines, contribution statements, limitations, future directions, conclusions, captions, and responses about this paper. Apply SHIFT to abstracts, BRIDGE to introductions, ANCHOR to background and methodology, and keep all claims grounded in README.md, data/research-report.md, data/references.bib, and verified primary sources.
---

# Evaluation in Self-Evolving AI Systems Survey Writing

## Purpose

Write this survey as a literature-grounded argument, not as a generic description of self-evolving AI. Preserve the paper's central subject: **the functions, objects, methods, limitations, and future directions of Evaluation in Self-Evolving AI Systems**.

Treat Control Evaluation, Proof Evaluation, and Meta-Evaluation as the high-level functional synthesis in Part I. Do not let that framework replace the broader survey structure.

## Ground the Draft Before Writing

When working in the project repository, read the following in order:

1. `README.md` for the current scope, five-part architecture, terminology, and central thesis.
2. `data/research-report.md` for the search design, literature streams, evidence, limitations, and proposed coding dimensions.
3. `data/references.bib` for candidate references relevant to the requested passage.

Read only the relevant parts after the initial orientation, but never draft from memory when the project files can answer the question.

Use the repository as the source of truth for the paper's **design**. Use original papers, official publisher pages, and authoritative metadata as the source of truth for **external factual claims**. A BibTeX entry is not proof that a paper is peer reviewed, eligible for the review, or supportive of a specific claim.

If support is absent or ambiguous, search and verify before adding the claim. State the uncertainty when verification is impossible. Never invent papers, results, publication status, citation counts, or field consensus.

## Preserve the Paper's Conceptual Architecture

Use these five questions to locate every passage:

1. **Functions:** Why does evaluation exist, and what role does it play in self-evolution?
2. **Objects:** What behavior, process, update, component, system state, evolution history, or evaluator is assessed?
3. **Methods:** What evaluator, signal, evidence source, protocol, or infrastructure implements the assessment?
4. **Limitations:** Why is current evaluation unreliable, insufficient, or difficult to scale in self-evolving systems?
5. **Future directions:** What research direction follows from each documented limitation?

Use the project coding frame when synthesizing literature:

`Function × Object × Method × Evidence Independence × Temporal Scale`

Keep the following distinctions explicit:

- Evaluation object is not necessarily the component being evolved.
- A state change is not evidence of an improvement.
- A score used repeatedly for optimization loses evidential independence.
- Control Evaluation can guide and admit changes but cannot alone certify robust evolution.
- Proof Evaluation must remain operationally independent from iterative candidate generation and selection.
- Meta-Evaluation can audit and update evaluators, but a candidate evaluator cannot approve its own promotion.
- Claims attributed to prior literature must be separated from this survey's proposed synthesis.

## Write Abstracts with SHIFT

Before drafting or revising an abstract, read `references/abstract-writing-patterns.md`.

Build the abstract as a compact argument:

1. **S — Set the shift.** State the technical or conceptual transition that makes the topic important.
2. **H — Highlight the gap.** Identify the unresolved fragmentation or conceptual failure, not merely the absence of a survey.
3. **I — Introduce the lens.** Present the survey's scope and organizing framework as the answer to that gap.
4. **F — Formulate the synthesis.** Report at least one field-level finding produced by the literature synthesis.
5. **T — Terminate with the takeaway.** End with the conceptual value or evidence-backed research agenda.

For this paper, the default field-level synthesis is an asymmetry, not a claim that no relevant work exists:

> Existing research provides increasingly rich evaluation signals for driving system change, but offers substantially less independent longitudinal evidence that those changes constitute robust evolution; evaluator co-evolution and governance are less mature still.

Use this only when the reviewed evidence supports it and calibrate the strength of the wording to the evidence.

### Default abstract sequence

Unless a venue imposes another format, use seven to nine sentences:

1. Paradigm shift in self-evolving AI.
2. Consequence for the role of evaluation.
3. Specific fragmentation or missing distinction in existing research.
4. Scope and organizing dimensions of the survey.
5. Functional synthesis: Control, Proof, and Meta-Evaluation.
6. Compressed coverage of evaluation objects and methods.
7. Principal structural finding from the literature.
8. Derived research agenda and final conceptual takeaway.

Target roughly 180–250 English words unless the venue specifies otherwise. Omit citations from the abstract by default. List only top-level categories; move inventories and examples to the body.

## Write Introductions with BRIDGE

Before drafting or revising an introduction, read `references/introduction-writing-patterns.md`.

Treat the introduction as an argument for why an evaluation-centric survey is needed, not as a background inventory. Build that argument with **BRIDGE**:

1. **B — Begin with the field transition.** Move from fixed post-training systems to systems that make persistent updates across interactions, tasks, or deployments.
2. **R — Reveal the conceptual consequence.** Explain why this transition makes evaluation part of the causal evolution loop and exposes a conflict between optimization and evidence.
3. **I — Inspect adjacent reviews.** Group prior surveys by the perspective they organize—self-evolution, agent or model evaluation, continual learning, automated optimization, verification, or evaluator reliability—and state what each perspective contributes.
4. **D — Define the exact gap and scope.** Identify the missing relationship among these perspectives, delimit what counts as self-evolution, and distinguish the present survey from a general survey of self-improvement algorithms.
5. **G — Ground the organizing lens and questions.** Introduce Functions, Objects, Methods, Limitations, and Future Directions; present Control, Proof, and Meta-Evaluation as this survey's functional synthesis; then state research questions that the body can answer.
6. **E — Enumerate deliverables and end with the roadmap.** State concrete intellectual and practical outputs, report the principal field-level synthesis, and make the section order mirror the research questions.

For this paper, the central tension should be stated before the taxonomy:

> Evaluation must both guide system change and support claims that the change constitutes progress, yet an evaluation signal repeatedly exposed to optimization cannot by itself remain independent evidence of progress; the evaluator may also become outdated or strategically exploitable.

Do not claim that adjacent surveys ignored evaluation altogether. The defensible gap is that the relevant literatures remain organized around different units and timescales, and do not jointly distinguish evaluation's control, evidential, and governance authorities across an evolution trajectory.

If subsection headings are appropriate for the venue, prefer argumentative headings in this order:

1. From Adaptation to Self-Evolution
2. Evaluation as the Infrastructure of Evolution
3. The Missing Evaluation-Centric Perspective
4. Scope and Research Questions
5. Contributions and Organization

The introduction may instead use unheaded paragraphs when the venue favors a continuous narrative. In either form, ensure that every contribution answers a previously established gap and that the roadmap follows the same order as the research questions.

## Write Background, Scope, and Review Methodology with ANCHOR

Before drafting or revising the Background, Scope, or Review Methodology, read `references/background-writing-patterns.md`.

Treat this section as the paper's **operational contract**: it must make later classifications reproducible by fixing what counts as self-evolution, which neighboring work is included, what an evaluation system contains, how functional roles are assigned, and how studies are found and coded.

Build the section with **ANCHOR**:

1. **A — Anchor the phenomenon.** Define self-evolution through observable criteria: repeated update opportunities, evidence-informed change, persistent modification of reusable system state, and consequences for later behavior. Introduce system snapshots and evolution trajectories.
2. **N — Name neighboring concepts and boundaries.** Relate self-evolution to inference-time self-refinement, continual learning, online adaptation, AutoML, neuroevolution, open-ended learning, and self-adaptive systems. State conditions for inclusion instead of treating the labels as synonyms.
3. **C — Construct the conceptual primitives.** Define the evaluation system, evaluation object, evolution object, evidence source, evaluator, signal, protocol, access policy, and induced decision; show how they relate in an update lifecycle.
4. **H — Harmonize roles with authority.** Define Control, Proof, and Meta-Evaluation briefly and assign roles by information access, timing, downstream use, and decision authority—not by whether the implementation is a test, human, reward model, or LLM judge.
5. **O — Operationalize the review design and scope.** Name the review type and explain why it fits the heterogeneous field. Define time, language, publication, topical, and evidence boundaries; distinguish direct self-evolving studies from enabling adjacent literature and emerging frontier evidence when those corpora are mixed.
6. **R — Record retrieval, selection, coding, and synthesis.** Report every database and platform, last search date, full query, limits, deduplication, screening, reviewer process, exclusion reasons, coding fields, reliability procedure, synthesis method, and accessible audit artifact.

For this project, prefer a **structured scoping survey with evidence mapping** unless the completed protocol supports the stronger label “systematic review.” Keep the direct, enabling, and frontier evidence layers distinguishable. Do not present the current `data/research-report.md` as a reproducible completed search: it records a 50-paper journal-focused evidence set but explicitly marks database hit counts and a same-day rerun as still required.

Never invent missing search dates, record counts, duplicate counts, reviewer agreement, or screening decisions. Use conspicuous compile-safe placeholders for unverified fields and list exactly what must be replaced. Do not claim PRISMA or PRISMA-S compliance merely because a flow diagram or search string is present.

Prefer argumentative subsection headings in this order:

1. Operational Definition of Self-Evolving AI Systems
2. Conceptual Boundaries and Related Paradigms
3. Evaluation-System Primitives and Lifecycle
4. Functional Roles and Evidence Independence
5. Review Design and Scope
6. Search and Study Selection
7. Literature Coding and Synthesis

Keep the functional-role discussion compact here. Part I owns the full Control–Proof–Meta taxonomy; Background defines only enough semantics to make later coding unambiguous.

## Draft Other Survey Sections

For taxonomy or related-work sections, synthesize papers by the project's dimensions instead of writing one-paper-per-paragraph summaries. Explain why each category exists, how categories differ, and what the comparison reveals.

For limitations and future directions, pair them explicitly:

`observed limitation → supporting evidence → consequence for self-evolution → research requirement`

For conclusions, answer the paper's central question and restate only findings already established in the body. Do not introduce new methods, evidence, or claims.

## Style Rules

- Write an argument, not a compressed table of contents.
- Lead paragraphs with the claim and use literature as evidence.
- Prefer precise contrasts such as “drives change” versus “validates progress.”
- Keep Control, Proof, and Meta-Evaluation capitalized and consistently defined.
- Use “evaluator” for a concrete judging mechanism and “evaluation” for the broader function, process, or system.
- Avoid promotional phrases such as “comprehensive,” “first,” “unprecedented,” or “paradigm-defining” unless directly defensible.
- Do not imply that the Control–Proof–Meta terminology is already a community consensus; present it as this survey's synthesis unless evidence establishes otherwise.
- Do not overstate “Proof” as mathematical proof when it denotes empirical evidence; qualify formal verification separately.
- Avoid long lists, repeated definitions, generic AI hype, and conclusions such as “we hope this survey inspires future work.”

## Quality Gate

Before returning a draft, check:

1. **Grounding:** Can every substantive literature claim be traced to the repository or a verified primary source?
2. **Scope:** Is Evaluation, rather than self-evolution in general, the grammatical and conceptual subject?
3. **Logic:** Does each paragraph move from problem to organization, evidence, synthesis, or consequence?
4. **Architecture:** Is the passage correctly placed within Functions, Objects, Methods, Limitations, or Future Directions?
5. **Independence:** Are optimization signals distinguished from independent evidence?
6. **Claim strength:** Are established findings, inferences, and the survey's own proposals clearly separated?
7. **Terminology:** Are self-evolution, system snapshot, evolution trajectory, evaluator, and evaluation used consistently?
8. **Contribution:** Does the passage reveal a useful synthesis rather than merely enumerate papers?
9. **Introduction argument:** For an introduction, does each BRIDGE move appear in order, and does each research question and contribution follow from the stated gap?
10. **Background contract:** For background or methodology, does each ANCHOR move appear, are neighboring paradigms separated by operational criteria, and are all review-protocol facts auditable rather than aspirational or fabricated?

Revise any failed item before presenting the text.
