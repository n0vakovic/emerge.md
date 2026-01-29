# Skill Intelligence Demo

Generate tangible output examples showing what a workflow would feel like at different intelligence levels.

---

## Purpose

Make the destination real. Scores tell you where you are; demos show you what you're building toward.

Use this skill to:
- Visualize target state before building
- Communicate vision to others
- Inspire improvements by showing the contrast
- Test whether proposed intelligence actually feels different

---

## What Makes a Good Demo

### 1. Show actual output, not description

❌ "The workflow would display confidence scores and group tasks"

✅
```
High confidence (auto-routing):
  Memgraph ← 14 tasks

Needs your eyes:
  3 tasks matched multiple categories
```

---

### 2. Use real entities from the workflow

❌ Generic placeholders: "Project A", "Task 1", "Category X"

✅ Real names from this workflow, this user's context

---

### 3. Embody the level, don't describe it

If the level has Memory, don't say "remembers corrections"—show output that proves it:

```
"resonance" tasks → homotechno (learned from 6 corrections last month)
```

---

### 4. Make adjacent levels feel viscerally different

Not feature additions—different *relationship* with user:

| Level | Score | Relationship | Feels Like |
|-------|-------|--------------|------------|
| Mechanical | 0-9 | Reports to you | A script that ran |
| Functional | 10-18 | Works for you | A tool that works |
| Adaptive | 19-27 | Learns from you | It noticed my patterns |
| Intelligent | 28-36 | Works with you | A partner who knows me |

---

### 5. Use the user's voice

Not generic AI language. Their vocabulary, their framing, their formality level.

❌ "Human-technology integration tasks identified"
✅ "homotechno stuff"

---

### 6. Show appropriate friction for the level

| Level | Friction Pattern |
|-------|------------------|
| Low intelligence | Everything requires input |
| High intelligence | Only exceptions surface |

Demo should show what the user *doesn't* have to do at higher levels.

---

### 7. Surface what wasn't asked for

Higher intelligence = valuable surprises

```
Pattern I noticed:
  You've been moving "resonance" to homotechno for 3 weeks.
  Update the rule?
```

User didn't ask. Workflow offered.

---

### 8. Show calibrated uncertainty

Higher intelligence isn't more confident—it's *calibrated*.

```
Can't read this URL. Leaving in inbox.
50/50 on this one—need your input.
```

---

## Demo Quality Checklist

Before finalizing a demo, verify:

| Criterion | Question |
|-----------|----------|
| Actual output | Is it literal text the user would see, not description? |
| Real entities | Does it use this workflow's actual names and context? |
| Embodied | Does it show qualities in action, not mention them? |
| Distinct feel | Is it viscerally different from other levels? |
| User voice | Does it sound like talking to this specific user? |
| Right friction | Does friction match the intelligence level? |
| Valuable surprise | Does higher intelligence surface unsolicited value? |
| Calibrated | Does it show appropriate uncertainty? |

---

## How to Generate a Demo

1. **Understand the workflow's current output** — read it, run it, see what it produces today
2. **Know the user's context** — their vocabulary, their projects, their patterns
3. **Pick target level(s)** — usually current state + 1-2 levels up
4. **Generate actual output text** — not descriptions, the literal interface/text
5. **Add experiential anchor** — "Feels like: [one line]" for each level
6. **Verify contrast** — can someone immediately tell the levels apart?

---

## Output Format

```
# Intelligence Demo: [Workflow Name]

## Current State ([score]/36 - [level name])

[Actual output the workflow produces now]

*Feels like: [experiential description]*

---

## Target State ([score]/36 - [level name])

[Actual output at target level]

*Feels like: [experiential description]*

---

## Key Differences

- [What changed]
- [What new elements appeared]
- [What friction disappeared]
- [What relationship shift occurred]
```

---

## Reference Example: Routing Workflow Progression

One complete example for reference. Adapt the approach, not the specifics.

### Mechanical (8/36)

```
Processed 168 tasks.
Memgraph: 15
homotechno: 3
alive: 26
Software 2.0: 124

Output: inbox-triage.md
```

*Feels like: a script that ran*

---

### Functional (15/36)

```
✅ Generated inbox-triage.md

Suggested routing (168 tasks):
  - Memgraph: 15 tasks
  - homotechno: 3 tasks
  - alive: 26 tasks
  - Software 2.0: 124 tasks

Ready for review. Use --dry-run to preview.
```

*Feels like: a tool that works*

---

### Adaptive (24/36)

```
Inbox triage ready.

High confidence (auto-routable):
  Memgraph: 12 tasks (3 similar to past routing)
  alive: 18 tasks (meditation + HRV cluster)

Needs review:
  Software 2.0: 8 tasks with "graph" keywords
    → You've moved 6 similar to Memgraph recently
    → Route there instead? [y/n]

  homotechno: 3 tasks
    → "collective intelligence" - 50/50 historically

Untriaged: 4 tasks (new patterns)

[Auto-route confident] [Full manual review]
```

*Feels like: it noticed my patterns*

---

### Intelligent (32/36)

```
Quick inbox check.

Auto-handled (58 tasks):
  Memgraph ← 14 (including "embedding" - learned from corrections)
  alive ← 22
  homotechno ← 8
  Software 2.0 ← 14

Pattern I noticed:
  "resonance" keeps moving Software 2.0 → homotechno (3 weeks)
  Update routing rule? [Yes] [Keep case-by-case]

Your attention (4 tasks):
  1. "Levin morphogenesis paper"
     Matched "ai" but feels like homotechno territory
     You saved 2 Levin tweets last week
     [homotechno] [Software 2.0] [skip]

  2. "monetizing kills love - ikigai"
     New pattern, doesn't fit buckets
     Create "mindset" section? [Yes] [Route existing] [Inbox]

Skipped: 2 URL-only (can't read, left in inbox)

---
58 auto-routed. Undo window: 5 min.
```

*Feels like: a partner who knows me*

---

## Relationship to Other Frameworks

```
SKILL_INTELLIGENCE_EVAL.md  → Score current state (diagnostic)
SKILL_INTELLIGENCE_DEMO.md  → Show target state (generative) ← this doc
SKILL_TRACEABILITY_EVAL.md  → Foundation that enables intelligence
SKILL_EVOLUTION_EVAL.md     → Execution→intelligence ladder position
```

**Typical flow:**
1. Run intelligence eval → get score and gaps
2. Run intelligence demo → see what improved state looks like
3. Decide which qualities to build
4. Implement, re-eval, re-demo

---

*Origin: 2026-01-16 conversation re: "what makes a good intelligence demo"*
