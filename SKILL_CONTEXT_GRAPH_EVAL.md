# Skill Context Graph Evaluation

Determine whether a context graph would unlock intelligence for a workflow—and what context would make it smarter.

**Context graphs** provide AI with persistent memory, relationship understanding, and grounded reasoning. They're the infrastructure layer for L4 intelligence qualities. ([Foundation Capital thesis](https://foundationcapital.com/context-graphs-ais-trillion-dollar-opportunity/))

**This eval answers:**
1. Do you need a context graph yet?
2. What's the first unlock point?
3. What additional context would provide more value if connected?

**Runs after:** SKILL_INTELLIGENCE_EVAL (needs quality scores)

---

## 1) Required Inputs

```yaml
skill: [name]
does: [what it does - enrichment, routing, research, etc.]
storage: [current - JSONL, SQL, files, API, etc.]

# From INTELLIGENCE_EVAL
intelligence_scores:
  memory: [0-4]
  calibration: [0-4]
  connection: [0-4]
  awareness: [0-4]
  # ... other qualities

# From INTELLIGENCE_EVAL or conversation
target_qualities:
  - [quality]: [target level]

# Optional - helps diagnosis
entities: [what nouns exist]
relationships_wished: [what connections you want but don't have]
unanswerable_questions: [questions you can't currently answer]
```

---

## 2) Context Graph-Relevant Qualities

Only these qualities have context graph as a primary enabler:

| Quality | Graph Relevant At | Why |
|---------|-------------------|-----|
| **Memory** | L4 (generalizes) | Pattern propagation across similar entities |
| **Connection** | L2+ (links to history) | Traversal, similarity, link prediction |
| **Calibration** | L4 (calibrates from outcomes) | Importance propagation, centrality |
| **Awareness** | L4 (anticipates) | Temporal graph patterns, context chains |
| **Agency** | L4 (suggests system improvements) | Cross-workflow pattern mining |

**Not graph-dependent:** Voice, Humility, Flexibility, Restraint, Predictability, Resourceful
(These have other primary enablers: embeddings, confidence models, feedback loops, etc.)

---

## 3) Decision Logic

```
For each target_quality in graph-relevant set:

  current = intelligence_scores[quality]
  target = target_qualities[quality]

  if target <= 3:
    → Graph not needed for this quality yet
    → Can achieve with: JSONL + code, SQL joins, manual traversal

  if target == 4 AND current < 4:
    → Graph is likely unlock
    → Record as unlock_point
```

---

## 4) Output Format

### Output A: Don't Need Yet

```
Skill: [name]
Context graph verdict: NOT NEEDED YET

Reason: Target levels achievable without graph
- [quality]: L[current]→L[target] — achievable with [alternative]

When to revisit: If you want L4 for Memory, Connection, Calibration, or Awareness
```

### Output B: Graph Unlocks

```
Skill: [name]
Context graph verdict: UNLOCKS INTELLIGENCE

First unlock point: [quality] L[current]→L4

What graph enables:
- [quality]: [specific capability] via [algorithm]

Graph level needed: [3-5 from capability assessment]

Implementation paths:
- Light: Python networkx over existing JSONL
- Medium: Graph DB (Memgraph/Neo4j)
- Heavy: Graph + ML pipeline

Would you like to see what L4 [quality] would look/feel like?
→ [Triggers SKILL_INTELLIGENCE_DEMO for that quality]

Context that would unlock more:
[See Section 5]
```

---

## 5) Context Enrichment — What Would Make It Smarter?

Beyond "do you need graph?" ask: **"What context would provide more value if connected?"**

### Context Source Categories

| Category | Examples | What It Unlocks |
|----------|----------|-----------------|
| **Communication** | Slack, email, meetings | Intent, priority signals, relationship context |
| **Code/Work artifacts** | GitHub, PRs, commits, docs | What was built, why, by whom |
| **Tasks/Planning** | Todoist, Linear, Notion | Goals, deadlines, dependencies |
| **Calendar/Time** | Events, focus blocks | Availability, rhythm, temporal patterns |
| **External knowledge** | Arxiv, docs, web | Domain grounding, reference material |
| **Sibling workflows** | Other skills' outputs | Cross-workflow patterns, shared entities |
| **User signals** | Corrections, preferences, feedback | Personalization, calibration data |

### Diagnostic Questions

For each category, ask:

1. **Would knowing X make decisions better?**
   - "If I knew what was discussed in Slack about this task..."
   - "If I could see the PR that introduced this code..."
   - "If I knew what else is due this week..."

2. **Is there context you provide manually that could be connected?**
   - "I always have to remind it that X relates to Y"
   - "It doesn't know that this project is high priority"
   - "It can't see that I already solved this in another workflow"

3. **What patterns span sources?**
   - Task discussed in Slack → created in Todoist → implemented in GitHub
   - Correction made here → should apply to similar items elsewhere

### Output: Context Wishlist

```
Context that would unlock more intelligence:

High value (directly improves target qualities):
- [source]: [what it provides] → enables [quality] L[X]
- [source]: [what it provides] → enables [quality] L[X]

Medium value (supports but not critical):
- [source]: [what it provides]

Already connected:
- [source]: [how it's used]

Not relevant for this skill:
- [source]: [why]
```

### Example

```yaml
skill: todoist-inbox-router

context_wishlist:
  high_value:
    - slack: "discussion context for tasks" → Connection L4 (link task to conversation)
    - github: "which tasks became PRs" → Memory L4 (learn routing from outcomes)
    - past_corrections: "human overrides" → Calibration L4 (calibrate from feedback)

  medium_value:
    - calendar: "deadline pressure signals"
    - other_todoist_projects: "sibling task patterns"

  already_connected:
    - todoist_api: "current tasks and projects"

  not_relevant:
    - arxiv: "academic papers not useful for task routing"
```

---

## 6) Ceiling Symptoms (Supporting Evidence)

If target qualities aren't explicit, these symptoms indicate graph need:

| Symptom | Indicates | Quality Affected |
|---------|-----------|------------------|
| "Has this happened before?" unanswerable | Missing similarity links | Memory, Connection |
| Corrections don't generalize | Can't propagate patterns | Memory |
| You hold connections in your head | Brain is the graph | Connection |
| "What's most important?" has no answer | Missing centrality | Calibration |
| Complex JOINs for simple relationship Qs | SQL fighting graph data | Connection |
| "Show me related items" requires multiple queries | No adjacency | Connection |
| Can't anticipate based on patterns | Missing temporal graph | Awareness |

**3+ symptoms = strong signal for graph**

---

## 7) Context Graph Capability Levels (Reference)

| Level | Name | You Can... | Implementation |
|-------|------|-----------|----------------|
| **0** | Flat | Filter, sort, aggregate | JSONL/SQL native |
| **1** | Joined | Combine related records | SQL JOINs, dict lookups |
| **2** | Traversable | Walk relationships 1-2 hops | Manual code over flat storage |
| **3** | Queryable | Ask relationship questions declaratively | Graph query language or abstraction |
| **4** | Algorithmic | Run PageRank, community detection, link prediction | Graph algorithms (library or DB) |
| **5** | Learning | Algorithms improve from feedback | ML on graph + feedback loops |

---

## 8) Algorithm → Quality Mapping (Reference)

| Algorithm | Enables | Quality |
|-----------|---------|---------|
| Similarity / kNN | "What's like X?" | Memory L4, Connection L4 |
| Link prediction | "What connection am I missing?" | Connection L4 |
| Community detection | "What clusters exist?" | Memory L4 (generalize within cluster) |
| PageRank / centrality | "What matters most?" | Calibration L4 |
| Label propagation | "Spread learned labels" | Memory L4 |
| Temporal patterns | "What happens next?" | Awareness L4 |
| Path finding | "How are A and B related?" | Connection L3-4 |

---

## 9) Quick Diagnostic (If No INTELLIGENCE_EVAL Available)

Answer these:

1. Do you want it to generalize corrections to similar cases? → Memory L4 → Graph
2. Do you want it to surface connections you don't know exist? → Connection L4 → Graph
3. Do you want it to know what's more/less important? → Calibration L4 → Graph
4. Do you want it to anticipate based on accumulated context? → Awareness L4 → Graph
5. Do you want it to suggest improvements across workflows? → Agency L4 → Graph

**Any "yes" where current < L4 = graph likely unlocks**

---

## 10) Relationship to Other Frameworks

```
SKILL_EVOLUTION_EVAL        → Where on execution→intelligence ladder?
SKILL_TRACEABILITY_EVAL     → Can you reconstruct what happened?
SKILL_INTELLIGENCE_EVAL     → Which qualities, what levels, where stuck?
SKILL_CONTEXT_GRAPH_EVAL    → Is context graph the unlock? What context would help? (this doc)
SKILL_INTELLIGENCE_DEMO     → What would L4 look/feel like? (triggered from here)
```

**Flow:**
```
INTELLIGENCE_EVAL (scores + targets)
         ↓
  CONTEXT_GRAPH_EVAL (this doc)
         ↓
    ┌────┴────────────────┐
    ↓                     ↓
NOT NEEDED            UNLOCKS
                          ↓
              ┌───────────┴───────────┐
              ↓                       ↓
    INTELLIGENCE_DEMO          CONTEXT_WISHLIST
    "what L4 looks like"       "what context to add"
```

---

## 11) Unpack for Humans

**After completing the structured evaluation, translate findings into natural language for this specific workflow.**

### The Core Question

Explain in plain language: **"Why does this workflow hit a ceiling, and what would change if we added a context graph?"**

Template:
> Right now, [skill name] treats every [entity] as a stranger. When you [common correction/action], that knowledge [what happens to it].
>
> With a context graph, [what would change]. The skill would [concrete behavior difference].

### Translate the Wishlist

For each high-value context item, explain **what it would feel like** if connected:

Instead of:
```yaml
past_corrections: "claude_suggestion → user_edit pairs" → Memory L4
```

Say:
> **Past corrections:** Every time you fix a suggestion, that's a lesson sitting in a log file. Right now, Claude forgets it immediately. If we connected those corrections, the next time a similar tweet appears, Claude could say "Last time you changed 'Xenobots form memories' to 'xenobot memory - Levin' — should I use that pattern here?"

### Translate the Symptoms

For each ceiling symptom present, describe **the frustration it causes**:

Instead of:
```
| Corrections don't generalize | Can't propagate patterns | Memory |
```

Say:
> **Corrections don't stick:** You've told Claude three times that researcher tweets should end with "- [Name]". Each time feels like teaching a new person. That's because each correction is a line in a log file with no connection to the next tweet.

### Translate the Algorithms

Don't say "kNN" or "label propagation" — describe **what becomes possible**:

| Algorithm | Human Translation |
|-----------|-------------------|
| Similarity / kNN | "Find tweets that feel like this one" |
| Label propagation | "When you correct one, similar ones learn too" |
| Community detection | "Notice that these 20 tweets are all about the same theme" |
| PageRank / centrality | "Know which patterns matter most based on how often they come up" |
| Link prediction | "Suggest connections you haven't made yet" |

### Output Template

After the structured evaluation, add a **Plain English Summary**:

```markdown
## Plain English Summary

**Why you're stuck:**

Right now, [skill name] treats every [main entity] as a stranger.
When you [typical correction or feedback], that knowledge [what happens — lost? logged but unused?].
[Describe the repeated frustration in concrete terms.]

**What a context graph would change:**

[Describe the key behavior shift — what would the skill notice/remember/connect?]
[Give 1-2 concrete "it would say..." examples.]

**What context would help most:**

1. **[High-value context #1]** — [What it is in plain language] → [What it enables]
2. **[High-value context #2]** — [What it is] → [What it enables]
3. **[High-value context #3]** — [What it is] → [What it enables]

**The felt difference:**

- Without graph: [The current frustration — repetitive, forgetful, disconnected]
- With graph: [The target experience — learning, connecting, anticipating]
```

### Tone Guide

- Use "you" and "your" — speak to the person using the skill
- Describe feelings: "frustrating", "feels like teaching a new person every time"
- Give concrete examples from that specific workflow
- Avoid jargon: no "kNN", "L4", "label propagation" in this section
- The goal: someone unfamiliar with graph concepts should understand the value

---

*Origin: 2026-01-16 conversation re: context graphs as AI infrastructure*
*Reference: [Foundation Capital - Context Graphs](https://foundationcapital.com/context-graphs-ais-trillion-dollar-opportunity/)*
