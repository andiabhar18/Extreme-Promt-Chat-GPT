# Humanizer for Abhar Mastery

Humanizer is integrated into Abhar Mastery v1.3.0 as an automatically selectable skill for ChatGPT-compatible skill hosts.

## Automatic use

Users do not need to type `@Humanizer` or ask for a humanization pass. When this skill is available and selected by the host, use it automatically for prose deliverables intended for human readers, including emails, reports, essays, articles, posts, proposals, explanations, and other documents.

Prompt Master also directs the final prose deliverable through Humanizer after the content has been checked. This keeps the style pass connected to the verified task rather than treating it as a separate request.

## What it does

- Checks the 26 writing patterns in the upstream Humanizer skill.
- Rewrites formulaic AI-sounding prose in a more specific, natural voice.
- Preserves supported facts, claims, names, numbers, dates, quotations, citations, and the writer's intent.
- Matches a supplied writing sample when available.
- Keeps code, data, formulas, commands, paths, YAML metadata, and link targets unchanged.
- Avoids inventing details when source material is incomplete.
- Does not aim to bypass AI detectors. The goal is clear, specific writing for human readers.

## Integration boundaries

Humanizer is a style and prose-quality pass, not a factual verification system. In Abhar Mastery, factual and evidentiary checks happen first. Humanizer must not remove necessary uncertainty, safety notices, legal qualifications, source limitations, or caveats merely because they resemble a style pattern. A final fidelity check follows the rewrite.

Do not apply the prose rewrite to code, raw data, mathematical formulas, exact quotations, citations, structured metadata, or text the user explicitly asks to preserve verbatim. For ordinary short answers, use a proportionate style check rather than exposing an unnecessary draft-and-critique sequence.

The host decides whether the skill is loaded. `allow_implicit_invocation: true` permits automatic selection where supported but cannot force the host to load it on every turn or override account and product eligibility.

## Upstream attribution and license

This integration is based on Humanizer 3.1.0 by Siqi Chen (GitHub: `blader/humanizer`).

- Upstream: https://github.com/blader/humanizer
- Copyright: Copyright (c) 2025 Siqi Chen
- License: MIT
- The upstream `SKILL.md` is retained unchanged at `UPSTREAM-SKILL.md`.
- The upstream MIT license is retained unchanged at `LICENSE`.
- The active `SKILL.md` changes only the discovery description for automatic ChatGPT use; the instruction body is unchanged.
