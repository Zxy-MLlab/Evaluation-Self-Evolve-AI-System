---
name: evaluation-self-evolving-ai-survey-writing
description: Draft or revise the Evaluation in Self-Evolving AI Systems survey using the repository's architecture and literature evidence. Use for abstracts, introductions, related-work synthesis, section outlines, contribution statements, limitations, future directions, conclusions, captions, and responses about this paper. Apply the SHIFT argument structure to abstracts and keep all claims grounded in README.md, data/research-report.md, data/references.bib, and verified primary sources.
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

## Draft Other Survey Sections

For an introduction, establish the field transition, define the unresolved problem, position adjacent surveys precisely, state the review questions, and present contributions without unsupported novelty claims.

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

Revise any failed item before presenting the text.
