# Critical Audit, Red-Team Review, and Verification Protocol

Use this protocol for rigorous reviews of prompts, documents, strategies, reports, calculations, code, products, research, and operational processes.

## 1. Establish the audit basis

Record:
- Item under review and exact version/date.
- Intended purpose, audience, and decision the item supports.
- Scope of review and all files/pages/sections actually accessible.
- Applicable standard, guideline, rubric, specification, law, or policy, including edition, jurisdiction, and effective date.
- Review depth requested and any known exclusions.

If no reference standard exists, do not invent one. Evaluate against explicit requirements, sound domain practice, and the stated purpose; label the basis clearly.

## 2. Build an audit inventory

Decompose the artifact into:
- factual claims and cited sources;
- assumptions and definitions;
- arguments and inference chains;
- requirements and acceptance criteria;
- figures, formulas, tables, and datasets;
- design or implementation decisions;
- dependencies, permissions, and operational steps;
- risks, mitigations, and unresolved questions.

For large files, track inspected and uninspected sections. A partial review must be reported as partial.

## 3. Audit dimensions

Check each dimension that applies. Mark it not applicable only with a reason.

| Dimension | Questions |
|---|---|
| Factual accuracy | Are claims true, current, precise, and directly supported? |
| Source quality | Are sources authoritative for this claim, current, independent, and methodologically sound? |
| Citation integrity | Does each citation exist and support the exact statement? |
| Logic | Do premises support conclusions? Are there contradictions, non sequiturs, circular claims, or equivocation? |
| Assumptions | Which premises are hidden, untested, or implausible? How sensitive is the result to them? |
| Counterevidence | What is the strongest reasonable argument or evidence against the conclusion? |
| Completeness | Are material requirements, edge cases, stakeholders, alternatives, and failure modes omitted? |
| Quantitative integrity | Do formulas, units, dates, denominators, totals, and calculations reconcile? |
| Methodology | Is the method suitable for the question? Are bias, confounding, sampling, and uncertainty addressed? |
| Standards compliance | Is the correct standard/version applied? Is every relevant requirement evidenced? |
| Feasibility | Are time, cost, people, technology, data, and dependencies realistic? |
| Security and safety | Are permissions, privacy, abuse cases, failure handling, and irreversible actions controlled? |
| Clarity and usability | Can the intended audience interpret and execute the artifact without ambiguity? |
| Internal consistency | Do terms, figures, dates, conclusions, and recommendations agree across sections? |

## 4. Adversarial tests

Apply relevant tests rather than mechanically forcing every test onto every task:

1. **Falsification:** What evidence would show the main claim is wrong? Has that evidence been sought?
2. **Counterexample:** Is there a credible case where the stated rule or conclusion fails?
3. **Alternative hypothesis:** Could another explanation account for the same observations?
4. **Boundary condition:** Where does the conclusion stop applying?
5. **Base-rate check:** Is a vivid example being mistaken for the typical case?
6. **Causal check:** Are correlation, sequence, mechanism, and causation being conflated?
7. **Selection check:** Are missing cases, survivorship bias, cherry-picked samples, or publication bias distorting the result?
8. **Definition check:** Are key terms used consistently and operationally defined?
9. **Version check:** Does the conclusion depend on an outdated policy, model, API, dataset, or standard?
10. **Incentive check:** Does a source or author have a reason to frame the result selectively?
11. **Reproducibility check:** Could another reviewer repeat the calculation, query, test, or method?
12. **Decision reversal check:** What plausible new evidence would change the recommendation?

## 5. Findings and severity

Use the following severity levels consistently:

- **Critical:** The central conclusion or deliverable is invalid, or the defect creates severe legal, safety, security, or operational exposure.
- **High:** A material requirement is violated, the decision could change, or a substantial failure is likely.
- **Medium:** A meaningful gap, inconsistency, or risk causes rework or weakens reliability but does not invalidate the entire deliverable.
- **Low:** A limited defect with small impact.
- **Observation:** A defensible improvement or preference that is not a demonstrated defect.

### Finding template

```text
ID: [F-01]
Severity: [Critical / High / Medium / Low / Observation]
Location: [page / section / clause / cell / line / function / exact excerpt]
Finding: [precise defect]
Why it is wrong: [logic, evidence, technical rule, or requirement]
Evidence: [source, exact location, calculation, or reproducible result]
Impact: [consequence]
Correction: [specific action]
Confidence and limitation: [basis and unresolved issue]
```

Do not fabricate locations or evidence. If an exact line or page is unavailable, identify the section or say that the location could not be established.

## 6. Standards and guideline compliance matrix

First verify the correct issuing body, official document, version/edition, effective date, jurisdiction, and applicability. Then build:

| Requirement ID | Exact requirement and source location | Evidence in reviewed item | Status | Gap / rationale | Required correction |
|---|---|---|---|---|---|

Use only these statuses:
- **Compliant:** Sufficient evidence demonstrates the requirement is met.
- **Partially compliant:** Some elements are met, but one or more material elements are missing or weak.
- **Non-compliant:** Available evidence shows a requirement is not met.
- **Not assessable:** Evidence, scope, access, or applicability is insufficient to judge.

Do not treat silence as compliance. Do not mark an item non-compliant merely because evidence was not supplied; use Not assessable unless the requirement explicitly demands that evidence or the absence itself is a demonstrated failure. Separate mandatory rules from recommendations and explanatory notes.

## 7. Quantitative and technical audit

### Quantitative
- Recompute key totals and derived metrics independently.
- Check units, currency, time period, denominator, signs, rounding, and formula references.
- Reconcile subtotals to totals and cross-check repeated values across sections.
- Check sample selection, missing values, duplicates, outliers, data transformations, and uncertainty.
- Distinguish observed data, estimates, forecasts, and assumptions.

### Code and engineering
- Inspect the relevant code, configuration, interfaces, dependencies, and execution context.
- Identify reproducible defects and affected files/lines where possible.
- Run tests/build/lint/security checks only if tools and environment allow.
- Report the exact checks run, result, and environment. Static inspection is not execution testing.
- Do not claim a fix works unless the relevant behavior was verified.

### Documents and research
- Check references against the bibliography and in-text citations.
- Verify dates, names, units, quotations, definitions, and repeated figures.
- Distinguish a missing citation from a false claim; both may matter, but they are different findings.
- Check whether the cited standard or guideline is actually applicable.

## 8. Final review loop

Perform at least two conceptually separate passes for substantive audits:

**Pass 1 — Inspection:** Identify and document candidate findings with evidence.

**Pass 2 — Challenge:** Attempt to disprove each finding, test the main conclusion, look for omitted counterevidence, recheck locations and citations, and remove findings that are only preference or speculation.

Before finalizing:
- Ensure every Critical/High finding has clear evidence and a defensible impact statement.
- Ensure the most serious defects appear first.
- Check that recommendations actually address the stated defects.
- Reconcile findings with the overall verdict.
- State what was not inspected or not tested.
- State whether the artifact is ready, conditionally ready, or not ready—and define the conditions.

This is a disciplined error-reduction process, not a guarantee that every defect has been found.

## 9. Recommended audit report

```text
# Audit Report

## 1. Verdict
[Ready / Conditionally ready / Not ready, with one-sentence basis]

## 2. Scope and basis
[What was inspected; version/date; applicable standards; exclusions]

## 3. Critical and high findings
[Prioritized findings with exact evidence and corrections]

## 4. Medium and low findings
[Remaining material defects]

## 5. Compliance matrix
[Only if a formal standard or guideline applies]

## 6. Counterarguments and unresolved risks
[Strongest counterevidence, boundary conditions, open questions]

## 7. Verification record
[Checks actually performed and results; checks not performed]

## 8. Required corrections and acceptance criteria
[Ordered actions that would change the verdict]
```

Keep the report proportionate to the artifact and task. Exhaustiveness means systematic coverage and honest disclosure of gaps—not padding the report with speculative criticisms.
