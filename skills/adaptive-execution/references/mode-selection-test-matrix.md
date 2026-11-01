# Adaptive Execution — Mode Selection Test Matrix (1.4.2)

Use this matrix for static review and live host testing. Static package checks cannot prove that the host selects the skill automatically.

| User request | Expected classification | Expected behavior |
|---|---|---|
| "What is photosynthesis?" | Light | Answer directly; no Adaptive Execution and no selector. |
| "Translate this paragraph into Indonesian." | Light | Translate directly; no selector. |
| "Draft a short meeting follow-up email." | Light/medium | Draft directly; no selector. |
| "Compare these three product options and recommend one." | Medium | Analyze and answer; no selector unless scope expands materially. |
| "Review this journal" with a full research paper and methodological/statistical/reference appraisal | Heavy | Start Automatic Intelligence Execution by default; no A/B/C selector. |
| "Write a 40,000-word academic book with research and citations." | Heavy | Start Automatic by default; plan outline and word allocation; stage the work. |
| "Audit these 12 spreadsheets and reconcile the financial model." | Heavy | Start Automatic by default; define files, checks, milestones, and completion criteria. |
| "Create a prompt for a 40,000-word book; do not execute it." | Prompt-only | Produce the prompt; no Adaptive Execution selector. |
| "Create the prompt and then write the 40,000-word book." | Heavy | Start Automatic by default unless the user selects another mode. |
| "Do this in Controlled Professional Execution: review the attached thesis." | Heavy, Controlled preselected | Present the full plan and wait for explicit approval. |
| "Do this in Hybrid Adaptive Execution: review the attached thesis." | Heavy, Hybrid preselected | Present concise plan, begin autonomously, and checkpoint at milestones. |
| "Show me the three execution modes before we begin." | Mode-choice request | Display A/B/C choices; wait for the user's selection. |
| "Switch this project from Automatic to Controlled." | Existing project | Change mode for future work; preserve completed work and request approval before the next substantive stage. |
| "Continue from this checkpoint." | Existing project | Resume at the next incomplete step; keep the established mode. |

## Acceptance checks

- No Adaptive Execution selector appears for Light or ordinary Medium tasks.
- Heavy work defaults to Automatic when no explicit mode preference exists.
- No A/B/C selector appears unless the user asks to choose/compare modes or selects a non-default mode.
- Controlled mode waits for explicit approval.
- Automatic mode minimizes check-ins but preserves safety, clarification, and authorization gates.
- Hybrid mode uses meaningful milestones and does not over-interrupt.
- The selected mode persists within the current project conversation and can be changed by the user.
- Long-form work is planned and drafted in stages; planned and actual word counts are not conflated.
- A checkpoint identifies the last completed section and exact next action.
- No claim is made of background execution or persistent state across chats.
- Partial work is never described as complete.
