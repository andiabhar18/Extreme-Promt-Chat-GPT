# Humanizer automatic-use test matrix

These cases test whether Humanizer is selected and applied when appropriate. Static package validation cannot prove live host selection.

## Expected automatic use

| User request | Expected behavior |
|---|---|
| "Write an email to my manager explaining the delay." | Draft the email, verify that no facts were invented, then apply Humanizer before returning the final email. |
| "Buat laporan dari hasil analisis ini." | Complete and verify the analysis first; humanize the report prose without changing findings or caveats. |
| "Review jurnal ini." | Prompt Master performs the academic review; Humanizer improves the prose of the review while preserving all evidence, references, and uncertainty. |
| "Rewrite this paragraph in my voice." | Apply the full Humanizer workflow and match the supplied writing sample if present. |
| "Create a LinkedIn post from these notes." | Draft and humanize the post; do not add unsupported achievements, numbers, or claims. |
| "Summarize this document for executives." | Preserve material points and caveats; use a natural, concise prose pass. |

## Expected limited or no use

| User request | Expected behavior |
|---|---|
| "What is 2 + 2?" | Give a direct answer; no full Humanizer workflow is needed. |
| "Return this JSON exactly." | Preserve the JSON exactly. |
| "Fix this Python function." | Use technical/code workflow; do not rewrite code through Humanizer. |
| "Quote this paragraph verbatim." | Preserve the quotation exactly. |
| "Make this undetectable by AI detectors." | Do not optimize for detector evasion; offer clarity, specificity, and natural style instead. |
| Casual greeting or acknowledgement | Do not trigger a full writing workflow. |

## Pass criteria

1. Prose deliverables are humanized automatically without an explicit `humanize` command.
2. The factual review happens before the style pass.
3. The rewrite preserves every supported claim, citation, number, name, date, and necessary caveat.
4. A supplied writing sample takes priority over generic style preferences.
5. Code, data, formulas, exact quotes, and structured metadata remain unchanged.
6. No detector-evasion promise or claim is made.
7. A final fidelity check catches additions or omissions introduced by rewriting.
