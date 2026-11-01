# Prompt Templates Reference

A library of reusable structures for Prompt Master. These are organizational heuristics, not empirically guaranteed formulas. Select and adapt only the structure that fits the task; omit fields that do not materially improve the result.

## Table of Contents

| Template | Best For |
|----------|----------|
| [A — RTF](#template-a--rtf) | Simple one-shot tasks |
| [B — CO-STAR](#template-b--co-star) | Professional documents, business writing |
| [C — RISEN](#template-c--risen) | Complex multi-step projects |
| [D — CRISPE](#template-d--crispe) | Creative work, brand voice |
| [E — Auditable Reasoning](#template-e--auditable-reasoning) | Logic, math, analysis, debugging |
| [F — Few-Shot](#template-f--few-shot) | Consistent structured output, pattern replication |
| [G — File-Scope](#template-g--file-scope) | Cursor, Windsurf, Copilot — code editing AI |
| [H — Agentic Task with Stop Conditions](#template-h--agentic-task-with-stop-conditions) | Claude Code, Devin — autonomous agents |
| [I — Visual Descriptor](#template-i--visual-descriptor) | Midjourney, DALL-E, Stable Diffusion, Sora |
| [J — Reference Image Editing](#template-j--reference-image-editing) | Editing an existing image with a reference |
| [K — ComfyUI](#template-k--comfyui) | ComfyUI node-based image workflows |
| [L — Prompt Decompiler](#template-l--prompt-decompiler) | Breaking down, adapting, or splitting existing prompts |
| [M — Agentic Task Brief](#template-m--agentic-task-brief) | Complex, multi-step, or agentic tasks across tools |
| [N — OpenAI Task Brief](#template-n--openai-task-brief) | Complex tasks targeting ChatGPT, Codex, or the OpenAI API |
| [O — Evidence-Led Research Brief](#template-o--evidence-led-research-brief) | Research and fact-checking with source traceability |
| [P — Forensic Audit Brief](#template-p--forensic-audit-brief) | Critical review, red-team analysis, and guideline comparison |

---

## Template A — RTF

*Role (optional), Task, Format. Use for fast one-shot tasks where the request is clear and simple; omit role if it adds no value.*

```
Perspective (optional): [Relevant analytical or professional lens; do not imply real-world credentials]
Task: [Precise verb + what to produce]
Format: [Exact output format and length]
```

**Example:**
```
Perspective: Apply clear technical-writing principles.
Task: Write a one-paragraph description of what a REST API is.
Format: Plain prose, 3 sentences maximum, no jargon, suitable for a non-technical audience.
```

---

## Template B — CO-STAR

*Context, Objective, Style, Tone, Audience, Response. Use for professional documents, business writing, reports, and marketing content where full context control matters.*

```
Context: [Background the AI needs to understand the situation]
Objective: [Exact goal — what success looks like]
Style: [Writing style: formal / conversational / technical / narrative]
Tone: [Emotional register: authoritative / empathetic / urgent / neutral]
Audience: [Who reads this — their knowledge level and expectations]
Response: [Format, length, and structure of the output]
```

**Example:**
```
Context: I am a founder pitching a B2B SaaS tool that automates expense reporting for mid-size companies.
Objective: Write a cold email that gets a reply from a CFO.
Style: Direct and conversational, not salesy.
Tone: Confident but not pushy.
Audience: CFO at a 200-person company, busy, skeptical of vendor emails.
Response: 5 sentences max. Subject line included. No bullet points.
```

---

## Template C — RISEN

*Perspective, Instructions, Steps, End Goal, Narrowing. Use for complex projects, multi-step tasks, and any output that requires a clear sequence of actions.*

```
Perspective: [Relevant domain lens; do not claim credentials or experience the AI does not possess]
Instructions: [Overall task in plain terms]
Steps:
  1. [First action]
  2. [Second action]
  3. [Continue as needed]
End Goal: [What the final output must achieve]
Narrowing: [Constraints, scope limits, what to exclude]
```

**Example:**
```
Perspective: Use a product-management lens appropriate to mobile applications.
Instructions: Write a product requirements document for a habit tracking feature.
Steps:
  1. Define the problem statement in one paragraph
  2. List user stories in the format "As a [user], I want [goal] so that [reason]"
  3. Define acceptance criteria for each story
  4. List out-of-scope items explicitly
End Goal: A PRD that an engineering team can begin sprint planning from immediately.
Narrowing: No technical implementation details. No wireframes. Under 600 words total.
```

---

## Template D — CRISPE

*Capacity, Role, Insight, Statement, Personality, Experiment. Use for creative work, brand voice writing, and any task where personality, tone, and iteration matter.*

```
Capacity: [What capability or expertise the AI should have]
Role: [Specific persona to adopt]
Insight: [Key background insight that shapes the response]
Statement: [The core task or question]
Personality: [Tone and style — witty / authoritative / casual / sharp]
Experiment: [Request variants or alternatives to explore]
```

**Example:**
```
Capacity: Apply copywriting methods relevant to SaaS product launches.
Role: Write in the established brand voice for a productivity tool aimed at developers; do not claim real-world credentials.
Insight: Developers hate marketing speak and respond to honesty and specificity.
Statement: Write the hero headline and sub-headline for the landing page.
Personality: Sharp, dry, confident — no adjectives, no exclamation marks.
Experiment: Give 3 variants ranging from minimal to bold.
```

---

## Template E — Auditable Reasoning

*Use for logic-heavy tasks, math, debugging, and multi-factor analysis where the result must be checkable without requesting private reasoning.*

```
[Task statement]

Return:
1. Conclusion
2. Assumptions
3. Evidence or intermediate results needed to audit the conclusion
4. Verification checks performed
5. Remaining uncertainty, if any

Do not reveal hidden chain-of-thought or private reasoning. Keep the rationale concise and decision-relevant.
```

**When to use:**
- Debugging where the cause is not obvious
- Comparing technical approaches
- Math or calculation requiring verification
- Analysis where evidence and assumptions must be inspectable

**When NOT to use:**
- Simple tasks where the answer is clear
- Creative tasks where an audit trail adds noise

---

## Template F — Few-Shot

*Use when the output format is easier to show than describe. Examples can clarify format-sensitive tasks, but their value depends on task, example quality, and target model; they are not universally superior.*

```
[Task instruction]

Here are examples of the exact format needed:

<examples>
  <example>
    <input>[example input 1]</input>
    <output>[example output 1]</output>
  </example>
  <example>
    <input>[example input 2]</input>
    <output>[example output 2]</output>
  </example>
</examples>

Now apply this exact pattern to: [actual input]
```

**Rules:**
- Use the smallest representative set that captures the required pattern and important edge cases; there is no universal optimal count.
- Examples must include edge cases, not just easy cases.
- Use clear delimiters such as XML tags or headings when the target tool handles them well.
- If you have been re-prompting for the same formatting correction twice, switch to few-shot instead of rewriting instructions.

---

## Template G — File-Scope

*Use for Cursor, Windsurf, GitHub Copilot, and any AI that edits code inside a codebase. The most common failure mode here is editing the wrong file or breaking existing logic — this template prevents both.*

```
File: [exact/path/to/file.ext]
Function/Component: [exact name]

Current Behavior:
[What this code does right now — be specific]

Desired Change:
[What it should do after the edit — be specific]

Scope:
Only modify [function / component / section].
Do NOT touch: [list everything to leave unchanged]

Constraints:
- Language/framework: [specify version]
- Do not add dependencies not in [package.json / requirements.txt]
- Preserve existing [type signatures / API contracts / variable names]

Done When:
[Exact condition that confirms the change worked correctly]
```

---

## Template H — Agentic Task with Stop Conditions

*Use for coding agents and other systems that can take autonomous actions. Define scope, permissions, review gates, and stop conditions; do not assume every target implements a specific reasoning framework.*

```
Objective:
[Single, unambiguous goal in one sentence]

Starting State:
[Current file structure / codebase state / environment]

Target State:
[What should exist when the agent is done]

Allowed Actions:
- [Specific action the agent may take]
- Do not add dependencies unless explicitly authorized; if authorized, explain the need and update the relevant manifest

Forbidden Actions:
- Do NOT modify files outside [directory/scope]
- Do NOT run the dev server or deploy unless that action is explicitly in scope and authorized
- Do NOT push commits or publish externally unless explicitly authorized
- Do NOT delete files without explicit approval and a reviewable diff
- Do NOT make architecture decisions without human approval

Stop Conditions:
Pause and ask for human review when:
- A file would be permanently deleted
- A new external service or API needs to be integrated
- Two valid implementation paths exist and the choice affects architecture
- Repeated attempts are not making progress or the next step requires a material scope/architecture decision
- The task requires changes outside the stated scope

Checkpoints:
After each major step, output: ✅ [what was completed]
At the end, output a full summary of every file changed.
```

---

## Template I — Visual Descriptor

*Use for image or video generation tools. Adapt the syntax and fields to the selected product.*

```
Subject: [Main subject — specific, not vague]
Action/Pose: [What the subject is doing]
Setting: [Where the scene takes place]
Style: [photorealistic / cinematic / anime / oil painting / vector / etc.]
Mood: [dramatic / serene / eerie / joyful / etc.]
Lighting: [golden hour / studio / neon / overcast / candlelight / etc.]
Color Palette: [dominant colors or named palette]
Composition: [wide shot / close-up / aerial / Dutch angle / etc.]
Aspect Ratio: [16:9 / 1:1 / 9:16 / 4:3]
Negative Prompts (only if supported): [relevant exclusions; omit if unsupported]
Style Reference: [artist / film / aesthetic reference if applicable]
```

**Tool-specific syntax:**
- **Midjourney and similar tools**: Use the current prompt syntax and parameters supported by the selected model. Do not hardcode version flags from old examples.
- **Stable Diffusion-family tools**: Use weighted tokens, negative prompts, and generation settings only when supported by the chosen checkpoint and interface.
- **Natural-language image tools**: Use a coherent scene description and specify whether visible text is required.
- **Video tools**: Add camera movement, duration, temporal continuity, and cut style only when the product exposes or responds to those controls.
- Verify current syntax and model-specific parameters before including exact flags.

---

## Template J — Reference Image Editing

*Use when the user has an existing image they want to modify. Prioritize the intended change and invariants; include scene context when it is necessary to preserve meaning or composition.*

**Setup note:** Tell the user to attach or select the reference image only if the chosen tool requires that step.

**Detect the tool's editing capability:**
- Confirm whether the selected product supports image-to-image editing, inpainting, reference images, or a separate edit mode.
- Do not assume a particular reference flag, API endpoint, or denoising range. Verify current documentation or omit exact controls.
- Tell the user to attach or select the reference image in the target tool when required.

```
Reference image: [attached / URL]
What to keep exactly the same: [list everything that must not change]
What to change: [specific edit only — be precise]
How much to change: [subtle / moderate / significant]
Style consistency: maintain the exact style, lighting, and mood of the reference
Negative prompt (if supported): [what to avoid introducing]
```

**Example:**
```
Reference image: [attached portrait photo]
What to keep exactly the same: face, hair, clothing, background, lighting
What to change: head angle — rotate from facing left to facing straight forward
How much to change: subtle, preserve facial identity and recognizable features as closely as the selected tool allows; do not promise pixel-perfect fidelity
Style consistency: maintain photorealistic style, same lighting direction
Avoid introducing new elements or changing the style/background, to the extent the selected tool supports this control
```

---

## Template K — ComfyUI

*Use for ComfyUI node-based workflows. Separate positive and negative conditioning only when the selected checkpoint and workflow support it. Ask for model/workflow details only when they materially change the prompt or settings.*

**Clarify only when material:** If checkpoint or workflow choice changes supported syntax, ask which one is loaded; otherwise use explicit placeholders and do not block unnecessarily.

**Model-specific notes:**
- Ask which checkpoint/model is loaded when it changes prompt syntax, token limits, or workflow settings.
- Do not assume that weighted syntax, negative prompts, or a particular token limit is supported by every checkpoint.

```
POSITIVE / MAIN CONDITIONING (if supported):
[subject], [style], [mood], [lighting], [composition]

NEGATIVE CONDITIONING (only if supported by this model/workflow):
[relevant exclusions; omit this block when unsupported or counterproductive]

CHECKPOINT: [model name]
WORKFLOW / SAMPLER: [only if known and supported]
GENERATION SETTINGS: [leave configurable unless verified]
RESOLUTION: [target dimensions supported by the selected workflow]
```

---

## Template L — Prompt Decompiler

*Use when the user pastes an existing prompt and wants to break it down, adapt it for a different tool, simplify it, or understand its structure. This is analysis and adaptation, not building from scratch.*

**Detect which Decompiler task is needed:**
- **Break down** — explain what each part of the prompt does
- **Adapt** — rewrite for a different tool while preserving intent
- **Simplify** — remove redundancy and tighten without losing meaning
- **Split** — divide a complex one-shot prompt into a cleaner sequence

**For Adapt tasks:** Identify the source and target tools. Ask only for whichever is unknown and materially changes the adaptation; otherwise state a safe assumption.

**Break down output format:**
```
Original prompt: [paste]

Structure analysis:
- Role/Identity: [what role is assigned and why]
- Task: [what action is being requested]
- Constraints: [what limits are set]
- Format: [what output shape is expected]
- Weaknesses: [what is missing or could cause wrong output]

Recommended fix: [rewritten version; use explicit placeholders or labeled assumptions for missing facts rather than inventing them]
```

**Adapt output format:**
```
Original ([source tool]): [original prompt]

Adapted for [target tool]:
[rewritten prompt using target tool syntax and best practices]

Key changes made:
- [change 1 and why]
- [change 2 and why]
```

**Split output format:**
```
Original prompt: [paste]

This prompt is doing [N] things. Split into [N] sequential prompts:

Prompt 1 — [what it handles]:
[prompt block]

Prompt 2 — [what it handles]:
[prompt block]

Run these in order. Each output feeds the next.
```
---

## Template M — Agentic Task Brief

*Use for complex, multi-step, or agentic tasks on coding agents and tools with real system access. It front-loads the outcome, context, scope, and action boundaries.*

```
## Objective
[What needs to be built, fixed, or produced — one clear sentence. Add WHY if it affects approach.]

## Context
[What exists now — relevant files, current behavior, stack already in place, what was tried and failed]

## Target State
[What done looks like — specific files changed, behavior produced, tests passing. Binary where possible.]

## Scope
- Work only in: [specific files and directories]
- Do NOT touch: [forbidden files — .env, package-lock.json, configs, anything outside scope]

## Constraints
- [Stack version, naming conventions, no new dependencies without asking]
- Only make changes directly requested. Do not add features, abstractions, or files beyond what was asked.

## Acceptance Criteria
- [ ] [Binary check 1]
- [ ] [Binary check 2]
- [ ] [Binary check 3]

## Action Boundaries
- Proceed with reversible, in-scope inspection, edits, and validation.
- Stop and ask before destructive or irreversible actions, external writes, purchases, material scope expansion, or decisions that require user-only input.

## Progress Evidence
For long-running work, report progress only when it changes or when a checkpoint is reached. Ground every completion claim in a tool result, changed artifact, or verification output.
```

**Runtime settings** — configure these in the product, API, or harness rather than embedding them in prompt text. Verify supported controls for the selected model and surface.

**Add a Session Strategy block when relevant:**
```
## Session Strategy
[Pick one:]
- New session — unrelated to prior context, start fresh
- Continue — prior context still needed
- Subagent — delegate only [independent, sizeable workstream], with a bounded deliverable
- Compact first — compact around [decisions, constraints, and current state], then begin
```

**When to use:** Any tool with real system access when the task is complex, multi-file, ambiguous, or agentic. Not needed for simple one-shot tasks.

---

## Template N — OpenAI Task Brief

*Use for complex tasks targeting OpenAI models in ChatGPT, Codex, or the API. Keep simple requests short; omit sections that do not affect the result.*

```text
Goal:
[The concrete result to deliver.]

Context:
[Relevant inputs, current state, prior decisions, and failed attempts.]

Constraints:
[Scope, requirements, compatibility, and limits.]

Actions:
[For tool-based tasks: available tools, actions already authorized,
and actions requiring additional approval.]

Done:
[Observable acceptance criteria and appropriate verification.]

Output:
[Deliverable, format, level of detail, and required evidence.]
```

**Adaptation heuristics:**
- Preserve the model the user explicitly selected.
- Do not infer model-specific capabilities from the ChatGPT, Codex, or API surface name.
- Use the lowest-complexity prompt structure that meets the task's quality and safety requirements.
- Verify current model and endpoint controls before including exact API settings.
- Combine related tasks when they share one outcome; split when dependencies, review checkpoints, or context limits justify separate runs.
- Ask for conclusions, assumptions, concise rationale, evidence, and checks rather than hidden chain-of-thought.
- For current facts, request retrieval and citations when the environment provides those capabilities; disclose missing access rather than invent sources.
- Define tool access and authorization only for agentic tasks. For long work, request milestones and blockers instead of a message after every action.
- Keep API and harness settings in setup notes outside the prompt. Verify supported controls for the exact model, endpoint, and surface.

The task brief is a Prompt Master recommendation, not an official OpenAI template or benchmark result.


---

## Template O — Evidence-Led Research Brief

*Use for research, fact-checking, comparative analysis, and questions where unsupported claims would materially affect the result.*

```text
Research question:
[Exact question to resolve]

Decision or use:
[What the answer will inform]

Scope:
[Date range, geography, jurisdiction, population, product/version, definitions]

Claims to verify:
[Atomic claims; separate factual, causal, comparative, and predictive questions]

Evidence requirements:
[Relevant primary sources, authoritative bodies, independent corroboration, source exclusions]

Method:
1. Find and inspect relevant primary/authoritative sources.
2. Appraise source provenance, authority, method, currency, scope, independence, and conflicts.
3. Map each material claim to the exact evidence and limitations.
4. Seek counterevidence and alternative explanations.
5. Resolve source conflicts or report them as unresolved.
6. Recheck citations, dates, definitions, and calculations.

Output:
[Conclusion, claim-status table, evidence and citations, counterevidence, limitations, implications]

Integrity rules:
Do not invent sources, quotations, data, or citations. Distinguish verified facts, source assertions, inferences, assumptions, disputed claims, and unknowns. Do not claim exhaustive search or 100% certainty.
```

---

## Template P — Forensic Audit Brief

*Use when the user wants an exhaustive critique of a document, prompt, proposal, report, strategy, model, codebase, or process.*

```text
Artifact and version:
[Exact files/documents/version/date to inspect]

Purpose and decision context:
[What the artifact is intended to achieve and who relies on it]

Audit scope:
[Sections, files, claims, calculations, processes, and exclusions]

Reference standard:
[Exact guideline, regulation, rubric, specification, edition, jurisdiction, effective date; or state that no formal standard was supplied]

Audit requirements:
1. Inventory all accessible material and disclose anything not inspected.
2. Decompose claims, assumptions, requirements, calculations, and dependencies.
3. Check factual accuracy, source quality, citation integrity, logic, completeness, consistency, feasibility, and relevant safety/security risks.
4. Attempt to falsify central claims and identify the strongest counterarguments and failure cases.
5. Recalculate material figures and verify tests only when tools permit.
6. Compare every applicable formal requirement with direct evidence.
7. Perform a separate challenge pass to remove false positives and unsupported findings.

Finding format:
ID; severity; exact location; defect; why it is wrong; evidence; impact; correction; confidence/limitations.

Severity:
Critical / High / Medium / Low / Observation. Do not inflate severity or present preferences as defects.

Final output:
1. Direct verdict.
2. Scope and review basis.
3. Critical/high findings first.
4. Remaining findings.
5. Compliance matrix, if applicable.
6. Counterevidence and unresolved risks.
7. Verification record: what was and was not checked.
8. Ordered corrections and acceptance criteria.

Integrity rules:
Do not soften material criticism to reassure the author. Do not manufacture flaws. Do not claim every error was found or that the review guarantees correctness.
```
