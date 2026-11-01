# Abhar Mastery Prompt Extreme — 1.4.3

An evidence-first, Skills-only plugin for task mastery, per-prompt data validation, capacity-aware execution prompts for heavy work, adaptive execution modes, staged long-form delivery, automatic prose humanization, academic review, and project-wide verification whenever its skills are available to the host.

## What's new in 1.4.3: Structured Clarification UI

This release improves how Abhar Mastery collects essential missing information. When the task requires exact additional details and the active host supports interactive controls, it uses labeled text inputs and appropriate choice controls rather than relying only on free-form questions.

### Text inputs for exact details

Use clearly labeled fields for values such as name, faculty, study program, institution, course, lecturer, academic year, date, version, or word count. For a task requiring several independent details, collect them in one compact form when that is easier for the user.

Example for an academic cover page: name, faculty, study program, and only other fields required by the requested format. NIM/student ID is requested only when necessary; it is not an automatic field.

### Checkboxes and single-choice controls

- Checkboxes are used for multi-select preferences and independent boolean options.
- Radio buttons or a single-select dropdown are used when exactly one option must be selected.
- An "Other" choice may include a short text field.
- Optional fields remain optional; required fields are marked clearly.

### Better clarification discipline

Before asking, the system checks the conversation and supplied files for values already available. It asks only for material missing information, validates entered values against known rules, and resumes the original task after the user responds. It avoids oversized forms and unnecessary personal-data collection.

Interactive rendering depends on the active host. If controls are unavailable, the plugin provides a plain-text fill-in template and does not pretend that it is interactive.

## What's new in 1.4.2: Inter-Skill Orchestration & Automatic Execution Default

This release makes Prompt Master the explicit coordinator of all relevant Abhar Mastery skills, changes Heavy-task execution to Automatic by default, and adds a Runtime Test Protocol.

### Inter-Skill Orchestration

Prompt Master coordinates the skill sequence and role ownership:

1. Prompt Validation — first preflight and validation authority for every actionable prompt.
2. Prompt Master — primary coordinator for intent, task decomposition, methods, and final synthesis.
3. MarkItDown File Ingestion or supported host file tools — preparation of supplied files when needed.
4. Adaptive Execution — Heavy-task staging, prompt optimization, checkpoints, and project-wide audit.
5. Evidence Standards and Critical Audit — factual corroboration and adversarial review when relevant.
6. Humanizer — prose refinement only after substantive verification.
7. Final fidelity and project-wide validation — confirm that the assembled result still meets the original task.

Only relevant skills are used. The system avoids duplicate audits, uses an internal fallback when a specialist skill is unavailable, and never claims an unloaded skill ran. Runtime Test Protocol is reserved for plugin diagnostics.

### Automatic Execution Default

Adaptive Execution remains reserved for genuinely Heavy tasks. **Automatic Intelligence Execution is now the default** when the user has not selected a project mode.

- Heavy tasks begin in Automatic mode without an A/B/C selector.
- Controlled Professional Execution remains available when explicitly requested and waits for approval before substantive work.
- Hybrid Adaptive Execution remains available when explicitly requested and uses meaningful checkpoints.
- Light and ordinary Medium tasks continue directly without Adaptive Execution.
- The selected mode persists within the current project conversation.

This removes unnecessary setup friction while preserving user control and all safety, clarification, and authorization gates.

### Runtime Test Protocol

A new diagnostic skill separates:
- static ZIP/manifest/YAML validation;
- live host routing and implicit-invocation tests;
- behavioral conformance;
- directly observed invocation traces;
- Humanizer and release regression tests.

Static package validation is not represented as proof of runtime behavior. If the host does not expose invocation traces, the report must distinguish behavioral conformance from confirmed skill loading. Untested cases must be marked NOT TESTED.

## What's new in 1.4.1: Prompt Capacity Optimization & Validation

This release adds a cross-cutting Prompt Validation skill and strengthens Adaptive Execution for heavy work.

### Per-prompt validation

Every actionable prompt receives a proportionate preflight when the skill is loaded. It checks:

- intent, scope, audience, constraints, exclusions, and completion criteria;
- context continuity and contradictions with earlier project decisions;
- source provenance, file accessibility, document coverage, and version;
- data integrity, schema, types, units, dates, missing values, duplicates, and totals where relevant;
- evidence and citation support, including what cannot be independently verified;
- feasibility, available tools, permissions, and platform constraints.

Every generated execution prompt and every stage output is validated before the workflow advances. Material blockers are corrected or clarified; they are not silently guessed. Routine checks remain internal, while material warnings are disclosed.

### Prompt Capacity Optimization for heavy tasks

For each heavy-task execution prompt, the plugin consolidates all high-value instructions and context, removes redundancy, and uses the largest safely useful portion of the active capacity. It preserves objectives, scope, constraints, data definitions, evidence standards, source restrictions, output criteria, and safety boundaries.

The optimizer distinguishes input/prompt capacity, total context window, and maximum output. It uses exact limits only when current and applicable to the actual ChatGPT/API surface. If exact remaining capacity is not exposed, it estimates conservatively and never invents an exact maximum or utilization percentage. It reserves headroom for conversation history, files, tool results, and the response. It does not pad prompts with irrelevant text or force a theoretical 100% fill.

When large inputs cannot safely fit, the plugin uses supported file tools or splits work into coherent stages with a compact, validated project-state handoff. It does not silently truncate or omit data.

### Project-wide final validation

Per-prompt and per-stage validation are necessary but not sufficient. After all work is assembled, the plugin runs a separate second-pass audit across the complete project, reconciling original requirements, input inventory, source data, definitions, units, dates, calculations, citations, cross-section consistency, completeness, and measurable targets.

Final status is one of:
- **PASS** — material requirements met within the inspected scope;
- **PASS WITH LIMITATIONS** — usable output with disclosed limitations or unverified elements;
- **INCOMPLETE / BLOCKED** — required work or a material validation gate remains unfinished.

## Adaptive Execution modes

Adaptive Execution is reserved for **Heavy tasks only**. Automatic Intelligence Execution is the default; the selector is not shown unless the user asks to choose/compare modes or explicitly requests a non-default mode.

- **Automatic Intelligence Execution (default):** internally expands the brief, optimizes prompts within safe capacity, selects methods/tools, validates each stage, and executes with minimal interruption.
- **Controlled Professional Execution (explicit choice):** presents the professionalized prompt, scope, methodology, capacity strategy, validation criteria, work plan, and deliverables; waits for user approval.
- **Hybrid Adaptive Execution (explicit choice):** begins autonomously, validates each prompt and stage, and provides checkpoints only at meaningful milestones or material decisions.

Users can switch modes during the current project. The selected mode persists within the current conversation unless changed.

## Long-form execution

For books, theses, dissertations, large reports, systematic reviews, or other extensive deliverables:

1. Check scope, constraints, data/source inventory, and feasibility.
2. Build the full outline and approximate chapter/section word allocation.
3. Plan research and evidence collection before drafting when needed.
4. Optimize and validate each stage prompt within safe capacity.
5. Draft in logical sections instead of forcing the whole deliverable into one response.
6. Validate each section before moving forward.
7. Reconcile definitions, terminology, data, citations, tables, figures, and conclusions across sections.
8. Run the separate project-wide final audit and report actual completion status.

A target such as 40,000 words is a project target, not a promise that one response can contain 40,000 words. If output, context, usage, or tool limits interrupt work, the plugin provides a resume checkpoint identifying completed work, the last completed section, validation status, open issues, and the next step.

**Checkpoint boundary:** this package has no hosted backend, background worker, or persistent project database. Progress is tracked in the current conversation. If a user starts a new chat, they must carry forward the checkpoint or relevant project files. The plugin must never claim it continued working in the background between turns.

## Universal implicit invocation

Users should not need to type `@Abhar Mastery`, mention the plugin name, or request "Deep Audit". Prompt Master and Prompt Validation are designed to be considered for actionable requests based on the user's goal, where the host supports implicit skill invocation.

- Short prompts are expanded internally and validated proportionately.
- Detailed prompts are checked for gaps, conflicts, feasibility, and data integrity.
- Follow-ups preserve established project context and are revalidated after material changes.
- File-based tasks check actual accessible coverage rather than assuming all uploaded content was read.
- Adaptive Execution is reserved for heavy, multi-stage, resource-intensive, or long-form work—not ordinary everyday requests.

Implicit invocation is a host routing decision. Metadata permits automatic selection but cannot force the host to load a skill or override account eligibility, workspace settings, product availability, safety controls, or tool access.

## Included skills

- `skills/prompt-master/` — task mastery, prompt engineering, evidence appraisal, fact-checking, academic review, critical audits, and verification.
- `skills/prompt-validation/` — per-prompt instruction/data preflight, output validation, capacity-aware prompt checks, and project-wide final audit.
- `skills/adaptive-execution/` — heavy-task classification, Automatic default, explicit Controlled/Hybrid modes, prompt capacity optimization, stage validation, project-wide audit, and resume checkpoints.
- `skills/humanizer/` — automatic prose humanization based on 26 patterns, with fact and voice preservation.
- `skills/runtime-test-protocol/` — diagnostic workflow and runtime test matrix for release and host behavior.
- `skills/markitdown-file-ingestion/` — conditional file-ingestion workflow. It uses MarkItDown only if a real converter is connected; otherwise the host's supported file-reading tools are used.
- `skills/runtime-test-protocol/` — static package checks, live host behavior tests, interactive clarification tests, invocation observability, and regression diagnostics.
- `skills/setup/` — onboarding, invocation, orchestration, and runtime boundaries.

## Humanizer boundaries

Humanizer is a style pass, not a fact-checker. The content must be verified first. It must not remove necessary uncertainty, source limitations, safety notices, legal qualifications, or caveats. It must not invent missing details. The objective is natural, specific writing for human readers, not detector evasion.

## Runtime architecture and availability

This is a Skills-only package. It does not include an MCP server, hosted backend, API connection, database, background worker, tokenizer service, hidden platform telemetry, or independent file-conversion service.

The host decides whether to load skills. `allow_implicit_invocation: true` allows automatic selection where supported but cannot guarantee selection on every turn. Skills availability differs by ChatGPT plan, workspace, and product surface. Do not assume a Skills-only package is available in every account without checking current product documentation.

The plugin cannot inspect, increase, bypass, or guarantee a user's remaining quota or exact remaining context. Prompt wording cannot expand platform limits. If a hard limit blocks work, it must disclose incomplete checks and provide a resume checkpoint.

## Package structure

- `plugin.json` — portable Agent Plugins manifest.
- `.codex-plugin/plugin.json` — Codex compatibility manifest.
- `agents/openai.yaml` — root presentation and implicit-invocation metadata.
- `skills/prompt-master/` — core task-mastery workflow, inter-skill orchestration protocol, and reference files.
- `skills/prompt-validation/` — cross-cutting prompt/data/output validation, structured clarification UI protocol, and test matrix.
- `skills/adaptive-execution/` — Heavy-task classification, Automatic default, explicit Controlled/Hybrid modes, prompt capacity, staged execution, and project audit.
- `skills/humanizer/` — active Humanizer skill, upstream copy, license, and test matrix.
- `skills/markitdown-file-ingestion/` — file-ingestion workflow and reference notes.
- `skills/runtime-test-protocol/` — static package checks, live host behavior tests, interactive clarification tests, invocation observability, and regression diagnostics.
- `skills/setup/` — onboarding instructions.
- `THIRD-PARTY-NOTICES.md` — upstream notices and license locations.

## Test and publish

1. Validate both manifests and the archive structure.
2. Test light and medium tasks: per-prompt checks should remain proportionate and no execution selector should appear.
3. Test heavy tasks without a mode preference: Automatic Intelligence Execution should begin by default without an A/B/C selector. Then separately test explicit Controlled and Hybrid requests.
4. Test prompt budget behavior with exact and unknown limits; verify no fabricated token counts, irrelevant padding, or unsafe 100% fill.
5. Test large source files: verify tool-based ingestion or coherent splitting, no silent truncation, and clear coverage reporting.
6. Test data validation for missing values, duplicates, inconsistent units, conflicting totals, and incomplete files.
7. Test per-stage validation and a separate project-wide audit that catches cross-stage contradictions and missing references.
8. Test mode switching, persistence, checkpoints, and honest partial-completion reporting.
9. Test inter-skill orchestration and fallback behavior using `skills/prompt-master/references/inter-skill-orchestration-test-matrix.md`.
10. Run Runtime Test Protocol checks using `skills/runtime-test-protocol/references/runtime-test-matrix.md`; distinguish static validation, behavioral conformance, and directly observed invocation traces.
11. Test structured clarification: exact values use labeled text inputs, multi-select uses checkboxes, one-of-many uses radio/select, known data is not requested again, and plain-text fallback is used if controls are unavailable.
12. Test short prompts, detailed prompts, follow-ups, file tasks, and prose deliverables without `@mentions`.
13. Test Humanizer and confirm factual verification occurs before style refinement and a final fidelity check follows it.
14. Test in a supported, eligible ChatGPT/Codex environment. Static package validation cannot prove live host routing.
15. For public distribution, use the current OpenAI Plugins/Skills submission workflow and complete its review requirements.

## Package identity

- Display name: Abhar Mastery Prompt Extreme
- Internal package name: `prompt-master`
- Package version: `1.4.2`
- Included upstream Humanizer version: `3.1.0`
- Developer: Andi Abhar
- Developer email: `andiabharanakselayar@gmail.com`
- Office affiliation: Premium Portal
- Office email: `009ownedby@premiumportal.id`
- Root package license: MIT
- Humanizer upstream license: MIT, with original copyright notice preserved

## Official references

- [OpenAI Skills and automatic activation](https://developers.openai.com/plugins/concepts/skills)
- [OpenAI build skills](https://developers.openai.com/plugins/build/skills)
- [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html)
- [Humanizer upstream repository](https://github.com/blader/humanizer)
- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
