# Inter-Skill Orchestration Test Matrix — Abhar Mastery 1.4.2

This matrix tests the intended coordination contract. It does not prove that the host loaded each skill; actual routing is observable only when the host exposes invocation traces or equivalent diagnostics.

| Scenario | Expected coordinator behavior | Relevant specialist sequence |
|---|---|---|
| "What is 2 + 2?" | Keep the workflow proportionate; no heavy-task machinery. | Prompt Validation preflight → direct answer → output check. |
| "Review this journal" + article | Expand the short request into a structured academic review; inspect all accessible sections. | Prompt Validation → file ingestion if needed → Evidence Standards → Critical Audit → output validation → Humanizer for review prose → fidelity check. |
| "Analyze this spreadsheet" | Verify actual sheet/range coverage and data integrity before drawing conclusions. | Prompt Validation → file ingestion/host file tools → data analysis → relevant evidence/critical checks → output validation → Humanizer for narrative only. |
| Heavy research report, no mode specified | Start in Automatic Intelligence Execution; do not show A/B/C selector. | Prompt Validation → Adaptive Execution (Automatic default) → Evidence Standards → Critical Audit → stage gates → project-wide audit → Humanizer → final fidelity. |
| Heavy research report, user says "Controlled" | Present professionalized plan and wait for explicit approval. | Prompt Validation → Adaptive Execution (Controlled) → approval → staged work and validation → final audit. |
| Heavy research report, user says "Hybrid" | Present concise plan, start autonomously, checkpoint at meaningful milestones. | Prompt Validation → Adaptive Execution (Hybrid) → stage gates → checkpoints → final audit. |
| User asks "Test whether Abhar Mastery is working" | Run package/runtime diagnostics; do not treat diagnostics as normal task execution. | Runtime Test Protocol → static checks → supported live behavior tests → evidence-based report. |
| Human-readable email or report | Verify substance before style changes; preserve user voice and facts. | Prompt Validation → task execution/evidence checks → Humanizer → fidelity check. |
| Code or exact JSON output | Do not run prose humanization on code or structured content. | Prompt Validation → code/structured-data workflow → relevant tests → output integrity check. |
| Exact additional details are missing | Ask through labeled text inputs; group several independent fields compactly; do not ask for data already in supplied files. | Prompt Validation clarification UI → validate response → resume task. |
| User must choose between mutually exclusive options | Use radio buttons or a single-select dropdown; use checkboxes only for multi-select. | Prompt Validation choice semantics → Prompt Master resumes task. |
| Specialist skill is unavailable | Use an internal fallback only if adequate; disclose meaningful coverage limits. | Prompt Master fallback → report actual checks; never claim unavailable skill was loaded. |

## Acceptance criteria

- Prompt Master is the only primary coordinator; specialist skills retain clear role ownership.
- Prompt Validation is the first proportionate quality gate for every actionable task.
- Adaptive Execution is invoked for genuinely Heavy work, not Light/Medium work.
- Automatic Intelligence Execution is the default for Heavy work when no explicit preference exists.
- The A/B/C selector is not displayed by default.
- Controlled mode requires explicit user approval before substantive execution.
- Hybrid mode uses meaningful checkpoints without repeated approval prompts.
- Evidence Standards and Critical Audit are used when relevant, not indiscriminately.
- Humanizer runs only after substantive/factual verification and is followed by a fidelity check.
- File extraction is not represented as substantive review.
- If a skill is unavailable, the assistant does not claim it ran; a proportionate internal fallback may be used.
- Runtime tests distinguish static package validation, behavioral conformance, and directly observed host invocation.
