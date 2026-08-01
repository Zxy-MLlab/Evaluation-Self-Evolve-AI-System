# Review Methodology Patterns for This Survey

## Purpose

Use this reference only when drafting the separate Review Methodology section.
Its job is to explain how the corpus and synthesis were produced. It must not be
embedded in the conceptual Background.

For this project, prefer the description **structured scoping survey with
evidence mapping** unless the completed protocol justifies the stronger label
“systematic review.” The literature spans heterogeneous fields, study designs,
outcomes, and terminology, so the principal goal is to map concepts and
relationships rather than pool a common effect size.

## Minimum Reportable Elements

### Review design and scope

Report the review objective, time window, language, publication types, topical
eligibility, foundational exceptions, unit of analysis, and treatment of
multiple versions of a work.

Keep evidence layers explicit when the manuscript combines them:

1. **Core archival evidence:** peer-reviewed work used for stable taxonomic and
   maturity claims.
2. **Enabling evidence:** adjacent literature used to transfer established
   evaluation concepts and methods.
3. **Frontier evidence:** recent conference papers or preprints used to identify
   emerging mechanisms, reported separately and not used alone to claim field
   maturity or consensus.

### Search and study selection

Report actions already performed:

- every database and platform;
- supplementary sources and citation chasing;
- the last search date for each source;
- complete source-specific search strings;
- fields, filters, limits, and their justification;
- records retrieved per source and export format;
- deduplication tool and matching rule;
- screening stages and number of reviewers;
- disagreement-resolution procedure;
- full-text exclusion reasons;
- counts at identification, deduplication, screening, eligibility, and inclusion;
- dated protocol deviations.

### Coding and synthesis

Use the project's primary coding frame:

`Function × Object × Method × Evidence Independence × Temporal Scale`

Also capture evolution object, domain, benchmark or environment, publication
status, resource cost, safety evidence, evaluator version, intermediate
snapshots, and evidence layer.

Report the codebook version, pilot coding, reviewer procedure, adjudication,
missing-data rules, and treatment of studies that receive multiple codes.
Explain what each synthesis operation can support:

- descriptive mapping shows coverage and concentration;
- cross-tabulation reveals common and missing combinations;
- qualitative synthesis explains mechanisms and failure modes;
- gap analysis identifies absences in the corpus, not universal non-existence;
- publication counts do not establish methodological maturity.

## Methodological Honesty for the Current Repository

`data/research-report.md` contains a 50-paper journal-focused evidence set, but
also states that database-level hit counts were not fabricated and that a
same-date rerun, exports, deduplication, and a PRISMA-S-compatible flow remain to
be completed. Therefore:

- do not convert recommended search strings into past-tense claims that they
  were run;
- do not present the 50 papers as the output of a fully reproducible flow until
  the audit artifacts exist;
- do not infer two-reviewer screening, agreement statistics, or quality
  assessment that was not recorded;
- use visible compile-safe placeholders such as
  `\emph{[LAST SEARCH DATE]}` and `\emph{[N RECORDS]}`;
- provide an author-facing list of every unresolved placeholder.

Use [PRISMA 2020](https://www.bmj.com/content/372/bmj.n71) and
[PRISMA-S](https://link.springer.com/article/10.1186/s13643-020-01542-z) as
reporting guidance when applicable. A flow diagram or search string alone does
not establish compliance or review quality.

## Quality Gate

Before accepting a methodology draft, verify that:

1. the review type matches the completed procedure;
2. conceptual boundaries are not confused with database eligibility rules;
3. databases, platforms, dates, queries, limits, and counts are auditable;
4. deduplication, screening, exclusions, and reviewer procedures are reported;
5. the codebook and synthesis operations are reproducible;
6. direct, enabling, and frontier evidence remain distinguishable;
7. no missing protocol fact has been replaced with a plausible invention.
