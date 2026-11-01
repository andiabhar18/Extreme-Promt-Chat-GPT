# Implicit Invocation Test Matrix — Abhar Mastery 1.2.6

Purpose: evaluate whether the Prompt Master metadata clearly describes when the skill should be selected. These are test cases for a live host, not proof that the host will always invoke the skill.

## Positive cases — should be considered a match without @mention

| User input | Expected selection and behavior |
|---|---|
| "Review jurnal ini" + attached research article | Select Prompt Master; expand into the default academic review workflow and inspect all accessible article sections. |
| "Apakah klaim ini benar?" | Select Prompt Master; identify the claim, verify sources, seek counterevidence, and report uncertainty. |
| "Buat laporan dari file ini" + spreadsheet | Select Prompt Master and file-ingestion workflow; inspect data, derive findings, and validate calculations. |
| "Ringkas dokumen ini dalam 5 poin" | Select Prompt Master; honor the five-point constraint and verify coverage. |
| "Terjemahkan ini ke bahasa Inggris" | Select Prompt Master; preserve meaning, terminology, and requested tone. |
| "Perbaiki kode ini" + code | Select Prompt Master; inspect context, fix the issue, and run available checks or state why tests were not run. |
| "Bandingkan dua proposal ini" + two files | Select Prompt Master; define comparable criteria, inspect both files, and separate evidence from judgment. |
| "Apa kelemahan argumen saya?" | Select Prompt Master; challenge the argument fairly and correct only demonstrable weaknesses. |
| "Buat rencana implementasi" | Select Prompt Master; clarify outcome, constraints, dependencies, risks, and milestones as needed. |
| Spoken: "Tolong cek apakah kesimpulan penelitian ini sesuai datanya" | Select Prompt Master; treat the spoken/transcribed request like a typed request and confirm uncertain critical transcription. |
| Follow-up: "Sekarang cek referensinya juga" | Continue the same Mastery workflow and add reference verification without losing prior constraints. |
| A detailed multi-paragraph instruction | Select Prompt Master; audit completeness, ambiguity, conflicts, and acceptance criteria before execution. |

## Negative cases — no task-level selection is needed

| User input | Expected behavior |
|---|---|
| "Halo" | Respond naturally; no task workflow is required. |
| "Terima kasih" | Acknowledge briefly; no task workflow is required. |
| "Oke" / "Baik" | Treat as acknowledgement unless context clearly makes it an instruction to proceed. |
| Casual small talk with no requested work | Respond conversationally; do not manufacture a task. |

## Pass criteria

A live host test passes when:
1. Most positive cases select Prompt Master without an `@mention`.
2. Short and detailed prompts both select the skill when they describe actionable work.
3. Follow-ups preserve the existing task context.
4. Greetings and non-task small talk do not trigger unnecessary heavy workflows.
5. The skill executes the requested work rather than merely rewriting the prompt.
6. The model does not claim invocation when the host did not load the skill.

## What package validation cannot prove

Static validation can check that the description, manifests, product scope, and implicit-invocation flag are present and well-formed. It cannot measure the host's routing decisions. Actual selection rates require testing in the target ChatGPT or Codex environment with the skill installed and available.
