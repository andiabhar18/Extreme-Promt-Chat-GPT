# Evidence Standards and Source Appraisal

Use this reference for research, fact-checking, source evaluation, and evidence-backed recommendations. It is an operational guide, not a universal formal grading framework.

## 1. Evidence is claim-specific

Do not assign a source one permanent reliability score for every subject. A regulator may be authoritative about its own rules but not an independent evaluator of its own performance. A company is authoritative about what it announced, not necessarily about whether its product works as advertised. A primary study is direct evidence of its reported methods and results, but may still be underpowered, biased, or non-reproducible.

Evaluate the relationship between the exact claim and the exact source.

## 2. Source classes

| Class | Typical material | Appropriate use | Main caution |
|---|---|---|---|
| A. Authoritative primary | Official laws, regulator notices, standards text, original datasets, product docs, original study | Establishing what the authority/document/data actually says | May be outdated, narrow, self-interested, or methodologically weak |
| B. High-quality synthesis | Systematic reviews, meta-analyses, consensus guidelines, rigorous technical reviews | Synthesizing a body of evidence | Quality depends on methods, search coverage, inclusion criteria, and currency |
| C. Independent expert analysis | Reputable technical analysis, specialist reporting, independent audits | Interpretation, context, corroboration, identifying implications | Expertise and independence must be checked |
| D. Contextual reporting | General news, trade press, practitioner writeups | Timeline, context, leads, stakeholder positions | May simplify, omit methods, or repeat another source |
| E. Anecdotal / community | Forums, social posts, reviews, personal accounts | Experience reports, sentiment, discovering failure modes | Not representative and not proof of general causation |
| F. Unverified / opaque | Anonymous claims, unattributed reposts, AI-generated summaries without traceable sources | At most a lead to investigate | Do not use as material evidence without verification |

These classes are a starting point, not a mechanical ranking. Use domain-specific standards and judge the actual document.

## 3. Appraisal checklist

For each source material to the conclusion, assess:

- **Identity:** Original title, author/publisher, publication date, update date, version, and stable location.
- **Authority:** Relevant expertise, institutional mandate, editorial controls, or data stewardship.
- **Direct support:** The exact passage, table, result, or dataset field that supports the claim.
- **Method quality:** Research design, sample, measurement, controls, definitions, statistical methods, and limitations, where relevant.
- **Currency:** Whether the source is current enough for the question; check retractions, amendments, errata, and superseding versions.
- **Scope match:** Whether the evidence matches the user's jurisdiction, population, product version, geography, timeframe, and operating conditions.
- **Independence:** Whether corroborating sources rely on the same press release, paper, dataset, or unnamed informant.
- **Conflicts of interest:** Funding, sponsorship, commercial incentives, advocacy, and disclosed limitations.
- **Reproducibility:** Whether data, methods, calculations, or procedures can be checked.
- **Integrity:** Missing context, selective quotation, altered screenshots, suspicious provenance, corrections, or retractions.

Do not infer quality from domain suffix, search rank, visual polish, follower count, or the number of sites repeating the same claim.

## 4. Domain-specific source strategy

### Law, regulation, and policy

Use the current official text and authoritative regulator/court guidance. Verify jurisdiction, effective date, amendments, binding status, exceptions, and transition rules. Commentary may explain a rule but does not replace the rule. Distinguish legal requirement from recommended practice and from an interpretation.

### Science and medicine

Identify the exact population, intervention/exposure, comparator, outcome, setting, and time horizon where applicable. Prefer well-conducted systematic reviews and current guidelines for synthesis, then inspect key primary studies. Check study design, sample size, bias, effect size, uncertainty intervals, absolute as well as relative effects, external validity, preregistration, conflicts, corrections, and retractions. Do not treat statistical significance as practical importance or observational association as proof of causation.

### Software, engineering, and AI capabilities

Prefer versioned official documentation, specifications, changelogs, issue trackers, source code, and reproducible tests. Distinguish documented support, observed behavior, vendor claims, community workarounds, and assumptions. Verify product/version/plan/surface before stating a feature is available.

### Statistics and data

Inspect source dataset, collection process, definitions, population, sampling frame, missingness, revisions, time period, units, denominator, and transformations. Distinguish counts from rates, nominal from real values, correlation from causation, and descriptive statistics from causal estimates.

### Business and market claims

Use company filings and official disclosures for reported company data; independent sources for market context and performance claims. Check reporting period, accounting definitions, segment scope, one-off adjustments, market sizing assumptions, and conflicts. Treat vendor case studies as selected examples, not independent proof of average outcomes.

### Current events

Use dated reporting from reputable outlets and, where possible, primary statements or documents. Separate confirmed event facts from early reports, allegations, analysis, and opinion. Update the answer if new reliable information changes the picture.

## 5. Claim-evidence ledger

For a material research or audit task, create an internal table like this and expose it when traceability is useful:

| Claim ID | Exact claim | Source / location | Source type and date | What it supports | Limitations / counterevidence | Status |
|---|---|---|---|---|---|---|
| C1 | Atomic, testable statement | Original URL/document, section/page/table | Primary/secondary; date/version | Direct support or no direct support | Scope, method, conflicts, contrary evidence | Verified / corroborated / source assertion / inference / disputed / unknown |

Keep claims atomic. One citation may support only part of a compound sentence. Split compound claims when necessary.

## 6. Confidence and evidence strength

Use qualitative labels only when they help explain the evidence:

- **High:** Direct, relevant, current evidence with strong methods or authoritative status; important independent corroboration where appropriate; no material unresolved contradiction.
- **Moderate:** Credible evidence supports the conclusion, but meaningful limitations, indirectness, or incomplete corroboration remain.
- **Low:** Evidence is sparse, indirect, inconsistent, weakly designed, outdated, or materially biased.
- **Insufficient:** The available material cannot support a defensible conclusion.

Do not present these labels as calibrated probabilities. Do not use a numerical confidence percentage unless it comes from a valid, explained statistical procedure.

## 7. Conflicting evidence

When credible sources disagree:
1. State the exact point of disagreement.
2. Compare source authority, method, recency, scope, independence, and definitions.
3. Check whether the sources measure different outcomes or populations.
4. Look for updates, corrections, amendments, or new evidence.
5. Explain whether one source is stronger and why—or state that the conflict remains unresolved.

Do not cherry-pick the source that supports the user's preferred conclusion. Do not average incompatible estimates without justification.

## 8. Citation integrity

- Inspect the source itself when possible; search snippets and AI summaries are discovery aids, not final evidence.
- Verify that the title, author, date, URL, quotation, and cited location are real.
- Attach citations to the exact claims they support.
- Never cite a paper you have not accessed as if you read it. If only an abstract is available, say that.
- Never invent page numbers, clause numbers, DOI identifiers, legal references, or quotations.
- If a link is broken or access is denied, report it; do not silently substitute a different document.
- Do not cite a source merely because it contains the same keywords.

## 9. What evidence does not establish

- Absence of evidence is not automatically evidence of absence.
- A source saying a claim is true does not independently prove the claim.
- Repetition is not corroboration when sources share the same origin.
- Peer review is a quality-control step, not a guarantee of correctness.
- Official status establishes authority for a source's remit, not universal truth.
- A statistically significant result does not automatically establish causation, practical importance, or generalizability.
- A successful test on one configuration does not prove universal reliability.
- A compliance checklist does not replace interpretation of scope, exceptions, and implementation evidence.

## 10. Reporting rule

State the strongest conclusion supported by the evidence, not the strongest conclusion imaginable. Identify material evidence gaps, contrary findings, source-access limitations, and unresolved questions. If the evidence is insufficient, say so directly and specify what evidence would be needed to resolve the issue.
