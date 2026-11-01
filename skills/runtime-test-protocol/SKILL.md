---
name: runtime-test-protocol
description: Use when a user asks to test, validate, diagnose, troubleshoot, or audit an Abhar Mastery installation, skill routing, implicit invocation, inter-skill coordination, execution modes, or release package. Separate static package checks from live host behavior and directly observed skill invocation. Never claim runtime tests passed unless they were actually run in a supported environment.
---

# Runtime Test Protocol — Abhar Mastery

## 1. Purpose

Provide a repeatable way to test whether an Abhar Mastery release is structurally valid and behaves as intended in a supported ChatGPT or Codex environment.

This skill is for plugin diagnostics and release acceptance. It is not a mandatory workflow for ordinary user tasks and must not be invoked merely because the user asks for research, writing, analysis, or document review.

## 2. Test layers

Keep these test layers separate:

1. **Static package validation:** inspect ZIP integrity, file inventory, JSON manifests, YAML metadata, skill frontmatter, version consistency, required references, links, and preserved third-party assets.
2. **Host availability and routing:** check whether the target product, account/workspace, and skill installation support the package. Test implicit invocation without `@mentions`.
3. **Behavioral conformance:** run harmless prompts and compare actual behavior with the expected orchestration, validation, execution, and humanization rules.
4. **Invocation observability:** record whether the host exposes a direct skill/tool invocation trace. If it does not, behavioral conformity is not proof that a specific skill was loaded.
5. **Regression and release acceptance:** verify that existing capabilities and third-party copyright/license assets remain intact after an update.

## 3. Static package checks

When package files are available:

- Verify ZIP integrity and absence of unexpected path traversal entries.
- Check required files and detect duplicate or missing paths.
- Parse every JSON manifest and YAML metadata file.
- Confirm all version fields and release notes match the target release.
- Validate skill frontmatter, names, descriptions, product scope, and implicit-invocation flags.
- Check that metadata descriptions fit documented length constraints where applicable.
- Verify that all referenced files exist and all documented paths match actual paths.
- Check that the Structured Clarification UI Protocol and its test matrix are present and linked from Prompt Validation, Prompt Master, and setup guidance.
- Compare protected third-party files against the supplied upstream version using cryptographic hashes when both are available.
- Confirm that licenses, copyright notices, and attribution are retained exactly when preservation is required.
- Check for accidental inclusion of platform-specific manifests that do not apply to the target package.

A successful static check proves package structure and metadata only. It does not prove that ChatGPT or Codex loads or executes the skills.

## 4. Live host routing tests

Where a supported host environment is available:

- Install or select the exact release under test.
- Run the positive and negative cases in `references/runtime-test-matrix.md`.
- Do not use `@` in positive implicit-invocation cases.
- Include short prompts, detailed prompts, follow-ups, file tasks, prose deliverables, and Heavy tasks.
- Test a greeting or casual acknowledgement as a negative control.
- Record the product surface, date, available account/workspace context if known, prompt, observed response, and any host-provided invocation trace.
- Do not infer account eligibility, model identity, or feature availability from assumptions. Record unknown values as unknown.

If no live host is available, mark live routing tests **NOT TESTED**. Do not substitute static metadata checks for live invocation tests.

## 5. Inter-skill orchestration tests

Verify the intended sequence:

- Prompt Master interprets and coordinates the task.
- Prompt Validation checks the actionable request and relevant inputs before execution.
- File ingestion is used only when supplied content requires it and the tool/converter is actually available.
- Adaptive Execution is selected for Heavy work and defaults to Automatic without a mode selector.
- Evidence Standards and Critical Audit are used when the task requires factual evidence or adversarial scrutiny.
- Humanizer is applied only after substantive verification and is followed by a fidelity check.
- Runtime Test Protocol is used only for plugin diagnostics.

A specialist may not appear in a host trace even if its behavior is emulated internally. Distinguish observed invocation from behavior that merely conforms to the skill's instructions.

## 6. Adaptive Execution tests

For a Heavy task with no mode preference:
- confirm that Automatic Intelligence Execution starts by default;
- confirm that no A/B/C selector blocks the task;
- confirm that material clarifications and authorization gates remain intact;
- confirm per-prompt and per-stage validation;
- confirm a separate project-wide audit after all stages are assembled;
- confirm honest checkpointing if a simulated or actual interruption occurs.

For explicit Controlled mode:
- confirm the plan is presented before substantive work;
- confirm the system waits for explicit approval.

For explicit Hybrid mode:
- confirm the system begins after a concise plan;
- confirm checkpoints occur only at meaningful milestones.

For Light/Medium tasks:
- confirm no Adaptive Execution selector or unnecessary heavy workflow appears.

## 7. Structured clarification UI tests

When the host supports interactive controls, test:
- one missing exact value produces a labeled text input rather than an unnecessarily broad questionnaire;
- multiple independent required fields are grouped into one compact form when useful;
- multi-select preferences use checkboxes;
- mutually exclusive choices use radio buttons or a single-select dropdown;
- known information is extracted from supplied files/context instead of being requested again;
- optional fields remain optional and only essential fields are required;
- invalid or missing values trigger a focused follow-up for the affected field;
- after submission, the original task resumes without requiring the user to repeat the prompt;
- unnecessary personal data is not requested.

When interactive controls are not supported, verify that the host provides a plain-text fill-in template and does not claim it is an interactive form. Mark live control rendering NOT TESTED if the host surface cannot be exercised.

## 8. Humanizer regression tests

- Confirm factual verification precedes the style pass.
- Confirm citations, claims, numbers, names, dates, caveats, uncertainty, and writer voice are preserved.
- Confirm code, data, formulas, exact quotations, and structured metadata are not rewritten.
- Confirm no AI-detector-evasion promise is made.
- Compare protected upstream Humanizer files and copyright/license text against the previous release.

## 9. Result statuses

Use explicit statuses:

- **PASS:** the specific test was actually run and met its acceptance criteria.
- **FAIL:** the test was run and did not meet its acceptance criteria.
- **BLOCKED:** the test could not proceed because a required environment, file, permission, or dependency was unavailable.
- **NOT TESTED:** no test was performed. Do not imply a result.

Report separate results for static package checks, live host routing, behavioral conformance, and invocation observability. Do not collapse them into a single unqualified "passed" badge.

## 10. Diagnostic report

A useful report includes:

- package name and exact version;
- package/file under test and test date;
- target surface (ChatGPT, Codex, or other) if known;
- static package results;
- live implicit-invocation results;
- inter-skill orchestration results;
- Adaptive Execution mode results;
- Humanizer regression results;
- direct invocation traces, if exposed;
- blocked and untested cases;
- defects, severity, evidence, and recommended remediation.

Do not claim background testing, hidden host access, persistent test state, or successful runtime invocation without direct evidence.

## 11. Platform and safety boundaries

- Do not bypass account eligibility, workspace settings, safety controls, permissions, usage limits, or tool restrictions.
- Do not use consequential external actions as test fixtures unless the user has explicitly authorized them and the host permits them.
- Prefer harmless, reversible prompts and test artifacts.
- If the user supplies a ZIP, inspect and test that exact package; do not substitute a different release.
- The Runtime Test Protocol can describe and organize tests, but it cannot itself force a host to load a skill or expose hidden routing traces.
