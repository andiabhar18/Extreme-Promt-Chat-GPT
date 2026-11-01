# Prompt Failure, Evidence, and Audit Patterns

60 recurring failure patterns that make prompts, research, analysis, and reviews unreliable. Use them as diagnostic checks, not as a rigid checklist that must be applied to every task.

## Task patterns

| # | Pattern | Failure example | Correction |
|---|---|---|---|
| 1 | Vague task verb | “Help me with my code.” | Name the operation, target, expected behavior, and output. |
| 2 | Unrelated tasks in one prompt | “Fix login and write a sales email.” | Split independent outcomes; combine only tasks with shared context and acceptance criteria. |
| 3 | No success criteria | “Make it better.” | Define observable completion conditions. |
| 4 | Over-permissive agent | “Do whatever it takes.” | Specify allowed actions, forbidden actions, and approval gates. |
| 5 | Emotion replacing diagnosis | “Everything is broken.” | Preserve useful context but identify the reproducible fault or desired outcome. |
| 6 | Build-the-whole-thing scope | “Build my entire app.” | Define a deliverable and sequence only when dependencies justify it. |
| 7 | Implicit reference | “Add the other thing we discussed.” | Restate essential requirements when the target context may not include prior discussion. |

## Context patterns

| # | Pattern | Failure example | Correction |
|---|---|---|---|
| 8 | Assumed prior knowledge | “Continue where we left off.” | Carry forward only relevant decisions and verify that the target session has them. |
| 9 | No project context | “Write a cover letter.” | Supply role, audience, relevant experience, constraints, and purpose. |
| 10 | Forgotten stack or decisions | New prompt contradicts the existing architecture. | Include current stack, versions, and decisions when the target lacks context. |
| 11 | Citation without source validation | “Cite only sources you are certain of.” | Inspect each source, verify that it exists and directly supports the claim, and label uncertainty. |
| 12 | Undefined audience | “Write something for users.” | Specify reader expertise, needs, and decision context. |
| 13 | Missing prior failures | Repeats an approach already shown to fail. | Include what was tried, observed result, and why it failed. |

## Format patterns

| # | Pattern | Failure example | Correction |
|---|---|---|---|
| 14 | Missing output format | “Explain this concept.” | Specify a usable structure and length when format matters. |
| 15 | Implicit length | “Write a summary.” | State the intended level of detail or length when material. |
| 16 | Missing domain lens | Specialized task with no relevant context. | Add the applicable analytical perspective without inventing credentials. |
| 17 | Vague aesthetic language | “Make it professional.” | Translate preferences into concrete visual or editorial criteria grounded in the brief. |
| 18 | Assuming negative prompts are supported | Adds a negative-prompt block to every image tool. | Use exclusions only when the selected model and workflow support them; otherwise express constraints naturally. |
| 19 | Wrong syntax for a target tool | Uses stale model flags or parameters. | Verify current syntax for the exact product/version or omit unsupported controls. |

## Scope patterns

| # | Pattern | Failure example | Correction |
|---|---|---|---|
| 20 | No scope boundary | “Fix my app.” | Name files, functions, components, and explicit exclusions where known. |
| 21 | Unverified stack constraints | Assumes a framework version or dependency. | Use confirmed project metadata or label assumptions. |
| 22 | No stop condition | Agent keeps expanding the task. | Define stop conditions, milestones, and review gates. |
| 23 | No file path for IDE AI | “Update the login function.” | Identify the actual path and symbol when known; do not invent paths. |
| 24 | Wrong template for tool | Chat prompt pasted into a code-editing agent. | Adapt the task brief to the target surface and its real capabilities. |
| 25 | Excessive context dump | Entire repository pasted without selection. | Provide relevant files, dependencies, and context; include more only when necessary. |

## Reasoning patterns

| # | Pattern | Failure example | Correction |
|---|---|---|---|
| 26 | No audit contract | “Which approach is better?” | Define criteria, assumptions, evidence, trade-offs, and verification. |
| 27 | Requesting hidden reasoning | “Show your chain of thought.” | Request conclusion, concise rationale, evidence, checks, and uncertainty. |
| 28 | Assuming cross-session memory | “You already know my project.” | Include essential context or verify available memory/context. |
| 29 | Contradicting prior work | New instructions ignore accepted architecture. | Carry forward verified decisions and flag conflicts. |
| 30 | No evidence standard | “Summarize what experts say.” | Define source types, date range, traceability, and how to report unknowns. |

## Agentic patterns

| # | Pattern | Failure example | Correction |
|---|---|---|---|
| 31 | No starting state | “Build me a REST API.” | State current repository, environment, installed dependencies, and known behavior. |
| 32 | No target state | “Add authentication.” | Define required endpoints, behavior, security properties, and acceptance tests. |
| 33 | Silent agent | No evidence of progress or completion. | Request meaningful milestones, blockers, changed files, and verification evidence. |
| 34 | Unrestricted filesystem | Agent edits unrelated files or secrets. | Set file scope and protect credentials/configuration. |
| 35 | No human review trigger | Agent makes consequential choices autonomously. | Require approval for destructive, external, costly, or irreversible actions. |
| 36 | Vague first turn | “Fix the auth bug.” | Front-load outcome, context, scope, constraints, permissions, and acceptance criteria. |
| 37 | Context rot | Old assumptions persist through a long task. | Reconcile current decisions, constraints, failures, and target state; compact or restart only when useful. |

## Evidence and source-integrity patterns

| # | Pattern | Failure example | Correction |
|---|---|---|---|
| 38 | Search snippet treated as proof | Cites the search preview without opening the source. | Inspect the actual page/document and verify the exact supporting passage. |
| 39 | Single-source dependency | Major conclusion rests on one uncorroborated source. | Seek independent corroboration where feasible and disclose when unavailable. |
| 40 | Reposts mistaken for corroboration | Five sites repeat one press release. | Trace sources to their origin and assess independence. |
| 41 | Stale evidence | Old policy, API, or study used for a current claim. | Check publication/update/effective dates, version, amendments, and superseding sources. |
| 42 | Conflicting evidence suppressed | Only favorable sources are reported. | State the disagreement and compare source quality, scope, and methods. |
| 43 | Source authority assumed | Official or famous source treated as infallible. | Evaluate directness, method, scope, incentives, and limitations. |
| 44 | Citation mismatch | Citation exists but does not support the sentence. | Match each citation to the exact atomic claim it supports. |
| 45 | Missing provenance | Unattributed chart, quote, or statistic is repeated. | Trace original author, dataset, document, date, and context—or mark unverified. |

## Critical-analysis patterns

| # | Pattern | Failure example | Correction |
|---|---|---|---|
| 46 | Fact/inference conflation | An interpretation is stated as an observed fact. | Label source assertion, fact, inference, assumption, and hypothesis separately. |
| 47 | Correlation/causation error | “X and Y move together, so X causes Y.” | Check design, confounders, temporal order, mechanism, and alternative causes. |
| 48 | Base-rate neglect | One vivid case is treated as typical. | Compare the case with relevant population rates and denominators. |
| 49 | Selection or survivorship bias | Only successful examples are examined. | Search for failures, missing cases, selection mechanisms, and denominator effects. |
| 50 | No counterevidence search | Only supporting evidence is collected. | Deliberately seek the strongest credible counterargument and disconfirming evidence. |
| 51 | Confirmation bias | Search terms and source selection presuppose the desired answer. | Frame neutral queries and test competing hypotheses. |
| 52 | False precision | Unsupported percentages or confidence scores are reported. | Use exact numbers only when a valid method and source support them; otherwise use calibrated qualitative language. |

## Audit and verification patterns

| # | Pattern | Failure example | Correction |
|---|---|---|---|
| 53 | No standard/version | “Check compliance” without identifying the rule. | Identify issuing body, edition, jurisdiction, effective date, and applicability. |
| 54 | Wrong jurisdiction | Applies a rule from another country or state. | Verify where and to whom the rule applies. |
| 55 | Missing applicability analysis | A standard is cited without checking whether it covers the case. | Assess scope, exceptions, transition rules, and binding status. |
| 56 | Audit finding without location | “This section is wrong” with no pinpoint. | Give exact page, clause, cell, line, function, or section when available. |
| 57 | Severity inflation | Preferences are called critical defects. | Separate demonstrated defects from observations and use consistent severity definitions. |
| 58 | Test claimed but not run | “All tests pass” without execution evidence. | Distinguish static review from executed tests and report actual commands/results. |
| 59 | Calculation not independently checked | Totals are copied without recomputation. | Recalculate important figures and inspect units, denominators, rounding, and formula references. |
| 60 | Unknown treated as false (or true) | “No source found, therefore false.” | Use unknown/unverified unless direct evidence establishes or refutes the claim. |

## Use rule

These patterns are diagnostic aids, not a scorecard. Apply only relevant checks. A rigorous review should identify material defects with evidence, avoid invented criticism, and state what could not be verified.
