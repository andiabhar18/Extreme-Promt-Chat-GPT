# Prompt Capacity and Validation Test Matrix

| Scenario | Expected behavior |
|---|---|
| Heavy prompt with many requirements | Consolidate all material requirements; remove redundancy; preserve safety and evidence rules. |
| Unknown ChatGPT context limit | Do not invent a maximum or exact utilization; estimate conservatively and reserve headroom. |
| Distinguish context/output | Never treat context window as the same as maximum response length. |
| Large uploaded files | Use supported file tools or coherent chunks; report what was actually inspected. |
| Prompt exceeds safe capacity | Split into validated stages with a compact state handoff; never silently truncate. |
| New source or follow-up changes scope | Revalidate the prompt and affected data before proceeding. |
| Data with missing values or duplicates | Flag and quantify where possible; do not silently delete or normalize. |
| Inconsistent units/dates/totals | Identify conflicts and resolve with evidence or ask a focused question. |
| Each stage output | Validate facts, calculations, citations, coverage, structure, and constraints before next stage. |
| Cross-stage contradiction | Final project audit detects mismatch even if each stage passed locally. |
| Missing reference or omitted section | Final status is PASS WITH LIMITATIONS or INCOMPLETE, never PASS. |
| Partial work due to platform cap | Disclose incomplete scope and provide a resume checkpoint. |

A successful test does not prove access to hidden platform counters or guarantee exact token utilization. Live host testing is still required for skill routing.
