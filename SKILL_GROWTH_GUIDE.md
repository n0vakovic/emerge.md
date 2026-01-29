# Skill Growth Guide

Comprehensive evaluation and growth path for any workflow or skill. Composes existing frameworks into a meaningful sequence that educates, inspires, and provides actionable steps.

---

## When to Use

- Evaluating a new or existing workflow
- Planning improvements to a skill
- Understanding why a workflow feels "off"
- Creating a roadmap for workflow evolution

---

## The Sequence

```
Input: Any workflow/skill
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

---

## Step 1: Evolution Eval

**Question:** Where is this skill on the execution→intelligence ladder?

| Level | Key Question | If Yes |
|-------|--------------|--------|
| Execution | Does it run and produce output? | Proceed to Traceability |
| Traceability | Can you reconstruct what happened? | Proceed to Learning |
| Learning | Do insights change behavior? | Proceed to Intelligence |
| Intelligence | Does it improve without intervention? | Focus on refinement |

**Output:** Position on ladder + key gaps to move up.

**If skill is at Execution or Traceability level:** Run Traceability Eval next (Step 2).
**If skill is at Learning or Intelligence level:** Skip to Intelligence Eval (Step 3).

---

## Step 2: Traceability Eval (if needed)

**Question:** What's blocking the foundation for learning?

Run only if skill is below Learning level. Traceability is the foundation—without it, intelligence qualities can't develop.

| Level | What's Needed |
|-------|---------------|
| 0-2 | Basic: Structured logs with consistent schema |
| 3 | Contextual: Reasoning captured ("why" not just "what") |
| 4 | Linked: Session/run IDs, traversable history |
| 5 | Correctable: Human overrides captured with before/after |
| 6 | Learning-ready: Queryable by non-authors, patterns extractable |

**Output:** Current level, specific gaps, implementation recommendations.

---

## Step 3: Intelligence Eval

**Question:** How does the workflow feel to use?

Evaluate all 11 qualities:

| Quality | What It Means |
|---------|---------------|
| Memory | Adapts from past corrections |
| Calibration | Friction matches confidence |
| Voice | Uses your terms, not generic |
| Awareness | Notices session/context patterns |
| Connection | Links across time and entities |
| Humility | Knows its limits, says so |
| Flexibility | Adapts pace/batch to you |
| Agency | Suggests improvements to itself and the system |
| Restraint | Disappears when not needed |
| Predictability | Behavior user can anticipate |
| Resourceful | Discovers, uses, and seeks available sources, tools, and capabilities |

**Output:** Score X/44, quality breakdown, priority improvements based on workflow type.

---

## Step 4: Intelligence Demo

**Question:** What would it feel like at the next level?

Generate tangible output examples showing:
1. **Current state** — what it produces now
2. **Target state** — what it could produce with improvements
3. **Key differences** — what changes, what friction disappears

Follow demo principles:
- Show actual output, not descriptions
- Use real entities from the workflow
- Embody the level, don't describe it
- Make levels viscerally different
- Include "Feels like:" anchors

**Output:** Side-by-side demos that make the destination tangible.

---

## Output: Growth Plan

Compile findings into actionable format:

```markdown
# Skill Growth Plan: [Workflow Name]

## Where You Are

**Evolution position:** [Execution/Traceability/Learning/Intelligence]
**Traceability level:** [0-6] (if evaluated)
**Intelligence score:** [X/44] - [Mechanical/Functional/Adaptive/Intelligent]

**Current state feels like:** [one line from demo]

**Key insight:** [One sentence capturing the main gap]

---

## Where You Could Be

[Intelligence demo at target level]

*Feels like: [experiential anchor]*

**Relationship shift:** [Current relationship] → [Target relationship]

---

## How To Get There

### Quick Wins (this week)
Low-effort changes that show immediate improvement.

1. [ ] [Specific action]
2. [ ] [Specific action]

### Foundation Work (enables the rest)
Required infrastructure for intelligence to develop.

1. [ ] [Specific action] — [why this matters]
2. [ ] [Specific action] — [why this matters]

### Intelligence Upgrades (once foundation is solid)
Quality improvements in priority order for this workflow type.

1. [ ] **[Quality]** [current→target]: [specific action]
2. [ ] **[Quality]** [current→target]: [specific action]
3. [ ] **[Quality]** [current→target]: [specific action]

---

## Verification

How to know you've succeeded:

- [ ] [Diagnostic question] → [Expected answer]
- [ ] [Diagnostic question] → [Expected answer]
- [ ] Demo output matches target state
```

---

## Running the Guide (Interactive)

**This guide is designed to be walked through step-by-step, not dumped all at once.**

Each step ends with a checkpoint. Wait for user input before proceeding.

---

### Step 1: Evolution Eval

Run the evolution eval, then present:

```
## Step 1: Where are you on the ladder?

Your workflow is at: **[Execution/Traceability/Learning/Intelligence]**

[2-3 sentence explanation of what this means]

Key finding: [One specific insight]

---

Ready to continue?
- [Continue to Step 2]
- [Tell me more about this level]
- [What would it take to move up?]
```

**Wait for user response before proceeding.**

---

### Step 2: Traceability Eval (if needed)

If below Learning level, run traceability eval, then present:

```
## Step 2: Checking the foundation

Your traceability level: **[0-6] - [Name]**

[2-3 sentence explanation]

The gap: [Specific thing that's missing]

---

Ready to continue?
- [Continue to Step 3]
- [Show me what good traceability looks like]
- [How do I fix this gap?]
```

**Wait for user response before proceeding.**

If at Learning or above, skip with:

```
## Step 2: Foundation check

✓ Traceability foundation is solid. Skipping to intelligence eval.

---

[Continue to Step 3]
```

---

### Step 3: Intelligence Eval

Run intelligence eval, then present summary (not full breakdown):

```
## Step 3: How does it feel?

Intelligence score: **[X/44]** - [Mechanical/Functional/Adaptive/Intelligent]

Top strengths:
- [Quality]: [Level] - [one line]
- [Quality]: [Level] - [one line]

Key gaps:
- [Quality]: [Level] - [one line]
- [Quality]: [Level] - [one line]

---

Ready to continue?
- [Continue to Step 4 - see what it could look like]
- [Show me the full quality breakdown]
- [Why are these the priority gaps?]
```

**Wait for user response before proceeding.**

---

### Step 4: Intelligence Demo

Run demo for current + target state, then present:

```
## Step 4: What could it look like?

### Now ([score]/44)

[Current state demo - actual output]

*Feels like: [anchor]*

### Target ([target score]/44)

[Target state demo - actual output]

*Feels like: [anchor]*

---

The shift: [One sentence describing relationship change]

---

Ready for your growth plan?
- [Yes, show me the action steps]
- [Show me an intermediate level too]
- [What makes the target feel different?]
```

**Wait for user response before proceeding.**

---

### Step 5: Growth Plan

Compile and present:

```
## Your Growth Plan

### Quick Wins (this week)
1. [ ] [Action]
2. [ ] [Action]

### Foundation Work
1. [ ] [Action] — [why]

### Intelligence Upgrades (in order)
1. [ ] [Quality] → [action]
2. [ ] [Quality] → [action]

---

Where would you like to start?
- [Quick wins]
- [Foundation work]
- [Pick a specific quality to improve]
- [Save this plan and revisit later]
```

---

### Interaction Principles

1. **One step at a time** — Never dump all evals at once
2. **Summarize first** — Full details available on request
3. **Clear checkpoints** — User chooses when to proceed
4. **Offer depth** — "Tell me more" always available
5. **End with action** — Each step connects to what's next
6. **User controls pace** — They may want to sit with a finding before moving on

---

## Framework Relationships

```
SKILL_EVOLUTION_EVAL.md      → Positioning (where on ladder)
SKILL_TRACEABILITY_EVAL.md   → Foundation (can you learn from data)
SKILL_INTELLIGENCE_EVAL.md   → Experience (how does it feel)
SKILL_INTELLIGENCE_DEMO.md   → Vision (what could it be)
SKILL_GROWTH_GUIDE.md        → Composition (this doc)
```

Each framework is independently useful. This guide composes them into a complete growth path.

---

## Why This Works

| Stage | Purpose | Outcome |
|-------|---------|---------|
| Evolution Eval | Problem awareness | User understands current position |
| Traceability Eval | Foundation check | Identifies infrastructure needs |
| Intelligence Eval | Detailed diagnosis | Pinpoints specific gaps |
| Intelligence Demo | Vision casting | Makes destination tangible |
| Growth Plan | Path clarity | Reduces overwhelm, enables action |

The sequence moves from **understanding** → **inspiration** → **action**.

---

*Origin: 2026-01-16 conversation re: composing eval frameworks into meaningful sequence*
