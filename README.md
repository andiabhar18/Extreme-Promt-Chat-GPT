# Abhar Mastery promt extrem — 1.2.0

An evidence-first prompt-engineering and critical-audit plugin for ChatGPT-compatible plugin packaging.

## Included capabilities

- Prompt engineering, prompt repair, and cross-platform prompt adaptation.
- Evidence appraisal, source-quality checks, fact-checking, and explicit uncertainty reporting.
- Critical audit, adversarial review, red-team analysis, and standards-compliance checks.
- MarkItDown-first file-ingestion workflow for content-focused reading and analysis.
- Visual-style exception: when the user explicitly asks to preserve, reproduce, or evaluate a file's visual design or layout, inspect the original visual file rather than treating Markdown as the primary representation.

## Install a private copy in ChatGPT

1. Open ChatGPT using the account that should own the plugin.
2. Open the plugin creation/import workflow available to that account.
3. Upload this ZIP as a private plugin package and complete the save/install steps shown by ChatGPT.
4. Open the plugin and test it with a document or prompt-review task.

Availability of plugin creation/import can depend on the user's ChatGPT environment and account. If the account cannot import plugin ZIPs, create a Project and upload the files under `skills/prompt-master/` and `skills/markitdown-file-ingestion/` as project reference material, then add the relevant instructions to Project instructions. That fallback is not a plugin installation.

## MarkItDown runtime limitation

This package includes MarkItDown integration instructions, not the MarkItDown Python runtime or a connected MCP server. The skill must not claim MarkItDown conversion occurred unless a real converter is connected and actually ran. If it is unavailable, use the host's supported file-reading tools and accurately identify that fallback. Do not expose an unauthenticated MarkItDown MCP server to the public Internet.

## Package identity

- Display name: Abhar Mastery promt extrem
- Internal package name: prompt-master (retained for continuity with the existing plugin)
- Version: 1.2.0
- Visibility on initial creation: private, subject to the host's installation flow
