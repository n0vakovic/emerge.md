# Workflow Evolution Evaluation Framework

Evaluate a workflow against the "execution → traceability → learning → intelligence" ladder.

---

## 1) Fit Criteria - Does it belong in this frame?

**Strong fit signals:**
- Reads text → produces enrichment (labels, priorities, categories, summaries)
- Runs repeatedly (not one-off)
- Contains judgment calls (not pure deterministic transformation)
- Entities have relationships (natural graph structure)
- Past decisions could inform future ones (context accumulates)
- Feedback is possible (human review, downstream usage reveals quality)

**Weak fit / doesn't belong:**
- Pure deterministic transformation (regex, parsing, format conversion)
- One-off task (no repetition = no learning opportunity)
- Stateless by nature (each run truly independent)
- No way to know if output was good or bad
- No relationships between entities (flat list, not network)

---

## 2) Spectrum Assessment - Where is it now?

| Level | Key question | Indicators |
|-------|--------------|------------|
| **Execution** | Does it run? | Produces output. No logging. Each run independent. If wrong, no one knows unless human notices. |
| **Traceability** | Can you reconstruct what happened? | Decisions logged. Inputs/outputs captured. "Why" recorded. Can query "all X decisions last month." But: logs sit unused. |
| **Learning** | Do insights change behavior? | Logs analyzed. Patterns extracted. Defaults updated from evidence. Human corrections incorporated. But: manual process. |
| **Intelligence** | Does it improve without intervention? | Learning loop closed automatically. Cross-session improvement. Anticipates and suggests. Data exhaust powers evolution. |

---

## 3) Quick Diagnostic Questions

1. **"Can you show me every decision this skill made last week?"** (traceability test)
2. **"Has anything changed based on what you learned from past runs?"** (learning test)
3. **"Does it get better automatically as it runs more?"** (intelligence test)

---

## 4) Output Format

Provide a concise evaluation with:
- Fit score (strong/medium/weak)
- Current level on spectrum
- Key gaps to move up
- Specific recommendations

---
