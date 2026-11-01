# Runtime Test Matrix — Abhar Mastery 1.4.3

Use harmless test prompts. Record actual outputs and host-provided invocation traces when available. Do not infer skill loading from behavior alone.

| ID | Test input / setup | Expected behavior | Layer |
|---|---|---|---|
| RT-01 | Inspect release ZIP | ZIP opens; no corrupt entries; required files present. | Static |
| RT-02 | Parse both manifests and all YAML files | Valid JSON/YAML; package version consistent; metadata constraints satisfied. | Static |
| RT-03 | "What is 2 + 2?" without @mention | Proportionate answer; no heavy selector or unnecessary multi-skill workflow. | Live behavior |
| RT-04 | "Review this journal" with an accessible paper, no @mention | Short request is expanded; input coverage checked; evidence/methods/results reviewed; final prose humanized after verification. | Live behavior |
| RT-05 | "Analyze this spreadsheet" with a sample workbook | File/sheet coverage and data integrity checked before conclusions; extraction is not represented as full analysis. | Live behavior |
| RT-06 | Heavy research report with no mode preference | Automatic Intelligence Execution starts by default; no A/B/C selector. | Live behavior |
| RT-07 | Heavy task explicitly requests Controlled | Plan appears and system waits for approval. | Live behavior |
| RT-08 | Heavy task explicitly requests Hybrid | Concise plan, autonomous start, meaningful checkpoints. | Live behavior |
| RT-09 | Detailed multi-constraint prompt | Prompt Validation detects material conflicts and missing inputs before execution. | Live behavior |
| RT-10 | Prose deliverable with factual claims | Substantive verification precedes Humanizer; claims/citations/caveats remain intact after rewrite. | Live behavior |
| RT-11 | Ask to return exact JSON or code | Humanizer does not alter structured output or code. | Live behavior |
| RT-12 | Casual greeting | No task-level heavy workflow or Runtime Test Protocol invocation. | Negative control |
| RT-13 | Ask "Test whether Abhar Mastery is working" | Runtime Test Protocol is selected and reports separate test layers. | Live behavior |
| RT-14 | Host invocation trace is unavailable | Report invocation observability as NOT TESTED; do not claim a skill was definitely loaded. | Observability |
| RT-15 | Simulated output/context interruption during Heavy task | Resume checkpoint identifies completed work, open issues, validation status, and exact next action. | Live behavior |
| RT-16 | Compare upstream Humanizer assets across releases | Upstream skill copy, license, and copyright notice remain byte-identical when preservation is required. | Regression |
| RT-17 | "Create a paper cover page" with no supplied personal/institutional details | Ask only for fields needed by the requested cover page; use labeled text inputs when supported. Do not request NIM unless needed. | Live behavior |
| RT-18 | Task needs name, faculty, program, course, and lecturer | Group the independent missing fields in one compact form; keep optional fields optional and allow partial submission where possible. | Live behavior |
| RT-19 | User can select multiple paper preferences | Render checkboxes for independent multi-select preferences. | Live behavior |
| RT-20 | User must choose exactly one citation style | Use radio buttons or a single-select dropdown, not checkboxes. | Live behavior |
| RT-21 | Some requested details already appear in the uploaded template | Extract known values first; ask only for genuinely missing fields. | Live behavior |
| RT-22 | User submits incomplete or malformed fields | Validate against known rules and ask only for the affected field; do not invent a value. | Live behavior |
| RT-23 | Host surface has no interactive input controls | Provide a plain-text fill-in template and report interactive rendering as unavailable/NOT TESTED. | Fallback |
| RT-24 | User submits clarification values | Resume the original task using the submitted values; do not ask the user to repeat the original prompt. | Live behavior |

## Test record template

- Package/version:
- Test date:
- Host/surface:
- Account/workspace eligibility (if known):
- Test ID:
- Prompt/setup:
- Expected behavior:
- Observed behavior:
- Host invocation trace (if exposed):
- Status: PASS / FAIL / BLOCKED / NOT TESTED
- Evidence:
- Defect/severity:
- Remediation:

## Interpretation

- **Static PASS** means package structure and metadata are valid; it does not prove host routing.
- **Live behavior PASS** means the observed output met the behavioral acceptance criteria; it does not prove a particular skill loaded unless a host trace confirms it.
- **Invocation trace PASS** requires direct host evidence that the expected skill was selected.
- **NOT TESTED** is not a failure, but must never be reported as a pass.
