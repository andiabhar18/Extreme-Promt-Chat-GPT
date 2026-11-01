# Changelog

## 1.4.3

- Added the Structured Clarification UI Protocol to Prompt Validation for collecting essential missing information through labeled text inputs when supported by the active host.
- Added compact forms for multiple independent required fields when grouping is useful; retained conversational clarification when a form would add friction.
- Added explicit control semantics: checkboxes for multi-select/independent boolean choices and radio buttons or single-select dropdowns for mutually exclusive choices.
- Added rules to inspect conversation and supplied files before asking, keep optional fields optional, validate entered values against known rules, and resume the original task after clarification.
- Added data-minimization safeguards, including requesting NIM/student ID only when required by the requested deliverable.
- Added plain-text fill-in templates as a transparent fallback when interactive controls are unavailable; package metadata does not claim to create unsupported host UI.
- Added clarification UI acceptance tests to Prompt Validation, inter-skill orchestration, and Runtime Test Protocol matrices.
- Updated Prompt Master orchestration, setup guidance, README, both manifests, and release metadata.
- Retained all v1.4.2 orchestration, Automatic heavy-task default, validation, capacity optimization, Humanizer, and upstream copyright/license assets.

## 1.4.2

- Made Prompt Master the explicit inter-skill orchestrator with clear role ownership for Prompt Validation, Adaptive Execution, Evidence Standards, Critical Audit, Humanizer, file ingestion, and Runtime Test Protocol.
- Added a default orchestration sequence, relevance rules, duplicate-audit avoidance, truthful skill-status reporting, and internal fallback behavior when a specialist skill is unavailable.
- Changed Heavy-task execution to Automatic Intelligence Execution by default; the A/B/C selector is shown only when the user asks to choose/compare modes or explicitly requests a non-default mode.
- Retained Controlled Professional Execution with explicit approval and Hybrid Adaptive Execution with meaningful checkpoints.
- Added the Runtime Test Protocol skill for static package validation, live host behavior tests, implicit invocation, inter-skill orchestration, Adaptive Execution, Humanizer fidelity, and regression checks.
- Added an inter-skill orchestration test matrix and a runtime test matrix with PASS, FAIL, BLOCKED, and NOT TESTED outcomes.
- Updated Adaptive Execution, Prompt Validation, setup guidance, root metadata, manifests, README, and release notes.
- Retained the v1.4.1 Prompt Validation gates, capacity-aware heavy-task prompt optimization, project-wide audit, Humanizer 3.1.0, academic review, file-ingestion workflow, and upstream copyright/license assets.
- Clarified that static package checks do not prove live host routing or direct skill invocation.

## 1.4.1

- Added the Prompt Validation skill as a cross-cutting preflight for every actionable prompt, including short instructions, follow-ups, prompt-only requests, and file/data tasks.
- Added per-prompt validation of task intent, scope, constraints, source provenance, data integrity, completeness, schema, units, dates, duplicates, missing values, contradictions, and acceptance criteria where relevant.
- Added validation gates with PASS, PASS WITH LIMITATIONS, or BLOCKED outcomes; material blockers require correction or a focused clarification rather than silent guessing.
- Added capacity-aware prompt optimization for heavy tasks: distinguish input limits, context windows, and output limits; use current verified limits only when available; estimate rather than fabricate when not; preserve safe headroom for context, tools, and output.
- Added rules to consolidate relevant instructions and context, remove redundancy, avoid irrelevant padding, reference large files through supported file tools, and split oversized work into coherent validated stages.
- Added mandatory validation after each execution prompt/chunk and before advancing to the next stage.
- Added a separate project-wide final audit to reconcile source data, claims, calculations, citations, units, dates, cross-section consistency, omissions, duplicates, requirements coverage, and actual completion.
- Added a Prompt Validation test matrix and updated manifests, README, onboarding, discovery metadata, and release notes.
- Retained all 1.4.0 adaptive modes, mode switching, staged long-form workflow, checkpoints, Humanizer 3.1.0, academic review, and file-ingestion guidance.
- Clarified that prompt optimization cannot expose or override hidden platform limits, increase quotas, or guarantee that a prompt near a theoretical maximum will execute without truncation.

## 1.4.0

- Added the Adaptive Execution skill for heavy, complex, multi-stage, and long-form tasks.
- Added a heavy-task-only execution selector with Automatic Intelligence Execution, Controlled Professional Execution, and Hybrid Adaptive Execution.
- Kept light and ordinary medium tasks on the existing direct-execution path without an unnecessary mode prompt.
- Added mode persistence within the current project conversation and user-directed mode switching at any stage.
- Added long-form planning with chapter/section outlines, approximate word allocation, staged drafting, consistency checks, and honest target-completion reporting.
- Added project progress summaries and conversation-based resume checkpoints for output, context, or usage interruptions.
- Added safeguards against claiming background execution, cross-chat persistent storage, or capabilities the Skills-only package does not provide.
- Updated manifests, onboarding, discovery metadata, README, and release notes while retaining Prompt Master, Humanizer, academic review, evidence verification, and file-ingestion workflows.

## 1.3.0

- Added the Humanizer 3.1.0 skill for automatic prose refinement in ChatGPT-compatible skill hosts.
- Preserved the upstream Humanizer `SKILL.md` verbatim as `UPSTREAM-SKILL.md`.
- Preserved the upstream MIT `LICENSE` verbatim, including `Copyright (c) 2025 Siqi Chen`.
- Adapted only the active Humanizer discovery description and added ChatGPT/Codex skill metadata.
- Integrated Humanizer into Prompt Master's final writing workflow after factual verification.
- Added safeguards to preserve facts, claims, citations, caveats, uncertainty, writer voice, code, data, formulas, and exact quotations.
- Clarified that Humanizer is not intended for AI-detector evasion.
- Added an automatic Humanizer test matrix and updated onboarding, manifests, and release notes.

## 1.2.6

- Optimized Prompt Master discovery metadata around user goals and actionable task categories rather than plugin-specific keywords.
- Explicitly covered terse prompts, detailed prompts, follow-ups, file-based tasks, and spoken/transcribed requests.
- Added skill-level `agents/openai.yaml` metadata with implicit invocation enabled for `CHAT` and `CODEX`.
- Aligned root agent metadata and both plugin manifests with the 1.2.6 release.
- Added a positive/negative live invocation test matrix.
- Clarified that implicit invocation is a host routing decision and cannot be forced by package metadata.
- Documented current ChatGPT Skills eligibility and product-surface limitations.
- Retained all v1.2.5 Mastery, academic review, verification, and file-ingestion workflows.

## 1.2.5

- Made Prompt Master an always-on internal mastery layer for every actionable request when the host loads the skill.
- Added a mandatory task cycle: understand, decompose, internally expand, clarify material gaps, select method, execute, verify, challenge, and report.
- Required short prompts to be expanded internally and detailed prompts to be audited for gaps, contradictions, and unsupported premises.
- Added selective clarification rules so users are not asked to rewrite prompts or answer unnecessary questionnaires.
- Added a default structured academic journal/article review workflow for short requests such as "Review this journal".
- Clarified that file extraction is preparation only and does not replace substantive review or verification.
- Updated onboarding, package descriptions, and release metadata.

## 1.2.4

- Added plan-neutral verification rules: free accounts receive the same task-appropriate evidence and audit standards.
- Added advance warnings for resource-intensive tasks without pretending to know exact remaining quota.
- Added explicit handling for platform caps, including honest partial-result reporting and resume checkpoints.
- Strengthened independent cross-checking of material claims.
- Clarified prompt mastery versus execution: execute when asked to execute; provide only prompt work when that is what was requested.
- Aligned README, plugin manifests, and release metadata.

## 1.2.3

- Set the developer metadata email to Andi Abhar's personal email.
- Documented Premium Portal and its office email separately as affiliation/contact information.
- Preserved the existing Nidhin Joseph Nelson copyright attribution and all source acknowledgements.

## 1.2.2

- Updated the developer name in both plugin manifests to Andi Abhar.
- Retained the existing office contact email.
- No changes to skill behavior, files, or runtime architecture.

## 1.2.1

- Added a portable Agent Plugins manifest and retained the Codex compatibility manifest.
- Added an onboarding skill.
- Added a default square SVG icon for the plugin listing and composer.
- Clarified that this release is Skills-only and does not ship an MCP server or MarkItDown runtime.
- Updated publication and release metadata.
- Preserved the existing Prompt Master and MarkItDown File Ingestion skills and their reference files.
