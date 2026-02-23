# emerge.md

> Evaluate and grow AI-assisted workflows from "a script that ran" to "a partner who knows me."

emerge.md is a set of composable evaluation frameworks for diagnosing where an AI-assisted workflow sits on the execution-to-intelligence ladder — and what it would take (and feel like) to reach the next level. Designed as prompts for AI assistants like Claude.

## The Ladder

| Level | Key Question | Feels Like |
|-------|-------------|------------|
| **Execution** | Does it run? | A script that ran |
| **Traceability** | Can you reconstruct what happened? | A tool that shows its work |
| **Learning** | Do insights change behavior? | It noticed my patterns |
| **Intelligence** | Does it improve without intervention? | A partner who knows me |

The difference between levels isn't features — it's the **relationship** between the workflow and the person using it.

## Frameworks

- **[Basic Eval](SKILL_BASIC_EVAL.md)** — Score a skill against Anthropic's best practices for authoring quality. 10 criteria (Description, Conciseness, Progressive Disclosure, Degrees of Freedom, Decision Clarity, Failure Handling, Examples, Consistency, Model Robustness, Testability) each 0–4, totaling /40
- **[Evolution Eval](SKILL_EVOLUTION_EVAL.md)** — Position a workflow on the ladder using fit criteria and diagnostic questions
- **[Traceability Eval](SKILL_TRACEABILITY_EVAL.md)** — 7-level rubric (L0–L6) for whether you can reconstruct what happened and why. The foundation — without traceability, intelligence qualities can't develop
- **[Intelligence Eval](SKILL_INTELLIGENCE_EVAL.md)** — Score 11 qualities (Memory, Calibration, Voice, Awareness, Connection, Humility, Flexibility, Agency, Restraint, Predictability, Resourceful) each 0–4, totaling /44. Includes priority matrix by workflow type
- **[Intelligence Demo](SKILL_INTELLIGENCE_DEMO.md)** — Generate tangible before/after output showing what the next level would look and feel like. Show actual output, not descriptions
- **[Context Graph Eval](SKILL_CONTEXT_GRAPH_EVAL.md)** — Determine whether a context graph is the unlock for reaching L4 qualities, or whether simpler infrastructure suffices
- **[Growth Guide](SKILL_GROWTH_GUIDE.md)** — Compose all frameworks into a step-by-step interactive walkthrough ending with a concrete growth plan

### How They Compose

```
Input: Any workflow/skill
         ↓
┌────────────────────────────┐
│ 0. BASIC EVAL              │  Is the skill well-authored?
│    (SKILL_BASIC_EVAL)      │  Score /40 against Anthropic best practices
└────────────────────────────┘
         ↓
┌────────────────────────────┐
│ 1. EVOLUTION EVAL          │  Where on the ladder?
│    (SKILL_EVOLUTION_EVAL)  │  Execution → Traceability → Learning → Intelligence
└────────────────────────────┘
         ↓
    [If below Learning]
         ↓
┌────────────────────────────┐
│ 2. TRACEABILITY EVAL       │  What's blocking the foundation?
│    (SKILL_TRACEABILITY_EVAL)│  Level 0-6, specific gaps
└────────────────────────────┘
         ↓
┌────────────────────────────┐
│ 3. INTELLIGENCE EVAL       │  How does it feel?
│    (SKILL_INTELLIGENCE_EVAL)│  Score /44, quality breakdown
└────────────────────────────┘
         ↓
┌────────────────────────────┐
│ 4. INTELLIGENCE DEMO       │  What could it look like?
│    (SKILL_INTELLIGENCE_DEMO)│  Target state visualization
└────────────────────────────┘
         ↓
      Output: Growth Plan
```

Each framework is independently useful. Use one or compose them.

## Usage

### Quick Start

1. **Pick a workflow** you want to evaluate
2. **Start with Evolution Eval** — where on the ladder?
3. **If below Learning**, run Traceability Eval — what's blocking the foundation?
4. **Run Intelligence Eval** — which qualities matter for this workflow type?
5. **Run Intelligence Demo** — what would the next level feel like?
6. **Compile a Growth Plan** — concrete next steps

### As Claude Code Skills

These files work as Claude Code skills. Point Claude at a workflow and a framework document, and it will run the evaluation against that workflow.

## License

MIT
